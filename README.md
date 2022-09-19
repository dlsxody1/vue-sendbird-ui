### 현재 앱 아이디의 기간이 만료되어 프로젝트 실행이 안됩니다.

## **1. 프로젝트 소개**

- 인티그레이션 내 모든 서비스에 탑재되는 웹 채팅 프로덕트입니다.
- 프로젝트 요구사항입니다.

|기능|컴포넌트|설명|
|:---|:---|:---|
|채팅방(루트 컴포넌트)|MessageWidget|• Channel Id, User Id 를 prop 으로 설정 , 올바르지 않은 파라미터 입력시 fallback 메시지|
|메세지 목록|MessageLog|• (입력창 위치에 따라 정렬 방향도 맞춰줘야 함), Infinite Scroll|
|메시지 검색|MessageSearch |• 단순 검색만 (날짜 선택 검색 X), 검색결과 포커스 위/아래 이동|
|메세지 입력창|MessageInput |• 입력창 위치 상단/하단 토글 가능해야 함 |

이외의 파일첨부, 사진 찍어서 보내기 등의 기능이 있지만 제가 맡은 부분은 이것들이었습니다.

### **2. 개발 인원 및 기간**

- 개발기간 : 2022/07/20 ~ 2022/08/11
- 개발 인원

  - 프론트엔드(2명) : 김인태, 김보미
  
### **3. 적용 기술**

- Vue.js 2.0, javascript, sendbird API , notion, slack


### **구현 기능**

- 채팅 내역 불러오기, 실시간 채팅
- sendbird API의 key를 받아서 API에 내장되어 있는 method를 썼습니다.
- SendbirdAction.js 파일의 getInstance로 객체 생성후에 init 메소드를 created 과정에서 호출 후 getMessageList를 호출하는 방식으로 만들었습니다.

![채팅내역](https://user-images.githubusercontent.com/62875596/185731967-e526385a-e68f-4378-a099-1ae425c86f4c.gif)

- 채팅 내역 무한 스크롤
- vue-infinite-scroll이라는 라이브러리를 사용해서 만들었습니다.
- MessageWidget에서 provide를 사용했고, 생성된 message를 자식 객체에게 내려줬습니다.
- 무한스크롤에서는 불러오는 spinner를 보여주기 위해서 setTimeout을 사용해 보여주었고, getMessageList를 호출해 메세지 로그를 보여줬습니다.

![무한스크롤](https://user-images.githubusercontent.com/62875596/185731982-8858be43-29a5-4d27-8dcb-965d11fb7f97.gif)

- 채팅방안의 사용자 변경
- 채널 변경도 같은 원리입니다. userId, nickname, channel 을 parameter로 받는 SenbirdAction.js의 connect라는 함수를 사용합니다
- init이 호출되면 그 안에서 호출되는데 userId, nickname, channel들은 제일 상위 컴포넌트인 App.vue에서 props로 내려주고 @click event로 value들을 변경 해줬습니다.

![사용자 변경](https://user-images.githubusercontent.com/62875596/185731994-6b8a1a8d-009d-42a5-bd30-1662ab46c853.gif)

- 채널 변경

![채널변경](https://user-images.githubusercontent.com/62875596/185732003-d2b3327b-67ca-479e-8424-e19389528788.gif)

 ### **아쉬웠던 점**
 
 - 무한스크롤의 메세지가 계속 같은 메세지만을 불러들여와서 전에 있던 모든 채팅 로그들을 확인할 수 없었습니다.
 - search 할 수 있는 기능을 만들었지만 구조를 바꾸는 과정에서 error가 생겼기 때문에 search 기능을 넣을 수 없었습니다. 또한 검색했을 때 
   채팅 메세지로 focus되는 기능을 만들고 싶었지만 시간관계상 못만들었습니다.
 
 ### **느낀 점**
 확실히 현업과 부트캠프에서 학습하는 것은 다르다고 느꼈습니다. 질문하기 좋은 분위기의 회사였고, 환경도 좋았지만 처음 보는 기술을 사용해서 (vue.js) 
 처음부터 만들어놓은 코드가 아닌 전에 만들어 놓았던 코드를 수정하고 업그레이드를 하는데 어려움이 있었고 회사의 체계가 있다보니 회의 때 정했던 것을 말없이 바꿨다가
 혼난적도 있었습니다. 그러나 굉장히 값진 경험이었습니다. 회의의 중요성을 깨달았고, 어떻게 좋은 질문을 하는지도 생각해보는 시간이 되었으며, 회사가 새로운 기술을 배우기를
 요구하더라도 두려워 하지않고 즐거운 기분으로 임할 수 있을 것 같습니다!


