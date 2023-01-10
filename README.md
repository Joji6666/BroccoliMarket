# BroccoliMarket

### 🖥 프로젝트 소개

자신의 물건을 업로드 하여 판매 게시글을 올릴 수 있고 다른 사람의 물건을 채팅을 이용하여 거래할 수 있는 중고 거래 사이트 입니다.

### 🛠사용기술

Front-end :javascript,bootstrap,jquery

Back-end:firebase

### 💡 개발비화

평소 중고 거래를 자주 하는 애용하는 편이며  첫 프로젝트는 중고 거래 사이트를 꼭 만들어보고 싶었습니다.

그래서 실생활에 쓰이는 다른 마켓들과 같은 기능을 구현하고 싶었습니다.

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

 

### 🚧 개선점

시각적인 부분을 좀 더 보완해야 될 것 같습니다.

이미지 업로드 부분에서 반복되는 코드들의 수정이 필요하고 이미지 다중 선택 업로드 기능을 구현해야 합니다.

또한 이미지 업로드시 스토리지에 업로드시 생기는 에러 때문에 이를 방지하기 위해 setTimeout 함수를 사용했는데 이 점 또한 수정해야 합니다.
