<div style="font-family: 'Pretendard', sans-serif; max-width: 800px; margin: 40px 0;">
    <h3 style="border-bottom: 2px solid #8E44AD; padding-bottom: 10px; color: #8E44AD;">🔍 초대 문제 자가 진단 (클릭해보세요)</h3>
    <p style="color: #666; font-size: 14px; margin-bottom: 20px;">현상을 선택하면 상세 해결 방법이 나타납니다.</p>
    <details style="margin-bottom: 12px; border: 1px solid #E1BEE7; border-radius: 8px; overflow: hidden;">
        <summary style="padding: 16px; background-color: #F3E5F5; cursor: pointer; font-weight: bold; color: #333; list-style: none;">
            ❓ 초대 메일이 도착하지 않아요
        </summary>
        <div style="padding: 20px; background-color: #fff; line-height: 1.6; border-top: 1px solid #E1BEE7;">
            <p style="margin: 0 0 10px 0;"><strong>체크리스트:</strong></p>
            <ul style="margin: 0; padding-left: 20px; color: #444;">
                <li><strong>스팸함 확인:</strong> <code>bounces.slack.com</code>에서 발송된 메일이 있는지 확인하세요.</li>
                <li><strong>초대 상태 확인:</strong> 관리자 패널 > [초대 관리]에서 상태가 '대기 중'인지 확인하세요.</li>
                <li><strong>도메인 제한:</strong> IT 팀에 Slack 발송 도메인이 방화벽에 막혀있는지 문의하세요.</li>
            </ul>
        </div>
    </details>
    <details style="margin-bottom: 12px; border: 1px solid #E1BEE7; border-radius: 8px; overflow: hidden;">
        <summary style="padding: 16px; background-color: #F3E5F5; cursor: pointer; font-weight: bold; color: #333; list-style: none;">
            ❓ 게스트(외부 협업자) 초대가 안 돼요
        </summary>
        <div style="padding: 20px; background-color: #fff; line-height: 1.6; border-top: 1px solid #E1BEE7;">
            <p style="margin: 0 0 10px 0;"><strong>해결 방법:</strong></p>
            <p style="margin: 0; color: #444;">
                비즈니스 플랜은 유료 멤버 1명당 <strong>최대 5명의 멀티 채널 게스트</strong>를 초대할 수 있습니다. 
                현재 워크스페이스의 남은 라이선스 수량을 확인해 보세요. 수량이 부족하면 추가 구매가 필요합니다.
            </p>
        </div>
    </details>
    <details style="margin-bottom: 12px; border: 1px solid #E1BEE7; border-radius: 8px; overflow: hidden;">
        <summary style="padding: 16px; background-color: #F3E5F5; cursor: pointer; font-weight: bold; color: #333; list-style: none;">
            ❓ 초대 링크가 만료되었다고 나옵니다
        </summary>
        <div style="padding: 20px; background-color: #fff; line-height: 1.6; border-top: 1px solid #E1BEE7;">
            <p style="margin: 0; color: #444;">
                Slack 초대 링크는 보안상 <strong>30일 후 자동 만료</strong>됩니다. 
                관리자 화면의 [초대 관리] 메뉴에서 해당 사용자의 초대를 취소한 뒤, 다시 초대를 보내 새 링크를 발급받으세요.
            </p>
        </div>
    </details>
</div>
<style>
    /* 화살표 모양 커스텀 (필요시) */
    summary::-webkit-details-marker { display: none; }
    summary::before { content: "▶ "; color: #8E44AD; margin-right: 10px; font-size: 12px; }
    details[open] summary::before { content: "▼ "; }
</style>
