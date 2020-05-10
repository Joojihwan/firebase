# firebase
=====================
파이어베이스 활용해보기
--------------------------

  Firebase를 활용한 웹사이트 만드는 연습을 해보기로 했다.  
  
  제일 처음 할 것  
    1. 연결할 html 파일 만들기  
    2. Firebase 프로젝트 생성하기 ( 미리 하는것이 처음에는 편하다. )
    
  Firebase 프로젝트를 생성한 후 Hosting 탭을 선택한다.    
  시작하기를 누르면 cmd 창에서 내려야할 명령을 순서대로 알려준다.  
  
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
  (각 항목을 선택하기 위해서는 스페이스바를 누른다)  
  
  항목을 선택하고 Enter를 누르고 첫번째 항목인 존재하는 프로젝트를 사용한다고 선택해준다.  
  (이 과정에서 새로운 프로젝트를 생성하거나 다른 항목을 선택할 수 있다.)  
  
  이후 기본으로 설정되어있는 rule에 대해 모두 enter를 누르면서 설치 및 진행시킨다.
  
  모든 과정이 끝난 후 
  
       firebase deploy  
  
  위 명령을 수행하면 선택된 firebase project를 성공적으로 hosting 하게 된다.  
  
  hosting을 성공적으로 마치게 되면 url을 보여주는데 해당 url로 접근하면  
  
      Welcome  
    Firebase Hosting Setup Complete  
    You're seeing this because you've successfully setup Firebase Hosting. Now it's time to go build something extraordinary!  

  위와 같은 메시지를 확인 할 수 있다.
  
  첫 Hosting을 끝냈다.
