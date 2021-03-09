# Index of JavaScript

* [async 메소드](#async-메소드)
* [defer 메소드](#defer-메소드)
* [guessField 메소드](#guessField-메소드)
* [Math 메소드](#Math-메소드)
* [UI / UX](#UI-/-UX)
* [DOM 객체](#DOM-객체)
* [특이한 문법](#특이한-문법)
* [자바스크립트 내에서 CSS사용](#자바스크립트-내에서-CSS사용)
* [JQuey](#JQuey)
* [Ajax](#Ajax)
* [TIPS](#TIPS)




[뒤로](https://github.com/LeeMooho/TIL)


## async 메소드
async 함수는 자바스크립트가 다운받는 대로 html과 별개로 실행.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)


## defer 메소드
defer는 자바스크립트에 순서에 따라서 실행.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

## guessField 메소드
guessField.focus()
자동으로 커서를 페이지가 로딩되자마자 텍스트 필드에 위치시킨다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)


## Math 메소드
Math.random() -> 0~1사이 랜덤값 <br>
Math.floor() -> 10진수 버림.

## UI / UX
* late binding를 사용하지 않고 자바스크립트를 사용시에는 window.onload = function(){} 함수는 웹브라우저의 모든 구성요소에 대한 로드가 끝났을 때 브라우저에 의해서 호출되는 함수을 사용한다. 혹은 script 태그를 문서 하단에 위치
* prompt('') 사용자가 입력된 값을 리턴 받을 수 있다.
* 새창을 버튼을 클릭하지 않고 그냥 띄어버리면 팝업으로 제한당할 수도 있다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)


## DOM 객체
* document.getElementsByTagName 는 문서 전체에서 태그들을 노드리스트 형태로 저장한다. 그러므로 var ul = document.getElementsByTagName('ul')[0]; var lis = ul.getElementsByTagName('li');같은 형태도 가능하다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

## 특이한 문법
* 함수명(self){내용} 하면 함수를 선언. 스크립트 태그안에 선언해야한다. this를 self로 변경. 사용할 때는 함수명(this)로 사용.
* 매개변수는 타입을 선언할 필요없다.
* ==는 문자1과 숫자 1는 같다고 나오지만 ===는 문자의 타입까지도 비교한다.
* null은 undefined임.
* '문자열' + 변수명 + |n 줄바굼 '문자열' 이런 글을 `문자열 ${변수명} 문자열` 이렇게 바꿀 수 있다.
* console.dir(location); 으로 모든 프로퍼티를 열람가능.
* 기능테스트 사용하려는 javascript기능이 다른 버전, 다른 브라우저에서 지원하는 지 확인하는 것. 만일 지원하지 않는다면 그러한 함수를 직접만들어서 사용해야하지만 속도는 느려짐.

## 자바스크립트 내에서 CSS사용
* 국소적으로 색상을 변경할 떄에는  &#x3C; div style>를 사용해야한다.
* 리턴을 사용하지 않으면 함수안에 css태그를 넣어도 html의 출력에서는 그냥 무시된다.
* HTMLCollection의 목록은 실시간으로 변경된다. 따라서 변경이 생긴후에 재조회할 필요가 없다.

## JQuey
* $('a')는 모든 a라는 태그를 사용하겠다라는 의미이다.
* $('a').css('color',매개변수)
* $()는 jQuery의 함수이다. 이 함수의 인자로 CSS 선택자(li)를 전달하면 jQuery 객체라는 것을 리턴한다.
* late binding

jQuery는 존재하지 않는 엘리먼트에도 이벤트를 등록할 수 있는 놀라운 기능을 제공한다. 그것도 특별한 객체나 메소드를 호출할 필요없이 자동으로 지원. 따라서 jQuery로 굳이 스크립트 뒤쪽에 배치할 필요가 없다.

* console.group('그룹명');  console.groupEnd(); 로 console 출력을 그룹핑해서 보여준다.
* li.map(function(index, elem){} map은 jQuery 객체의 엘리먼트를 하나씩 순회한다. 이 때 첫번째 인자로 전달된 함수가 호출되는데 첫번째 인자로 엘리먼트의 인덱스, 두번째 인자로 엘리먼트 객체(DOM)이 전달된다.
* var items = text.split(',') ,를 기준으로 텍스트를 분리한다. items에 배열의 형태로 저장한다.
* item = item.trim() 공백이나 줄바꿈을 제거하는 함수이다.

## Ajax
* fetch('파일명') 를 사용하여 요청과 응답을 한다
* fetch('파일명').then(fetch후에 실행할 것)
* 익명함수를 사용가능하다. function(){} 로 함수에 이름이 없다.
* response.text()를 이용하여 본문 불러오기.
* response는 서버와의 통신 상태를 나타내며 만일 response.status가 200이면 잘받았다. 404는 파일이 없다.
* document.querySelector('article').innerHTML='들어갈 내용'
* 주소창에 #이름으로 id 이동이 가능하다.
* location.hash 하면 문서의 현재 위치를 표기. 스크립트 태그안에 if(location.hash){fetchPage(location.hash); 로 링크를 받아서 이동시키는 것이 가능해짐.}
* fetch('list').then(function(response){response.text().then(function(text){

document.querySelector('#nav').innerHTML = text;})

]);를 스크립트 태그안에 넣으면 list파일을 id=nav인 태그 사이에 넣는다는 의미이다

## TIPS
* ctrl+space를 누르면 자동 완성 기능 동작. 
* window는 브라우저 창을 제어하는 객체로 open,close 등등이 있다.
* navigator는 브라우저의 정보를 담고 있어 호환성관련한 문제에 대응할 수 있다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)
