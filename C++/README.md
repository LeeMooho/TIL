# Index of C++

* [전처리기(#)에서의 상수 선언과 const로 상수 선언 비교](#전처리기(#)에서의-상수-선언과-const로-상수-선-비교)
* [인터페이스, 추상 함수](#인터페이스,-추상-함수)
* [비트단위 연산](#비트단위-연산)
* [포인터의 특징](#포인터의-특징)
* [메모리 관리](#메모리-관리)
* [typedef](#typedef)
* [](#)
* [](#)

## 전처리기(#)에서의 상수 선언과 const로 상수 선언 비교

 | |#define | const|
 |------|---|---|
 |공통점 |  상수를 선언.| |
 |처리시점|전처리|컴파일 단계
 |자료형|의미없다|const 뒤에 자료형이 뒤따름(안전한 코드)
 |메모리 할당|기호상수값은 할당되지 않음.|할당됨.
 |스코프|코드 전역|지역변수
[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-C++)


## 인터페이스, 추상 함수
interface 함수명 {
반드시 있어야 하는 함수
}

class 클래스명 implements 인터페이스 함수명{
반드시 있어야한는 함수
}

 
abstract class를 사용하면 다른 클래스는 extends를 사용하여 상속 받을 수 있다.
[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-C++)

## 비트단위 연산
* 비트 단위 4<<1 하면 값이 두배 되고 반대로 하면 1/2 배가 된다.
* 비트 ~ 와 논리 ! 는 다르게 적용된다 .
* 비트 ^ 는 XOR로 적용된다.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-C++)

## 포인터의 특징
* 포인트도 ++사용가능. 다음 변수의 주소값으로 이동.
* 구조체에 name이 char[10]을 할당시키면 s.name =“홍길동” 는 선언이 안된다. strcpy(s.name,“홍길동”); 이렇게 선언해야함.

 

 

단일 포인트라면 char *greet = “Goodbye”을 했어도 문제없음.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-C++)

## 메모리 관리
* malloc() 함수는 할당된 메모리 블럭의 첫번쨰 바이트에 대한 주소를 반환한다. 메모리를 할당할 수 없을 경우 NULL을 반환한다. 

* malloc()함수가 반환한 값은 반드시 포인터 변수가 받아야한다.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-C++)

## typedef

* typedef unsigned char BYTE; 새로운 자료형을 정의 / 기존의 자료형 / 새로운 자료형
[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-C++)


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-C++)


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-C++)

