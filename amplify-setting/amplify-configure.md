# Amplify configure

Amplify CLI를 사용하기 위한 설정 작업입니다. 이 페이지의 작업을 통해 로컬개발환경 혹은 원격개발환경과 AWS Account 를 연동하게 됩니다.

또한 여러개의 AWS Account 를 이용하는 경우에도 이 페이지의 작업을 활용해서 account를 변경하실 수 있습니다.

우선 AWS Console의 IAM에서 사용자를 새로 생성해보겠습니다.

서비스 검색 창에 IAM을 입력하여 IAM콘솔로 이동합니다.

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오전 11.59.34.png" alt=""><figcaption></figcaption></figure>

좌측 탭에서 사용자(user)를 클릭합니다.

![](<../.gitbook/assets/스크린샷 2023-04-11 오후 12.00.34.png>)

우측 중앙의 사용자 추가를 선택합니다.

![](<../.gitbook/assets/스크린샷 2023-04-11 오후 12.02.23.png>)

사용자 이름을 적은 후 다음을 누릅니다. (Console 액세스 권한 제공은 체크하지 않습니다)

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 12.03.04.png" alt=""><figcaption></figcaption></figure>

직접 정책 연결을 선택한 다음 amplify로 검색하여 AdministratorAccess-Amplify 권한을 체크하고 사용자를 생성합니다.

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 12.03.47.png" alt=""><figcaption></figcaption></figure>

생성된 사용자를 클릭하고 보안자격증명 탭을 선택합니다.

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 12.05.17.png" alt=""><figcaption></figcaption></figure>

액세스 키를 기타 사용사례로 생성합니다.

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 12.06.57.png" alt=""><figcaption></figcaption></figure>

생성된 액세스 키를 csv로 저장해둡니다. (액세스 키와 비밀 엑세스 키 값이 필요합니다)

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 12.07.18.png" alt=""><figcaption></figcaption></figure>



이제 다시 Cloud9쉘로 돌아와서 아래 명령어를 수행합니다. (수행하는 위치는 상관없습니다.)&#x20;

```
amplify configure
```

Region을  ap-northeast-2(Seoul) 로 선택한 다음 위에서 생성한 accessKeyId, HiddenKey를 입력합니다. 생성된 프로필 이름은 default로 둡니다.

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 12.08.26.png" alt=""><figcaption></figcaption></figure>

