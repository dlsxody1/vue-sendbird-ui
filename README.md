

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



#### 채팅 내역 불러오기, 실시간 채팅
- 

![채팅내역](https://user-images.githubusercontent.com/62875596/185731967-e526385a-e68f-4378-a099-1ae425c86f4c.gif)

- 채팅 내역 무한 스크롤

![무한스크롤](https://user-images.githubusercontent.com/62875596/185731982-8858be43-29a5-4d27-8dcb-965d11fb7f97.gif)

- 채팅방안의 사용자 변경

![사용자 변경](https://user-images.githubusercontent.com/62875596/185731994-6b8a1a8d-009d-42a5-bd30-1662ab46c853.gif)

- 채널 변경

![채널변경](https://user-images.githubusercontent.com/62875596/185732003-d2b3327b-67ca-479e-8424-e19389528788.gif)

- 


