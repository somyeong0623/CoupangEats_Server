#  📌 프로젝트 소개
> 2주동안 클라이언트(Android) 1명, 백엔드(Spring boot) 2명이 진행한 쿠팡이츠 앱 클론코딩 프로젝트 입니다. 저는 백엔드를 담당하였습니다.
> 
> 진행 기간 : 2022.5.21~2022.6.2
</br>


## 🔫 Skills
- Nginx
- SpringBoot, Spring Security(JWT)
- MySQL
- AWS
  - EC2(ubuntu)
  - RDS
- ETC
  - 문자 인증 (coolSMS)
  - Kakao Login  
 </br>
 

## ✏️ ERD 설계
<img width="749" alt="image" src="https://user-images.githubusercontent.com/69009355/173038067-cb6e7468-8f7d-46e1-923a-37e12e6210b3.png">
 </br>
 
## 📁 명세서
https://docs.google.com/spreadsheets/d/12NbyQjtQOgHWWXliXaRoaPF-h8EOUAruAxuXhAhKCbo/edit#gid=1732779101
</br>
</br>

## 🌵 개발 우선순위 및 담당 부분
기획 단계에서 다음과 같이 우선순위를 정하였고, 개발하면서 놓친 api가 있으면 추가하여 순위를 조절하면서 진행하였습니다. 저는 회원 관련 api, 주소 관련 api, 카테고리 및 검색 관련 api, 즐겨찾기 관련 api를 담당하였습니다.
<img width="660" alt="image" src="https://user-images.githubusercontent.com/69009355/173106314-819940d3-7350-4db8-a1cd-2e31d45022fc.png">
</br>

## 👩🏻‍💻 개발 일지 
<details>
<summary>개발일지 정리 (2022.5.21~2022.6.2)</summary>
<div markdown="1">

</br>
  
> ## 2022.5.21(토) - 1일차
- 기획서 작성
- ERD 작성 (70% 완료)
  - https://aquerytool.com/aquerymain/index/?rurl=ee5ba43a-8924-45d6-982d-34b96f86392b
  - 비밀번호 : 615ul8
- API 리스트업
  - https://docs.google.com/spreadsheets/d/12NbyQjtQOgHWWXliXaRoaPF-h8EOUAruAxuXhAhKCbo/edit#gid=1732779101
- EC2, RDS 구축 및 연결 확인

> ## 2022.5.22(일) - 2일차
### user 관련 API 
  - 회원가입 API 
  - 로그인 API
  - 회원 정보 수정 API (이름, 이메일, 휴대폰 번호)

> ## 2022.5.23(월) - 3일차
  ### ERD 수정 (90% 완료)
  - StoreCategory, Menu_Image, Store_Image, Menu_Keyword 테이블 추가
  - <img width="1264" alt="image" src="https://user-images.githubusercontent.com/69009355/170168831-f79bb6df-0a67-4d53-8ca9-63331eca7a6c.png">

  ### user 관련 API
  - 아이디 찾기, 비밀번호 찾기, 회원 탈퇴 API, 회원이 작성한 후기 조회 API
  - validation 추가
  
 ## 💡 1차 피드백 내용
  1. ERD 수정  - 메뉴 키워드(메뉴 하위 카테고리) 반영 해야한다.
  - 주문테이블에 데이터를 어떻게 넣을지 고민하기.
  2. 모든 API에 Validation, Transaction 반영하기
    - validation은 DB를 지키는 방식으로. (ex 회원이 50명인 경우, 100번째 회원 조회하는 것 차단)
  3. 위치기반 구현하기
    - 클라이언트로부터 경도, 위도 값 받아와서 DB에 저장
  4. Dummy data 정성껏 넣기
  5. Image의 경우 firbase 또는 S3 사용
    - 이미지를 로컬 저장소에 넣고, 브라우저에 경로 입력하면 이미지가 뜬다.
  6. 클라이언트분께 명세서 잘 전달하기


> ## 2022.5.24(화) - 4일차
- 주소 관련 api 구현: 주소 목록 조회, 추가, 수정, 삭제 
  
### 그 외
- 클라이언트와 로그인/회원가입 연동 확인
- API 리스트업 수정 - 도메인을 users, store, category, order 4개로 최소화 
  - https://docs.google.com/spreadsheets/d/12NbyQjtQOgHWWXliXaRoaPF-h8EOUAruAxuXhAhKCbo/edit?usp=sharing
- 클라이언트 분과의 회의를 통해, 사용자 정보, 주소 관련 API 및 홈화면 조회 API를 우선순위로 정하고, 연동해보기로 함.
  
> ## 2022.5.25(수) - 5일차
- 주소 관련 API 마무리
- 클라이언트 요청에 따라 Address의 detail_address를 Null 허용으로 수정.
- 주소목록 전체조회 말고도 각 주소의 상세정보를 보는 화면도 있기 때문에 주소 상세조회 API 추가.
- 주소 관련 dummay data 추가
- 즐겨찾기 생성, 삭제 API 구현
- 클라이언트 분과 실시간 소통하면서 에러 수정 중.

> ## 2022.5.26(목) - 6일차
- 즐겨찾기 생성, 삭제 API validation 수정
- 즐겨찾기 조회 API 구현
- ERD에 Delivery_Request 테이블 추가 
  - 배송 요청사항 관리 테이블
- Order_Detail 테이블에 user_id 칼럼 추가
- Category 테이블에 category_image_url 칼럼 추가
- 즐겨찾기, 카테고리 연관된 테이블에 dummy data 추가
### 문제 해결
  - 유저 비밀번호/이메일 찾기 에서 GET 메소드임에도 불구하고, request body를 이용해 요청 데이터를 보내는 실수를 저질렀다.
  - request param 방식으로 요청데이터를 보내도록 수정하였고, 클라이언트분과 연동을 확인하였다.

> ## 2022.5.27(금) - 7일차
- 카레고리 목록 조회 API 구현
- 검색 생성 (카테고리 검색) API 구현
- menu 테이블에 menu_img_url 칼럼 추가
- 프렌차이즈여도 가게마다 메뉴 구성이 조금 씩 다른것처럼 가게마다 고유 메뉴를 가진다고 생각해서 Store_Menu 매핑테이블 삭제 하고 Menu 테이블에 store_id 추가
- 주소 상세조회 시 삭제된 주소도 볼 수 있는 버그 수정

> ## 2022.5.28(토) - 8일차
  ### 검색 관련 API
  - 검색 생성, 최근 검색목록 조회, 검색어 삭제, 검색어 전체삭제 API 구현	
  - 인기 검색어 테이블 추가 
  - 즐겨찾기 목록 조회시, 삭제한 북마크도 같이 조회되는 오류 수정


 > ## 2022.5.29(일) - 9일차
 - 검색 관련 API Validation 추가
 - 검색목록 조회시 '인기검색어 목록'도 조회되게끔 반영
 - 카테고리 상세조회 API 구현중

 > ## 2022.5.30(월) - 10일차
 - 사용자 현재 주소 변경 API 구현
 - 즐겨찾기 선택 삭제 API 구현
 - 현금영수증 관련 Table이 필요하여 Cash 테이블 추가
 - 회원의 현재 주소를 나타내는 속성값이 필요하여 Address 테이블에 is_current 칼럼 추가
 - 2차 피드백 이후, 놓친 API들이 있어서 API 리스트업 수정
   - https://docs.google.com/spreadsheets/d/12NbyQjtQOgHWWXliXaRoaPF-h8EOUAruAxuXhAhKCbo/edit#gid=1732779101
  ## 💡 2차 피드백 내용
- 명세서를 정확하게 쓰자. (중요)
- api가 restful하게 잘 되어있는지 항상 생각하자
- 생각 못한 API는 없는지 살펴보자
- API는 ‘클라이언트가 만들 수 있는지’를 기준으로 잡고 구현하도록하자.
- 소셜로그인, 문자인증, 푸쉬알림 등을 구현해보자.

 > ## 2022.5.31(화) - 11일차
 - 검색어에 따른 카테고리 상세 조회 API 구현
 - 카테고리 상세화면 조회 API 구현
 - 홈화면, 마이이츠 화면에 광고 배너를 담을 Ad table 추가
 - 카카오 로그인 (Oauth)

 > ## 2022.6.1(수) - 12일차
 - Question, Notice 테이블 추가
 - Coupon과 User가 다대다 관계이므로 Coupon_User 테이블 추가
 - SMS 휴대폰인증 API 구현
 - Ad 테이블에 광고 url 칼럼 추가
 - 공지사항 조회 API 구현

 > ## 2022.6.2(목) - 13일차
 - 로그아웃 API 구현 및 validation 적용
 - 자동로그인 API 구현 시도
 - 회원 설정정보 변경 API
 - 데이터 및 명세서 정리
 - 최종 API 명세서
    - https://docs.google.com/spreadsheets/d/12NbyQjtQOgHWWXliXaRoaPF-h8EOUAruAxuXhAhKCbo/edit?usp=sharing
 

</div>
</details>
</br>

## 😱 개발 이슈 
<details>
<summary> 개발 이슈 정리 </summary>

</br>

### github 충돌 이슈 해결 
개인 branch에 push하고 github에 merge 하는 과정에서 충돌이 발생하여 merge가 이루어지지 않는 경우가 자주 발생했다.
```
git checkout main
git pull origin main
git checkout somyeong(개인 branch 이름)
git merge main
  ```
해당 코드를 실행 해준 후, 다시 커밋 & 푸쉬 과정을 진행하여 문제를 해결하였다.
#
  
### 서버 중단 이슈 해결
하나의 api 단위로 로컬에서 동작 확인 후, ssh 접속하여 서버 환경에서 다시 빌드하여 snapshot 파일을 실행하는 식으로 개발하였는데, 내가 컴퓨터를 끄면 프론트엔드분이 서버환경에서 test를 진행할 수가 없었다.
 ```
 nohup java -jar build/libs/demo-0.0.1-SNAPSHOT.jar &
 ```
 nohup 명령어를 이용하여 리눅에서 프로세스를 실행한 터미널의 연결이 끊어지더라도 지속적으로 동작 할 수 있도록 해주었다.
#
### 에러 메세지 출력
지금까지 DATABASE_ERROR가 발생했을 때, DB의 어떤 칼럼이 오류인지 몰라서 받아오는 데이터를 전부 sout으로 찍어보면서 힘들게 찾았는데 같이하시는 서버분이 새로운 방법을 알려주셨다 🙂 Provider나 Service에서 해당 함수의 catch문에서 예외메시지를 출력하면 데이터베이스의 어느 칼럼에서 어떤 이상이 있는지까지 자세히 출력해준다.(자바 지식이 부족해서 잘 몰랐다.) 
 ```java
    catch (Exception exception){
    System.out.println("exception.getMessage() = " + exception.getMessage());
    throw new BaseException(DATABASE_ERROR);}
```

#
### port 이미 사용중 에러 해결
```bash
    Web server failed to start. Port 9001 was already in use.
```
  - 9001번 포트를 사용하고 있는데 다음과 같은 오류가  발생하여 해결하였다.
  - 포트 9001에서 실행중인 서버 종료
  ```bash
  우분투 ssh 접속 후 
  sudo netstat -nlp | grep :9001
  kill -15 '해당PID'
  ```

<div markdown="1">
</div>
</details>
</br>




## 🤩 리팩토링 계획
- 기본 CRUD의 반복, sql코드의 반복을 보완하기 위해 JPA를 이용하여 리팩토링
- S3를 통한 이미지 업로드
- interceptor 적용
- 필터 적용 구체화
- 프론트 분과 협업하여 앱 완성도 개선
