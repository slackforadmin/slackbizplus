<div id="slack-guide-wizard" style="font-family: 'Pretendard', sans-serif; max-width: 800px; margin: 40px 0; border: 1px solid #E1BEE7; border-radius: 16px; background: #ffffff; box-shadow: 0 10px 25px rgba(142, 68, 173, 0.1); overflow: hidden;">
    <div style="padding: 24px; background: linear-gradient(135deg, #F3E5F5 0%, #EDE7F6 100%); border-bottom: 1px solid #E1BEE7;">
        <div style="display: flex; align-items: center; gap: 12px;">
            <span style="font-size: 24px;">⚡</span>
            <h3 style="margin: 0; font-size: 20px; color: #4A148C; font-weight: 800;">초대 문제 해결 시뮬레이터</h3>
        </div>
        <div style="width: 100%; height: 6px; background: #D1C4E9; border-radius: 10px; margin-top: 20px; overflow: hidden;">
            <div id="wiz-progress" style="width: 20%; height: 100%; background: #8E44AD; transition: width 0.4s cubic-bezier(0.4, 0, 0.2, 1);"></div>
        </div>
    </div>
    <div style="padding: 32px;">
        <div id="wiz-question-container">
            <h4 id="wiz-question" style="margin: 0 0 24px 0; font-size: 19px; color: #333; line-height: 1.5;">어떤 단계에서 문제가 발생했나요?</h4>
            <div id="wiz-options" style="display: grid; gap: 12px;">
                </div>
        </div>
        <div id="wiz-result" style="display: none; animation: fadeIn 0.5s ease forwards;">
            <div style="background: #F3E5F5; padding: 24px; border-radius: 12px; border-left: 5px solid #8E44AD;">
                <strong style="display: block; font-size: 18px; color: #8E44AD; margin-bottom: 12px;">💡 진단 결과 및 해결책</strong>
                <p id="wiz-result-text" style="margin: 0; font-size: 16px; color: #444; line-height: 1.7;"></p>
            </div>
            <button onclick="restartWiz()" style="margin-top: 24px; background: none; border: 1px solid #8E44AD; color: #8E44AD; padding: 10px 20px; border-radius: 8px; cursor: pointer; font-weight: 600; transition: 0.2s;">
                처음부터 다시 진단하기
            </button>
        </div>
    </div>
</div>

<style>
    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
    }
    .wiz-btn {
        width: 100%; text-align: left; padding: 18px 24px; border: 1px solid #E1BEE7; border-radius: 12px; 
        background: #fff; color: #444; font-size: 16px; font-weight: 500; cursor: pointer; 
        transition: all 0.2s ease; box-shadow: 0 2px 4px rgba(0,0,0,0.02);
    }
    .wiz-btn:hover {
        border-color: #8E44AD; background: #F8F4FF; transform: translateX(5px); color: #8E44AD;
    }
</style>

<script>
(function() {
    const wizData = {
        start: {
            q: "현재 겪고 계신 초대 관련 증상을 선택해 주세요.",
            p: 25,
            opts: [
                { t: "초대 이메일이 아예 안 와요", n: "no_mail" },
                { t: "권한 설정(게스트/멤버)이 꼬였어요", n: "role_error" },
                { t: "초대 링크가 만료되었다고 떠요", n: "expired" }
            ]
        },
        no_mail: {
            q: "관리자 설정 > 초대 관리 목록에 해당 이메일이 있나요?",
            p: 50,
            opts: [
                { t: "네, '대기 중'으로 떠있어요", n: "in_list" },
                { t: "아니요, 목록에도 없어요", n: "not_in_list" }
            ]
        },
        role_error: {
            q: "초대하려는 분이 외부 업체 사람인가요?",
            p: 50,
            opts: [
                { t: "네, 특정 채널만 공유할 외부인입니다", n: "guest_solve" },
                { t: "아니요, 우리 회사 직원입니다", n: "member_solve" }
            ]
        },
        // 최종 답변 노드
        in_list: { q: "결과", p: 100, a: "사용자의 이메일 서비스(Outlook, Gmail 등)에서 스팸으로 분류했을 가능성이 90%입니다. 스팸함을 확인하게 하시고, 해결되지 않으면 IT 팀에 'bounces.slack.com' 도메인을 안전한 발신자로 등록해달라고 요청하세요." },
        not_in_list: { q: "결과", p: 100, a: "전송 버튼이 제대로 눌리지 않았거나 일시적인 네트워크 오류일 수 있습니다. 관리자 화면에서 해당 사용자를 다시 한번 초대해 주세요." },
        expired: { q: "결과", p: 100, a: "슬랙 보안 정책상 초대 링크는 30일이 지나면 자동 만료됩니다. [초대 관리]에서 기존 초대를 취소한 후 '다시 초대'를 눌러 새 링크를 발송하세요." },
        guest_solve: { q: "결과", p: 100, a: "비즈니스 플랜은 유료 멤버 1명당 5명의 게스트를 초대할 수 있습니다. 라이선스 한도를 초과하지 않았는지 확인해 보시고, 설정에서 '멀티 채널 게스트' 옵션을 선택했는지 체크하세요." },
        member_solve: { q: "결과", p: 100, a: "사내 직원이라면 [워크스페이스 설정]에서 허용된 도메인(@회사이름.com)으로 가입을 시도하는지 확인하세요. SSO 로그인이 활성화되어 있다면 SSO 계정 생성이 우선입니다." }
    };

    function renderWiz(id) {
        const step = wizData[id];
        const qContainer = document.getElementById('wiz-question-container');
        const rContainer = document.getElementById('wiz-result');
        const qText = document.getElementById('wiz-question');
        const btnGroup = document.getElementById('wiz-options');
        const progress = document.getElementById('wiz-progress');
        const rText = document.getElementById('wiz-result-text');

        // 프로그레스 바 업데이트
        progress.style.width = step.p + "%";

        if (step.a) { // 결과 화면
            qContainer.style.display = 'none';
            rContainer.style.display = 'block';
            rText.innerText = step.a;
        } else { // 질문 화면
            rContainer.style.display = 'none';
            qContainer.style.display = 'block';
            qText.innerText = step.q;
            btnGroup.innerHTML = '';
            
            step.opts.forEach(opt => {
                const btn = document.createElement('button');
                btn.className = 'wiz-btn';
                btn.innerText = opt.t;
                btn.onclick = () => renderWiz(opt.n);
                btnGroup.appendChild(btn);
            });
        }
    }

    window.restartWiz = () => renderWiz('start');
    
    // 초기 로드 시점 조절
    if (document.readyState === 'complete') restartWiz();
    else window.addEventListener('load', restartWiz);
})();
</script>
