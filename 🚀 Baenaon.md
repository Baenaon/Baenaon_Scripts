## Django-react 배달비 공유 웹 서비스 플랫폼 🔥

<br>

## ***Introduction*** ✔

<hr>

### ***Summary*** 🔽
> - Project 소개
>   - 배나온 (배달비 나눔 온라인 커뮤니티)
>   - JWT 기반 회원가입, 로그인 기능 구현
>   - 지역 커뮤니티 활성화를 위한 지역 게시판 구현
>   - 카카오 Map API를 이용하여 지역 게시판과 연동
>  
> - BACKEND(Djagno Authentication Server)
>   - Django를 이용하여 회원, 게시판 정보 저장용 REST API 서버 구현
>   - JWT를 이용하여 OAuth 2.0 Auth 프로토콜 기반으로 Authentication 및 Authorization 구현
> 
> - FRONTEND(React Webapp Client)
>   - React를 이용하여 로그인 및 회원가입, 게시판 CRUD 서비스용 Web App구현

### ***Requirments*** 🤔
> - BACKEND(Djagno Authentication Server)
>   - Python 3.7
>   - Django 3.2.15
>   - Django REST Famework 3.13.1
>   - Django REST Framework JWT 1.11.0
> 
> - FRONTEND(React Webapp Client)
>   - ???
> - DataBase
>   - Mysql 

<br>

### ***IDE*** 🥢
> - BACKEND
>   - Pycharm Professional
>   - VScode
>   
> - FRONTEND
>   - Intellij
>   - VScode

<br>
### Frontend Components

> **Component description**
> 
> - 로그인/회원가입 관련 Components
> 
>   | File Name |  Directory | 목적 |
>   | --- | --- | --- |
>   | LoginForm.js | /components/auth/ |로그인 Form (기존 회원 or 구글 계정)|
>   | SignupForm.js | /components/auth/ |회원가입 Form|
>   | GoogleLoginButton.js | /components/auth/ |Custom Google Login Button 컴포넌트|
> 
> - 라우팅 관련 Components
> 
>   | File Name |  Directory | 목적 |
>   | --- | --- | --- |
>   | AppliedRoute.js | /components/routing/ |토큰 인증 필요 없는 컴포넌트 라우팅|
>   | AthenticatedRoute.js | /components/routing/ |토큰 인증 필요로 하는 컴포넌트 라우팅|
>   | Nav.js | /components/routing/ |메뉴 네비게이션 라우팅|
> 
> - Todo 관련 Components
> 
>   | File Name |  Directory | 목적 |
>   | --- | --- | --- |
>   | TodoList.js | /components/todo/ |서버로 인증 후 받아온 Todo의 CRUD를 수행|
>   | TodoModal.js | /components/todo/ |Todo Create/Update 하기 위한 모달 윈도 컴포넌트|
> 
> - State 및 핸들러 관련 Components
> 
>   | File Name |  Directory | 목적 |
>   | --- | --- | --- |
>   | Login.js | /containers/ |LoginForm에 대한 로직 수행하는 컴포넌트|
>   | Signup.js | /containers/ |SignupForm에 대한 로직 수행하는 컴포넌트|
>   | Home.js | /containers/ |토큰이 유효성에 따라 결과를 렌더링 시켜주는 컴포넌트|
>   
### ***Backend End-points*** 
> Resource modeling(수정 예정)
> 
> 1️⃣ 회원 관련 API
> 
>   |  HTTP |  Path |  Method |  Permission |  목적 |
>   | --- | --- | --- | --- | --- |
>   |**POST** |/api/user/signup|CREATE| AllowAny |사용자 회원가입|
>   |**POST** |/api/user/signin|NONE| AllowAny |사용자 로그인, access_token 생성 및 반환|
> 
> 
> 2️⃣ 게시판 리소스 관련 API
> 
>   |  HTTP |  Path |  Method |  Permission |  목적 |
>   | --- | --- | --- | --- | --- |
>   |**GET** |/api/posts/|LIST| AllowAny |모든 게시글 목록 확인|
>   |**GET**, **PUT**, **DELETE** |/api/posts/<int:pk>/|RETRIEVE, UPDATE, DESTORY| Access_token or ReadOnly OR IsOwner |게시글 하나 확인, 수정, 삭제|
>   |**POST** |/api/posts/create/|CREATE| Access_token |게시글 생성|
>   |**POST** |/api/posts/<int:pk>/comments/create|CREATE| Access_token | 해당 게시글에 댓글 생성|
>   |**GET**, **PUT**, **DELETE**|/api/posts/<int:pk>/comments/|RETRIEVE, UPDATE, DESTORY| Access_token |댓글 확인, 수정, 삭제|
>   |**GET**|/api/posts/search/category/|LIST|AllowAny|카테고리별 검색|
>   
> 3️⃣ 지도 API
> 
>   |  HTTP |  Path |  Method |  Permission |  목적 |
>   | --- | --- | --- | --- | --- |
>   | **GET**|/api/map/|LIST|Access_token or ReadOnly| 사용자와 가까운 default 배달 픽업 장소 확인 |
>   | **GET**|/api/map/<int:pk>/posts/|LIST|Access_token or ReadOnly| 해당 배달 픽업 장소에 적힌 글 확인 |
 
<br>

### ***ERD*** 🏳

> ![image](https://user-images.githubusercontent.com/87630540/189979975-9192d16e-c126-474f-b389-3e92b5a249d3.png)

<br>

### ***process*** 🚀
>
> - 사용자 회원가입
> - 사용자 로그인
> - 사용자 주변 희망하는 배달 픽업 장소 선택
> - 희망하는 배달 픽업 장소에 달린 게시글 보기
> - 공동 배달을 희망하는 게시글에 댓글 달기
> - 게시글 CRUD
> - 댓글 CRUD

### Installation

> **1. Baenaon repository clone**
> 
> ```bash
> git clone https://github.com/Baenaon/Baenaon/
> ```
> **2. backend 환경 설정**
>
> ```bash
> cd backend
> ```
> **2-1 가상환경 생성 및 실행**
>
> ```bash
> python -m venv venv
> venv/Scripts/activate
> ```
>
> **2-2 requirements 라이브러리 설치**
> 
> ```bash
> pip install -r requirements.txt
> ```
>
> **3. my_settings.py파일 생성 후 시크릿 키, 데이터베이스 넣기**
> 
> ![image](https://user-images.githubusercontent.com/87630540/190362704-92f72db2-09aa-4552-b0f7-4ebf542a16f7.png)
> 
> **4. python manage.py makemigrations * python manage.py migrate**
> 


