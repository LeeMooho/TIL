# Index of JavaScript

* [async 메소드](#async-메소드)
* [defer 메소드](#defer-메소드)
* [guessField 메소드](#guessField-메소드)
* [Math 메소드](#Math-메소드)
* [UI / UX](#UI-/-UX)
* [DOM 객체](#DOM-객체)  
* [DOM과 JQuery](DOM과-JQuery)
* [JQuery로 DOM 제어](#JQuery로-DOM-제어)
* [UI/UX](#UI/UX)
* [특이한 문법](#특이한-문법)
* [자바스크립트 내에서 CSS사용](#자바스크립트-내에서-CSS사용)
* [JQuery](#JQuery)
* [CSS](#CSS)
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

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

## UI / UX
* late binding를 사용하지 않고 자바스크립트를 사용시에는 window.onload = function(){} 함수는 웹브라우저의 모든 구성요소에 대한 로드가 끝났을 때 브라우저에 의해서 호출되는 함수을 사용한다. 혹은 script 태그를 문서 하단에 위치
* prompt('') 사용자가 입력된 값을 리턴 받을 수 있다.
* 새창을 버튼을 클릭하지 않고 그냥 띄어버리면 팝업으로 제한당할 수도 있다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

---
## DOM 객체
* document.getElementsByTagName 는 문서 전체에서 태그들을 노드리스트 형태로 저장한다. 그러므로 
```
var ul = document.getElementsByTagName('ul')[0]; var lis = ul.getElementsByTagName('li');
```
같은 형태도 가능하다.
* DOM으로 css를 작성하면 
```var lis = document.getElementsByTagName('li');

for(var i=0; i&lt;lis.length; i++){
lis[i].style.color='red';
}
```
* jQuery으로 작성하면 
```
"$('li').css('color', 'red')" 
```
차이가 난다.
* DOM tree로 알 수 있고 필요한 API를 검색할 떄 유용하다.
* 주의할 것은 li[i]의 값은 해당 엘리먼트에 대한 jQuery 객체가 아니라 DOM 객체라는 것이다. 따라서 jQuery의 기능을 이용해서 이 객체를 제어하려면 jQuery 함수[$()로 감싸야한다]를 이용해야 한다.
```
for(var i=0; i<li.length; i++){

$(li[i]).css('color', 'red');
```

}
* Element 객체의 주요 기능으로는 식별자, 조회, 속성등이 있다.
* 클래스를 String처럼 사용가능하다.
```
var active = document.getElementById('active');

active.className = "important current"; 클래스를 부여.

active.className += " readed"

 

active.classList.add('marked');

active.classList.remove('important');

active.classList.toggle('current'); 등 string처럼 관리가능.
```

* Attribute로 HTML의 태그명으로는 부족한 정보를 부여한다. 
```
t.getAttribute('href')); //http://opentutorials.org 값을 얻는다.

t.setAttribute('title', 'opentutorials.org'); // title 속성의 값을 설정한다.

t.hasAttribute('title'); // true, title 속성의 존재여부를 확인한다.

t.removeAttribute('title'); // title 속성을 제거한다.

setAttribute('class', 'important')와 className = 'important'는 같은 결과를 만든다. 하지만 속성과 프로퍼티값이 다를 수도 있다.
```
[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

# DOM에서의 JQuery
* setAttribute, getAttribute에 대응되는 메소드는 attr이다. 또한 removeAttribute에 대응되는 메소드로는 removeAttr이 있다
* var t = $('#target'); target은 id이다.
* selector context로 범위를 제한하는 방법으로는 아래 방법 둘다 가능하다.
```
$( ".marked", "#active").css( "background-color", "red" );

$( "#active .marked").css( "background-color", "red" );
```
* find를 쓰는 이유는 체인을 끊지 않고 작업의 대상을 변경하고 싶을 때 사용한다.
```
$( "#active").find('.marked').css( "background-color", "red" );

$('#active').css('color','blue').find('.marked').css( "background-color", "red" );
```
[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

---
## JQuery로 DOM 제어
* 노트 선택방법 
    * Node.childNodes자식노드들을 유사배열에 담아서 리턴한다.
    * Node.firstChild 첫번째 자식노드
    * Node.lastChild 마지막 자식노드
    * Node.nextSibling 다음 형제 노드
    * Node.previousSibling 이전 형제 노드

유의할 것은 \n, 공백도 #text로 출력하기 한다.

* 노드의 종류에 따라 정해진 상수가 존재한다.
```
확인법
for(var name in Node){

console.log(name, Node[name]);

}
```

* DOM으로 노드 제어
    * appendChild(child) 노드 추가
    * insertBefore(newElement, referenceElement) 노드의 마지막 자식으로 주어진 엘리먼트 추가. appendChild와 동작방법은 같으나 두번째 인자로 엘리먼트를 전달 했을 때 이것 앞에 엘리먼트가 추가된다.
    * document.createElement(tagname)
    * document.createTextNode(data)
    * target.parentNode.removeChild(target) 삭제 
    * target.replaceChild(a,target.firstChild);

* JQuery로 노드 제어
    * 노드 추가
        * before 태그 밖에서 앞에 추가
        * prepend 태그 안에서 앞에 추가
        * append 태그 안에서 뒤에 추가
        * after 태그 밖에서 뒤에 추가

        ```
        $('.target').before(' <div>before</div>')
        ```

    *  노드 삭제 
        * remove 선택된 엘리멘트를 제거
        * empty 선택된 엘리먼트의 텍스트 노트를 제거
        * replaceAll과 replaceWith는 모두 텍스트 노드를 교체하는 API이다.
        ```
        $('<div>replaceAll</div>').replaceAll('#target1')

        $('#target2').replaceWith('<div>replaceWith</div>');
        ```

    * 노드 복사
        ```
        $('#source').clone().replaceAll('#target1');

        $('#target2').replaceWith($('#source').clone());
        ```

    * 노드 이동
        ```
        $('#target1').append($('#source')); 
        ```

* DOM 과 JQuery 2
    * innerHTML는 문자열로 자식 노드를 만들 수 있는 기능을 제공한다. 또한 자식 노드의 값을 읽어올 수도 있다. 
    ```
    target.innerHTML = "<li>JavaScript Core</li><li>BOM</li><li>DOM</li>"; 
    엘리먼트의 내용은 출력되지 않는다.
    ```
    
    * outerHTML은 자기자신을 포함한 엘리먼트를 처리된다.

    * innerText, outerText

    ```
    alert(target.innerText); 엘리먼트의 내용은 표시되지않는다.

    target.innerText = "<li>JavaScript Core</li><li>BOM</li><li>DOM</li>"; 엘리멘트의 내용까지 그대로 출력된다.
    ```
    * insertAdjacentHTML
     ```
     target.insertAdjacentHTML('객체이름','<li>HTML</li>');
    ```        
    * insertAdjacentHTML의 옵션
        * beforebegin 타겟 엘리멘트와 동등한 레벨로 바로 앞에 입력.

        * afterbegin 타겟 엘리멘트 안에서 가장 앞에 입력.

        * beforeend 타겟 엘리멘트 안에서 가장 뒤에 입력.

        * afterend 타겟 엘리멘트와 동등한 레벨로 바로 뒤에 입력.

    * DATA 조작

        * appendData() "appendData(data)"

        * deleteData() deleteData(start,end)"

        * insertData()

        * subStringData() "replaceData(start,end,data)"

        * replaceData()

    * 생성
        * docuemnt.createTextNode()

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

## UI/UX
* 문서의 margin이나 padding, 높이를 알 수 있는 API로는 getBoundingClientRect
* 뷰포트는 문서의 내용 중 사용자에게 보여주는 영역을 의미한다. 이에 따라서 문서의 좌표가 있고 뷰포트의 자표가 있다. 우리가 위에서 살펴본 getBoundingClientRect는 viewport의 좌표를 사용한다.
* 스크롤의 위치는 pageYOffset을 사용하면 된다. 
* 문서의 좌표는  뷰포트의 좌표에 스크롤된 정도를 더해서 알 수 있다.
* 스크롤 이동은 window.scrollTo(0, 1000)
* 모니터의 크기와 브라우저 뷰포트의 크기를 각각 screen.width 등, window.innerWidth 등으로 알 수 있다.
* 이벤트 삽입 방법은 태그안에 넣는 인라인 방식, 프로퍼티 리스너 방식, 이벤트리스너 사용.
    * 인라인 방식 
    * 프로퍼티 리스너 방식 
    * 이벤트리스너 방식 
    
    
    ```
    <script>
    var t = document.getElementById('target');
    t.onclick = function(){
    alert('Hello world');
    }
    </script>

    <script>
    var t1 = document.getElementById('target1');
    var t2 = document.getElementById('target2');

    function btn_listener(event){
    switch(event.target.id){

    case 'target1':
    alert(1);
    break;

    case 'target2':
    alert(2);
    break;
    }
    }

    t1.addEventListener('click', btn_listener);

    t2.addEventListener('click', btn_listener);

    </script>
    ```
    이벤트리스너를 사용하면 복수의 동일 타입의 리스너를 등록할 수도 복수의 엘리먼트에 하나의 리스너를 등록해서 재사용할 수 도 있다.

* HTML 태그는 중첩되어 있다. 따라서 특정한 태그에서 발생하는 이벤트는 중첩되어 있는 태그들 모두가 대상이 될 수 있다. 이벤트가 부모에서부터 발생해서 자식으로 전파되고 있다. 이러한 방식을 capturing이라고 한다[click이벤트 같은 전역 핸들러]

* capturing은 코드의 위치와 상관없다
```
document.querySelector('html').addEventListener('click', handler, true)......; .
```
```
document.querySelector('html').addEventListener('click', handler, false); 세번째인자가 false가 된에 따라서 자식으로부터 부모로 이벤트가 전파됨. 버블링이라고 부름. 두번째 인자인 handler를 stophandler로 바꿈에 따라서 자기 자신까지는 이벤트가 실행되고 후술한 이벤트는 실행되지 않는다.
```
* submit, 텍스트의 입력, 하이퍼링크 등의 기본적인 동작들을 기본 이벤트라고 하는데 inline, property의 return을 false로 두면 기본 동작이 취소되고 addEventListener는 event.preventDefault(); 객체를 호출하면 된다. 
* change는 폼 컨트롤의 값이 변경 되었을 때 발생하는 이벤트다.
```
t.addEventListener('change', function(event){}
```
* focus는 엘리먼트에 포커스가 생겼을 때, blur은 포커스가 사라졌을 때 발생하는 이벤트다.
* 웹페이지를 프로그래밍적으로 제어하기 위해서는 웹페이지의 모든 요소에 대한 처리가 끝나야 한다. 이것을 알려주는 이벤트가 load, DOMContentLoaded이다. 뒤로 옮기는 방법도 있다.

    * window.addEventListener('load', function(){} 단점으로는 문서내의 모든 리소스(이미지, 스크립트)의 다운로드가 끝난 후에 실행된다.

    * DOMContentLoaded는 문서에서 스크립트 작업을 할 수 있을 때 실행되기 때문에 이미지 다운로드를 기다릴 필요가 없다.
* 마우스 클릭, 더블클릭, 움직임, 오른쪽 클릭, 엘리먼트를 빠져나가고 들어올 떄 를 감지.
* 키보드 특수키 (alte,ctrl, shift)를 감지.
* clientX와 clientY로 마우스 포인터의 위치를 알아냄.
* 하나에 엘리먼트에 여러개의 이벤트 타입을 동시에 등록가능.
```
<script>

$('#target').on('focus blur', function(e){

$('#status').html(e.type);

})

</script>

 
```

* 만약 이벤트에 따라서 다른 핸들러를 실행하고 싶다면

```
<script>

$('#target').on({

'focus' : function(e){

},

'blur' : function(e){

}

})

</script>
```

* 이벤트를 제거할 때에는 off 사용가능하다.
```
$('#target').off('focus blur', handler);
```

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

---

## 특이한 문법
* 함수명(self){내용} 하면 함수를 선언. 스크립트 태그안에 선언해야한다. this를 self로 변경. 사용할 때는 함수명(this)로 사용.
* 매개변수는 타입을 선언할 필요없다.
* ==는 문자1과 숫자 1는 같다고 나오지만 ===는 문자의 타입까지도 비교한다.
* null은 undefined임.
* '문자열' + 변수명 + |n 줄바굼 '문자열' 이런 글을 `문자열 ${변수명} 문자열` 이렇게 바꿀 수 있다.
* console.dir(location); 으로 모든 프로퍼티를 열람가능.
* 기능테스트 사용하려는 javascript기능이 다른 버전, 다른 브라우저에서 지원하는 지 확인하는 것. 만일 지원하지 않는다면 그러한 함수를 직접만들어서 사용해야하지만 속도는 느려짐.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

## 자바스크립트 내에서 CSS사용
* 국소적으로 색상을 변경할 떄에는  &#x3C; div style>를 사용해야한다.
* 리턴을 사용하지 않으면 함수안에 css태그를 넣어도 html의 출력에서는 그냥 무시된다.
* HTMLCollection의 목록은 실시간으로 변경된다. 따라서 변경이 생긴후에 재조회할 필요가 없다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

## JQuery
* $('a')는 모든 a라는 태그를 사용하겠다라는 의미이다.
* $('a').css('color',매개변수)
* $()는 jQuery의 함수이다. 이 함수의 인자로 CSS 선택자(li)를 전달하면 jQuery 객체라는 것을 리턴한다.
* late binding

jQuery는 존재하지 않는 엘리먼트에도 이벤트를 등록할 수 있는 놀라운 기능을 제공한다. 그것도 특별한 객체나 메소드를 호출할 필요없이 자동으로 지원. 따라서 jQuery로 굳이 스크립트 뒤쪽에 배치할 필요가 없다.

* console.group('그룹명');  console.groupEnd(); 로 console 출력을 그룹핑해서 보여준다.
* li.map(function(index, elem){} map은 jQuery 객체의 엘리먼트를 하나씩 순회한다. 이 때 첫번째 인자로 전달된 함수가 호출되는데 첫번째 인자로 엘리먼트의 인덱스, 두번째 인자로 엘리먼트 객체(DOM)이 전달된다.
* var items = text.split(',') ,를 기준으로 텍스트를 분리한다. items에 배열의 형태로 저장한다.
* item = item.trim() 공백이나 줄바꿈을 제거하는 함수이다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

## CSS와 비교
 * 순수 CSS
 ```
var target = document.getElementById('pure');

if(target.addEventListener){

target.addEventListener('click', function(event){

alert('pure');

});

} else {

target.attachEvent('onclick', function(event){

alert('pure');

});

}
 ```

 * JQuery 사용
```

$('#jquery').on('click', function(event){

alert('jQuery');

})

</script>

.on( events [, selector ] [, data ], handler(eventObject) )
```


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

## Ajax
* fetch('파일명') 를 사용하여 요청과 응답을 한다
* fetch('파일명').then(fetch후에 실행할 것)
* 익명함수를 사용가능하다. function(){} 로 함수에 이름이 없다.
* response.text()를 이용하여 본문 불러오기.
* response는 서버와의 통신 상태를 나타내며 만일 response.status가 200이면 잘받았다. 404는 파일이 없다.
* document.querySelector('article').innerHTML='들어갈 내용'
* 주소창에 #이름으로 id 이동이 가능하다.
* location.hash 하면 문서의 현재 위치를 표기. 스크립트 태그안에 if(location.hash){fetchPage(location.hash); 로 링크를 받아서 이동시키는 것이 가능해짐.}
* fetch('list').then(function(response){response.text().then(function(text){document.querySelector('#nav').innerHTML = text;})파일을 id=nav인 태그 사이에 넣는다는 의미이다
* data 서버로 데이터를 전송할 때 이 옵션을 사용한다.
* dataType 서버측에서 전송한 데이터를 어떤 형식의 데이터로 해석할 것인가를 지정한다. 값으로 올 수 있는 것은 xml, json, script, html이다. 형식을 지정하지 않으면 jQuery가 알아서 판단한다.
* success 성공했을 때 호출할 콜백을 지정한다.
* type 데이터를 전송하는 방법을 지정한다. get, post를 사용할 수 있다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)

## TIPS
* ctrl+space를 누르면 자동 완성 기능 동작. 
* window는 브라우저 창을 제어하는 객체로 open,close 등등이 있다.
* navigator는 브라우저의 정보를 담고 있어 호환성관련한 문제에 대응할 수 있다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-JavaScript)
