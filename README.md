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


- ❗ 먼저 clone된 워킹 디렉토리에 들어가야함!!

```bash
cd backend
```
![image](https://user-images.githubusercontent.com/87630540/185682556-05ae634f-3d28-4173-8d05-cbf48a3622ff.png)

<hr>

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


