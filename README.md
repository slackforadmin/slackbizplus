<div id="slack-wizard-final" style="max-width: 800px; margin: 20px 0; border: 1px solid #E1BEE7; border-radius: 16px; background: #fff; overflow: hidden; box-shadow: 0 4px 20px rgba(0,0,0,0.1); font-family: sans-serif;">
    <div style="padding: 20px; background: #F3E5F5; border-bottom: 1px solid #E1BEE7;">
        <h3 style="margin:0; color:#8E44AD; font-size:18px;">🔍 초대 문제 해결 가이드</h3>
        <div style="width: 100%; height: 4px; background: #E1BEE7; border-radius: 2px; margin-top: 15px;">
            <div id="wiz-bar-final" style="width: 20%; height: 100%; background: #8E44AD; transition: width 0.3s;"></div>
        </div>
    </div>
    <div style="padding: 24px; min-height: 200px;">
        <div id="final-step-1" class="step-div">
            <p style="font-size: 18px; font-weight: bold; margin-bottom: 20px;">Q1. 어떤 단계에서 문제가 발생했나요?</p>
            <button onclick="moveNext('1', '2-email', 50)" style="display:block; width:100%; text-align:left; padding:15px; margin-bottom:10px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">📧 초대 메일 발송 관련</button>
            <button onclick="moveNext('1', '2-role', 50)" style="display:block; width:100%; text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">🔑 권한 및 설정 관련</button>
        </div>
        <div id="final-step-2-email" class="step-div" style="display:none;">
            <p style="font-size: 18px; font-weight: bold; margin-bottom: 20px;">Q2. '초대 관리' 목록에 이름이 있나요?</p>
            <button onclick="showResult('상대방의 이메일 스팸함을 확인하게 하세요. 발신 주소 bounces.slack.com이 차단되었는지 확인이 필요합니다.')" style="display:block; width:100%; text-align:left; padding:15px; margin-bottom:10px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">네, '대기 중'으로 뜹니다</button>
            <button onclick="showResult('초대가 정상 발송되지 않았습니다. 다시 한번 이메일을 정확히 입력하여 초대를 보내주세요.')" style="display:block; width:100%; text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">아니요, 목록에 없습니다</button>
        </div>
        <div id="final-step-2-role" class="step-div" style="display:none;">
            <p style="font-size: 18px; font-weight: bold; margin-bottom: 20px;">Q2. 누구를 초대하시나요?</p>
            <button onclick="showResult('비즈니스 플랜은 유료 멤버 1명당 5명의 게스트를 초대할 수 있습니다. 남은 라이선스 수량을 체크하세요.')" style="display:block; width:100%; text-align:left; padding:15px; margin-bottom:10px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">외부 협업자(게스트)</button>
            <button onclick="showResult('사내 직원이라면 SSO 로그인이 필수인지 확인하세요. 관리자 설정의 도메인 제한 기능도 체크 대상입니다.')" style="display:block; width:100%; text-align:left; padding:15px; border:1px solid #ddd; border-radius:10px; background:#fff; cursor:pointer;">사내 정직원(멤버)</button>
        </div>
        <div id="final-result" class="step-div" style="display:none;">
            <div style="background: #F8F4FF; padding: 20px; border-radius: 12px; border: 1px solid #8E44AD;">
                <strong style="color: #8E44AD;">✅ 해결책:</strong>
                <p id="final-result-text" style="margin-top:10px; line-height:1.6;"></p>
            </div>
            <button onclick="location.reload()" style="margin-top:20px; padding:10px; cursor:pointer; background:none; border:1px solid #8E44AD; color:#8E44AD; border-radius:8px;">처음으로</button>
        </div>
    </div>
</div>
<script>
    // 전역 함수로 정의하여 어디서든 호출 가능하게 함
    window.moveNext = function(curr, next, prog) {
        document.getElementById('final-step-' + curr).style.display = 'none';
        document.getElementById('final-step-' + next).style.display = 'block';
        document.getElementById('wiz-bar-final').style.width = prog + '%';
    };
    window.showResult = function(text) {
        document.querySelectorAll('.step-div').forEach(function(div) { div.style.display = 'none'; });
        document.getElementById('final-result').style.display = 'block';
        document.getElementById('final-result-text').innerText = text;
        document.getElementById('wiz-bar-final').style.width = '100%';
    };
</script>
