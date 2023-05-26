## 💡개요

- 진행기간 : 2023.05.17(수) ~ 2023.05.25(목)
- 주제 : 사용자 정보를 기반으로 한 예적금 상품 비교 및 추천 사이트
- 서비스명 : ***나우(NOW)***


## 🐽서비스 소개

- 지금 당신의 예적금은 안녕하신가요? 저희는 'NOW'라는 애플리케이션을 통해 예적금 상품 비교 및 상품 추천 서비스를 제공합니다. NOW은 '지'(**知)와 '금'융(金**)의 합성어로, 금융 상품에 대해 알고 싶은 사용자를 위해 제작되었으며, 정확하게 알고 저축해야한다는 메시지를 전달합니다.

- '지금'과 '저금'은 한 끗 차이입니다. '지금'은 당장을 의미하고, '저금'은 돈을 저축하거나 모으는 것을 의미합니다. NOW 애플리케이션을 통해 여러 예적금 상품을 비교하고, 지금 당장 가입할 수 있는 상품을 추천받으세요.


## 📺서비스 화면
![리드미첨부1](https://github.com/I-HYEON/1-Project/assets/122415843/1fdfaae6-7d47-4fe2-a716-380b246b24e8) ![리드미첨부2](https://github.com/I-HYEON/1-Project/assets/122415843/0422e09e-7c0a-4d11-87b6-a58ebc255ee4)


## 🦾주요 기능

- 메인페이지
    - 사이트 첫 화면. 주요 기능에 대한 링크와 간략한 안내를 포함
    - 필수 기능 및 사용자의 관심을 끌 수 있는 콘텐츠(상품 추천, 근처 은행 검색, 커뮤니티 게시판,마이페이지 등의 기능)를 네비게이션 및 퀵 바(quick bar)로 제공
- 회원 관리
    - 회원 가입을 통해 개인 정보를 등록하고, 로그인을 통해 상품 가입, 게시글 작성 및 수정 기능 접근 가능
    - 비밀번호 변경이나 회원 정보 수정 기능 포함
    - 로그인한 사용자의 경우, 마이페이지에서 정보 확인 및 활동 관리.
- 예적금 상품 조회
    - 다양한 은행들의 예적금 상품의 최신 금리 정보를 제공
    - 각 상품의 금리, 기간, 조건 등에 대한 정보를 제공하여 사용자가 가장 유리한 예적금 상품을 선택할 수 있도록 도와줌
- 커뮤니티 게시
    - NOW 회원들 간의 소통과 정보 공유를 위한 공간. 회원들은 금융에 관련된 질문이나 정보를 게시하고, 다른 회원들과 의견을 나눌 수 있음.
- 각종 편의 기능
    - 근처 은행 검색 : 사용자의 위치 정보 및 검색어를 활용, 주변에 위치한 은행을 찾아줌.
    - 환율조회 및 환율 계산 : 사용자가 현재 환율 정보를 조회하고 환율 계산을 할 수 있도록 도움.
    - 금융용어 검색 : 사용자가 금융 용어의 정의와 설명을 검색할 수 있도록 도움.


## 🧬데이터베이스 모델링(ERD)

![Image Pasted at 2023-5-25 11-03](https://github.com/I-HYEON/1-Project/assets/122415843/7edc6319-5d8c-4e6e-b2b3-17f858b1f0bd)


## 🪙금융 상품 추천 알고리즘에 대한 기술적 설명

저희 알고리즘은 ***다양한 사용자의 정보를 기반***으로 현재 사용자의 정보와 유사한 ***조건의 사용자들이 많이 가입한 금융 상품***들을 내림차순으로 보여줍니다.

1. 사용자가 폼에 나이, 취향, 투자성향 등의 정보를 선택하면, 해당 정보는 axios를 통해 Django 서버로 전송되어 API에 전달됩니다.
2. 서버에서는 전달받은 정보를 기반으로 조건문을 활용하여 데이터베이스에서 필터링을 수행합니다. Q 객체를 사용하여 작성된 조건문은 해당 정보와 일치하는 유저들의 가입 상품을 필터링합니다.
3. 초기에는 가입된 유저들의 데이터가 부족하기 때문에, 표본 유저의 수가 충분하지 않을 경우, 최고 우대금리를 기준으로 추천 상품을 내림차순으로 정렬하여 제공합니다.

이렇게 구현된 알고리즘은 사용자의 정보와 다른 유저들의 선택을 비교하여 가장 많은 유저들이 가입한 금융상품을 추천해주는 기능을 수행합니다.


## 🎡작업 

## 5월 17일(수)

- 사이트 전체 기획 및 ERD 작성
- 컴포넌트 구조 생성
- django model 구축
- 업무 분담 및 메인 페이지 기본 틀 구현

**문제점 개선 및 논의 사항**

첫 프로젝트인만큼 프론트와 백의 통신 과정을 전반적으로 이해하고 싶다는 의견이 있었고, 합의 하에 ‘프론트/백’이 아닌 기능별로 업무를 분담. 세부 일정을 미리 정해두지 않고, 해나가면서 진행 상황을 적극적으로 공유하고, 유동적으로 조절할 것으로 합의.

---

## 5월 18일(목)

- 예적금 상품 조회: 금융상품 데이터 조회 페이지 수정
- 회원관리 기능 : django-rest-auth 사용해서 기본 회원 관리 api 구현, custom user 메서드 및 serializer 구현
- 커뮤니티 기능 : 게시물  CRUD 함수 및 vue 작성

**문제점 개선 및 논의 사항** 

1. 예적금 상품 api 호출에 에러가 발생 문제, 회원가입 및 로그인 기능 구현이 늦어지는 문제로, 업무 재분담.(프로필 상세 페이지(이현→정우)/예적금 상품 조회 페이지(정우→성환))
2. 깃 허브 pull시 주의 : 깃 이슈로 회원 관리 기능 코드 일부 날라감.. 

---

## 5월 19일(금)

- 예적금 상품 조회 : 상세 조회 페이지 시작. 인증된 유저의 경우 금융상품 가입 및 취소 가능하도록 구현.
- 회원 관리 기능 : Custom User 모델 필드 모두 받아오는 회원 가입 api 구현. 회원가입 및 로그인 시, user데이터 전부 불러와 store에 저장.(isLogin으로 회원 인증 상태 확인 가능)
- 커뮤니티 기능 : 댓글 생성, 수정, 변경 ,삭제 기능 구현

**문제점 개선 및 논의 사항** 

1.  회원가입 기능 구현도중 db에 데이터가 default값으로 저장됨 → serializer 내부 메서드 수정.
2. 금융회사 이미지 출력시 동적 경로 오류 → require 사용.

---

## 5월 20일(토)

- 예적금 상품 추천 : 추천 알고리즘 구현
- 가까운 은행 검색 : 카카오 지도 api 호출 후 지도 생성 및 마커 구현. 현재 사용자 위치 파악 api 사용.
- 커뮤니티 기능 : 게시글의 좋아요와 상품에 대한 댓글 기능 구현

**문제점 개선 및 논의 사항**
1. 검색 기능 구현 중, 현재 위치 파악 안돼서 사용자 불편 있을 수 있다는 의견 → geolocation api 사용해서 좌표 파악 후 활용
2. 금융상품 추천 알고리즘 구현 과정에서 복잡한 조건문 요구 → Q 사용.

---

## 5월 21일(일)

- 회원 관리 기능 : User model 에서 email 필드 사용 시도 했으나 실패. 다시 되돌리고 내일부터 기본 기능으로 변경 기능 구현 예정
- 회원 프로필(마이페이지) : 구현 시작
- 예적금 상품 추천 : 기존 알고리즘 수정
- 사전 검색 기능 : API 호출로 검색 및 결과 불러오기 구현

**문제점 개선 및 논의 사항**

1. 금융상품 추천 과정에서 충분한 자료(더미데이터)가 없을 경우, 최고 금리로 정렬하자는 아이디어.
2. 사용자가 더 많은 정보를 알고 싶을 때 사용할 수 있는 검색 기능 추가하자는 아이디어 → 검색 api 찾아보고, 사전 검색 이용 가능할 것으로 판단해 기능 추가

---

## 5월 22일(월)

- 회원관리 기능 :
    - 회원정보변경, 비밀번호변경, 회원탈퇴변경 기능 구현
    - 회원 프로필 페이지 구현

**문제점 개선 및 논의 사항**

1. 회원정보 관련 local storage에 저장하는 것 보안이 취약함 → 문제 해결 필요(session storage 논의 중)
2. 회원탈퇴시 해당 유저를 DB에서 DELETE하면 on_delete = models.CASCADE로 연관된 관계의 모델도 삭제되는 문제 → isActive 필드를 활용하면 될 것으로 보임
3. 회원 정보 변경시 username의 unique속성으로 인해 put요청 시 유저네임을 변경하지 않으면 저장이 거절되는 문제 발생. patch로 메서드 변경하여 일부분만 변경하도록해 해결

---

## 5월 23일(화)

- 사이트 디자인 시작 : 디자인 상의 컨셉 상의
    - 메인 페이지 틀 수정 및 컴포넌트 재생성
    - 회원관리 기능 관련 페이지 css
    

**문제점 개선 및 논의 사항**

1.  vue 컴포넌트에서 style 태그에 css를 정의했을때, 전역에 적용됨 → scoped 속성을 추가
2. 동일 페이지로 router push 하는 경우 에러발생

---

## 5월 24일(수)

- 전체 폰트 및 색상 통일
- 예적금 상품 조회 및 추천 기능 css : 카드 컴포넌트 디자인
- 게시글, 댓글에 대한 css 규격 통일

 **문제점 개선 및 논의 사항**

컴포넌트 개수가 급증 but 미리 폴더 구조를 구조적으로 만들어두지 않아 어려움 있음. → 현 상황에서 수정이 어렵다고 판단, 폴더 구조를 새로 만들지는 x

---

## 5월 25일(목)

- 사용자 편의 목적 및 추가 확장 고려해 ‘환율 조회 및 계산’ 기능 추가
- 예적금 상품 추천 : 기존 알고리즘 + 최고 우대 금리 정렬 구현
- 사이트 전반적인 css 세부사항 조정 및 오탈자 확인

**문제점 개선 및 논의 사항**

1. 회원 인증 기능에서 사용자가 잘못된 정보 입력 시 사용자에게 알려주는 기능 누락
2. 다른 페이지로 이동이 가능한 요소들 중 cursor가 pointer 되지 않는 부분들 수정 필요

→ 수정 완료

---
## 👨팀원 소개 및 소감

- 서이현
  - 로그인, 로그아웃, 회원가입 회원 관리 기능
  - 가까운 은행 검색(카카오 맵 검색) 기능
  - 사이트 디자인 및 CSS

- 방정우
  - 상세 조회 페이지 리뷰 기능
  - 정보 공유 커뮤니티 기능
  - 회원 정보 수정, 비밀번호 변경, 회원 탈퇴 기능
  - CSS

- 신성환
  - 예적금 상품 조회 및 상세 조회
  - 예적금 추천 알고리즘을 통한 추천 기능
  - 용어 검색 및 환율 정보 조회/계산
  - CSS


### 서이현😊

첫 프로젝트인만큼 정말 열심히 했지만 아쉬움도 많이 남는 프로젝트인 것 같습니다. django와 vue, 파이썬과 자바스크립트 등 4개월 간 열심히 배웠지만 실제로 하나의 서비스를 구현한다는 것이 그 모든 걸 융합하면서도 웹의 통신 과정을 유기적으로 이해하고 있어야 가능한 것이구나를 느꼈습니다. 무엇보다 팀원들이 너무 열심히 해주고 모르는 부분도 잘 알려줘서 힘들지만 계속해서 진행할 수 있었던 것 같아서 고맙다고 말하고 싶습니다! 매일 디스코드에서 소통하면서 프로젝트를 진행한 것이 좋은 결과물을 내는데 기여한 것 같습니다. ‘금융’이라는 주제를 택한 것도, 프론트와 백을 나누기보다 기능별로 업무를 분담한 것도, 비교적 어려울 줄 알지만 그만큼 많이 경험해보고 싶어서 도전하게 되었는데 많이 공부할 수 있었던 기회였습니다.

### 신성환🙂

처음 '금융상품추천사이트'를 제작하라는 기준이 매우 모호하여 많은 고민이 되었습니다. 따라서 처음부터 계획을 세우기보다 애자일 방법론을 채택하여 매일 계획, 검토하는 방식으로 진행했습니다. 그 과정에서 본인이 더 잘할 수 있는 부분을 맡고 서로의 부족한 부분을 채워주며 짧은 시간이지만 빠르게 완성할 수 있었습니다.
구현하는 과정에서 다중 조건 필터를 위해 Q를 사용하거나, Serializer에 field를 추가로 작성해 본 것이 이번 프로젝트에서 크게 기억에 남습니다. 예비군만 아니었으면 조금 더 신경을 써 UI/UX 부분에 시간을 투자하고 사전 API가 아닌 인공지능 API를 활용하여 완성도를 더 높일 수 있었을 거라 아쉬움도 있습니다.

### 방정우😲

처음 들어왔을 때는 제가 프로그래밍 언어를 배워서 누군가와 협업하고 소통을 통해 어떤 프로젝트를 진행할줄은 생각지도, 생각할 수도 없었습니다. 당장 배우기에 급급했고, 날마다 새로운 정보를 받아들이기에 벅찼었습니다. 그랬던 제가 첫 프로젝트를 시작하게 되고, 배웠던 내용을 넘어 구현하기 위해 더 새로운 정보를 받아들이게 되는 현재를 보고 있습니다.
다른 사람들보다 배움도 느리고, 이해가 되지않는 내용을 받아들이지 않으려 했지만 친절한 조원 둘과 다른 동료들을 만나서 많은 도움을 받을 수 있었습니다. 제가 작성한 코드가 돌아갈까 반신반의하면서, 조마조마해하면서 밤을 지새기도하고, 그러다 로직이 돌아가면 언제 그랬냐는듯 아주 잠깐이지만 뿌듯함을 느끼기도 했습니다. 이렇게 맞닥뜨리면서 겪었던 고생들을 메모해서 다음에는 개선된 실력으로 프로젝트를 진행하고 싶습니다.
