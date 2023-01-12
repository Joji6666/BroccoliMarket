# BroccoliMarket

### 🖥 프로젝트 소개

브로콜리 마켓은 자신의 물건을 업로드 하여 판매 게시글을 올릴 수 있고 다른 사람의 물건을 채팅을 이용하여 거래할 수 있는 중고 거래 사이트 입니다. 프론트엔드로는 자바스크립트,제이쿼리를 사용하였으며 반응형 웹은 부트스트랩을 이용하여 구현하였습니다. 백엔드 부분은 파이어베이스를 이용하였으며 파이어베이스의

****Authenticati****를 이용하여 회원가입과 로그인을 구현하였고 데이터베이스로는 ****Firestore**** 를 사용하였습니다.

### **주요 기능**

회원가입과 로그인,로그아웃 기능

웹 사이트에 자신이 판매할 물건 사진과 함께 업로드 하기

업로드 한 게시글 수정,삭제

업로드 된 게시글에 접속해 1:1 채팅 하기

자신이 속한 채팅방 목록 살펴보기

### 시연 영상

[https://youtu.be/YkzjCoHNShY](https://youtu.be/YkzjCoHNShY)

### 🛠사용기술

Front-end :javascript,bootstrap,jquery

Back-end:firebase

### 💡 개발비화

평소 중고 거래를 자주 하는 애용하는 편이며  첫 프로젝트는 중고 거래 사이트를 꼭 만들어보고 싶었습니다.

그래서 실생활에 쓰이는 다른 마켓들의 기능을 최대한 구현하고 싶었습니다.

백엔드 부분의 지식이 얕았던 때라 이를 해결하기 위해 파이어베이스를 사용하였습니다.

가장 애를 먹었던 부분은 채팅창 부분에서 상대방 메세지와 사용자의 메세지를 각각 왼쪽 오른쪽에 보이게 하는 작업이였는데 반나절을 시행착오를 견디면서 uid 값을 이용하여 아주 쉽게 해결할 수 있는 문제임을 알아채고 여러 관점에서 문제를 바라봐야 한다는 것을 느꼈습니다.

해결한 코드

```html
document.querySelectorAll("#" + myUid).forEach((data) => {
                      console.log("data", data);
                      data.style.float = "right";
                    });
                    document
                      .querySelectorAll(`#${myUid}content`)
                      .forEach((data) => {
                        console.log("data", data);
                        data.style.float = "right";
                        data.style.backgroundColor = " rgba(0, 255, 0, 0.5)";
                        data.style.borderRadius = "5px";
                      });
```

처음 배포 후 주변 지인들에게 서비스 사용을 권했는데 여러 피드백을 받았습니다. (회원가입시 빈 값을 제출해도 경고창이 안뜬다, 로그인,회원가입 버튼을 클릭해서만 기능 사용이 가능하다,상세 페이지 이미지가 짤린다 등)

경고창 같은 경우는 if문과 alert 기능을 이용하여 해결했습니다.

```html
if (password < 6) {
              alert("비밀번호를 6자 이상 입력해주세요.");
            }
```

 

input에 enter를 입력하여 작동하게 하는 코드는 구글링을 해서 해결했습니다.

```html
$(".register-form").keypress((e) => {
        if (e.keyCode === 13) {
          var email = $("#email-new").val();
          var password = $("#pw-new").val();
          var name = $("#name-new").val();
          firebase
            .auth()
            .createUserWithEmailAndPassword(email, password)
            .then((result) => {
              console.log(result);
              var userInfo = {
                name: name,
                email: email,
              };
```

문제점들을 개선하고  시각적인 효과 부분을 조금 더 추가하여 다시 배포하였을 때  괜찮은 반응을 얻어냈습니다.

사용자들의 피드백이 얼마나 중요한지 느낄 수 있었습니다.

### 🚧 개선해야 할 점

시각적인 부분을 좀 더 보완/ 1.11 인트로 페이지 키프레임을 이용하여 슬라이드 애니메이션       구현,버튼 에니메이션 효과 추가 1.12 업로딩바 에니메이션  추가

리액트로 프로젝트 전환하기

백엔드 부분 NodeJs,express를 이용하여 구축하기 db는 Mysql를 사용 할 예정

이미지 업로드 부분에서 반복되는 코드들의 수정이 필요하고 이미지 다중 선택 업로드 기능을 구현할 것

또한 이미지 업로드시 스토리지에 업로드시 생기는 에러 때문에 이를 방지하기 위해 setTimeout 함수를 사용했는데 이 점 또한 수정해야 합니다. // async await을 이용해봐야겠다.

수정시 기존에 업로드 했던 이미지 파일 불러오기

타입스크립트 적용하기
