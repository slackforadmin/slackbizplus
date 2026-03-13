
# SSO 및 인증

<details style="border: 1px solid #d1d5da; border-radius: 6px; margin-bottom: 10px;">
  <summary style="padding: 12px; cursor: pointer; background: #f6f8fa; font-weight: 800;">
    :dart: SSO 연동 방법
    <span style="background: #ffd33d; color: #24292e; padding: 2px 8px; border-radius: 10px; font-size: 13px; margin-left: 10px;">추천</span>
  </summary>
  <div style="padding: 15px; border-top: 1px solid #d1d5da;">
    <ul style="line-height: 1.8;">
      <li><Strong>Okta SSO</Strong></li>
         <video width="400" controls>
           <source src="https://github.com/minaslack/slackbizplus/releases/download/v1.0/oktavideo.mp4" type="video/mp4">
           <a href="https://github.com/minaslack/slackbizplus/blob/main/asset/pdf/slackbotusecasesprompts.pdf" target="_blank" title="PDF 가이드 보기" style="text-decoration: none; display: inline-block;">
          <div style="width: 160px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden; box-shadow: 0 4px 10px rgba(0,0,0,0.1); transition: transform 0.2s;">
            <img src=""
 alt="Slack Bot Use Cases PDF" style="width: 100%; display: block;">
            <div style="padding: 8px; background: #fff; font-size: 12px; color: #586069; text-align: center; border-top: 1px solid #e1e4e8;">
              📄 Use Cases 가이드
            </div>
          </div>
        </a>
         <li><Strong>Google SSO</Strong></li>
         <li><Strong>MS SSO</Strong></li>
 </video>
    </ul>
  </div>
</details>

<details style="border: 1px solid #d1d5da; border-radius: 6px; margin-bottom: 10px;">
  <summary style="padding: 12px; cursor: pointer; background: #f6f8fa; font-weight: 800;">
    :dart: SSO 연동 가이드
    <span style="background: #ffd33d; color: #24292e; padding: 2px 8px; border-radius: 10px; font-size: 13px; margin-left: 10px;">추천</span>
  </summary>
  <div style="padding: 15px; border-top: 1px solid #d1d5da;">
    <ol style="line-height: 1.8; list-style: none; padding-left: 0;">
      <li><strong>Okta</strong></li>
      <div style="display: flex; align-items: flex-start; gap: 20px; margin-top: 10px; flex-wrap: wrap;">
        <video width="400" controls style="border-radius: 8px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
          <source src="https://github.com/minaslack/slackbizplus/releases/download/v1.0/oktavideo.mp4" type="video/mp4">
        </video>
        <a href="https://github.com/minaslack/slackbizplus/blob/main/asset/pdf/slackbotusecasesprompts.pdf" target="_blank" title="PDF 가이드 보기" style="text-decoration: none; display: inline-block;">
          <div class="pdf-card" style="width: 160px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden; box-shadow: 0 4px 10px rgba(0,0,0,0.1); transition: transform 0.2s;">
            <img src="https://spn-sta.github.io/gen-ai-w/demos/mina_slack_pdf_preview.png" alt="Slack Bot Use Cases PDF" style="width: 100%; display: block;">
            <div style="padding: 8px; background: #fff; font-size: 12px; color: #586069; text-align: center; border-top: 1px solid #e1e4e8;">
              📄 Use Cases 가이드
            </div>
          </div>
        </a>
      </div>
    </ol>
  </div>
</details>

우측 상단의 SSO 설정을 클릭하여 SSO 설정을 끝내고 나면, 아래 화면이 보입니다. 

<img width="1429" alt="image" src="https://github.com/user-attachments/assets/cbfce6c0-8b9f-4379-8791-bb7bd5b24587" />

[Google 인증]<br>
 - 멤버가 Google 계정으로 로그인할 수 있습니다.<br>

<img width="638" alt="image" src="https://github.com/user-attachments/assets/4a90e25a-bc7f-4c90-bd79-f764e214239d" />

[ID 제공업체 또는 사용자 지정 SAML]<br>
 - 멤버가 SSO를 통해 로그인할 수 있습니다.<br>
 - ID 제공업체에서 사용자 규칙 기반 액세스를 자동으로 프로비저닝은 아래와 같은 기능을 제공합니다.<br>
   1. SAML SSO를 통한 기본적인 사용자 인증<br>
   2. SCIM을 통한 사용자 계정 생성/삭제<br>
   3. 프로필 필드 동기화<br>

   <div style="background-color: #F3E5F5; border-left: 5px solid #8E44AD; padding: 15px; margin: 10px 0; border-radius: 4px;">
  <span style="color: #6A1B9A; font-weight: bold;">⚠️ IDP 그룹을 워크스페이스/채널에 자동으로 연결하는 기능은 Enterprise+ 플랜에서만 가능합니다.<br>
  </span>
</div>
   
[Slack용 SAML Single Sign-On 설정](https://slack.com/intl/ko-kr/help/articles/203772216-Slack%EC%9A%A9-SAML-Single-Sign-On-%EC%84%A4%EC%A0%95) <br>
[사용자 맞춤형 SAML Single Sign-On](https://slack.com/intl/ko-kr/help/articles/205168057-%EC%82%AC%EC%9A%A9%EC%9E%90-%EB%A7%9E%EC%B6%A4%ED%98%95-SAML-Single-Sign-On) <br>
[ADFS Single Sign-On](https://slack.com/intl/ko-kr/help/articles/230902028-ADFS-Single-Sign-On) <br>

<img width="474" alt="image" src="https://github.com/user-attachments/assets/4f08fff9-e182-4bf5-9843-053e5589eb3a" />


