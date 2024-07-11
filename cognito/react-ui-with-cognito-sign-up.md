# React UI with Cognito Sign Up

UI Code 적용을 위해 App.js를 다음과 같이 변경합니다. amplify에서 react용으로 제공하는 ui 라이브러리를 통해 손쉽게 회원가입/로그인 모듈을 적용할 수 있습니다.

```
import * as React from 'react';
import { Amplify } from 'aws-amplify';
import '@aws-amplify/ui-react/styles.css';

import { withAuthenticator } from '@aws-amplify/ui-react';

import awsExports from './aws-exports';
Amplify.configure(awsExports);

function App({ signOut, user }) {
    
  return (
     <div className='App'>
          <h1>Hello {user.username}</h1>
          <button onClick={signOut}>Sign out</button>
     </div>
  );
}

export default withAuthenticator(App);
```

아래 명령으로 리액트 앱을 재실행하면 아래와 같은 모듈이 보여집니다.

```
npm run start
```

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 4.33.15.png" alt=""><figcaption></figcaption></figure>

가입절차를 진행하면 이메일로 인증코드가 전송되며, 해당 코드를 인증한 뒤 로그인이 가능합니다.

![](<../.gitbook/assets/스크린샷 2023-04-11 오후 4.35.17.png>)

실제 AWS Console에서도 가입된 유저를 확인해 볼 수 있습니다.

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 9.35.32.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
이것은 매우 간단한 인증 UI이지만 직접 React 컴포넌트로 교체하거나 완전히 호스팅 된 UI를 사용하여 앱으로 다시 리디렉션하는 등 사용자 정의 할 수있는 작업이 많이 있습니다. 자세한 내용은 [AWS Amplify 인증 안내서](https://docs.amplify.aws/lib/auth/getting-started/)의 사용자 지정 섹션을 참조하세요.
{% endhint %}

