# React UI with API Gateway, Lambda

이제 버튼하나를 추가해서 API Gateway에서 제공하는 path를 호출해 보겠습니다.



App.js를 아래와 같이 변경해줍니다. API Gateway에서 새로 생성된 api 이름으로 apiName값을 설정해주어야합니다.

```
import * as React from 'react';
import { Amplify } from 'aws-amplify';
import '@aws-amplify/ui-react/styles.css';
import { post, get } from 'aws-amplify/api';

import { withAuthenticator } from '@aws-amplify/ui-react';

import awsExports from './aws-exports';
Amplify.configure(awsExports);


async function postTest() {
  try {
    const restOperation = post({
      apiName: 'api1546f816', // API Gateway Name!
      path: '/test/value', // path
      options: {
        body: {
          message: 'My Message'
        }
      }
    });

    const { body } = await restOperation.response;
    const response = await body.json();

    console.log('POST call succeeded');
    alert(response);
  } catch (e) {
    console.log('POST call failed: ', e);
  }
}

async function getTest() {
  try {
    const restOperation = get({ 
      apiName: 'api1546f816',// API Gateway Name!
      path: '/test/val1' 
    });
    const { body } = await restOperation.response;
    const response = await body.json();
    console.log('GET call succeeded: ');
    alert(response);
  } catch (e) {
    console.log('GET call failed: ', e);
  }
}


function App({ signOut, user }) {
  return (
     <div className='App'>
          <h1>Hello {user.username}</h1>
          <button onClick={postTest}>postTest</button>
          <br/>
          <br/>
          <button onClick={getTest}>getTest</button>
          <br/>
          <br/>
          <button onClick={signOut}>Sign out</button>
     </div>
  );
}

export default withAuthenticator(App);
```

버튼을 누르면 아래와 같이 동작하게 됩니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 2.41.41.png" alt=""><figcaption></figcaption></figure>

실제로 Lambda 함수가 호출되었는 Cloudwatch를 통해서도 확인할 수 있습니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 2.42.31.png" alt=""><figcaption></figcaption></figure>





