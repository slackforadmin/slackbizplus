<div id="slack-wizard-fixed" style="font-family: 'Pretendard', sans-serif; max-width: 800px; margin: 40px 0; border: 1px solid #E1BEE7; border-radius: 16px; background: #fff; overflow: hidden; box-shadow: 0 4px 20px rgba(0,0,0,0.08);">
    <div style="padding: 20px; background: #F3E5F5; border-bottom: 1px solid #E1BEE7;">
        <h3 style="margin:0; color:#8E44AD; font-size:18px;">🔍 초대 문제 단계별 해결</h3>
    </div>
    <div style="padding: 24px;">
        <div id="step-start" class="wiz-step">
            <p style="font-size: 18px; font-weight: bold; margin-bottom: 20px;">어떤 단계에서 문제가 발생했나요?</p>
            <div style="display: flex; flex-direction: column; gap: 10px;">
                <button onclick="goStep('email')" style="text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">📧 초대 메일이 전송되지 않음</button>
                <button onclick="goStep('role')" style="text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">👥 게스트/멤버 권한 설정 오류</button>
                <button onclick="goStep('result-link')" style="text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">🔗 초대 링크 만료/에러 메시지</button>
            </div>
        </div>
        <div id="step-email" class="wiz-step" style="display:none;">
            <p style="font-size: 18px; font-weight: bold; margin-bottom: 20px;">관리자 메뉴의 '초대 관리'에 대상자가 보이나요?</p>
            <div style="display: flex; flex-direction: column; gap: 10px;">
                <button onclick="goStep('result-spam')" style="text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">네, '대기 중'으로 보입니다</button>
                <button onclick="goStep('result-resend')" style="text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">아니요, 목록에 없습니다</button>
            </div>
        </div>
        <div id="step-role" class="wiz-step" style="display:none;">
            <p style="font-size: 18px; font-weight: bold; margin-bottom: 20px;">초대하려는 분이 외부 업체 사람인가요?</p>
            <div style="display: flex; flex-direction: column; gap: 10px;">
                <button onclick="goStep('result-guest')" style="text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">네, 외부 협업자(게스트)입니다</button>
                <button onclick="goStep('result-member')" style="text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">아니요, 우리 회사 직원입니다</button>
            </div>
        </div>
        <div id="result-spam" class="wiz-step" style="display:none; background:#F9F9F9; padding:20px; border-radius:10px; border-left:4px solid #8E44AD;">
            <strong>✅ 해결책: 스팸함 및 필터 확인</strong><br><br>상대방 이메일 서버에서 Slack 메일을 차단했을 수 있습니다. IT 팀에 <code>bounces.slack.com</code> 허용을 요청하세요.
            <br><button onclick="goStep('start')" style="margin-top:15px; cursor:pointer;">처음으로</button>
        </div>
        <div id="result-resend" class="wiz-step" style="display:none; background:#F9F9F9; padding:20px; border-radius:10px; border-left:4px solid #8E44AD;">
            <strong>✅ 해결책: 초대 재전송</strong><br><br>일시적인 오류로 누락되었을 수 있습니다. 관리자 화면에서 해당 사용자를 다시 초대해 주세요.
            <br><button onclick="goStep('start')" style="margin-top:15px; cursor:pointer;">처음으로</button>
        </div>
        <div id="result-guest" class="wiz-step" style="display:none; background:#F9F9F9; padding:20px; border-radius:10px; border-left:4px solid #8E44AD;">
            <strong>✅ 해결책: 게스트 라이선스 확인</strong><br><br>비즈니스 플랜은 유료 멤버 1명당 5명의 게스트 초대가 가능합니다. 잔여 라이선스를 확인하세요.
            <br><button onclick="goStep('start')" style="margin-top:15px; cursor:pointer;">처음으로</button>
        </div>
        <div id="result-member" class="wiz-step" style="display:none; background:#F9F9F9; padding:20px; border-radius:10px; border-left:4px solid #8E44AD;">
            <strong>✅ 해결책: 도메인 설정 확인</strong><br><br>[설정 및 권한]에서 허용된 이메일 도메인(@회사명.com)으로 가입 중인지 확인하세요.
            <br><button onclick="goStep('start')" style="margin-top:15px; cursor:pointer;">처음으로</button>
        </div>
        <div id="result-link" class="wiz-step" style="display:none; background:#F9F9F9; padding:20px; border-radius:10px; border-left:4px solid #8E44AD;">
            <strong>✅ 해결책: 링크 재생성</strong><br><br>초대 링크는 30일 후 만료됩니다. 기존 초대를 취소하고 새로 초대를 보내주세요.
            <br><button onclick="goStep('start')" style="margin-top:15px; cursor:pointer;">처음으로</button>
        </div>
    </div>
</div>
<script>
function goStep(stepId) {
    // 모든 단계 숨기기
    const steps = document.querySelectorAll('.wiz-step');
    steps.forEach(s => s.style.display = 'none');
    // 선택한 단계만 보이기
    const target = document.getElementById('step-' + stepId) || document.getElementById(stepId);
    if (target) {
        target.style.display = 'block';
        // 애니메이션 효과
        target.style.animation = "fadeIn 0.3s ease-in-out";
    }
}
// 애니메이션 정의
const style = document.createElement('style');
style.innerHTML = `@keyframes fadeIn { from { opacity: 0; transform: translateY(5px); } to { opacity: 1; transform: translateY(0); } }`;
document.head.appendChild(style);
</script>
