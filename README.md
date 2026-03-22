<div id="troubleshooter-section" style="font-family: 'Pretendard', sans-serif; max-width: 800px; margin: 40px 0; border: 1px solid #E1BEE7; border-radius: 16px; background-color: #ffffff; box-shadow: 0 4px 12px rgba(142, 68, 173, 0.08); overflow: hidden;">
    
    <div style="padding: 24px 28px; background-color: #FCF9FE; border-bottom: 1px solid #E1BEE7;">
        <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 16px;">
            <span style="font-size: 24px;">🔍</span>
            <h3 style="margin: 0; font-size: 20px; font-weight: 700; color: #333;">초대 관련 문제 해결 위저드</h3>
        </div>
        <div style="width: 100%; bg-color: #E0E0E0; height: 6px; rounded-full: 3px; overflow: hidden; background: #EEE; border-radius: 3px;">
            <div id="ts-progress" style="background-color: #8E44AD; h-full: 100%; transition: width 0.4s ease; width: 25%; height: 100%;"></div>
        </div>
    </div>

    <div id="ts-content-area" style="padding: 28px; transition: opacity 0.3s ease;">
        <h4 id="ts-question" style="margin-top: 0; margin-bottom: 20px; font-size: 18px; color: #333; line-height: 1.4;">
            슬랙 비즈니스 플랜 사용 중, 사람 초대와 관련하여 어떤 문제가 있나요?
        </h4>
        
        <div id="ts-options" style="display: flex; flex-direction: column; gap: 12px;">
            </div>
        
        <div id="ts-result" style="display: none; background-color: #F3E5F5; padding: 20px; border-radius: 12px; border: 1px solid #CE93D8; margin-top: 20px;">
            <strong style="display: block; color: #8E44AD; margin-bottom: 8px; font-size: 16px;">✅ 해결책:</strong>
            <p id="ts-result-text" style="margin: 0; font-size: 15px; color: #555; line-height: 1.6;"></p>
        </div>

    </div>

    <div style="padding: 0 28px 24px; text-align: right;">
        <button onclick="resetTSWizard()" style="background: none; border: none; color: #8E44AD; cursor: pointer; text-decoration: underline; font-size: 14px; opacity: 0.7;">
            🔄 처음부터 다시
        </button>
    </div>

</div>

<script>
/**
 * 트러블슈팅 플로우 데이터
 */
const tsFlow = {
    start: {
        q: "슬랙 비즈니스 플랜 사용 중, 사람 초대와 관련하여 어떤 문제가 있나요?",
        options: [
            { text: "초대 메일 자체가 발송되지 않음", next: "email_sent_issue" },
            { text: "멤버 권한(게스트/풀멤버) 설정에 문제", next: "role_config_issue" },
            { text: "특정 도메인의 사용자가 초대를 못 받음", next: "domain_issue" },
            { text: "초대를 승인할 수 없다는 에러", next: "error_msg" }
        ],
        progress: 25
    },
    // 대분류 1: 메일 발송 안됨
    email_sent_issue: {
        q: "관리자 화면의 '초대 관리' 메뉴에서 해당 멤버의 상태가 '초대 대기 중'으로 보이나요?",
        options: [
            { text: "예, 대기 중입니다.", next: "spam_check" },
            { text: "아니요, 목록에 없습니다.", next: "resend_invite" }
        ],
        progress: 50
    },
    // 대분류 2: 권한 설정
    role_config_issue: {
        q: "혹시 '멀티 채널 게스트'로 초대하려고 하시나요?",
        options: [
            { text: "예, 그런데 설정이 안 됩니다.", next: "billing_check" },
            { text: "아니요, 일반 멤버로 초대 중입니다.", next: "check_standard_flow" }
        ],
        progress: 50
    },
    // 대분류 3: 도메인
    domain_issue: {
        q: "모든 사용자가 같은 도메인(@company.com)을 사용하나요?",
        options: [
            { text: "예, 그렇습니다.", next: "sso_check" },
            { text: "아니요, 외부 게스트입니다.", next: "check_whitelist" }
        ],
        progress: 50
    },
    // 대분류 4: 에러 메시지
    error_msg: {
        q: "사용자가 링크를 클릭했을 때 '만료된 링크'라고 나오나요?",
        options: [
            { text: "예, 만료되었다고 합니다.", next: "resend_with_new_link" },
            { text: "아니요, 다른 메시지입니다.", next: "contact_slack_support" }
        ],
        progress: 50
    },

    // ----------------------------------------
    // ✅ 결과 해결책 단계 (Result Nodes)
    // ----------------------------------------
    spam_check: { q: "결과: 이메일 서버 문제", result: "해당 사용자의 이메일 서버에서 Slack 메일을 스팸으로 처리했을 가능성이 높습니다. 사용자의 스팸함을 확인하게 하거나, IT 팀에 'bounces.slack.com' 도메인의 화이트리스트 등록을 요청하세요.", progress: 100 },
    resend_invite: { q: "결과: 초대 재전송 필요", result: "초대 목록에 없다면 정상적으로 발송되지 않은 것입니다. 관리자 화면에서 '초대하기' 버튼을 통해 다시 이메일을 입력하여 전송해 주세요.", progress: 100 },
    billing_check: { q: "결과: 결제 확인 필요", result: "비즈니스 플랜에서 '게스트'는 유료 시트(멤버 5명당 멀티채널 게스트 1명)가 필요합니다. 결제 수단이 정상인지, 남은 게스트 시트가 있는지 확인하세요.", progress: 100 },
    check_standard_flow: { q: "결과: 워크스페이스 설정 확인", result: "워크스페이스 설정 -> '멤버 초대' 옵션에서 '모든 멤버가 초대할 수 있음'이 켜져 있는지 확인하세요. 관리자만 초대할 수 있게 설정된 경우, 권한을 변경해야 합니다.", progress: 100 },
    sso_check: { q: "결과: SSO 설정 확인", result: "비즈니스 플랜에서 SSO(단일 로그인)를 사용하는 경우, 사용자가 SSO 계정을 먼저 생성해야 Slack에 참여할 수 있습니다. SSO 설정을 확인하세요.", progress: 100 },
    check_whitelist: { q: "결과: 도메인 화이트리스트 확인", result: "[관리자 설정 > 인증]에서 허용된 이메일 도메인을 확인하세요. 외부 게스트의 도메인이 등록되어 있지 않다면 초대가 차단될 수 있습니다.", progress: 100 },
    resend_with_new_link: { q: "결과: 초대 재전송", result: "초대 링크의 유효기간(기본 30일)이 만료되었습니다. 관리자 화면의 '초대 관리' 메뉴에서 해당 멤버에게 '초대 재전송'을 클릭하여 새 링크를 보내주세요.", progress: 100 },
    contact_slack_support: { q: "결과: Slack 고객지원 문의", result: "다양한 이유(예: 이전에 비활성화된 계정 등)로 인한 특수한 에러일 수 있습니다. 화면의 에러 메시지를 캡처하여 Slack 고객지원에 문의하시기 바랍니다.", progress: 100 }
};

const troubleshooterSection = document.getElementById('troubleshooter-section');
const tsContentArea = document.getElementById('ts-content-area');
const tsQuestionEl = document.getElementById('ts-question');
const tsOptionsEl = document.getElementById('ts-options');
const tsProgressEl = document.getElementById('ts-progress');
const tsResultEl = document.getElementById('ts-result');
const tsResultTextEl = document.getElementById('ts-result-text');

/**
 * 특정 단계를 화면에 렌더링
 */
function renderTSStep(stepId) {
    const step = tsFlow[stepId];
    if (!step) return;

    // 화면 페이드 아웃 효과 (부드럽게)
    tsContentArea.style.opacity = 0;

    setTimeout(() => {
        // 결과창 숨기기
        tsResultEl.style.display = 'none';
        tsOptionsEl.style.display = 'flex';

        // 질문 업데이트
        tsQuestionEl.innerText = step.q;
        
        // 프로그레스 바 업데이트
        tsProgressEl.style.width = step.progress + "%";
        
        // 옵션 초기화
        tsOptionsEl.innerHTML = '';

        if (step.result) {
            // 해결책 결과 페이지인 경우
            tsOptionsEl.style.display = 'none'; // 버튼 숨김
            tsResultEl.style.display = 'block'; // 결과창 표시
            tsResultTextEl.innerText = step.result; // 결과 텍스트 입력
            tsQuestionEl.innerText = "진단 결과";
        } else {
            // 다음 질문이 있는 경우 (버튼 생성)
            step.options.forEach(opt => {
                const btn = document.createElement('button');
                btn.style.cssText = "display: block; width: 100%; text-align: left; padding: 16px 20px; border: 1px solid #E1BEE7; border-radius: 10px; background-color: #ffffff; color: #333; font-size: 15px; font-weight: 500; cursor: pointer; transition: all 0.2s; box-sizing: border-box;";
                btn.innerText = opt.text;
                
                // 마우스 오버 시 스타일 변경
                btn.onmouseover = () => { btn.style.borderColor = "#8E44AD"; btn.style.backgroundColor = "#F3E5F5"; };
                btn.onmouseout = () => { btn.style.borderColor = "#E1BEE7"; btn.style.backgroundColor = "#ffffff"; };
                
                // 클릭 시 다음 단계로 이동
                btn.onclick = () => renderTSStep(opt.next);
                tsOptionsEl.appendChild(btn);
            });
        }

        // 화면 페이드 인 효과
        tsContentArea.style.opacity = 1;
    }, 300);
}

/**
 * 처음부터 다시 시작
 */
function resetTSWizard() {
    renderTSStep('start');
}

// 폰트가 pretendard라면, Pretendard 링크 추가 (없다면 주석 처리해도 무방)
const pretenderdLink = document.createElement('link');
pretenderdLink.href = 'https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css';
pretenderdLink.rel = 'stylesheet';
document.head.appendChild(pretenderdLink);

// 페이지 로드 시 위저드 시작
document.addEventListener('DOMContentLoaded', resetTSWizard);

// DOMContentLoaded가 이미 지난 경우를 대비해 한번 더 호출
if (document.readyState === 'complete' || document.readyState === 'interactive') {
    resetTSWizard();
}
</script>
