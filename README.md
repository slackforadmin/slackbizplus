<div id="slack-wizard-container" style="font-family: sans-serif; max-width: 800px; margin: 40px 0; border: 1px solid #E1BEE7; border-radius: 12px; background: #fff; overflow: hidden; box-shadow: 0 4px 15px rgba(0,0,0,0.05);">
  <div style="background-color: #F3E5F5; padding: 20px 24px; border-bottom: 1px solid #E1BEE7;">
    <h3 style="margin: 0; color: #8E44AD; font-size: 20px;">🔍 초대 문제 해결 가이드</h3>
    <p style="margin: 5px 0 0; font-size: 14px; color: #666;">발생한 증상을 선택하면 해결 방법을 안내해 드립니다.</p>
  </div>
  <div id="wizard-body" style="padding: 24px;">
    <div id="q-area">
      <p id="q-text" style="font-size: 18px; font-weight: bold; color: #333; margin-bottom: 20px;">질문을 불러오는 중...</p>
      <div id="btn-group" style="display: flex; flex-direction: column; gap: 10px;"></div>
    </div>
    <div id="a-area" style="display: none; background: #F9F9F9; padding: 20px; border-radius: 8px; border-left: 4px solid #8E44AD;">
      <p id="a-text" style="margin: 0; line-height: 1.6; color: #444;"></p>
      <button onclick="goStart()" style="margin-top: 20px; background: #8E44AD; color: #fff; border: none; padding: 8px 16px; border-radius: 6px; cursor: pointer;">처음으로</button>
    </div>
  </div>
</div>
<script>
(function() {
  const data = {
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
    guest_tip: { q: "해결책: 게스트 시트 확인", a: "비즈니스 플랜은 유료 멤버 1명당 5명의 멀티 채널 게스트를 초대할 수 있습니다. 남은 라이선스 수량을 확인해 보세요." },
    member_tip: { q: "해결책: 도메인 설정 확인", a: "사내 직원이라면 [설정 및 권한]에서 허용된 이메일 도메인(@company.com)으로 가입을 시도 중인지 확인하세요." }
  };
  function show(id) {
    const step = data[id];
    const qArea = document.getElementById('q-area');
    const aArea = document.getElementById('a-area');
    const qText = document.getElementById('q-text');
    const btnGroup = document.getElementById('btn-group');
    const aText = document.getElementById('a-text');
    if (step.a) { // 결과 페이지
      qArea.style.display = 'none';
      aArea.style.display = 'block';
      aText.innerHTML = "<strong>" + step.q + "</strong><br><br>" + step.a;
    } else { // 질문 페이지
      aArea.style.display = 'none';
      qArea.style.display = 'block';
      qText.innerText = step.q;
      btnGroup.innerHTML = '';
      step.opts.forEach(opt => {
        const btn = document.createElement('button');
        btn.innerText = opt.t;
        btn.style.cssText = "text-align:left; padding:12px; border:1px solid #ddd; border-radius:8px; background:#fff; cursor:pointer; font-size:15px;";
        btn.onmouseover = () => btn.style.background = "#F3E5F5";
        btn.onmouseout = () => btn.style.background = "#fff";
        btn.onclick = () => show(opt.n);
        btnGroup.appendChild(btn);
      });
    }
  }
  window.goStart = () => show('start');
  goStart();
})();
</script>
