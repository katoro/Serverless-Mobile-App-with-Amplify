# Amplify Hosting

다음으로 사용하게 될 [AWS Amplify 콘솔](https://aws.amazon.com/amplify/console/) 방금 git에 커밋한 웹사이트를 배포합니다. Amplify Console은 정적 웹 애플리케이션 코드를 저장할 장소를 설정하는 작업을 처리하고 해당 애플리케이션의 수명 주기를 단순화하고 모범 사례를 활성화하는 데 유용한 여러 기능을 제공합니다.\


Amplify 앱으로 진입해서, 브랜치 섹션에서 **시작하기** 버튼을 클릭합니다.\


<figure><img src="../.gitbook/assets/스크린샷 2024-06-19 오후 1.46.15.png" alt=""><figcaption></figcaption></figure>



Git 공급자를 선택할 수 있습니다. 우리는 CodeCommit에 리포지토리를 생성하였으므로 CodeCommit을 선택합니다

<figure><img src="../.gitbook/assets/스크린샷 2024-06-19 오후 2.00.31 (1).png" alt=""><figcaption></figcaption></figure>



CodeCommit에서 생성한 my-react-app 리포지토리를 선택합니다. 브랜치는 main밖에 없으나, 추후 브랜치를 추가하여 스테이징을 구분할 수도 있습니다!

<figure><img src="../.gitbook/assets/스크린샷 2024-06-19 오후 2.01.12.png" alt=""><figcaption></figcaption></figure>



이제 애플리케이션 백엔드를 배포할 수 있는 권한이 있는 새 서비스 역할을 생성해야 합니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-06-19 오후 2.01.52.png" alt=""><figcaption></figcaption></figure>



<figure><img src="../.gitbook/assets/스크린샷 2024-07-11 오후 4.03.21.png" alt=""><figcaption></figcaption></figure>

**새 역할 만들기** 를 클릭 하고 **Amplify** 가 선택되어 있는지 확인한 **다음 다음 권한** , **다음: 태그** , **다음: 검토** 를 차례로 클릭 합니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-07-11 오후 4.04.35.png" alt=""><figcaption></figcaption></figure>

역할에 새 이름 `amplify-backend-role` 을 지정하고 역할 **만들기** 를 클릭 합니다.



<figure><img src="../.gitbook/assets/스크린샷 2024-07-11 오후 4.09.10.png" alt=""><figcaption></figcaption></figure>

검색 필터에서 을 `amplify-backend-role` 검색하고 역할 이름을 클릭합니다.



<figure><img src="../.gitbook/assets/스크린샷 2024-07-11 오후 4.09.38.png" alt=""><figcaption></figcaption></figure>

**권한** 탭에서 정책 연결을 클릭합니다.



<figure><img src="../.gitbook/assets/스크린샷 2024-07-11 오후 4.10.47.png" alt=""><figcaption></figcaption></figure>

`AWSCodeCommitReadOnly`정책을 검색한 다음 체크하여 **권한 추가** 버튼을 클릭합니다

이 탭을 닫고 AWS Amplify Build 구성 콘솔로 돌아갑니다.



<figure><img src="../.gitbook/assets/스크린샷 2024-07-11 오후 4.11.55.png" alt=""><figcaption></figcaption></figure>

원형 화살표 버튼을 클릭하여 역할 목록을 새로고침하고 위 단계에서 생성된 `amplify-backend-role`역할을 선택합니다.



<figure><img src="../.gitbook/assets/스크린샷 2024-07-11 오후 4.12.22.png" alt=""><figcaption></figcaption></figure>

**다음** 선택후 **검토** 페이지에서 **저장 및 배포를** 선택 합니다.



<figure><img src="../.gitbook/assets/스크린샷 2024-07-11 오후 4.13.01.png" alt=""><figcaption></figcaption></figure>

이 초기 빌드 및 배포 프로세스는 Amplify Console에서 필요한 리소스를 생성하고 코드를 배포하는 데 최대 5분이 소요될 수 있습니다.





완료되면 제공되는 주소로 접속이 가능합니다.

