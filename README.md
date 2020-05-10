# firebase  
파이어베이스 활용해보기  
--------------------------
(http://myblog-jihwan.web.app)  

  Firebase를 활용한 웹사이트 만드는 연습을 해보기로 했다.  
  
  제일 처음 할 것  
    1. 연결할 html 파일 만들기  
    2. Firebase 프로젝트 생성하기 ( 미리 하는것이 처음에는 편하다. )
    3. 내 컴퓨터에 프로젝트 파일들을 저장할 빈 폴더 생성 ( firebase 프로젝트의 여러 파일들을 저장할 root )
    
  Firebase 프로젝트를 생성한 후 Hosting 탭을 선택한다.    
  시작하기를 누르면 cmd 창에서 내려야할 명령을 순서대로 알려준다. 
  
  위의 3번에서 생성한 폴더에서 cmd 창을 열어준다.
  ( 파일 탐색기로 해당 폴더에 들어간 후 폴더 주소창에서 "cmd."를 입력한 후 Enter하면 해당 폴더에서 cmd창을 실행할 수 있다.)  
  
      npm install -g firebase-tools  
      
  위 명령을 통해 firebase의 tool들을 최신 파일로 업데이트 혹은 설치해준다.  
  
      firebase login  
  
  위 명령을 통해 firebase의 콘솔에서 프로젝트를 생성할 당시 로그인 했던 아이디로 로그인 해준다.
  
      firebase init  
  
  이 명령을 시행하면  
  
      Are you ready to proceed?  
  
  라는 질문을 하고 Y로 응답을 하면 firebase를 초기화 및 시작한다.  
  그리고 Project Setup을 한다.  
  
      ( ) Database: Deploy Firebase Realtime Database Rules  
      ( ) Firestore: Deploy rules and create indexes for Firestore  
      ( ) Functions: Configure and deploy Cloud Functions  
      ( ) Hosting: Configure and deploy Firebase Hosting sites  
      ( ) Storage: Deploy Cloud Storage security rules  
      ( ) Emulators: Set up local emulators for Firebase features  
  
  테스트하기 위한 프로젝트이므로 모든 항목을 선택한다. (a키 입력) 
  (Hosting만 선택해도 무관)  
  (각 항목을 선택하기 위해서는 스페이스바를 누른다)  
  ** 예외상황 발생 (Hosting만 할 경우 발생하지 않는다)
    - firebase 콘솔에서 Database를 선택한 후 Cloud resource location을 먼저 설정해야한다.
  
  항목을 선택하고 Enter를 누르고 첫번째 항목인 존재하는 프로젝트를 사용한다고 선택해준다.  
  (이 과정에서 새로운 프로젝트를 생성하거나 다른 항목을 선택할 수 있다.)  
  ** 예외상황 발생 (만약 여기서 예상치 못한 Error가 발생한다면 이미 로그인 되어있던 경우에 취할 수 있는 방법)  
    1. firebase logout -> firebase login 으로 재로그인한다.
    2. 혹은 firebase login --reauth 로 로그아웃하지 않고 재로그인 할 수 있다.
  
  이후 기본으로 설정되어있는 rule에 대해 모두 enter를 누르면서 설치 및 진행시킨다.
  
  모든 과정이 끝난 후 
  
       firebase deploy  
  
  위 명령을 수행하면 선택된 firebase project를 성공적으로 hosting 하게 된다.  
  
  hosting을 성공적으로 마치게 되면 url을 보여주는데 해당 url로 접근하면  
  
      Welcome  
    Firebase Hosting Setup Complete  
    You're seeing this because you've successfully setup Firebase Hosting. Now it's time to go build something extraordinary!  

  위와 같은 메시지를 확인 할 수 있다.  
  
  첫 Hosting을 끝냈다면 다음 단계로 나아 갈 수 있다.  
  
  // Realtime Database 등 다른 것을 이용하기 위해서는 Web, Android, ios 등 각자 필요한 조취를 각 앱에서 취해야한다.  
  // 이 때 sdk를 잘 이용한다면 firebase 에서 제공하는 메소드를 통해 쉽게 접근 가능하다.  
  
  나는 최근 공부한 html, css, js를 활용하여 최소한의 기능을 갖춘 블로그를 만들어보기로 했다.  
  
  만약 이미 만들어진 web app을 hosting 하려한다면 위 과정을 진행한 후 public 폴더에 파일들을 넣어준 후
  
      firebase deploy  
    
  명령을 처음 만들었던 폴더에서 cmd창을 통해 명령을 내려주면 재배포할 수 있다.  
  (물론 처음부터 연결하는 것도 가능하다.)  
  
  만약 최초 url인 "프로젝트ID.web.app의 url" 이 맘에 들지 않는다면
  firebase.json의 파일에서  
  
      hosting {  
          ...  
          site: "수정할 부분";  
          }  
          
  을 수정 혹은 추가하면 된다.
