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

##### 파일 구성
##### server.js 파일이 있고
##### route 폴더 안에 gallery.js와 user.js 파일이 있다.

##### server.js의 코드는 다음과 같다.
```
var express = require("express")
var app = express()

// gallery, user
var gallery = require("./routes/gallery")
var user = require("./routes/users")

//uri 요청에 따라 모듈을 분기해준다.
app.use("/gallery", gallery)
app.use("/user", user)
// public 디렉토리 아래에 정적(image, video...etc)파일을 읽어서 넘겨준다.
app.use("/public",express.static("public"))


app.listen(8080, function(){
    console.log('server is running....')
})
```

##### gallery.js의 코드는 다음과 같다.
```
var express = require("express")

var router = express.Router()

// ROOT : /gallery

router.get("/",function(req,res,next){
    res.send("respond from gallery root!!")
});
//exports를 통해서 위에서 정의된 변수에 접근할 수 있게 해준다.
module.exports = router
```

##### user.js의 코드는 다음과 같다.
```
var express = require('express');
var router = express.Router();

/* GET users listing. */
router.get('/', function(req, res, next) {
  res.send('respond with a resource');
});

module.exports = router;
```

##### Powershell에서 node server.js를 입력하면 서버에 연결된다.

##### 브라우저에 localhost:8080/gallery 라고 하면
##### res.send("respond from gallery root!!") 동작

##### localhost:8080/user라고 하면
##### res.send('respond with a resource'); 동작
