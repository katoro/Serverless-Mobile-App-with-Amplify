# Code Commit

이 모듈에서는 웹 애플리케이션에 대한 정적 리소스를 호스팅하도록 AWS Amplify 콘솔을 구성합니다.



이 모듈의 아키텍처는 매우 간단합니다. HTML, CSS, JavaScript, 이미지 및 기타 파일을 포함한 모든 정적 웹 콘텐츠는 AWS Amplify 콘솔에서 관리되고 Amazon CloudFront를 통해 제공됩니다. 그러면 최종 사용자는 AWS Amplify 콘솔에서 노출된 공개 웹 사이트 URL을 사용하여 사이트에 액세스합니다. 사이트를 사용 가능하게 만들기 위해 웹 서버를 실행하거나 다른 서비스를 사용할 필요가 없습니다.

\
code commit 과 연동하기

```
cd ~/environment/my-react-app/
aws codecommit create-repository --repository-name my-react-app
```

git 명령어를 통해 리포지토리에 코드를 등록합니다.

```
cd ~/environment/my-react-app/
git init
git remote add origin codecommit://my-react-app
git push -u origin main

```
