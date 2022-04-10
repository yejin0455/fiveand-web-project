# 🗳 중고 경매 웹사이트 (3조 팀 프로젝트)
<br>

![main0](https://user-images.githubusercontent.com/70681797/162139074-e141bc66-7f99-403f-9bed-770ae9a9c8f8.png)

## 👩‍👩‍👧‍👧 팀원
- 김세린
- 양서영
- 유지연
- 장유진
- 최예진
<br>

## 🗓 프로젝트 기간
- 2022.01.21~2022.02.08 (19일)
<br>

## 📃 프로젝트 개요
- 중고 물품을 경매 할 수 있는 서비스를 제공하는 웹 어플리케이션
- 상세 페이지에서 경매 진행 상황 및 남은 시간 실시간 조회 가능
- 낙찰 시, 마이페이지에서 물품 결제 기능 구현
<br>

## 🚗 프로젝트 진행방법
- 깃허브를 활용하여 의사소통 진행
  - branch, merge 방법 익숙해지기

- 기능별 역할 분담 
  - 프로젝트 스케치 기능별로 역할을 나누어 진행
  - Frontend, Backend 구분 없이 프로젝트 수행

- 내가 담당한 역할
  - 회원가입
  - 관리자 페이지 / 회원목록, 블라인드 게시물 관리
  - 마이페이지 / 내정보, 내경매, 마음함(위시리스트)
  - 카카오 로그인, 결제 API
  - CSS
<br>

## 🛠 기술 스택
- Java
- JavaScript, HTML5, CSS3
- Oracle, SQL
<br>

### 프로젝트 스케치

![ProjectSketch](https://user-images.githubusercontent.com/70681797/162113061-b28a9c1d-11d1-4ab8-aac5-a28a5daa7bc7.png)

### ERD

![IndexMVC](https://user-images.githubusercontent.com/70681797/162112934-d6c2d460-da35-4874-aecb-d05317ab658f.png)

![AuctionMVC](https://user-images.githubusercontent.com/70681797/162112941-158bc0ee-b8ca-47f4-8c10-8a64c4432787.png)

## 💾 DB

![DBMVC](https://user-images.githubusercontent.com/70681797/162112954-a42f0146-ff75-44de-a6d8-da3bb63c9458.png)

|Table|Column|설명|
|---|---|---|
|FTBL_MEMBER|id : 아이디 <br> pwd : 비밀번호  <br> name : 이름 <br> phone : 핸드폰 번호 <br> email : 이메일 주소 <br> type : 회원 유형 구분 <br> warning_cnt : 누적 경고 수 |회원 정보를 저장하는 테이블|
|FTBL_PRODUCT|pd_no : 경매(제품) 번호 <br> id : 등록한 회원 아이디 <br> pd_name : 제품명 <br> hope_price : 경매 희망가 <br> start_price : 경매 시작가 <br> reg_date : 경매 등록일 <br> due_date : 경매 마감일 <br> pd_simple_info : 제품 게시글 제목 <br> pd_info : 제품 소개글 <br> c_no : 카테고리 번호 <br> view_cnt : 누적 조회수 <br> like_cnt : aa <br> sug_cnt : 누적 응찰수 <br> warn_cnt : 게시글 누적 경고수 |경매(제품) 정보를 저장하는 테이블|
|FTBL_PRODUCT_FILE|no : 이미지 고유 번호 <br> pd_no : 해당 이미지의 경매(제품) 번호 <br> file_ori_name : 오리지널 파일 이름 <br> file_save_name : 파일 저장 이름 <br> file_size : 파일 사이즈 |제품 이미지 파일 정보를 저장하는 테이블|
|FTBL_CATEGORY|c_no : 카테고리 번호 <br> category : 카테고리명 |제품 카테고리 분류를 저장하는 테이블|
|FTBL_AUCTION|a_no : 제시가 기록 고유 번호 <br> pd_no : 해당 경매(제품) 번호 <br> id : 제시한 회원 아이디 <br> sug_price : 제시가 <br> sug_date : 제시한 날짜 |경매 응찰 내용을 기록하는 테이블|
|FTBL_HEART|id : 마음 누른 회원 아이디 <br> pd_no : 마음 누른 경매(제품) |마음 누르기(위시리스트)를 기록하는 테이블|
|FTBL_QNA_BOARD|b_no : 질의응답 문의글 고유 번호 <br> id : 질의응답을 작성하는 회원 아이디 <br> pd_no : 질의응답 할 경매(제품) 번호 <br> title : 문의글 제목 <br> content : 문의글 내용 <br> reg_date : 문의글 등록일 <br> group_id : 부모글 <br> depth : 답글 깊이 <br> pos : 답글 순서 |질의응답 문의글 내용을 담는 테이블|
|FTBL_SOLD|s_no : 낙찰 정보 고유 번호 <br> pd_no : 경매(제품) 번호 <br> sug_id : 제시한 회원 아이디 <br> sug_price : 제시가 <br> sug_date : 제시한 날짜 <br> payment : 결제여부 |경매 최종 낙찰 및 결제 유무를 저장하는 테이블|
|FTBL_BLIND|pd_no : 경매(제품) 번호 <br> id : 등록한 회원 아이디 <br> pd_name : 제품명 <br> hope_price : 경매 희망가 <br> start_price : 경매 시작가 <br> reg_date : 경매 등록일 <br> due_date : 경매 마감일 <br> pd_simple_info : 제품 게시글 제목 <br> pd_info : 제품 소개글 <br> c_no : 카테고리 번호 <br> view_cnt : 누적 조회수 <br> like_cnt : aa <br> sug_cnt : 누적 응찰수 <br> warn_cnt : 게시글 누적 경고수 <br> del_date : 블라인드 처리한 날짜 |블라인드 처리한 경매(제품) 정보를 저장하는 테이블|
<br>

## 🔎 주요기능
### 경매
- 경매 등록, 수정, 검색
- 경매 참여(제시)
- 마음함(위시리스트) 추가, 제거
- 참여한 경매, 낙찰된 경매 조회
- 낙찰된 경매 결제
- QnA문의글-답글 등록
<br>

### 관리자
- 회원 정보 조회
- 부적절한 경매 블라인드 처리
- 회원(판매자) 경고 처리
<br>

## 🖥 화면구성
### 1. 메인화면
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - 제품명으로 검색 가능<br>
  - 카테고리별 상품 조회<br>
  - 최근 등록순, 조회순, 하트순 상품 조회<br>
  - 신규 경매, Top Suggested, 요즘 뜨는 경매, 오늘의 경매, 마감 임박 경매 클릭 시 상세페이지로 이동<br>
</div>
</details>

![main1](https://user-images.githubusercontent.com/70681797/162139078-c80552a5-351f-4dd5-8e0b-82f83a658411.png)

![main2](https://user-images.githubusercontent.com/70681797/162139093-d4c88132-67b9-4731-a352-5677a939532c.png)

<br>

### 2. 회원가입
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - id, 패스워드, 이름, 전화번호, 이메일 입력<br>
  - 키보드 입력을 받을 때 마다 id 중복 체크, ajax 사용<br>
  - 패스워드 이중 확인<br>
  - 모든 칸 입력 후 id, 패스워드 조건 충족 시 가입하기 버튼 활성화<br>
  - 회원가입 성공 시 로그인 페이지로 이동<br>
</div>
</details>

![sign](https://user-images.githubusercontent.com/70681797/162139148-7bf754d1-075d-4cad-97b9-e56c7aef73c2.png)

<br>

### 3. 로그인
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - id, 패스워드 입력<br>
  - 카카오 로그인 API<br>
  - id 또는 패스워드가 일치하지 않을 경우 실패 알림창 뜸<br>
  - 로그인 성공 시 메인 페이지로 이동<br>
</div>
</details>

![login](https://user-images.githubusercontent.com/70681797/162139066-663c524e-ef0a-41a3-85a5-7092ffd069e1.png)

<br>

### 4. 경매 등록
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - 현재 로그인 한 회원의 id 우측 상단에 표시<br>
  - 상품명, 희망가, 시작가, 한줄설명, 상세설명, 카테고리, 마감일 작성<br>
  - 최소 금액은 1000원으로 시작, 500원 단위로 증감<br>
  - 마감일은 최소 현재날짜 +1일, 최대 +20일<br>
  - 사진 최소 1장 이상 선택<br>
</div>
</details>

![reg_auction](https://user-images.githubusercontent.com/70681797/162139142-837ae8ec-bbcc-4dbd-bb7a-feed97022888.png)

<br>

### 5. 경매 참여 (경매 상세페이지)
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - 경매 마감일 실시간 출력<br>
  - 제시가 1000원 씩 증감하여 제시<br>
  - 마음(🤍) 누르면 🖤로 변경 됨, 하단의 🖤+1, 취소 가능<br>
  - 현재 제시가 TOP3 내역 표시<br>
</div>
</details>

![auction](https://user-images.githubusercontent.com/70681797/162139053-89603003-f7ca-4f97-b395-f301c3180bd8.png)

<br>

### 6. QnA 문의글
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - QnA 토글 클릭 시 해당 경매의 문의글 목록 표시<br>
  - 문의글 작성 클릭 시 등록 폼으로 이동<br>
  - 작성자는 현재 로그인 한 회원 id<br>
  - 제목, 내용 입력 후 등록, 전체 삭제 클릭 시 작성한 내용 초기화<br>
  - 문의글 제목 클릭 시 상세 페이지로 이동<br>
  - 답글 클릭 시 하단에 답글 작성 폼 생성<br>
  - 해당 경매의 판매자만 답글 작성 가능<br>
  - 답글 등록 시, 해당 게시글 바로 아래에 [Re] 답글이 추가됨<br>
</div>
</details>

![qna](https://user-images.githubusercontent.com/70681797/162139109-df3369a1-a691-40d7-baa2-aa85016c02c0.png)

![reg_qna](https://user-images.githubusercontent.com/70681797/162139144-6f5bbc5b-3f96-43e1-b3af-74dc3ee0f0b9.png)

![reply](https://user-images.githubusercontent.com/70681797/162139146-2efb563e-0957-43d3-89a6-e7c3a3cd6360.png)

<br>

### 7. 마이페이지
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - MY INFO 클릭 시 내 정보 페이지로 이동(정보 수정, 탈퇴)<br>
  - MY AUCTION 클릭 시 내가 등록한 경매 페이지로 이동(목록 조회, 경매 수정)<br>
  - MY HEART 클릭 시 내 마음함으로 이동(위시리스트 목록 조회)<br>
</div>
</details>

![mypage](https://user-images.githubusercontent.com/70681797/162139104-6c8adbc0-9ad5-4ad4-afb0-01482c42daf8.png)

<br>

### 8. 경매 현황
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - 참여한 경매 중 낙찰된 경매를 보여줌<br>
  - 결제하기 클릭 시 나오는 QR코드 스캔하여 결제<br>
  - 참여한 경매 목록을 보여줌, 클릭 시 상세페이지로 이동<br>
</div>
</details>

![sold](https://user-images.githubusercontent.com/70681797/162139133-f9f8a0bc-1d10-464b-b927-d562c3cb1369.png)

<br>

### 9. 결제
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - 낙찰된 해당 경매의 정보를 받아와 카카오 머니(테스트용 가상 계좌)로 결제<br>
  - 결제완료 후 화면<br>
</div>
</details>

![payment](https://user-images.githubusercontent.com/70681797/162139107-0698d01e-b24f-404b-8c25-0d0968c574ec.png)

![payed](https://user-images.githubusercontent.com/70681797/162139105-0c917260-2586-469a-9d63-74b89c6dd1b8.png)

<br>

### 10. 관리자 로그인
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - 관리자 계정으로 로그인 시 탑메뉴 변경(회원관리, 경매관리)<br>
  - 회원관리 클릭 시 전체 회원 조회 페이지로 이동<br>
  - 경매관리 클릭 시 블라인드된 경매 목록 페이지로 이동<br>
  - 경매 등록 불가<br>
</div>
</details>

![admin](https://user-images.githubusercontent.com/70681797/162139029-19f7753d-f615-4b96-80b8-fc06738d6293.png)

<br>

### 11. 블라인드 게시글
<details>
  <summary> 자세히 보기 </summary>
<div markdown="1">
  - 관리자가 부적절한 경매 글을 블라인드 처리할 수 있음<br>
  - 알림창 확인 클릭 시 해당 게시글은 블라인드 게시판으로 이동하고, 경매 목록에서 조회 불가<br>
  - 블라인드 된 경매 목록 조회<br>
  - 블라인드 된 게시글의 작성자는 경고 1회 받음, 5회 누적 시 로그인 불가<br>
</div>
</details>

![admin_blind](https://user-images.githubusercontent.com/70681797/162139033-e5b808c6-e908-4846-b9b6-c37466113526.png)

![admin_blind_list](https://user-images.githubusercontent.com/70681797/162139035-0dcb9bee-0dda-4e99-bcf2-ae23b08d8982.png)

![warning](https://user-images.githubusercontent.com/70681797/162139140-3609ea19-a7a3-4735-9122-85efd06e0c0f.png)

<br>

## 💫 트러블 슈팅
- 회원가입 시 id가 중복이어도 패스워드가 일치하면 회원가입 성공 처리 되는 문제 (실제 DB에는 insert 되지 않음)
  - 결과 상태를 체크할 플래그 생성 let resultFlag = true-> id 중복 시 resultFlag = false, 사용 가능할 경우 resultFlag = true -> 패스워드 일치 시 resultFlag = true, 않을 경우 resultFlag = false
  - 회원가입 form에 onsubmit="return checkForm()" 속성 추가 -> function checkForm(){}에 if(!resultFlag ) 추가하여 해결

- 관리자가 부적절한 게시글을 어떻게 처리할 것인지에 대한 문제
  - 관리자 마음대로 삭제 보다는 블라인드 게시판을 따로 만들어 보관하는 것으로 채택
  - 기존 테이블(FTBL_PRODUCT)을 복제하여 블라인드 테이블(FTBL_BLIND) 생성 -> CREATE TABLE FTBL_BLIND AS SELECT * FROM FTBL_PRODUCT WHERE 1=2;
  - 블라인드 할 경매에 대한 내용을 블라인드 테이블(FTBL_BLIND)에 추가 -> insert into FTBL_BLIND (PD_NO, ID, PD_NAME, HOPE_PRICE, START_PRICE, REG_DATE, DUE_DATE, PD_SIMPLE_INFO, PD_INFO, C_NO, VIEW_CNT, LIKE_CNT, SUG_CNT)
select * from FTBL_PRODUCT
where PD_NO = ?
  - 기존 테이블(FTBL_PRODUCT)에 있던 경매 글은 삭제 처리 -> delete from ftbl_product where pd_no = ?

<br>

## 💊 보완할 점
- 관리자 페이지 기능 다양화
  - 직접 회원 신고 기능 추가 : 현재 경매 게시글을 통해 1회 경고 가능, 다양한 방법으로 관리 기능 활성화 필요
- 낙찰 시, 낙찰자에게 알람 기능 추가
- 판매 후처리 관련
  - 직거래 vs 택배 : 경매 낙찰 이후 물품 거래 방법 모호
  - 직거래로 하는 경우, 채팅 기능을 추가하여 직거래 위치 조정
  - 택배로 하는 경우, 결제 시 배송지 입력
- QnA  ajax를 통한 비동기식 동작 구현 시도 (현재, JSP 동기식 구현)
