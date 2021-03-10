# Index of HTML / CSS

## HTML
* [테이블 생성](#테이블-생성)
* [태그](#태그)
* [다중 클래스](#다중-클래스)
* [개발 팁](#개발 팁)


## CSS
* [기본 지식](#기본-지식)
* [Flex](#Flex)
* [Grid](#Grid)
* [미디어쿼리](#미디어쿼리)
* [라이브러리](#라이브러리)
* [꾸미기 고급](#꾸미기-고급)
* [CSS FlexBox 연습 사이트](#CSS-FlexBox-연습-사이트)
* [CSS Selector 연습 사이트](#CSS-Selector-연습-사이트)


# HTML 
## 테이블 생성
```
<table>

  <tr>
    <td> 1행 1열 </td>
    <td> 1행 2열 </td>
  </tr>
</table>
```

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)


## 태그
* meta태그에는 charset뿐만 아니라 검색엔진을 위한 키워드, 설명, 저자, 리다이렉트, 뷰포트 설정 등의 기능을 한다.
* box 태그의 종류 header, section, footer, article, nav, div, aside, span, main, form
* item(inline) 태그의 종류 a, video, button, audio, input, map, label, canvas, img, table
* 각 디바이스 화면에 딱 맞추어 화면이 출력됨.
```
<meta name=“viewport” content=“width-device-width, initial-scale=1”> 
```

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)


## 다중 클래스

태그 안에서 class=""로 선언하면 그룹으로 관리할 수 있게 된다. 클래스의 값은 여러개를 가질 수 있고 띄어쓰기로 구분한다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)

## 개발 팁
*  단축키
```
div.container>div.item.item${$}*10 tab을하면 
<div class="item item1">1</div>에서 10까지 생성된다.
```
```
header+section.player 하면 헤더과 섹션이 나온다.
```

* 단위
  * %로 사용하면 내부 블록에 맞추어서 출력된다.
  * vh는 viewheith로 윈도우 창에 맞추어서 출력된다.
  * x단위이면 물리적인 크기가 아니라서 브라우저를 확대, 축소해도 크기는 변화가 없다. 그래서 보통 %를 이용해서 부모의 단위를 따름. 컨텐츠가 유동적으로 됨. 
  * 상대적 단위중 잘쓰이는 것은 vw,vh,%,em,rem이 있고 em은 1em==16px이고 부모크기와 상대적으로 비교된다. 최상위 부모는 브라우저이고 16px이다, rem은은 최상위 부모 즉 브라우저의 16px를 기준으로 설정된다.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)

# CSS

## 기본 지식
* style 태그로 css를 사용하라는 것을 알려준다. 혹은 국부적으로 사용하려면 태그안에 style:"color:red"를 추가한다.

 
```
<style>
a {
color :red;
text-decoration:none;
}
</style>
a라는 태그에 색상을 빨강색으로 변경해라.


<style>
a,h1 {
border:5px soild red;
}
</style>

이렇게 중복을 최소한 할 수도 있다.(a,h1 태그를 분리해서 선택할 수 있고 만일 띄어쓰기로 구분하면 a태그안에 있는 h1태그를 선택하는 것이다.)
```
* 클래스를 css에서 사용하려면 클래스명에 .을 붙여서 사용하면 된다 
.클래스명 {} 이렇게.

* id는 클래스와 같은 방법으로 단 css 사용은 .이 아닌 #을 붙여서 사용할 수 있게 된다.


* &#x3C; div>는 블록레벨의 디자인 구분 태그이다.

* &#x3C; span>는 인라인 레벨의 디자인 구분 태그이다.

* visibility: hidden; 일때 보이지는 않으나 공간은 차지한다. 이떄 position: absolute를 넣어주면 공간도 차지 하지 않는다.

* !important가 최우선 순위로 동작한다.

* 태그옆에 state(:)을 달수도 있고 attribute[]를 골라서 작성도 가능. 예를 들어
a[href] a태그의 하이퍼레퍼렌스가 있는 값만 바뀜.
* display 프로퍼티로 div, span을 inline-block, inline, block으로 만들 수 있다. 
* 포지션은 left, top등으로 변경할 수 있으며 position이 기본적으로 static이면 변화가 없고 relative로 변경시 변화가 생긴다. relative는 원래 있어야하는 위치에서 움직이고 absolute는 부모 박스를 기준 위치가 변경됨. fixed는 window를 기준으로 움직인다. sticky는 원래 있는 자리에 고정되면서 스크롤링과 상관없이 고정된다.
* position sticky를 사용할 때는 기준을 알려줘야함. 안될 때 top:0; 넣기
* float는 정렬에 관한 것 (css에 포함됨)
* hover는 마우스가 올라가는 것.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)

## Flex
* fiexbox는 박스를 동일한 간격으로 나누는 것, 정렬하는 것 이 가능해졌다. container와 item으로 이루어짐. main axis과 수직이 되는 cross axis가 존재함. display를 flex로 둠으로 써 flex사용이 가능하다. 
* flex-direction의 디폴트값은 row이고 왼쪽에서 오른쪽으로 정렬. row-reverse로 블록을 뒤집을 수 있다. 다른 옵션으로 column이 있다.
* flex-wrap의 디폴트값은 nowrap이고 창이 줄어들어서 한줄로 생략없이 꽉 채워진다. 다른 옵션으로 wrap이면 꽉차면 자동적으로 다음라인으로 넘어가게 된다.
* flwx-flow로 위에 두게를 합칠 수 있다. 
* justify-content의 디폴트는 flex-start이고 중심쪽의 아이템을 왼쪽으로 배치한다. 다른 옵션으로는 flex-end, center가 있다. space-around로 공백을 두를 수 있고 다른 옵션으로는 space-even, space-between이 있다.
* align-items 는 cross-axis를 기준으로 배치하고 center도 있고 baseline있는데 아이템을 기준으로 정렬한다..
* align-content 로 cross-axis를 기준으로 위와 동일한 옵션을 사용할 수 있다. 보통 space-between으로 균등하게 정렬시킴.

* 아이템의 order를 이용하여 숫서를 바꿀 수 있다. 
* flex-grow의 기본값은 0이고 창이 커져도 기본적으로 채우려고 하지 않는다. 하지만 1이면 빈칸을 모두 늘려서 채운다. 아이템 모두 1로 채우면 모두 균등하게 커진다. 
* 반대는 flex-shrink가 있다.
* flex-basis를 하면 위 두 명령을 %로 표현가능하다. 
* align-self를 이용하여 아이템 별로 위치를 조정할 수도 있다.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)

## Grid
* 홈페이지를 블록단위로 사용하려면 그리드를 적용할 부분을  &#x3C;div>로 구분하고 id를 부여한다. 그리고 아이디의 스타일을 display:grid; grid-template-columns:150px 2fr 1fr 등등으로 꾸며준다. (이떄 grid-template-columns:은 div로 구분이 되어있어야한다. fr은 화면의 비율로 2대1비율로 가져간다.)

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)

## 미디어쿼리
미디어 쿼리로 화면의 크기에 따라 css를 다르게 적용할 수 있다. 만일 screen width > 800px 의 의미를 담고 싶다면

style태그 안에 @media(min-width:800px){

div{}

}로 사용

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)

## 라이브러리
* SASS, LESS라이브러리를 사용하면
```
header {} header .logo{} 같은 것을 
header{
 .logo{
}
}
이렇게 정리할 수 있다.
```


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)


## 꾸미기 고급

* css 로 transition으로 애니메이션을 준다.
* margin:0 auto; 하면 위아래로는 지정하지 않고 양옆은 균등하게 들어간다.
* flex :1 1 35% 줄어들 떄나 늘어날 때 1의 비율로 되고 35%을 차지  


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)

## CSS FlexBox 연습 사이트
https://flexboxfroggy.com/#ko

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)


## CSS Selector 연습 사이트
https://flukeout.github.io/

요약

* A + B This selects all B elements that directly follow A.
* A ~ B selects all B that follow a A
* A > B selects all B that are a direct children A
* :first-child selects all first child elements.
* p:first-child selects all first child p elements.  p는 부모태그가 아님을 유의한다.
* ul li:only-child selects the only li element that are in a ul.
* parents element에 nesting 되어 있는 child elements들 중 독자(only child)인 녀석들만 선택할 수 있는 selector를 공부한다. 해당 method는 ":only-child"인데 여기서 주의할 점이 있다. A:only-child 라고 selector를 선언하면 "only child 인 모든 A element를 선택한다"는 뜻이 된다. 하지만 만약 A :only-child 와 같이 "A"와 ":" 사이에 space가 있다면 "A라는 parents elements들의 모든 only-child element를 선택한다"는 의미이다.

* div p:nth-child(2) selects the second p in every div

* p:nth-last-child(2) selects all second-to-last child elements. 모든 형제 엘리먼트중에 2번째이고 p인 것을 선택

* span:first-of-type selects the first span in any element.

* .example:nth-of-type(odd) selects all odd instances of a the example class.
* span:nth-of-type(6n+2)

* p span:only-of-type selects a span within any p if it is the only span in there.

* p span:last-of-type selects the last span in every p.

* div:empty selects all empty div elements.


* div:not(:first-child) selects every div that is not a first child.

*  :not(x)인데, 해당 selector는 'x'를 제외한 모든 나머지 element를 선택하게 된다. 여기서 주의할 점은 괄호안에 1가지 이상의 type이 존재할때는 ','로 나눠줘야 한다.

* a[href] selects all a elements that have a href="anything" attribute.
* input[type="checkbox"] selects all checkbox input elements.


* return new Promise() 해도 되지만 그냥 함수앞에 async를 집어넣는게 좋다.
* await delay()는 async함수 안에서만 사용할 수 있다. 

* .toy[category^="Swim"] selects elements with class toy and either category="Swimwear or category="Swimming".

* img[src$=".jpg"] selects all images display a .jpg image.

* [class*="heading"] selects all elements with "heading" in their class, like class="main-heading" and class="sub-heading"[f





[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)