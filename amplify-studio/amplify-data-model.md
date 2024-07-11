# Amplify Data Model

Auth작업을 할때 사용했던 Amplify CLI로 모델링을 할 수도 있지만, Amplify Studio에서도 GUI를 통해데이터 모델링을 할 수 있습니다.&#x20;

Amplify Studio를 열고 왼쪽 메뉴에서 "Data"를 클릭합니다.

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

"Data" 페이지를 열면 "Data Modeling" 제목 아래에 "Add model" 버튼이 있습니다.

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

모델 이름을 SocialPost로 정의하고 아래와 같이 필드를 작성합니다.

| Field name     | Type   | Note                   |
| -------------- | ------ | ---------------------- |
| id             | ID!    | This field is default. |
| message        | String |                        |
| replyCount     | Int    |                        |
| crossPostCount | Int    |                        |
| likesCount     | Int    |                        |
| author         | String |                        |

수정이 완료되면 우측 상단의 "Save and Deploy" 버튼을 클릭합니다. "Save and Deploy" 버튼을 클릭하면 아래와 같은 팝업이 뜨므로 "Deploy" 버튼을 클릭하면 됩니다.

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

데이터 모델을 저장하고 배포하면 다음 화면이 나타납니다. 우선 amplify pull 작업은 나중에 할 예정이니 "Done"을 눌러서 빠져나옵시다.

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

이제 샘플 데이터를 만들어보겠습니다. 좌측상단의 Content를 클릭합시다. SocialPost와 같이 각 데이터 모델에 대한 데이터 관리 페이지가 표시됩니다. "Auto-Generate Seed Data"를 눌러봅시다.

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Auto-generate Seed Data 버튼이 안보이는경우 Actions 드롭다운을 클릭해봅시다.
{% endhint %}

아래와 같이 팝업창이 뜨게 되며, 생성할 갯수와 제약사항을 만들 수 있습니다. 예를 들어 특정 컬럼을 사람이름으로 제한하거나, 도시명으로 제한하는 등의 작업을 할 수 있습니다.

<figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

