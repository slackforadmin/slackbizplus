<div id="slack-wizard-container" style="max-width: 800px; margin: 40px 0; border: 1px solid #E1BEE7; border-radius: 12px; background: #fff; overflow: hidden; box-shadow: 0 4px 15px rgba(0,0,0,0.05); font-family: 'Pretendard', -apple-system, sans-serif;">
  <div style="background-color: #F3E5F5; padding: 20px 24px; border-bottom: 1px solid #E1BEE7;">
    <h3 style="margin: 0; color: #8E44AD; font-size: 20px;">🔍 초대 문제 해결 가이드</h3>
  </div>
  <div id="wizard-inner-body" style="padding: 24px;">
    <p id="ts-q-text" style="font-size: 18px; font-weight: bold; color: #333; margin-bottom: 20px;">잠시만 기다려주세요...</p>
    <div id="ts-btn-group" style="display: flex; flex-direction: column; gap: 10px;"></div>
    <div id="ts-a-area" style="display: none; background: #F9F9F9; padding: 20px; border-radius: 8px; border-left: 4px solid #8E44AD;">
      <p id="ts-a-text" style="margin: 0; line-height: 1.6; color: #444;"></p>
      <button onclick="window.initSlackWizard()" style="margin-top: 20px; background: #8E44AD; color: #fff; border: none; padding: 8px 16px; border-radius: 6px; cursor: pointer;">처음으로</button>
    </div>
  </div>
</div>

<script>
(function() {
  const flowData = {
    start: {
      q: "어떤 단계에서 문제가 발생했나요?",
      opts: [
        { t: "초대 메일이 전송되지 않음", n: "email" },
        { t: "게스트/멤버 권한 설정 오류", n: "role" },
        { t: "초대 링크 만료/에러", n: "link" }
      ]
    },
    email: {
      q: "관리자 메뉴의 '초대 관리'에 대상자가 보이나요?",
      opts: [
        { t: "네, 대기 중으로 보입니다", n: "check_spam" },
        { t: "아니요, 목록에 없습니다", n: "resend" }
      ]
    },
    role: {
      q: "초대하려는 분이 외부 협업자인가요?",
      opts: [
        { t: "네, 외부 게스트입니다", n: "guest_tip" },
        { t: "아니요, 사내 직원입니다", n: "member_tip" }
      ]
    },
    link: { q: "해결책: 링크 재생성", a: "기존 초대 링크는 보안상 30일이 지나면 만료됩니다. [초대 관리]에서 해당 사용자를 취소 후 다시 초대하여 새 링크를 발송해 주세요." },
    check_spam: { q: "해결책: 스팸함 및 필터 확인", a: "대상자의 이메일 서버에서 Slack 메일을 차단했을 수 있습니다. IT 팀에 'bounces.slack.com' 허용을 요청하세요." },
    resend: { q: "해결책: 초대 재전송", a: "네트워크 오류로 발송이 누락되었을 수 있습니다. 관리자 화면에서 다시 한번 초대를 진행해 주세요." },
    guest_tip: { q: "해결책: 게스트 라이선스 확인", a: "비즈니스 플랜은 유료 멤버 1명당 5명의 멀티 채널 게스트를 초대할 수 있습니다. 남은 라이선스 수량을 확인해 보세요." },
    member_tip: { q: "해결책: 도메인 설정 확인", a: "사내 직원이라면 [설정 및 권한]에서 허용된 이메일 도메인(@company.com)으로 가입을 시도 중인지 확인하세요." }
  };

  window.initSlackWizard = function() {
    renderStep('start');
  };

  function renderStep(id) {
    const step = flowData[id];
    const qText = document.getElementById('ts-q-text');
    const btnGroup = document.getElementById('ts-btn-group');
    const aArea = document.getElementById('ts-a-area');
    const aText = document.getElementById('ts-a-text');

    if (step.a) {
      qText.style.display = 'none';
      btnGroup.style.display = 'none';
      aArea.style.display = 'block';
      aText.innerHTML = "<strong>" + step.q + "</strong><br><br>" + step.a;
    } else {
      aArea.style.display = 'none';
      qText.style.display = 'block';
      btnGroup.style.display = 'flex';
      qText.innerText = step.q;
      btnGroup.innerHTML = '';
      step.opts.forEach(opt => {
        const btn = document.createElement('button');
        btn.innerText = opt.t;
        btn.style.cssText = "text-align:left; padding:12px; border:1px solid #ddd; border-radius:8px; background:#fff; cursor:pointer; font-size:15px;";
        btn.onclick = function() { renderStep(opt.n); };
        btnGroup.appendChild(btn);
      });
    }
  }

  // 페이지 로드 완료 후 실행
  if (document.readyState === 'complete') {
    window.initSlackWizard();
  } else {
    window.addEventListener('load', window.initSlackWizard);
  }
})();
</script>
