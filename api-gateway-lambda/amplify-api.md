# Amplify Api

아래 명령을 수행하여 API Gateway, Lambda를 연동합니다.

```
cd ~/environment/my-react-app/
amplify add api
```



가장 처음으로 어떤 방식의 서비스를 사용할것인지 물어봅니다. 우리는 REST방식을 통해 API Gateway를 사용할것입니다. (GraphQL은 AppSync서비스와 통합됩니다)

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 12.10.59.png" alt=""><figcaption></figcaption></figure>

새로 생성될 API Gateway의 이름을 설정하고, path를 추가해줍니다. /test/{value} 라고 지정했습니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 12.12.42.png" alt=""><figcaption></figcaption></figure>

다음으로는 API Gateway 를 거쳐서 호출할 Lambda함수를 생성하는 부분입니다. 함수 이름을 정한 다음 런타임환경을 고르면 됩니다. 여기서는 NodeJS를 선택했습니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 12.12.53.png" alt=""><figcaption></figcaption></figure>



생성되는 Lambda함수의 Blueprint도 몇가지 제공하고 있습니다. 우선은 가장 간단한 Hello World 함수를 생성하겠습니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 12.13.20.png" alt=""><figcaption></figcaption></figure>

왼쪽 경로를 살펴보면 실제 수행될 Lambda함수의 NodeJS 파일이 만들어진것을 볼 수 있습니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 12.14.30.png" alt=""><figcaption></figcaption></figure>

아래 명령을 통해 변경된 사항을 Amplify로 업데이트 해줍니다.

```
amplify push
```

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 12.21.21.png" alt=""><figcaption></figcaption></figure>



AWS 콘솔의 API Gateway를 살펴보면 우리가 amplify를 통해 만든 API가 있는것을 볼 수 있습니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 12.22.05.png" alt=""><figcaption></figcaption></figure>



리소스의 경우도 /test/{value}가 잘 생성되어진것을 볼 수 있습니다. 또한 우리가 amplify를 통해 만든 lambda 함수도 호출되는것을 볼 수 있습니다.

<figure><img src="../.gitbook/assets/스크린샷 2024-06-20 오후 12.23.06.png" alt=""><figcaption></figcaption></figure>

