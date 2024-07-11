# Amplify Auth

아래 명령을 수행하여 Cognito를 연동합니다.

```
cd ~/environment/my-react-app/
amplify add auth
```

어떤 방식의 로그인을 할것인지, 유저네임이나 이메일로 로그인할것인지를 물어봅니다.

Default configuration과 username을 선택합니다. 이후 아래 명령어를 수행하면 AWS 어카운트에 작업한 내용을 반영하게 됩니다.

```
amplify push
```

내부적으로 Cloudformation 을 통해 cognito리소스를 생성하게 됩니다.

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 12.32.32.png" alt=""><figcaption></figcaption></figure>

AWS Console에서 Cognito로 이동하면, 방금 생성된 UserPool 정보가 보입니다. (\~\~\~7133d783)

<figure><img src="../.gitbook/assets/스크린샷 2023-04-11 오후 12.36.33.png" alt=""><figcaption></figcaption></figure>
