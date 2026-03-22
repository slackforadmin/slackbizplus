<div id="slack-wizard-final" style="font-family: 'Pretendard', sans-serif; max-width: 800px; margin: 40px 0; border: 1px solid #E1BEE7; border-radius: 16px; background: #fff; overflow: hidden; box-shadow: 0 4px 20px rgba(142,68,173,0.1);">
    <div style="padding: 20px; background: #F3E5F5; border-bottom: 1px solid #E1BEE7;">
        <h3 style="margin:0; color:#8E44AD; font-size:18px;">🔍 초대 문제 단계별 가이드</h3>
        <div style="width: 100%; height: 4px; background: #E1BEE7; border-radius: 2px; margin-top: 15px;">
            <div id="bar-gauge" style="width: 20%; height: 100%; background: #8E44AD; transition: width 0.3s ease;"></div>
        </div>
    </div>
    <div style="padding: 28px; min-height: 250px;">
        <div id="view-1" class="step-view">
            <p style="font-size: 19px; font-weight: bold; color: #333; margin-bottom: 24px;">Q1. 어떤 단계에서 문제가 발생했나요?</p>
            <div style="display: flex; flex-direction: column; gap: 12px;">
                <button class="wiz-btn" onclick="window.moveStep('1', '2-email', 50)">📧 초대 메일 발송 관련</button>
                <button class="wiz-btn" onclick="window.moveStep('1', '2-perm', 50)">🔑 권한 및 설정 관련</button>
            </div>
        </div>
        <div id="view-2-email" class="step-view" style="display:none;">
            <p style="font-size: 19px; font-weight: bold; color: #333; margin-bottom: 24px;">Q2. '초대 관리' 목록에 대상자가 있나요?</p>
            <div style="display: flex; flex-direction: column; gap: 12px;">
                <button class="wiz-btn" onclick="window.showFinal('spam')">네, '대기 중'으로 표시됩니다</button>
                <button class="wiz-btn" onclick="window.showFinal('domain')">아니요, 목록에 아예 없습니다</button>
            </div>
        </div>
        <div id="view-2-perm" class="step-view" style="display:none;">
            <p style="font-size: 19px; font-weight: bold; color: #333; margin-bottom: 24px;">Q2. 어떤 사용자에게 권한을 주려 하시나요?</p>
            <div style="display: flex; flex-direction: column; gap: 12px;">
                <button class="wiz-btn" onclick="window.showFinal('guest')">외부 협업자(게스트)</button>
                <button class="wiz-btn" onclick="window.showFinal('sso')">사내 정직원(멤버)</button>
            </div>
        </div>
        <div id="view-result" class="step-view" style="display:none;">
            <div style="background: #F8F4FF; padding: 24px; border-radius: 12px; border: 1px solid #CE93D8;">
                <strong style="display: block; font-size: 18px; color: #8E44AD; margin-bottom: 15px;">✅ 맞춤 해결책</strong>
                <p id="final-text" style="margin: 0; line-height: 1.7; color: #444; font-size: 16px;"></p>
            </div>
            <button onclick="window.location.reload()" style="margin-top: 24px; background: none; border: 1px solid #8E44AD; color: #8E44AD; padding: 10px 18px; border-radius: 8px; cursor: pointer; font-weight: 600;">처음부터 다시</button>
        </div>
    </div>
</div>
<style>
    .step-view { animation: fadeIn 0.4s ease; }
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    .wiz-btn {
        text-align: left; padding: 16px 20px; border: 1px solid #E1BEE7; border-radius: 12px; 
        background: #fff; cursor: pointer; font-size: 16px; transition: all 0.2s; color: #333; width: 100%;
    }
    .wiz-btn:hover { background: #F3E5F5; border-color: #8E44AD; color: #8E44AD; }
</style>
<script>
// 1. 다음 질문으로 넘기기 함수
window.moveStep = function(currentId, nextId, progress) {
    // 현재 화면 숨기기
    var current = document.getElementById('view-' + currentId);
    if (current) current.style.display = 'none';
    // 다음 화면 보여주기
    var next = document.getElementById('view-' + nextId);
    if (next) next.style.display = 'block';
    // 게이지 업데이트
    document.getElementById('bar-gauge').style.width = progress + '%';
};
// 2. 최종 결과 보여주기 함수
window.showFinal = function(type) {
    var solutions = {
        'spam': "상대방의 이메일 스팸함 혹은 Outlook 보안 필터를 확인하세요. 'bounces.slack.com' 허용이 필요합니다.",
        'domain': "초대 시 도메인 오타를 확인하시고, [관리자 설정 > 인증]에 등록된 도메인인지 체크하세요.",
        'guest': "비즈니스 플랜은 멤버 1명당 게스트 5명이 가능합니다. 라이선스 잔여 수량을 확인하세요.",
        'sso': "사내 직원은 SSO 가입이 우선일 수 있습니다. 관리자 화면의 '인증' 탭 설정을 확인하세요."
    };
    // 모든 질문 화면 숨기기
    var views = document.getElementsByClassName('step-view');
    for (var i = 0; i < views.length; i++) {
        views[i].style.display = 'none';
    }
    // 결과 화면 보여주기
    document.getElementById('view-result').style.display = 'block';
    document.getElementById('final-text').innerText = solutions[type];
    document.getElementById('bar-gauge').style.width = '100%';
};
</script>
