
# 보안 설정

Slack 워크스페이스의 보안 및 접근 권한을 관리하는 설정 화면입니다.<br>
로그인 보안, 세션 관리, 비밀번호 정책 등 다양한 보안 옵션을 제어할 수 있습니다.

<img width="1450" alt="image" src="https://github.com/user-attachments/assets/0f6df48f-b53f-413d-af34-729a162049b8" />



주요 기능<br>

[로그인 설정]<br>

* 이메일 로그인의 2단계 인증<br>
  2FA 를 설정하는 옵션 입니다.<br>
  허용된 2FA 방법은 [SMS 및 인증 앱] 그리고 [인증 앱만] 이렇게 두가지입니다.<br>

  SSO 인증을 사용하지 않고 이메일/패스워드를 통해 로그인시 슬랙의 2FA 를 사용하도록 할 수 있습니다.<br>
  사용할 수 있는 2FA 앱은 다음과 같습니다.<br>
  iPhone: Google Authenticator, Duo Mobile, 1Password, Authy, Microsoft Authenticator<br>
  Android: Google Authenticator, Duo Mobile, 1Password, Authy, Microsoft Authenticator<br>
  [필수 워크스페이스 2단계 인증](https://slack.com/intl/ko-kr/help/articles/212221668-%ED%95%84%EC%88%98-%EC%9B%8C%ED%81%AC%EC%8A%A4%ED%8E%98%EC%9D%B4%EC%8A%A4-2%EB%8B%A8%EA%B3%84-%EC%9D%B8%EC%A6%9D)

<img width="509" height="513" alt="image" src="https://github.com/user-attachments/assets/d6857d18-86d6-4ea3-bd68-074a3602ca80" />

* 데스크톱 세션기간<br>
  설정시 데스크톱 세션 기간을 지정할 수 있습니다.<br>
  사용자를 데스크톱에서 자동으로 로그아웃 방식은 [애플리케이션을 닫을 때마다] 그리고 [정해진 일정에 따라(최소 12시간마다)] 입니다.<br>
  [세션 기간 관리](https://slack.com/intl/ko-kr/help/articles/115005223763-%EC%84%B8%EC%85%98-%EA%B8%B0%EA%B0%84-%EA%B4%80%EB%A6%AC)

* 모바일 세션기간<br>
  설정시 모바일 세션 기간을 지정할 수 있습니다.<br>
  모바일 세션 주기는 최소 4시간 이상이어야 합니다.<br>
  [세션 기간 관리](https://slack.com/intl/ko-kr/help/articles/115005223763-%EC%84%B8%EC%85%98-%EA%B8%B0%EA%B0%84-%EA%B4%80%EB%A6%AC)<br>

* 비밀번호 강제 재설정<br>
  SSO가 아닌 이메일/패스워드를 통해 로그인하는 멤버들의 비밀번호를 강제로 재설정하도록 할 수 있습니다.<br>

[장치 설정]<br>

* 파일 다운로드<br>
  데스크톱과 모바일 앱에서 파일 다운로드 허용 여부를 제어할 수 있습니다.<br>
  데스크톱 : 지정된 IP 에서 접속하는 경우에만 파일 다운로드를 할 수 있도록 설정할 수 있습니다. (이미지 미리보기의 경우 Blur 처리 됩니다)<br>
  모바일 : 모바일 기기에서 다운로드 하지 못하도록 차단할 수 있습니다.<br>
[Slack에서 파일 다운로드 및 메시지 복사 차단](https://slack.com/intl/ko-kr/help/articles/360016181794-Slack%EC%97%90%EC%84%9C-%ED%8C%8C%EC%9D%BC-%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C-%EB%B0%8F-%EB%A9%94%EC%8B%9C%EC%A7%80-%EB%B3%B5%EC%82%AC-%EC%B0%A8%EB%8B%A8) <br>


* 모바일 기기에서 메시지 복사하기<br>
  멤버들이 Slack 모바일 앱에서 메시지를 복사할 수 있기 때문에, 데이터 유출 방지를 위해 필요시 이 기능을 비활성화할 수 있습니다.<br>
  모바일 앱에서 복사를 차단합니다.<br>
[Slack에서 파일 다운로드 및 메시지 복사 차단](https://slack.com/intl/ko-kr/help/articles/360016181794-Slack%EC%97%90%EC%84%9C-%ED%8C%8C%EC%9D%BC-%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C-%EB%B0%8F-%EB%A9%94%EC%8B%9C%EC%A7%80-%EB%B3%B5%EC%82%AC-%EC%B0%A8%EB%8B%A8) <br>

* 탈옥 또는 루팅된 기기<br>
  탈옥된 디바이스(iOS) 나 루팅된 디바이스(Android)인 경우 Slack 앱을 사용하지 못하도록 설정할 수 있습니다. (EMM 미사용시만 적용)<br>
[탈옥 또는 루팅된 모바일 장치가 Slack에 액세스하지 못하도록 차단](https://slack.com/intl/ko-kr/help/articles/360042097113-%ED%83%88%EC%98%A5-%EB%98%90%EB%8A%94-%EB%A3%A8%ED%8C%85%EB%90%9C-%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%9E%A5%EC%B9%98%EA%B0%80-Slack%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EC%A7%80-%EB%AA%BB%ED%95%98%EB%8F%84%EB%A1%9D-%EC%B0%A8%EB%8B%A8) <br>

