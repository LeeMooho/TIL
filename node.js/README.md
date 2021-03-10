# Index of Node.js


* [기본 지식](#기본-지식)


## 기본 지식
* var url = request.url의 값은 path 뒤의 /? query string이 저장된다.
* 변수선언 = require('모듈이름') 모듈을 import함.

* response.writeHead(200)은 정상 작동한다. 뒤에 response.end(tempmate);를 붙여 완성.

* response.writeHead(400); response.end('Not found');은 오류 출력

* response.writeHead(301,{Location: 'http://주소'}); response.end() 는 현재 주소는 영원히 바뀌었으니 다음 주소로 리다이렉션한다는 의미.

* response.writeHead(302,{Location: 'http://주소'}); response.end() 는 현재 주소는 임시로 바뀌었으니 다음 주소로 리다이렉션한다는 의미.


* 파일목록 알아내기 -> fs.readdir를 사용한다.

* 개인 서버를 껏다가 켜야지만 변경 파일들이 반영이된다.

* 기본적인 파일의 루트는 프로젝트 최상의 루트이다.

* 기본적으로 비동기이다.

* 함수를 쓰면 return이 있는지 없는지 확인후에 사용한다.

* 콜백은 부모 함수의 리턴이 없고 내부적인 자식 함수를 가지고 이 자식 함수를 호출하면서 사용하는것.

* package는 작은 단위로 돌아가는 프로그램.

* * NPM 패키지가 자동으로 설치된다. npm install pm2 -g하여 pm2를 설치하면 수정할 때만다 껏다켤 필요가 없어진다.

* 사용자가 서버로 정보를 보낼 떄는 다음과 같은 코드가 필요하다.
```
<form action='http://localhost:30000/process_create" method="post"> //post로 하면 query string이 숨겨진다.

<p><input type="text" name="title"

placeholder="title"></p>

<p><textarea name="description" placeholder="title"></textarea></p>

<p><input type="submit"></p>

</form>

 ```

* type=hidden하면 숨겨진다.

* if, while은 객체 취급이 안되지만 function은 객체 취급이 가능하다.


* 모듈은 파일을 js로 만들고 객체를 생성한 후에 마지막에 module.exports= 객체명; 을 선언.

* 임포트는 var module_name = require('.모듈 파일 이름'); 로 불러들임.

* ./ 는 현재폴더, data/../은 data의 부모 디렉터리로 이동


* 입력 정보의 보안의 문제로 var filteredID = path.parse(queryData.id).base; 하면 filteredID의 디렉터리를 확인할 수 없게 된다.

* 출력정보의 보안의 문제로 글안에 자바스크립트를 써놓으면 그 내용이 실행되는 위험성을 가지고 있다. 따라서 자바 스크립트 태그를 삭제하거나 sanitize 시켜서 무효로 만든다.

* npm 사이트에 가면 많은 모듈을 확인할 수 있고 다운로드 횟수를 확인해가며 신뢰성이 있는 모듈인지 확인하고 다운.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Node.js)