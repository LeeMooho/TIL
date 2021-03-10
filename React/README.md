# Index of React

* [TIPS](#TIPS)




[뒤로](https://github.com/LeeMooho/TIL)


## 기본지식

* 리액트 훅에서 함수형 컴포넌트를 지원해주어서 권장은 클래스보다 함수형 컴포넌트. 선언이 편하고 메모리 자원을 덜 사용한다는 장점이 있다.


* 콘솔창에 색을 넣을 수 있다.
```
var Srtle ='color:red';
console.log('%c내용',Style) 하면 
```

* class컴포넌트를 사용할 때에는 라이프 사이클 API로 render() 메소드 호출 전후로 다른 함수를 호출할 수 있었다.함수형 컴포넌트를 사용할 때에는 useEffect를 사용해야한다. /render()후에 호출되는 함수. useEffect는 두 인자를 가지는 데 첫번쨰 인자에는 함수가 들어간다. 그리고 이 함수의 return에 함수를 넣으면 useEffect안의 함수가 나오기 전에 실행된다. 두번 쨰인자는 [내용]가 들어가는데 내용이 바뀌여야만 첫번쨰 인자의 함수가 실행되게 할 수 있다.
두번쨰 인자를 []으로 아무것도 안넣으면 컴포넌트가 최초 실행될 떄만 실행되고 이후에는 실행되지 않는다. 


* 함수형 컴포넌트도 라이프 사이클 API로 클래스형 컴포넌트와 같이 사용할 수 있다.

* return안에는 하나의 최상위 태그만 사용할 수 있다. 자식 태그는 여러개 있어도 상관없다.
```
class Subject extentds Component {
	render(){
	return(
		<header>
			hello
		</header>

);
}
```

* 이떄 클래스의 이름이 태그로 정의된다. <Subject></Subject> 로 사용할 수 있다. 그리고 이를 유사 자바스크립트 JSX라고 불린다.

* App이 react에서 실제 출력되는 부분. 

* 사용자가 만든 태그를 컴포넌트라고 한다. 

* props로 attribute을 이용해서 다형화시켜 사용할 수 있다.

```
class Subject extentds Component {
	render(){
	return(
		<header>
			{this.props.title}
		</header>

);
}

<Subject title="web"></Subject>
```

* 컴퍼넌트 파일로 분리하는 법. 
받아서 사용할 파일에는 import App from './App'; 처럼하면 된다.
보낼 컴퍼넌트는 export default 클래스이름;

* app의 reder전에 state초기화후에 원하는 props입력하기. constructor를 사용한다. state를 사용하면 정보의 은닉성 면에서 좋다.
```
class app extends component {
	constructor(props){
	super(props);
	this.state ={
	 subject:{title:'WEB'}
	}
	}
 render(){ 
	return(
	<Subject title={this.state.subject.title}>
	</Subject>
	)
 }
}
}
```

* state에 항목을 두고 이 객체를 임포트받는 다른 컴퍼넌트의 render함수에 넣고 이를 불러들일 수 있다. 이를 통해 자동으로 목록구현화 같은 것이 가능하나 자동으로 list같은 걸 이용해 만들면 각 lis목록은 key prop를 가져야만한다. 

* react의 state모듈이 바뀔 떄마다 render함수 역시 재호출됨. 이를 통해 App의 페이지 내용전환을 render안에 if문을 넣어서 구현이 가능하다.

* debugger;를 넣으면 실행을 멈추고 개발자도구에서 현황을 확인할 수 있다.
* react사용시 onClick 이벤트 같은 걸 넣을 떄 기본적으로 reload하는 기능이 있는 이벤트들은 .preventDefault()를 넣어주어서 이러한 현상을 방지해야한다.

* this.state.mode를 바꾸려고하면 render함수안에 this.setState({mode =''}); 해야한다. this는 함수안의 객체를 찾게되어서 함수 끝에 .bind(this)를 추가시켜줘야한다. 

* 컴포넌트 이벤트들은
```
<Subject makeEvent={function(){alert('hh');}.bind(this)}}></Subject>

class Subject extentds Component {
	render(){
	return(
		<header makeEvent={function(e){
		e.preventDefault;
		this.props.makeEvent();
		}.bind(this)}}>
			{this.props.title}
		</header>

);
}
```

* 액션으로 데이터를 보냄
```
<form action="/create_process" method="post" onSubmit={function(e){
e.prevenDefalut;
}.bind(this)}>

</form>
```

* 폼안의 e.target.[name].value 는 각 데이터를 가지고 있다.
* arr2.concat()하면 arr2의 데이터를 넣고 새로운 데이터를 넣은 배열을 리턴한다. 오리지널 state를 변경하는 push 같은 걸 사용하지 말아야한다.
* props는 read-only , state는 가변데이터이다.
* var content = Array.from(this.state.contents); 하면 새로운 배열 생성.
* url하나밖에 안써서 다른 페이지를 찾기힘들다. 이를 위해 react router를 사용하면 된다.

* 리액트의 컴포넌트는 대문자로 써야한다.그렇게 해야 함수로인식

* object.assign 하면 오브젝트를 복사한다. 다만 객체안에 또 다른 객체가 있을 시 각은 객체를 가짐으로 o2.score=o2.score.concat()같이 concat()을 사용하여 복사한다. [score가 배열일시]
* 함수의 return을 사용하여 원본의 손상을 막는다.
* Object.freeze(); 객체의 프로퍼티의 수정을 금지.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-React)


## 리액트 라우터
URL을 부여하기 위해 사용

* 라이브러리를 설치한다.  npm install react-router-dom

* switch로 감싸면 path에 일치하는 것만 출력하고 나머지는 읽지않고 break. 

* Navlink로 사용자가 링크안에 들어가면 active 클래스를 생성해준다.

* href대신 link를 쓰면 reload가 없어짐.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-React)
