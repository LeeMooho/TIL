# Index of TypeScript

* [기본 지식](#기본-지식)




[뒤로](https://github.com/LeeMooho/TIL)

## 기본 지식

* 인터페이스를 사용할 수 있게 됨. :으로 implements age?:Number하면 age프로퍼티는 있어도 되고 없어도 됨. 
* 열거형을 타입으로 규정할 수 있음. 
```
enum GenderType{
Male
}
```
* 차례로 Male은 0을 암시적으로 가지고 있고 나중에 객체가 추가되면 1,2가 추가된다.
* gender:GenderType.Male

* 리터럴 타입으로 gender: &#x60;Male&#x60; | &#x60;Female&#x60; 이렇게 할 수도 있음.
* 타입을 여러개 지정하고 싶을 떄에는 |를 사용 이런 타입을 type으로 지정할 수도 있다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-TypeScript)

