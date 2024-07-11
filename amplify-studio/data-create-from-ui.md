# Data Create from UI

Figma 디자인 파일에서 생성된 UI 컴포넌트 중 아직 사용하지 않은 컴포넌트가 있습니다. PostForm인데요.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

PostForm 설정 화면이 열리면 Elements 트리에서 _PostForm > Buttons > PostButton 요소를 볼 수 있으므로 클릭합니다._ 그러면 오른쪽 메뉴에 "Set an onClick action"이 표시되므로 거기에서 "Set onClick action" 버튼을 클릭합니다.

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

onClick 속성의 action에는 Auth 관련 함수가 포함되어 있는데 여기서는 SocialPost 데이터를 게시물로 생성하고자 하므로 아래로 스크롤하여 _Data > Create를 선택합니다._

<figure><img src="../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

_Data > Create 를_ 선택하면 Model로 생성할 데이터 모델을 선택하게 되므로 Model은 SocialPost를 선택합니다.

모델을 선택하면 "Model filed names"이라는 양식이 나타납니다.

Data 생성 시 입력되는 값을 설정하는 양식입니다. 메시지의 경우 _"입력에서 값 선택" > TextField 를_ 선택합니다 .

replyCount, crossPostCount, likesCount는 게시물 데이터 생성 시 0이 되므로 고정값으로 0을 입력합니다. 작성자를 위한 간단한 구현으로 로그인한 사용자의 이름을 _CurrentUser > email_ 으로 설정합니다 .

위와 같이 설정하면 입력 결과는 아래 화면과 같이 됩니다.

<figure><img src="../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

## React App에 구성요소를 업데이트하기

Cloud9으로 이동하여 amplify pull 명령을 실행합니다.

```cmd
amplify pull
```

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

_그리고 src > App.js_ 에 있는 코드를 아래 코드로 다시 작성합니다.

```js
import './App.css';
import { Amplify } from 'aws-amplify';
import { NavBar, SideBar, SocialCollection, PostForm } from './ui-components'; // /* <-- Add "PostForm" */
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
            <PostForm/>  
          </Flex>
        </Flex>
      </Flex>
    </div>
  );
}

export default withAuthenticator(App);


```

코드 변경 완료 후 미리 보기 화면에서 변경 사항이 반영되었는지 확인합니다.

미리보기 화면 우측에 PostForm이 추가된 것을 확인할 수 있습니다.

TextField에 메시지를 입력하고 게시 버튼을 클릭합니다.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

로그인 아이디로 게시된 메시지가 중앙의 타임라인 상단에 표시되면 구현이 성공한 것입니다!

\
