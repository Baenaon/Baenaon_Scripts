## Django-react 배달비 공유 웹 서비스 플랫폼 🔥

<br>

### ***Introduction*** ✔

<hr>

#### Summary 🔽
> - Project 소개
>   - 배나온 (배달비 나눔 온라인 커뮤니티)
>   - JWT 기반 회원가입, 로그인 기능 구현
>   - 게시판 웹 애플리케이션
>  
> - BACKEND(Djagno Authentication Server)
>   - Django를 이용하여 회원, 게시판 정보 저장용 REST API 서버 구현
>   - JWT를 이용하여 OAuth 2.0 Auth 프로토콜 기반으로 Authentication 및 Authorization 구현
> 
> - FRONTEND(React Webapp Client)
>   - React를 이용하여 로그인 및 회원가입, 게시판 CRUD 서비스용 Web App구현

### Requirments 🤔
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

### Backend End-points 1️⃣
> Resource modeling(수정 예정)
> - 회원가입 및 로그인 관련 API
> 
>   |  HTTP |  Path |  Method |  Permission |  목적 | request data(frontend) | response data(backend) |
>   | --- | --- | --- | --- | --- | --- | --- |
>   |**POST** |/api/user/signup|CREATE| AllowAny |사용자 회원가입| JSON { "email", "nickname", "password", "address" } | { "email", "nickname", "password", "address" } |
>   |**POST** |/api/user/signin|NONE| AllowAny |사용자 로그인, access_token 생성 및 반환| JSON { "email", "password" } | { "access_token" }, HTTP_200_OK |
> 
> 
> - 게시판 리소스 관련 API
> 
>   |  HTTP |  Path |  Method |  Permission |  목적 | request data(frontend) | response data(backend) |
>   | --- | --- | --- | --- | --- | --- | --- |
>   |**GET** |/api/posts/|List| AllowAny |게시글 목록 확인| None(아무것도 필요없음) | { "id(post)", "title", "writer", "created_at", "view_count", "comments_count" } |
>   |**GET** |/api/posts/<int:pk>/|Retrieve| Access_token or ReadOnly |게시글 하나 확인(Detail)| None(그러나 path에 post의 id를 입력해야함) | { "id"(post), "title", "writer", "content", "view_count", "updated_at", "comments": [ { "user, "content", "created_at", "updated_at" },  { "user, "content", "created_at", "updated_at" } ...} ]
>   |**POST** |/api/posts/create/|CREATE| Access_token |게시글 생성| { "title", "content", (?)"Authorization : Bearer "Access_token" } | { "title", "content"} |
>   |**POST** |/api/posts/<int:pk>/comments/create|CREATE| Access_token |게시글 생성| { "content", (?)"Authorization : Bearer "Access_token" } | {"content"} |
>   |**PUT**  |/api/posts/<int:pk>|UPDATE| Access_token |자신의 게시글 수정| {"title", "content", (?)"Authorization : Bearer "Access_token" } |  { "id"(post), "title", "writer", "content", "view_count", "updated_at", "comments": [ { "user, "content", "created_at", "updated_at" },  { "user, "content", "created_at", "updated_at" } ...} ]
### ERD 🏳

![image](https://user-images.githubusercontent.com/87630540/186983541-2726b055-8606-44f0-8eb1-4e62df0cead1.png)
