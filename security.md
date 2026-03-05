
# 보안 설정

Slack 워크스페이스의 보안 및 접근 권한을 관리하는 설정 화면입니다.<br>
로그인 보안, 세션 관리, 비밀번호 정책 등 다양한 보안 옵션을 제어할 수 있습니다.

<img width="1450" alt="image" src="https://github.com/user-attachments/assets/0f6df48f-b53f-413d-af34-729a162049b8" />



<strong>주요 기능<strong><br>

<strong>로그인 설정<strong><br>

* 이메일 로그인의 2단계 인증 : 2FA 를 설정하는 옵션 입니다. 그리드에서는 문자 메세지는 사용할 수 없으며 2FA 앱 중에 선택할 수 있습니다.
그리드에서는 SAML 인증을 통해 SSO 로그인을  하는 경우에는 슬랙에서 2FA 를 설정하지 않고 IDP 에서 2FA 를 설정해야 합니다.
SSO 인증을 사용하지 않고 이메일/패스워드를 통해 로그인시 2FA 를 사용하도록 할 수 있습니다. 사용할 수 있는 2FA 앱은 다음과 같습니다.

  iPhone: Google Authenticator, Duo Mobile, 1Password, Authy, Microsoft Authenticator
  Android: Google Authenticator, Duo Mobile, 1Password, Authy, Microsoft Authenticator<br>
  [필수 워크스페이스 2단계 인증](https://slack.com/intl/ko-kr/help/articles/212221668-%ED%95%84%EC%88%98-%EC%9B%8C%ED%81%AC%EC%8A%A4%ED%8E%98%EC%9D%B4%EC%8A%A4-2%EB%8B%A8%EA%B3%84-%EC%9D%B8%EC%A6%9D)

<img width="509" height="513" alt="image" src="https://github.com/user-attachments/assets/d6857d18-86d6-4ea3-bd68-074a3602ca80" />

* 데스크톱 세션기간<br>
  기본값 : 비활성화 <br>
  설정시 데스크톱 세션 기간을 지정할 수 있습니다.<br>
  [세션 기간 관리](https://slack.com/intl/ko-kr/help/articles/115005223763-%EC%84%B8%EC%85%98-%EA%B8%B0%EA%B0%84-%EA%B4%80%EB%A6%AC)

* 모바일 세션기간<br>
  기본값 : 비활성화 <br>
  설정시 모바일 세션 기간을 지정할 수 있습니다.<br>
  [세션 기간 관리](https://slack.com/intl/ko-kr/help/articles/115005223763-%EC%84%B8%EC%85%98-%EA%B8%B0%EA%B0%84-%EA%B4%80%EB%A6%AC)<br>


* 비밀번호 강제 재설정 :<br>
  SSO가 아닌 이메일/패스워드를 통해 로그인하는 멤버들의 비밀번호를 강제로 재설정하도록 할 수 있습니다.<br>


<strong>장치 설정<strong><br>
* 파일 다운로드: 데스크톱과 모바일 앱에서 파일 다운로드 허용 여부를 제어할 수 있어요<br>
  기본값 : 데스크톱 / 모바일 허용<br>
  데스크톱 : 지정된 IP 에서 접속하는 경우에만 파일 다운로드를 할 수 있도록 설정할 수 있습니다. (이미지 미리보기의 경우 Blur 처리 됩니다) 지정가능한 IP 범위는 100 2000개 입니다.<br>
  모바일 : 모바일 기기에서 다운로드 하지 못하도록 차단할 수 있습니다.<br>
[Slack에서 파일 다운로드 및 메시지 복사 차단](https://slack.com/intl/ko-kr/help/articles/360016181794-Slack%EC%97%90%EC%84%9C-%ED%8C%8C%EC%9D%BC-%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C-%EB%B0%8F-%EB%A9%94%EC%8B%9C%EC%A7%80-%EB%B3%B5%EC%82%AC-%EC%B0%A8%EB%8B%A8) <br>


* 모바일 기기에서 메시지 복사하기 - 현재 "허용됨"으로 설정되어 있으며, 멤버들이 Slack 모바일 앱에서 메시지를 복사할 수 있어요. 데이터 유출 방지를 위해 필요시 이 기능을 비활성화할 수 있어요.<br>
  기본값 : 허용되지 않음<br>
  모바일 앱에서 복사를 차단합니다. <br>
[Slack에서 파일 다운로드 및 메시지 복사 차단](https://slack.com/intl/ko-kr/help/articles/360016181794-Slack%EC%97%90%EC%84%9C-%ED%8C%8C%EC%9D%BC-%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C-%EB%B0%8F-%EB%A9%94%EC%8B%9C%EC%A7%80-%EB%B3%B5%EC%82%AC-%EC%B0%A8%EB%8B%A8) <br>

* 탈옥 또는 루팅된 기기 - 현재 "허용됨"으로 설정되어 있어, 탈옥 또는 루팅된 기기를 사용하는 멤버도 Slack에 액세스할 수 있어요. 보안 강화를 위해 이러한 기기의 접근을 차단할 수도 있어요.<br>

  기본값 : 비활성화<br>
  고정된 으로 번역되어 있으나 영어 원문은 Root 입니다. 따라서 탈옥된 디바이스(iOS) 나 루팅된 디바이스(Android) 인 경우 Slack 앱을 사용하지 못하도록 설정할 수 있습니다. (EMM 미사용시만 적용)<br>
[탈옥 또는 루팅된 모바일 장치가 Slack에 액세스하지 못하도록 차단](https://slack.com/intl/ko-kr/help/articles/360042097113-%ED%83%88%EC%98%A5-%EB%98%90%EB%8A%94-%EB%A3%A8%ED%8C%85%EB%90%9C-%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%9E%A5%EC%B9%98%EA%B0%80-Slack%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EC%A7%80-%EB%AA%BB%ED%95%98%EB%8F%84%EB%A1%9D-%EC%B0%A8%EB%8B%A8) <br>

