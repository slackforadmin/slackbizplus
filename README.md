<div id="slack-wiz-v3" style="font-family: sans-serif; max-width: 800px; margin: 20px 0; border: 1px solid #E1BEE7; border-radius: 16px; background: #fff; overflow: hidden; box-shadow: 0 4px 20px rgba(0,0,0,0.1);">
  <div style="background: #F3E5F5; padding: 15px 20px; border-bottom: 1px solid #E1BEE7;">
    <div style="width: 100%; height: 6px; background: #E1BEE7; border-radius: 3px;">
      <div id="wiz-progress-bar" style="width: 25%; height: 100%; background: #8E44AD; transition: width 0.3s;"></div>
    </div>
  </div>
  <div style="padding: 25px; min-height: 250px;">
    <div id="sw-step-1" class="sw-step">
      <p style="font-size: 18px; font-weight: bold; margin-bottom: 20px;">Q1. 어떤 단계에서 문제가 발생했나요?</p>
      <button onclick="swNext('1', '2-email', 50)" style="display:block; width:100%; text-align:left; padding:15px; margin-bottom:10px; border:1px solid #E1BEE7; border-radius:10px; background:#fff; cursor:pointer;">📧 초대 메일 발송 관련</button>
      <button onclick="swNext('1', '2-perm', 50)" style="display:block; width:100%; text-align:left; padding:15px; border:1px solid #E1BEE7; border-radius:10px; background:#fff; cursor:pointer;">🔑 권한 및 설정 관련</button>
    </div>
    <div id="sw-step-2-email" class="sw-step" style="display:none;">
      <p style="font-size: 18px; font-weight: bold; margin-bottom: 20px;">Q2. '초대 관리' 목록에 대상자 이메일이 있나요?</p>
      <button onclick="swFinal('상대방의 스팸함을 확인하세요. bounces.slack.com 도메인 허용이 필요할 수 있습니다.')" style="display:block; width:100%; text-align:left; padding:15px; margin-bottom:10px; border:1px solid #E1BEE7; border-radius:10px; background:#fff; cursor:pointer;">네, '대기 중'으로 보입니다</button>
      <button onclick="swFinal('메일 발송 과정에서 오류가 있었습니다. 이메일 주소를 재확인하고 다시 초대를 보내보세요.')" style="display:block; width:100%; text-align:left; padding:15px; border:1px solid #E1BEE7; border-radius:10px; background:#fff; cursor:pointer;">아니요, 목록에 없습니다</button>
    </div>
    <div id="sw-step-2-perm" class="sw-step" style="display:none;">
      <p style="font-size: 18px; font-weight: bold; margin-bottom: 20px;">Q2. 초대 대상자가 누구인가요?</p>
      <button onclick="swFinal('비즈니스 플랜 게스트는 유료 멤버 1명당 5명까지 가능합니다. 시트 여유를 확인하세요.')" style="display:block; width:100%; text-align:left; padding:15px; margin-bottom:10px; border:1px solid #E1BEE7; border-radius:10px; background:#fff; cursor:pointer;">외부 협업자(게스트)</button>
      <button onclick="swFinal('사내 직원 초대가 안 된다면 SSO(단일 로그인) 설정이나 도메인 제한을 확인해야 합니다.')" style="display:block; width:100%; text-align:left; padding:15px; border:1px solid #E1BEE7; border-radius:10px; background:#fff; cursor:pointer;">회사 정직원(멤버)</button>
    </div>
    <div id="sw-step-final" class="sw-step" style="display:none;">
      <div style="background: #F8F4FF; padding: 20px; border-radius: 12px; border: 1px solid #8E44AD;">
        <strong style="color: #8E44AD; font-size: 17px;">✅ 해결 가이드</strong>
        <p id="sw-res-text" style="margin-top:10px; line-height:1.6; color:#444;"></p>
      </div>
      <button onclick="swReset()" style="margin-top:20px; padding:10px 20px; border:1px solid #8E44AD; background:none; color:#8E44AD; border-radius:8px; cursor:pointer; font-weight:bold;">처음으로</button>
    </div>
  </div>
</div>
<script>
window.swNext = function(curr, next, prog) {
  document.getElementById('sw-step-' + curr).style.display = 'none';
  var nextStep = document.getElementById('sw-step-' + next);
  if(nextStep) nextStep.style.display = 'block';
  document.getElementById('wiz-progress-bar').style.width = prog + '%';
};
window.swFinal = function(msg) {
  document.querySelectorAll('.sw-step').forEach(function(el) { el.style.display = 'none'; });
  document.getElementById('sw-step-final').style.display = 'block';
  document.getElementById('sw-res-text').innerText = msg;
  document.getElementById('wiz-progress-bar').style.width = '100%';
};
window.swReset = function() {
  document.querySelectorAll('.sw-step').forEach(function(el) { el.style.display = 'none'; });
  document.getElementById('sw-step-1').style.display = 'block';
  document.getElementById('wiz-progress-bar').style.width = '25%';
};
</script>
