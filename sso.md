
# SSO 및 인증

우측 상단의 SSO 설정을 클릭하여 SSO 설정을 끝내고 나면, 아래 화면이 보입니다. 

<div style="display: flex; justify-content: center; width: 100%;">
  <img src="https://github.com/user-attachments/assets/b89e3826-abae-43f5-a194-b5582e5139fd" 
       alt="image" 
       style="width: 100%; max-width: 1200px; height: 400px; object-fit: cover; border-radius: 8px;">
</div>

조직용
이메일과 비밀번호로 로그인하도록 허용
멤버가 SSO 인증을 하지 않고 Email 과 패스워드로 로그인하도록 설정할 수 있습니다. 

기본값 : 비활성화 

기본값은 비활성화 지만, 조직 주소유자와 그외 조직 소유자는 Email 과 비밀번호로 로그인할 수 있습니다. 그외 게스트나 특정 멤버를 포함시킬 수 있습니다. 

https://bookstack.byounghee.synology.me:6876/link/47#bkmrk-%EB%8B%A4%EB%A7%8C-%EC%A1%B0%EC%A7%81-%EC%86%8C%EC%9C%A0%EC%9E%90%EB%8F%84-%EB%AC%B4%EC%A1%B0%EA%B1%B4-sso-%EB%A1%9C

다만 조직 소유자도 무조건 SSO 로 로그인하도록 강제 할 수 있습니다.

<div style="display: flex; justify-content: center; width: 100%;">
  <img src="https://github.com/user-attachments/assets/067df41c-7c32-473e-abbb-3b7d2efaa86e" 
       alt="image" 
       style="width: 100%; max-width: 1200px; height: 400px; object-fit: cover; border-radius: 8px;">
</div>

사용자 프로필 동기화
기본값 : 비활성화

사용자가 SSO 로그인을 할 때마다 IDP(SSO) 와 동기화 합니다. 이 경우 사용자가 자신의 표시이름을 변경하도록 허용 항목도 비활성화 되어야 합니다.

사용자가 자신의 이메일 주소를 변경하도록 허용
기본값 : 비활성화

사용자가 자신의 이메일 주소를 변경할 수 있으나, 변경 후 IDP(SSO) 와 이메일 정보가 맞지 않는 경우 로그인 할 수 없게 됩니다.

사용자가 자신의 표시 이름을 변경하도록 허용
기본값 : 비활성화

사용자가 자신의 표시 이름을 변경하도록 허용할 수 있으며, 비활성화 시에는 IDP(SSO) 상의 displayName 항목과 동기화 합니다. 활성화시에는 IDP(SSO) 와 동기화 하지 않습니다.

SSO 설정 후에는 하단에 설정한 SSO 의 정보가 나옵니다. 
