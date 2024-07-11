# Data Model Binding with UI

만들어진 데이터 모델을 UI에 바인딩 시켜보겠습니다.



## Social Post 설정

UI Library의 Social를 선택후 Configure 버튼을 눌러봅니다.

<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

"Configure" 버튼을 클릭하면 다음 화면이 나타납니다.

이 화면에서 왼쪽의 "Elements Tree"에 표시되는 각 요소에 대해 데이터 바인딩 및 OnClick 등의 이벤트 처리를 추가할 수 있습니다.

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

이제 SocialPost 필드를 Social 구성 요소에 바인딩하겠습니다. 먼저 SocialPost  Author 데이터를 작성자의 텍스트를 표시하는 요소에 바인딩합니다.

**Elements Tree에서 Social > Body > Contents > Header > Info > Author를** 클릭합니다 .

그런 다음 오른쪽 메뉴의 "Bind label to data"에서 "Set text label" 버튼을 클릭합니다.\


<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

그러면 Amplify Studio에 등록된 데이터 모델 데이터를 앞에서 선택한 요소의 레이블 속성으로 바인딩할 수 있습니다.&#x20;

**여기에서 socialPost.author를** 선택합니다. Author 요소의 prop과 값은 아래와 같이 설정되며 SocialPost 샘플 데이터의 작성자는 미리보기 화면에 반영됩니다.\


<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

마찬가지로 SocialPost의 게시 시간을 표시합니다.

**Elements Tree에서 Social > Body > Contents > Header > Info > Timestamp를** 선택 하고 우측 메뉴에서 "Set Text Label"을 클릭합니다.

**표시된 옵션에서 socialPost.createdAt를** 선택하면 게시물 생성 시간이 반영됩니다.

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

레이블을 설정하는 나머지 요소는 다음과 같습니다.

* **Social > Body > Contents > message : socialPost.message**
* **Social > SocialMenu> Reply > ReplyCount : socialPost.replyCount**
* **Social > SocialMenu > CrossPost > CrossPostCount : socialPost.crossPostCount**
* **Social > SocialMenu > Likes> LikesCount : socialPost.likesCount**

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

이제 여러 SocialPost 데이터 표시를 지원하는 Social 구성 요소 모음을 만들어 보겠습니다.

오른쪽 상단에서 CreateCollection을 클릭합니다.

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

그러면 다음과 같은 팝업이 나타납니다.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

이미 채워진 SocialCollection으로 컬렉션의 이름을 지정하고 만들기를 클릭합니다.

<figure><img src="../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

그러면 아래와 같은 화면이 나오며 SocialPost의 여러 샘플 데이터가 Social 컴포넌트에 반영되어 리스트로 출력되는 것을 확인할 수 있습니다.

이 워크숍에서는 이 SocialCollection을 일반적인 소셜 미디어 타임라인 피드처럼 표시하려고 하므로 게시 날짜를 기준으로 내림차순으로 정렬합니다.

오른쪽 메뉴의 정렬 조건 설정에서 Add Sort를 클릭합니다.

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

그런 다음 속성에 대해 SocialPost.createdAt를 선택하고 주문에 대해 내림차순을 선택합니다.

<figure><img src="../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

이제 SocialCollection에 대한 설정이 완료되었으며 애플리케이션에서 설정한 대로 타임라인을 표시할 수 있습니다.



## NavBar 설정

여기에서 사용자 이름과 로그아웃 버튼을 NavBar에 추가해 보겠습니다.

Amplify Studio의 UI 라이브러리 페이지로 돌아가서 NavBar 구성 요소를 선택하고 구성 버튼을 클릭합니다.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

아래와 같이 NavBar의 Elements Tree가 표시되므로 NavBar > RightMenu > UserName을 클릭합니다.

그러면 오른쪽 메뉴에 "Bind Label to Data"가 표시되고 거기에 "Set Text Label"이 표시됩니다.

"Set Text Label"을 클릭합니다.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

소셜 구성 요소를 편집할 때와 마찬가지로 레이블 속성 값을 선택하지만 이번에는 로그인 사용자 이름을 표시하려고 하므로 옵션을 스크롤하여 현재 사용자 정보 이름을 선택합니다.

UserName 문자열은 일시적으로 공백이지만 문제는 없습니다.

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Email만 보이는경우 Email을 선택합니다.
{% endhint %}

다음으로 로그아웃 버튼을 구현합니다.

Amplify Studio는 인증 기능을 쉽게 추가할 수 있도록 만들었지만 인증 관련 처리도 쉽게 구현할 수 있습니다.

Element Tree에서NavBar > Right Menu > SignOutButton을 클릭합니다.

그러면 오른쪽 메뉴에 "Set onClick Action"이 표시되고 거기에 "Set onClick action" 버튼이 있습니다.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

그런 다음 onClick 속성에 대한 작업을 지정할 수 있습니다.

이번에는 로그아웃 기능을 추가하고 싶으므로 인증 > 이 장치에서 로그아웃을 선택합니다.

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

## React App에 구성요소를 업데이트하기

이제  UI 구성 요소 설정을 완료했으므로 Cloud9으로 개발 중인 애플리케이션에 적용해 보겠습니다.

Cloud9을 열고 Amplify로 개발 중인 애플리케이션의 디렉터리를 열고 다음 amplify pull 명령을 실행합니다.

```
amplify pull
```

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

amplify pull이 완료되면 파일 탐색기에서 개발 중인 애플리케이션 디렉토리 아래의 src > App.js를 엽니다.

그리고 App.js를 다음 내용으로 변경합니다.

```js

import './App.css';
import { Amplify } from 'aws-amplify';
import { NavBar, SideBar, SocialCollection } from './ui-components'; // /* <-- From "Social" to "SocialCollection" */
import { Flex, withAuthenticator } from '@aws-amplify/ui-react';
import '@aws-amplify/ui-react/styles.css';
import awsExports from './aws-exports';

Amplify.configure(awsExports);

function App() {
  return (
    <div className='App'>
      <Flex
        direction={"column"}
        alignItems={"center"}
      >
        <Flex
          direction={"column"}
        >
          <NavBar/>
          <Flex
            direction={"row"}
          >
            <SideBar/>
            <SocialCollection/>  
          </Flex>
        </Flex>
      </Flex>
    </div>
  );
}

export default withAuthenticator(App);

```

SocialPost 데이터를 지원하고 Amplify Studio에서 NavBar를 편집하여 크게 변경되었습니다.

이렇게 Amplify Studio를 사용하면 UI 구성 요소의 GUI 기반 편집과 최소한의 코딩으로 쉽게 애플리케이션을 개발할 수 있습니다.

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>
