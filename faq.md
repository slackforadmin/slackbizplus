<div style="font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; max-width: 800px; margin: 20px auto; color: #1d1c1d; line-height: 1.6;">
  <h2 style="margin-bottom: 25px; color: #8E44AD;">💬 Slack 자주 묻는 질문</h2>
  <div style="margin-bottom: 30px;">
    <h3 style="font-size: 16px; color: #616061; margin-bottom: 10px; border-bottom: 1px solid #e1e4e8; padding-bottom: 5px;">📁 채널 관리</h3>
    <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>[완료]비공개 채널을 관리하는 방법</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
        📌 채널 리스트에 비공개 채널이 안보이시나요?<br>
          - 비공개 채널을 관리하기 위해서는 <Strong>데이터 내보내기 요청 후 승인</Strong>을 받아야 합니다.<br>
          - 데이터 내보내기 활성화 사전신청 -> 내부 심사 및 활성화 승인 -> 채널리스트에 비공개 채널 표시<br>
        <br>
          <Strong>참고💡 비공개 채널 관리 도구는 한 번 승인되면 계속 접근 가능</Strong><br>
        <br>
          <Strong>[데이터 내보내기 요청]</Strong><br>
          워크스페이스 소유자는 추가 내보내기 유형에 대한 액세스를 신청할 수 있습니다.<br>
          신청서에는 워크스페이스 주 소유자의 승인이 필요하므로, 지원 팀에서 신청서를 검토하기 전에 이메일로 연락드릴 것입니다.<br>
      </div>
    <img width="80%" alt="image" src="https://github.com/user-attachments/assets/f4ef92dc-31e6-45db-aa6b-85e51494b181" />
      </div>
    </details>
  </div>
<div style="margin-bottom: 30px;">
  <h3 style="font-size: 16px; color: #616061; margin-bottom: 10px; border-bottom: 1px solid #e1e4e8; padding-bottom: 5px;">🔐 보안 및 인증</h3>
  <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
    <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
      <span>[완료]Google OAuth vs SAML 차이 및 권장 설정</span>
      <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
    </summary>
    <div style="padding: 15px 0; background: #fff; border-top: 1px solid #e1e4e8;">
      <div style="padding: 0 15px;">
        <p style="margin-top: 0; margin-bottom: 15px; font-size: 14px; color: #1d1c1d;">
          <strong>[Google OAuth vs SAML 차이]</strong><br>
          아래와 같이 제어가 가능하기 때문에 <Strong>SAML설정을 권장</Strong>합니다.<br>
        </p>
      </div>
      <table style="width: 70%; margin: 0 auto; border-collapse: collapse; font-size: 13px; line-height: 1.5; background-color: #ffffff;">
        <thead>
          <tr style="background: #f8f9fa;">
            <th style="padding: 12px 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d;">항목</th>
            <th style="padding: 12px 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d;">Google OAuth</th>
            <th style="padding: 12px 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d;">Google SAML</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; background-color: transparent;">설정 난이도</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">쉬움 (빠른 설정)</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">중간 (IDP 설정 필요)</td>
          </tr>
          <tr>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; background-color: transparent;">지원 플랜</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">Pro, Business+</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">Business+, Enterprise Grid</td>
          </tr>
          <tr>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; background-color: transparent;">JIT 프로비저닝 제어</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;"><span style="color: #e01e5a;">❌</span> 항상 ON (끌 수 없음)</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;"><span style="color: #2eb67d;">✅</span> ON/OFF 선택 가능</td>
          </tr>
          <tr>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; background-color: transparent;">사용자 단위 접근 제어</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;"><span style="color: #e01e5a;">❌</span> 도메인 단위만 가능</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;"><span style="color: #2eb67d;">✅</span> 사용자/그룹 단위 제어</td>
          </tr>
          <tr>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; background-color: transparent;">SCIM 연동</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;"><span style="color: #e01e5a;">❌</span> 불가</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;"><span style="color: #2eb67d;">✅</span> 가능</td>
          </tr>
          <tr>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; background-color: transparent;">2FA 적용</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">IDP 레벨 설정 필요</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">IDP 레벨 설정 필요</td>
          </tr>
        </tbody>
      </table>
        <div style="padding: 0 15px;">
          <p style="margin-top: 0; margin-bottom: 15px; font-size: 14px; color: #1d1c1d;">
            <br>
            📌 참조<br>
                  1. <strong>JIT(Just-In-Time) 프로비저닝</strong>은 <strong>사용자가 처음 로그인할 때 자동으로 계정이 만들어지는 기능</strong>입니다.<br>
              이 기능을 끄면 관리자가 사전에 승인한 사용자만 접근할 수 있어서 보안을 강화할 수 있습니다.<br>
              참고) 필요한 경우, Feedback 팀으로 요청하여 JIT를 Off할 수 있습니다.<br>
              2. <strong>SCIM</strong>은 사용자 계정을 IDP(Okta, Google Workspace 등)와 Slack 사이에서 자동으로 동기화해주는 기능입니다.
          </p>
      </div>
      <div style="height: 15px;"></div>
    </div>
  </details>
  <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
    <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
      <span>SCIM Provisioning 활용 방법 (프로필·유저 관리 자동화)</span>
      <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
    </summary>
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
        📌 <Strong>SCIM이란?</Strong><br>
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;회사의 IDP(Identity Provider, 예: Okta, Entra ID, Google)와 Slack을 연결해서 사용자 계정을 자동으로<br> 
        생성·수정·비활성화할 수 있게 해주는 <Strong>ID 관리를 자동화하는 국제 표준 프로토콜</Strong>입니다.<br>
        <br>
          <div style="background-color: #F3E5F5; border-left: 5px solid #8E44AD; padding: 15px; margin: 10px 0; border-radius: 4px;">
  <span style="color: #6A1B9A; font-weight: bold;">⚠️ 로그인 시 싱크는 SAML이, 계정 생성·수정·비활성화 등 라이프사이클 관리는 SCIM Connector 앱을 통해 별도로 수행됩니다.</span>
</div>
        🌟 <Strong>IDP별 지원 현황</Strong><br>
              <table style="width: 70%; margin: 0 auto; border-collapse: collapse; font-size: 13px; line-height: 1.5; background-color: #ffffff;">
        <thead>
          <tr style="background: #f8f9fa;">
            <th style="padding: 12px 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d;">IDP</th>
            <th style="padding: 12px 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d;">SCIM 연동 앱</th>
            <th style="padding: 12px 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d;">비고</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; background-color: transparent;">Entra ID</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">Microsoft Azure AD Provisioning</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">풀 지원</td>
          </tr>
          <tr>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; background-color: transparent;">Okta</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">Okta Provisioning</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">풀 지원</td>
          </tr>
          <tr>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; background-color: transparent;">Google</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">제한적</td>
            <td style="padding: 10px; border: 1px solid #e1e4e8; text-align: center; background-color: transparent;">이름·이메일 등 일부 필드만, 그룹 푸시<span style="color: #2eb67d;">❌</span></td>
          </tr>
        </tbody>
      </table>
      </div>
  </details>
</div>
  <div style="margin-bottom: 30px;">
    <h3 style="font-size: 16px; color: #616061; margin-bottom: 10px; border-bottom: 1px solid #e1e4e8; padding-bottom: 5px;">📤 데이터 내보내기 및 메시지 관리</h3>
        <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>[완료]비공개 채널/DM까지 포함하여 데이터 내보내기 방법</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
        📌 <Strong>비공개 채널/DM까지 포함하여 데이터 내보내기</Strong>를 하기위해서는 아래의 절차가 필요합니다.<br>
          - 데이터 내보내기 활성화 사전신청 -> 내부 심사 및 활성화 승인 -> 데이터 내보내기 가능<br>
        <br>
          <Strong>[데이터 내보내기 요청]</Strong><br>
          워크스페이스 소유자는 추가 내보내기 유형에 대한 액세스를 신청할 수 있습니다.<br>
          신청서에는 워크스페이스 주 소유자의 승인이 필요하므로, 지원 팀에서 신청서를 검토하기 전에 이메일로 연락드릴 것입니다.<br>
      </div>
    <img width="80%" alt="image" src="https://github.com/user-attachments/assets/f4ef92dc-31e6-45db-aa6b-85e51494b181" />
    </details>
    <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>[완료]데이터 내보내기 및 가독성 있게 확인하는 방법</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
            <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
        📌 <Strong>비공개 채널/DM까지 포함하여 데이터 내보내기</Strong>를 하기위해서 [<a href="https://minaslack.github.io/slackbizplus/#/dataexport?id=%eb%8d%b0%ec%9d%b4%ed%84%b0-%eb%82%b4%eb%b3%b4%eb%82%b4%ea%b8%b0-%ec%9a%94%ec%b2%ad" target="_blank" rel="noopener" style="color: #1264a3; text-decoration: underline; font-size: 15px; font-weight: 600;"> 데이터 내보내기 요청 </a>]🔼이 필요합니다.
      </div>
<div style="font-family: 'Pretendard', -apple-system, sans-serif; max-width: 900px; color: #333; line-height: 1.6;">
  
  <div style="padding: 20px 0 20px 0;">
    <div style="font-size: 13px; font-weight: bold; color: #007bff; margin-bottom: 5px; margin-left: 15px;">STEP 01</div>
    <div style="font-size: 15px; font-weight: bold; margin-bottom: 5px; margin-left: 15px;">데이터 내보내기 설정</div>
    <div style="padding: 15px 20px; background-color: #f9f9f9; border-radius: 8px; margin-bottom: 5px;">
      1. 보안 > 데이터 가져오기 및 내보내기 > 내보내기 날짜 범위 선택 후 <b>[내보내기 시작]</b> 클릭
    </div>
    <img width="401" alt="image" src="https://github.com/user-attachments/assets/7a2a06a8-cc2d-4a89-ad76-7e74c96f4423" style="display: block; border: 1px solid #eee; border-radius: 4px; margin-left: auto; margin-right: auto;" />
  </div>
  <div style="padding: 20px 0 20px 0;">
    <div style="font-size: 13px; font-weight: bold; color: #007bff; margin-bottom: 5px;margin-left: 15px">STEP 02</div>
    <div style="font-size: 15px; font-weight: bold; margin-bottom: 5px;margin-left: 15px;">파일 다운로드</div>
    <div style="padding: 15px 20px; background-color: #f9f9f9; border-radius: 8px; margin-bottom: 5px;">
      2. 목록에서 <b>[다운로드 준비]</b> 버튼을 클릭하여 파일을 저장
    </div>
    <img width="926" alt="image" src="https://github.com/user-attachments/assets/27de6c60-b338-42dd-9b1a-fdd95157a69c" style="display: block; max-width: 100%; border: 1px solid #eee; border-radius: 4px;" />
  </div>
  <div style="padding: 20px 0 20px 0;">
    <div style="font-size: 13px; font-weight: bold; color: #007bff; margin-bottom: 5px;margin-left: 15px;">STEP 03</div>
    <div style="font-size: 15px; font-weight: bold; margin-bottom: 5px;margin-left: 15px;">JSON 데이터 변환</div>
    <div style="padding: 15px 20px; background-color: #f9f9f9; border-radius: 8px; margin-bottom: 10px;">
      3. <b>[JSON을 표로 변환하기]</b> 버튼 클릭 후 변환 도구 웹사이트 오픈<br>
      &nbsp;&nbsp;&nbsp;JSON 파일 업로드 또는 붙여넣기 후 결과 확인
    </div>
  <a href="https://jsontotable.org/" target="_blank" rel="noopener" style="display: inline-block; padding: 8px 16px; background-color: #8E44AD; color: #ffffff; text-decoration: none; border-radius: 4px; font-size: 13px; font-weight: 600;margin-bottom: 10px;">
    JSON을 표로 변환하기 (JSON to Table)
  </a>
    <br>
    <img width="1454" alt="image" src="https://github.com/user-attachments/assets/b48dc82e-3f96-46cf-ad56-9ed7798e4d08" style="display: block; max-width: 100%; border: 1px solid #eee; border-radius: 4px;" />
<div style="margin-top: 15px; padding: 12px 20px; padding-left: 15px; padding-right: 15px; background-color: #fff5f5; border: 1px solid #fcbbbb; border-radius: 6px;">
  <p style="margin: 0 0 8px 0; font-size: 15px; color: #c0392b; font-weight: bold;">
    ⚠️ 보안 주의사항
  </p>
  <p style="margin: 0; font-size: 15px; color: #444; line-height: 1.6;">
    기업의 민감 데이터가 포함된 경우 외부 사이트 대신 <strong>엑셀(데이터 가져오기 > JSON)</strong>이나 
    브라우저의 <strong>JSON Viewer 확장 프로그램</strong>을 사용해 로컬에서 확인하는 것을 권장합니다.
  </p>
</div>
  </div>
</div>
    </details>
  </div>
    <div style="margin-bottom: 30px;">
    <h3 style="font-size: 16px; color: #616061; margin-bottom: 10px; border-bottom: 1px solid #e1e4e8; padding-bottom: 5px;">👤 계정 및 사용자 관리</h3>
    <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>[완료]승인 없이 다수 멤버 일괄 초대 방법</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
<div style="font-family: 'Pretendard', -apple-system, sans-serif; max-width: 900px; color: #333; line-height: 1.6; border-top: 1px solid #e1e4e8;">
  <div style="padding: 20px 0 20px 0;">
    <div style="font-size: 13px; font-weight: bold; color: #007bff; margin-bottom: 5px;margin-left: 15px;">STEP 01</div>
    <div style="font-size: 15px; font-weight: bold; margin-bottom: 5px;margin-left: 15px;">이메일 도메인 설정</div>
    <div style="padding: 15px 20px; background-color: #f9f9f9; border-radius: 8px; margin-bottom: 5px;">
      1. 관리자 화면에서 설정 > 설정 및 권한 > <b>승인된 이메일 도메인 설정</b> 
    </div>
    <img width="898" alt="이메일 도메인 설정" src="https://github.com/user-attachments/assets/f73d3b75-8076-40ce-8a5c-e5b9869cc4f2" style="display: block; max-width: 100%; border: 1px solid #eee; border-radius: 4px;margin-left: auto; margin-right: auto;" />
  </div>
  <div style="padding: 20px 0 20px 0;">
    <div style="font-size: 13px; font-weight: bold; color: #007bff; margin-bottom: 5px;margin-left: 15px;">STEP 02</div>
    <div style="font-size: 15px; font-weight: bold; margin-bottom: 5px;margin-left: 15px;">사용자 초대 메뉴 이동</div>
    <div style="padding: 15px 20px; background-color: #f9f9f9; border-radius: 8px; margin-bottom: 5px;">
      2. 워크스페이스명 > 사용자 초대 버튼 클릭해서 <b>사용자 초대 팝업 오픈</b>
    </div>
    <img width="376" alt="사용자 초대 이동" src="https://github.com/user-attachments/assets/5d6b5eb1-8aaa-4e15-8942-88b6994afc1d" style="display: block; max-width: 100%; border: 1px solid #eee; border-radius: 4px;margin-left: auto; margin-right: auto;" />
  </div>
  <div style="padding: 20px 0 20px 0;">
    <div style="font-size: 13px; font-weight: bold; color: #007bff; margin-bottom: 5px;margin-left: 15px;">STEP 03</div>
    <div style="font-size: 18px; font-weight: bold; margin-bottom: 5px;margin-left: 15px;">초대 링크 복사 및 전달</div>
    <div style="padding: 15px 20px; background-color: #f9f9f9; border-radius: 8px; margin-bottom: 5px;">
      3. 이메일 설정하거나 초대 링크를 복사해서 대상자들에게 전달<br>
      <span style="font-size: 15px;">※ 설정된 도메인 계정 사용자는 별도 승인 절차 없이 <b>즉시 입장</b>이 가능합니다.</span>
    </div>
    <img width="500" alt="초대 링크 복사" src="https://github.com/user-attachments/assets/8e1d2660-c074-4850-89ca-69c24abb469a" style="display: block; max-width: 100%; border: 1px solid #eee; border-radius: 4px;margin-left: auto; margin-right: auto;" />
  </div>
</div>
    </details>
    <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>[완료]SSO연동 시에 사용자 이메일 변경 방법</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
<div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
    📌 이메일이나 표시이름을 변경할 수 없으신가요?<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SSO를 활성화한 경우, 이메일 주소를 포함한 <b>개인 정보 편집 기능이 제한</b>될 수 있으나,<br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>워크스페이스 소유자</b>가 사용자들이 이메일 주소를 변경할 수 있도록 허용할 수 있습니다.
        <br>
  <br>
        🔗 참조 링크<br>
        <a href="https://slack.com/intl/ko-kr/help/articles/207262907-%EC%9D%B4%EB%A9%94%EC%9D%BC-%EC%A3%BC%EC%86%8C-%EB%B3%80%EA%B2%BD?gad_source=1&gad_campaignid=23274986143&gbraid=0AAAAACylTvomOl6mvXW5Kww-Pj98WDTOo&gclid=Cj0KCQjwve7NBhC-ARIsALZy9HWion0c2Ez6xoOYmDZYm113CjSolE9b0bVu26oxttDRe9rdAcAD_1saAkk-EALw_wcB#%EB%8D%B0%EC%8A%A4%ED%81%AC%ED%86%B1-1" target="_blank" rel="noopener" style="color: #1264a3; text-decoration: underline; font-size: 15px; font-weight: 600;"> 이메일 주소 변경 </a><br>
        <a href="https://slack.com/intl/ko-kr/help/articles/225531168-%EA%B5%AC%EC%84%B1%EC%9B%90%EC%9D%98-%EC%9D%B4%EB%A9%94%EC%9D%BC-%EC%A3%BC%EC%86%8C-%EB%B3%80%EA%B2%BD" target="_blank" rel="noopener" style="color: #1264a3; text-decoration: underline; font-size: 15px; font-weight: 600;"> 구성원의 이메일 주소 변경 </a><br>
        <br>
        💡 <b>이메일 주소를 변경할 수 있도록 허용하는 방법</b>
      </div>
      <img width="591" alt="image" src="https://github.com/user-attachments/assets/1b52ca77-dadf-4cf5-89f7-321452d0a7e3" />
      <div style="padding: 15px; background: #fff;">
              📌 단, 아래 3개 항목 중 하나라도 기본값과 다르게 설정되어 있는 경우,<br>
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;로그인 시, 해당 사용자의 프로필 값이 업데이트 되지 않는 다는 것 기억해주세요!!<br>
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;즉, 이메일 주소를 변경할 수 있도록 설정을 변경하면 사용자 프로필 정보가 싱크되지 않습니다.<br>
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(전제 : 자동 프로비저닝을 사용하고 있지 않음)<br>
              <br>
      </div>
      <img width="1154" alt="image" src="https://github.com/user-attachments/assets/7f316619-32f0-4bcb-84c1-dd66c909df5d" />
    </details>
      <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>사용자 프로필 항목을 중앙에서 API로 관리하는 방법 (Okta/Entra ID 없는 경우 포함)</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
        Q : 사용자 프로필에 들어가야 할 내용을 중앙에서 API로 넣어줄 수 있는 방법 (Okta, Entra ID 안 쓰는 경우에도)
      </div>
    </details>
    <div style="margin-bottom: 30px;">
    <h3 style="font-size: 16px; color: #616061; margin-bottom: 10px; border-bottom: 1px solid #e1e4e8; padding-bottom: 5px;">🌐 외부 협업 및 권한 설정</h3>
    <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>Slack Connect 및 게스트 초대를 관리자 승인 하에 운영하는 방법</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
        Q : 운영시 슬랙 Connect, 게스트 초대 관리자 승인하에 운영되게 하는 방법
      </div>
    </details>
  </div>
</div>
