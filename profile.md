
# 프로필 구성

Slack에서는 세 가지 방법 중에서 선택하여 프로필 필드를 업데이트할 수 있습니다.

1. SCIM<br>
SCIM API를 통해 프로필 필드를 자동으로 채웁니다.<br>
2. API<br>
Web API를 사용해 프로필 필드를 설정 또는 검색합니다.<br>
3. 사용자 편집 <br>
멤버는 수동으로 프로필 필드를 업데이트할 수 있습니다.<br>

<div style="background-color: #F3E5F5; border-left: 5px solid #8E44AD; padding: 15px; margin: 10px 0; border-radius: 4px;">
  <span style="color: #6A1B9A; font-weight: bold;">⚠️ 변경 후, 우측 상단의 활성화된 [변경사항 개시]버튼을 클릭해야 변경 내용이 저장됩니다.</span>
</div>

<details style="margin-bottom: 8px; border: 1px solid #e1e4e8; border-radius: 8px; overflow: hidden;">
  <summary style="padding: 16px; cursor: pointer; background: #fafbfc; font-weight: 700; color: #24292e; display: flex; align-items: center; justify-content: space-between; border-radius: 8px 8px 0 0;">
    <div>
      :dart: SCIM Provisioning 활용 방법 (프로필·유저 관리 자동화)
    </div>
  </summary>
        <div style="padding: 15px; background: #fff; border-top: 1px solid #e1e4e8;">
      📌 <Strong>SCIM이란?</Strong><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;회사의 IDP(Identity Provider, 예: Okta, Entra ID, Google)와 Slack을 연결해서 사용자 계정을 자동으로<br> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;생성·수정·비활성화할 수 있게 해주는 <Strong>ID 관리를 자동화하는 국제 표준 프로토콜</Strong>입니다.<br>
      <br>
        <div style="background-color: #F3E5F5; border-left: 5px solid #8E44AD; padding: 15px; margin: 10px 0; border-radius: 4px;">
<span style="color: #6A1B9A;font-weight: bold;">⚠️ SAML : 로그인 시 싱크 담당<br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SCIM : 계정 생성·수정·비활성화 등 라이프사이클 관리를 SCIM Connector 앱을 통해 별도 수행</span>
</div>
      <br>
      🌟 <Strong>IDP별 지원 현황</Strong><br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- 설정 하면서 슬랙에 해당 IDP의 SCIM Connector 설치가 진행됨. (<Strong>Org레벨</Strong>에 설치필요) <br>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- 만약 SCIM Connector 가 없다면 Custom SCIM Connector 제작이 필요합니다.<br>
<table style="width: 100%; margin: 10px 0 0 10px; border-collapse: collapse; font-size: 13px; line-height: 1.5; background-color: #ffffff;">
<thead>
  <tr style="background: #f8f9fa;">
    <th style="padding: 12px 15px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d; white-space: nowrap;">IDP</th>
    <th style="padding: 12px 15px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d; white-space: nowrap;">SCIM 연동 앱</th>
    <th style="padding: 12px 15px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d; white-space: nowrap;">비고</th>
    <th style="padding: 12px 15px; border: 1px solid #e1e4e8; text-align: center; font-weight: 700; color: #1d1c1d; white-space: nowrap;">공식 설정 문서</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; white-space: nowrap;">Entra ID</td>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; white-space: nowrap;">Microsoft Azure AD Provisioning</td>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; white-space: nowrap;">-</td>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; white-space: nowrap;">
      <a href="https://learn.microsoft.com/en-us/entra/identity/saas-apps/slack-provisioning-tutorial" target="_blank" style="color: #007bff; text-decoration: none;">링크</a>
    </td>
  </tr>
  <tr>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; white-space: nowrap;">Okta</td>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; white-space: nowrap;">Okta Provisioning</td>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; white-space: nowrap;">-</td>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; white-space: nowrap;">
      <a href="https://help.okta.com/en-us/content/topics/provisioning/slack/slck-integrate-slack.htm" target="_blank" style="color: #007bff; text-decoration: none;">링크</a>
    </td>
  </tr>
  <tr>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; font-weight: 600; white-space: nowrap;">Google</td>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; white-space: nowrap;">제한적</td>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; white-space: nowrap;">이름·이메일 등 일부 필드만, 그룹 푸시❌</td>
    <td style="padding: 10px 15px; border: 1px solid #e1e4e8; text-align: center; white-space: nowrap;">
      <a href="https://knowledge.workspace.google.com/admin/users/advanced/configure-slack-user-provisioning?sjid=17221264273189227714-AP&visit_id=639104557331627052-2063466825&rd=1&hl=ko" target="_blank" style="color: #007bff; text-decoration: none;">링크</a>
    </td>
  </tr>
</tbody>
</table>
    </div>
</details>

<img width="2940" alt="image" src="https://github.com/user-attachments/assets/af072ee6-61a4-49e0-8b70-aad0a882e9df" />
