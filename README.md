1. express 설치


2. express-generator -g 설치

3. 모듈생성
   express --view=ejs 모듈명 만들 디렉토리
   또는
   express 프로젝트명

4. cd 모듈명 만든 디렉토리 안에서
   npm install

5. 시작
   npm start

   - node_modules 폴더는 Jade 모듈 또는 EJS 모듈과 express모듈이 설치되어 있는 공간, "npm install" 명령어를 사용할 때 생성되는 폴더
- public 폴더는 connect 모듈을 Static 미들웨어를 사용하여 웹 서버에 올라가는 폴더, 이 폴더에 자바스크립트 파일, CSS 파일, 그림 파일 등 리소스 파일을 생성
- routes 폴더는 페이지 라우트와 관련된 모듈, index.js 파일이 있음
- views 폴더는 EJS 파일 또는 Jade 파일과 같은 템플릿 파일을 저장하는 공간
- app.js 파일은 프로젝트에서 중심이 되는 파일,
- package.json 파일은 현재 프로젝트와 관련된 정보아 모듈을 설치하는 데 필요한 내용을 담고 있음

- bin\www : 실행 시 최초 진입점, ( npm start 시 > node \bin\www 와 동일 )
[출처] [node.js] Express 설치|작성자 유니
