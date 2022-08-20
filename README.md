## 팀 모닥불 깃 플로우 🔥

### 1️⃣ 자신의 팀 레포지토리(난 backend)의 fork 버튼을 클릭후 Create a new fork 클릭

![image](https://user-images.githubusercontent.com/87630540/185680073-c1c84ba6-38d7-4d3e-9492-91b6b9e553f9.png)

- github에서 fork란 다른 사람의 프로젝트를 카피하는 것을 의미
- 다리(bridge)라고 생각, original repository와 자신이 copy 한 repository를 연결해준다고 생각하면 좋을 것 같음

<br> 

### 2️⃣ owner를 자신으로 설정하고 Create fork를 하면 내 레포지토리에 팀 레포지토리가 생김

![image](https://user-images.githubusercontent.com/87630540/185680697-6608fdc7-eb04-4b4d-a0bd-89f4cc577cbf.png)

<hr>

![image](https://user-images.githubusercontent.com/87630540/185680996-5d12b178-ac7e-4315-84c3-3a47a427e883.png)

<br> 

### 3️⃣ 이제 fork한 레포지토리를 나의 로컬 저장소(내 컴퓨터의 프로젝트 폴더로) 클론 ㄱㄱ

- 클론을 함 으로써 깃허브(서버 저장소)와 내 TestProject/backend 폴더와의 관계는
- 깃허브(서버 저장소)가 원격 저장소, 내 TestProject/backend가 로컬 저장소임 일단은 이렇게 이해

```bash
git clone <origin 레포>
```


![image](https://user-images.githubusercontent.com/87630540/185681407-c5cdedf9-f007-4077-a267-9a77414d86da.png)

<hr>

![image](https://user-images.githubusercontent.com/87630540/185682127-74029c1c-e8b5-48f1-8d76-6357d977d564.png)

<hr>

![image](https://user-images.githubusercontent.com/87630540/185682234-64efea7f-b44c-4ab5-8f6b-12dea599b899.png)

<br> 

### 4️⃣ 협업을 하기 위해 Upstream 저장소 추가 

🔥다른 사람의 Github 저장소를 Fork한 경우 내 Github 저장소는 origin이 됩니다.
이 때 우리가 처음 fork를 시도한 저장소는 upstream 이라고 부릅니다.
origin과 upstream 모두 remote 저장소입니다. 보통 둘을 구분하기 위해 upstream이라는 명칭을 사용합니다 🔥


- ❗ 먼저 clone한 워킹 디렉토리에 들어가야함!! 

```bash
cd backend
```

![image](https://user-images.githubusercontent.com/87630540/185682556-05ae634f-3d28-4173-8d05-cbf48a3622ff.png)

<hr>

- 중요한 건데 Upstream 레포에 로컬 저장소를 등록해 놔야함 그래야 둘이 연결이 돼서 커밋, 풀을 할 수 있는 것!

```bash
git remote add upstream <팀 레포 url>
```

![image](https://user-images.githubusercontent.com/87630540/185683896-bfde9b4f-38be-43cd-b73b-23555b22b111.png)

<hr>

- remote 저장소와 연결된 거 확인 

```bash
git remote -v
```

![image](https://user-images.githubusercontent.com/87630540/185684059-6ff65b5d-ad4d-41e0-9f6d-8a208855a433.png)

<br>

### 5️⃣ Branch 생성

- 자신의 로컬 저장소에 코드를 추가하는 작업은 branch를 만들어서 진행해야함
- branch를 만들어서 작업하는 이유는 우리가 협업하며 작성한 코드들 또는 작업의 흐름을 관리할 수 있음
- branch를 만들어서 협업 후, branch를 없애기도 함

```bash
# jaebeom이라는 이름의 branch를 생성
git checkout -b jaebeom
```

![image](https://user-images.githubusercontent.com/87630540/185688153-625127b0-ae87-4641-bf2d-67ea33fd13fd.png)

<hr>
<br>

### 6️⃣ 수정 작업 후 add, commit, push

- 이제 작업을 한 뒤 add, commit, push를 해주면 수정한 작업을 반영할 수 있음
- 이때 수정된 내용은 origin repository(우리가 fork를 떠온 repository, 즉 내 깃허브 repo)에 반영됨
- ❗ 주의할 점은 push 진행 시 branch 이름을 명시해줘야 함

```bash
# 스테이징 영역으로 이동
git add .
# 이제 .git(깃 저장소)이 관리 할 수 있도록 함
git commit -m "test"
# origin repo로 반영
# origin repo에도 jaebeom이라는 브런치가 생김 
git push origin jaebeom
```

![image](https://user-images.githubusercontent.com/87630540/185689139-7af2c997-06aa-4563-b5b0-936d2f797a80.png)

<hr>
<br>

### 7️⃣ Pull request 생성

- 수정된 내역이 반영이 되는 걸 볼려고 test2.txt 파일을 추가 시켰슴
- origin repository로 가보면 Compare & pull request 버튼이 활성화가 되어있음

![image](https://user-images.githubusercontent.com/87630540/185689487-598cb049-60e3-48c1-8095-4b44917b7c29.png)

<hr>
- Compare & pull request 버튼을 눌러서 들어간다.
- 해석을 해보자면 
- Upstream repository(backend)에게 "내꺼 수정했으니깐 통합으로 관리 되는 Upstream repository에 반영(pull request)해줘라"

![image](https://user-images.githubusercontent.com/87630540/185690064-02fb53d1-c9ea-429c-9be5-509a5ca9fe65.png)

<hr>
<br>

### 8️⃣ 코드 리뷰 및 Merge Pull Request

- Create pull request 버튼을 누르면 
- 자동으로 Upstream repository로 이동해서 pull request가 온것을 확인 할 수 있다
- 또 comment도 달 수 있음(코드리뷰같은거)

![image](https://user-images.githubusercontent.com/87630540/185690897-a5052212-b3e7-478f-93ae-e73ec3bb320d.png)

<hr>

- 이제 원본 저장소이 pull request를 읽고 작업 여부 또는 변경사항을 확인 후 merge pull request-> confirm merge로 Upstream repository에 수정된 이력을 반영(merge)해줌 

![image](https://user-images.githubusercontent.com/87630540/185691033-ea36c799-557d-4c40-90c8-242171eb5583.png)

<hr>

- test2.txt를 추가시킨것이 잘 반영된 걸 확인 할 수 있슴요

![image](https://user-images.githubusercontent.com/87630540/185691561-c51f472b-44bc-4406-a021-68511f4762b0.png)

<hr>
<br>

### ❗ (추가) 작업한 브랜치를 꼭 삭제 해주고, 후에 작업을 시작할 때는 새로운 브랜치를 만들어서 작업하자 ❗
#### 밑에서 스크린샷에는 (jaebeom) branch로 fetch를 햇지만 upstream에서의 branch는 main하나 이기 때문에 로컬저장소에 main branch로 가져오는거임 그래서 
#### jaebeom branch랑 upstream에서 가져온 변경사항들이랑 


```bash
# 로컬 저장소의 jaebeom 브랜치 삭제
# (main)브랜치로 바꾸고 수행해야함
git branch -d jaebeom 
# 원격 저장소의 jaebeom 브랜치 삭제
git branch --delete origin jaebeom
```


### 9️⃣ origin repository에 Upstream의 변경내용 당겨오기

- 이때 까지 로컬 저장소의 변경 사항을 Upstream repository에 반영하는 것 까지는 했으니깐
- 그럼 fork해 온 Origin repository에도 반영을 해줘야함

![image](https://user-images.githubusercontent.com/87630540/185693210-71117fd6-d9a9-452e-bec2-71bdec315583.png)

<hr>

- Upstream 저장소로부터 'fetch'한다
- fetch upstream은 우리가 contribute를 하기 원하는 프로젝트의 최신 내용을 동기화 하는 거임

```bash
git fetch upstream
```

![image](https://user-images.githubusercontent.com/87630540/185693545-e9ea6de9-5dd4-481b-8fe4-250a94b19563.png)

<hr>

- 로컬 저장소의 main 브랜치로 checkout후 Merge한다.(Checkout은 브런치를 변경해주는 것)
- (Upstream의 변경된 내용들을 취합하는 과정이라고 생각하면 댐) 
- 
```bash
git checkout main
git merge upstream/main
```

![image](https://user-images.githubusercontent.com/87630540/185693899-50c5b9f5-35e2-45ba-9eaa-b32bd069249e.png)

<hr>

- 자신의 원격 저장소인 origin에 반영하려면 git push를 수행한다
- 이렇게 함으로써 Upstream에서 변경되었던 내용을 origin repo로 반영할 수 있는 것이다.

```bash
git push
```

![image](https://user-images.githubusercontent.com/87630540/185694390-73125759-0de6-40f9-ba8b-ff78c4b67105.png)

<hr>

### Conclusion

- Upstream : 일반적으로 사용자가 fork한(The forked)원격 저장소를 의미
- origin : fork를 해서 나의 원격 저장소가 된 repository를 의미
- 즉 origin은 original repository가 아니고 fork repository는 origin이며 forked repository는 upstream이 된다.



## 끝 ~~~~ 🔥🤣🤣🤣😂😝

