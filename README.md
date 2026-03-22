<div id="slack-step-wizard" style="font-family: 'Pretendard', -apple-system, sans-serif; max-width: 800px; margin: 40px 0; border: 1px solid #E1BEE7; border-radius: 16px; background: #fff; overflow: hidden; box-shadow: 0 4px 20px rgba(142,68,173,0.1);">
    <div style="padding: 20px; background: #F3E5F5; border-bottom: 1px solid #E1BEE7;">
        <h3 style="margin:0; color:#8E44AD; font-size:18px; display: flex; align-items: center; gap: 8px;">
            <span>🔍</span> 초대 문제 해결 가이드
        </h3>
        <div style="width: 100%; height: 4px; background: #E1BEE7; border-radius: 2px; margin-top: 15px;">
            <div id="wiz-bar" style="width: 20%; height: 100%; background: #8E44AD; transition: width 0.3s ease;"></div>
        </div>
    </div>
    <div style="padding: 28px; min-height: 250px;">
        <div id="step-1" class="wiz-content">
            <p style="font-size: 19px; font-weight: bold; color: #333; margin-bottom: 24px;">Q1. 어떤 단계에서 문제가 발생했나요?</p>
            <div style="display: flex; flex-direction: column; gap: 12px;">
                <button class="wiz-btn" onclick="nextStep('1', '2', 'email', '40')">📧 초대 메일 발송 관련</button>
                <button class="wiz-btn" onclick="nextStep('1', '2', 'permission', '40')">🔑 권한 및 설정 관련</button>
            </div>
        </div>
        <div id="step-2-email" class="wiz-content" style="display:none;">
            <p style="font-size: 19px; font-weight: bold; color: #333; margin-bottom: 24px;">Q2. 관리자 '초대 관리' 목록에 이름이 있나요?</p>
            <div style="display: flex; flex-direction: column; gap: 12px;">
                <button class="wiz-btn" onclick="nextStep('2-email', '3', 'spam', '70')">네, '대기 중'으로 표시됩니다</button>
                <button class="wiz-btn" onclick="nextStep('2-email', '3', 'domain', '70')">아니요, 목록에 아예 없습니다</button>
            </div>
        </div>
        <div id="step-2-permission" class="wiz-content" style="display:none;">
            <p style="font-size: 19px; font-weight: bold; color: #333; margin-bottom: 24px;">Q2. 어떤 사용자에게 권한을 주려 하시나요?</p>
            <div style="display: flex; flex-direction: column; gap: 12px;">
                <button class="wiz-btn" onclick="nextStep('2-permission', '3', 'guest', '70')">외부 협업자(게스트)</button>
                <button class="wiz-btn" onclick="nextStep('2-permission', '3', 'sso', '70')">사내 정직원(멤버)</button>
            </div>
        </div>
        <div id="step-3" class="wiz-content" style="display:none;">
            <div id="solution-box" style="background: #F8F4FF; padding: 24px; border-radius: 12px; border: 1px solid #CE93D8;">
                <strong style="display: block; font-size: 18px; color: #8E44AD; margin-bottom: 15px;">✅ 맞춤 해결책</strong>
                <p id="solution-text" style="margin: 0; line-height: 1.7; color: #444; font-size: 16px;"></p>
            </div>
            <button onclick="resetWiz()" style="margin-top: 24px; background: none; border: 1px solid #8E44AD; color: #8E44AD; padding: 10px 18px; border-radius: 8px; cursor: pointer; font-weight: 600;">처음부터 다시</button>
        </div>
    </div>
</div>
<style>
    .wiz-content { animation: slideIn 0.3s ease-out; }
    @keyframes slideIn { from { opacity: 0; transform: translateX(10px); } to { opacity: 1; transform: translateX(0); } }
    .wiz-btn {
        text-align: left; padding: 16px 20px; border: 1px solid #E1BEE7; border-radius: 12px; 
        background: #fff; cursor: pointer; font-size: 16px; transition: all 0.2s; color: #333;
    }
    .wiz-btn:hover { background: #F3E5F5; border-color: #8E44AD; color: #8E44AD; transform: scale(1.01); }
</style>
<script>
// 전역 변수로 함수 선언 (GitHub Pages 호환성 강화)
window.nextStep = function(currentId, nextId, type, progress) {
    const solutions = {
        'spam': "상대방의 이메일 보안 설정(Outlook 필터 등) 문제일 가능성이 큽니다. 스팸함을 확인하게 하시고, 해결되지 않으면 IT 팀에 'bounces.slack.com' 화이트리스트 등록을 요청하세요.",
        'domain': "초대 시 도메인 오타가 있었거나 발송 오류일 수 있습니다. [관리자 설정 > 인증]에서 허용된 도메인인지 확인 후 다시 초대를 보내주세요.",
        'guest': "비즈니스 플랜은 멤버 1명당 5명의 게스트 초대가 가능합니다. 잔여 시트가 부족하지 않은지 확인하시고, '멀티 채널 게스트' 설정을 체크하세요.",
        'sso': "사내 직원은 일반 초대가 아니라 SSO(Single Sign-On) 연동을 통해 가입해야 할 수 있습니다. 관리자 화면의 '인증' 탭에서 SSO 강제 적용 여부를 확인하세요."
    };
    // 현재 단계 숨기기
    const currentEl = document.getElementById('step-' + currentId);
    if (currentEl) currentEl.style.display = 'none';
    // 다음 단계 ID 결정
    let targetId = 'step-' + nextId;
    if (nextId === '2') {
        targetId = 'step-2-' + type;
    }
    // 다음 단계 보여주기
    const nextEl = document.getElementById(targetId);
    if (nextEl) {
        nextEl.style.display = 'block';
        // 마지막 단계일 경우 텍스트 치환
        if (nextId === '3') {
            document.getElementById('solution-text').innerText = solutions[type];
            document.getElementById('wiz-bar').style.width = "100%";
        } else {
            document.getElementById('wiz-bar').style.width = progress + "%";
        }
    }
};
window.resetWiz = function() {
    document.querySelectorAll('.wiz-content').forEach(el => el.style.display = 'none');
    document.getElementById('step-1').style.display = 'block';
    document.getElementById('wiz-bar').style.width = "20%";
};
</script>
