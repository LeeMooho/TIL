# Index of HTML / CSS

## HTML
* [테이블 생성](#테이블-생성)
* [Meta 태그](Meta-태그)
* [다중 클래스](다중-클래스)


## CSS
* [기본 지식](#기본-지식)
* [Grid](Grid)
* [미디어쿼리](미디어쿼리)

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


## Meta 태그
meta태그에는 charset뿐만 아니라 검색엔진을 위한 키워드, 설명, 저자, 리다이렉트, 뷰포트 설정 등의 기능을 한다.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-HTML-/-CSS)


## 다중 클래스

태그 안에서 class=""로 선언하면 그룹으로 관리할 수 있게 된다. 클래스의 값은 여러개를 가질 수 있고 띄어쓰기로 구분한다.

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