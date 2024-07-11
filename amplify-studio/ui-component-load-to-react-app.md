# UI Component load to React App

아래 명령을 수행하여 방금  작업한 UI Library를  로드합니다.

```
cd ~/environment/my-react-app/
amplify pull
```

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

src/ui-components/ 아래에서 Amplify Studio가 생성한 JSX 파일을 볼 수 있습니다. 이 파일에서 각 구성 요소는 @aws-amplify/ui-react의 구성 요소와 기능을 사용하여 구현됩니다. 구성 요소에 대한 유형 정의 파일(xxx.d.ts)도 생성됩니다.&#x20;





amplify pull 명령은 git pull과 유사하게 작동하여 클라우드에서 업스트림 백엔드 환경 정의 변경 사항을 가져오고 해당 정의와 일치하도록 로컬 환경을 업데이트합니다. 자세한 내용은 [여기](https://docs.amplify.aws/cli/start/workflows/#amplify-push)를 클릭하세요.

다음으로 로드해온 컴포넌트들을 활용해서 UI를 재구성해보겠습니다.

App.js를 아래와 같이 수정해줍니다.

```

import './App.css';
import { Amplify } from 'aws-amplify';
import { NavBar, SideBar, Social } from './ui-components';  
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
            <Social/>
          </Flex>
        </Flex>
      </Flex>
    </div>
  );
}

export default withAuthenticator(App);

```

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Figma 디자인 파일에서 가져온 NavBar, SideBar, PostForm를 볼 수 있습니다.

지금까지 우리가 구현한 것은 응용 프로그램의 외형일 뿐이므로 응용 프로그램으로서는 아직 미완성입니다.  다음으로 게시물을 보고 제출할 수 있는 기능을 추가하기 위해 게시물 데이터를 생성합니다.
