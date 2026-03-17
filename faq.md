<div style="font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; max-width: 800px; margin: 20px auto; color: #1d1c1d; line-height: 1.6;">
  <h2 style="margin-bottom: 25px; color: #8E44AD;">💬 Slack 자주 묻는 질문</h2>
  <div style="margin-bottom: 30px;">
    <h3 style="font-size: 16px; color: #616061; margin-bottom: 10px; border-bottom: 1px solid #e1e4e8; padding-bottom: 5px;">📁 채널 관리</h3>
    <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>비공개 채널을 관리하는 방법</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
      Q : 비공개 채널 관리 + 2명이 비공개 채널에서 소통하다 퇴사시 해당 채널을 어떻게 다시 살려서 활용할지        <br><br>
        <a href="https://slack.com/intl/ko-kr/help/articles/217626378" target="_blank" rel="noopener" style="color: #1264a3; text-decoration: underline;">이메일 템플릿 보기 ↗</a>
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
      Q : 사용자 계정 관리를 위한 SCIM Provisioning은 어떻게 활용할 수 있을지 (프로필 및 유저 관리와 연관 있을 것 같은데 실제 저희 Plan 비교표에도 나와있지만 실제 활용하는 고객은 거의 없어 Business+ 를 계속 사용하게 하는데 중요한 요소가 될 수 있을 것 같습니다)
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
        <span>데이터 내보내기 및 가독성 있게 확인하는 방법</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
        📌 <Strong>비공개/DM까지 포함하여 데이터 내보내기</Strong>를 하기위해서 [<a href="https://minaslack.github.io/slackbizplus/#/dataexport?id=%eb%8d%b0%ec%9d%b4%ed%84%b0-%eb%82%b4%eb%b3%b4%eb%82%b4%ea%b8%b0-%ec%9a%94%ec%b2%ad" target="_blank" rel="noopener" style="color: #1264a3; text-decoration: underline; font-size: 15px; font-weight: 600;"> 데이터 내보내기 요청 </a>]🔼이 필요합니다.
      </div>
      <img width="401" alt="image" src="https://github.com/user-attachments/assets/7a2a06a8-cc2d-4a89-ad76-7e74c96f4423" />
      <div style="padding: 15px; background: #fff;">
  <div style="background: #F3E5F5; padding: 12px; border-radius: 6px; margin-bottom: 15px; font-size: 15px;">
    💡 <strong>팁:</strong> Slack에서 다운로드한 JSON 파일을 아래 도구에 붙여넣으면 표 형태로 편하게 보실 수 있습니다.
  </div>
        <div style="margin-top: 15px; padding: 12px; background-color: #fff5f5; border: 1px solid #fcbbbb; border-radius: 6px;">
  <p style="margin: 0 0 8px 0; font-size: 13px; color: #c0392b; font-weight: bold;">
    ⚠️ 보안 주의사항
  </p>
  <p style="margin: 0; font-size: 12px; color: #444; line-height: 1.6;">
    기업의 민감 데이터가 포함된 경우 외부 사이트 대신 <strong>엑셀(데이터 가져오기 > JSON)</strong>이나 
    브라우저의 <strong>JSON Viewer 확장 프로그램</strong>을 사용해 로컬에서 확인하는 것을 권장합니다.
  </p>
</div>
  <a href="https://jsontotable.org/" target="_blank" rel="noopener" style="display: inline-block; padding: 8px 16px; background-color: #8E44AD; color: #ffffff; text-decoration: none; border-radius: 4px; font-size: 13px; font-weight: 600;">
    JSON을 표로 변환하기 (JSON to Table)
  </a>
  <br>
  <br>
  [예시 화면]
  <img width="1459" alt="image" src="https://github.com/user-attachments/assets/e9e2f438-7290-458b-ab00-d5223f2803cb" />

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
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
          <ol style="line-height: 1.8;">
            <li>이메일 도메인 설정</li>
                    <img width="898" alt="image" src="https://github.com/user-attachments/assets/f73d3b75-8076-40ce-8a5c-e5b9869cc4f2" />
            <li>사용자 초대로 이동</li>
                    <img width="376" alt="image" src="https://github.com/user-attachments/assets/5d6b5eb1-8aaa-4e15-8942-88b6994afc1d" style="display: block; margin-top: 10px;" />
            <li>이메일 설정 및 초대링크 복사 후, 전달<br> - 설정된 도메인 계정으로 링크를 통해 접속하는 사용자는 승인 절차 없이 바로 입장</li>
              <img width="669" alt="image" src="https://github.com/user-attachments/assets/8e1d2660-c074-4850-89ca-69c24abb469a" style="display: block; margin-top: 10px;" />
          </ol>
      </div>
    </details>
    <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>Business+ 유저 이메일 변경 방법 (개인 계정 → 회사 계정, 관리자 이메일, 도메인 변경)</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
        Q : 유저 이메일 변경 방법 (간혹 개인 계정으로 만들어서 사용하는 유저들 이메일 변경 방법 + 관리자들 이메일 변경 방법), 회사 이메일 도메인 변경시 변경 방법
      </div>
    </details>
    <details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
      <summary style="padding: 12px 15px; background: #fafbfc; cursor: pointer; font-weight: 600; display: flex; justify-content: space-between; align-items: center; outline: none;">
        <span>최초 도입·평가판 시 권장 유저 초대 방법 (SSO 없는 환경 기준)</span>
        <span style="color: #1264a3; font-size: 12px;">더보기 ▼</span>
      </summary>
      <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
        Q : 최초 도입 혹은 평가판 활용시 권장 유저 초대 방법 (SSO 없다고 가정 하에)
      </div>
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
  </div>
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
