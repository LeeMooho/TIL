# Index of Android Studio / Kotlin

* UI / UX
    * [Layout](#Layout)
    * [Views](#Views)
    * [TIPS](#TIPS)

* 개발 관련
    * [Activity](#Activity)
    * [Directory](#Directory)
    * [Debugging](#Debugging)
    * [DATA](#DATA)
    * [단축키](#단축키)
* [특이한 문법](#특이한-문법)
* [Kotlin 언어 특징](#kotlin_언어-특징)

[뒤로](https://github.com/LeeMooho/TIL)

---
# UI / UX

## Layout
<br>

### FrameLayout
* 위치는 android:layout_gravity =“center|top” ,android:layout_marginLeft=“10dp” 등으로 조절한다.

### TableLayout
* android:layout_span=“3”이면 다른 행과 비교하여 다른 행의 열의 길이만큼 늘어난다. 다른 행의 열이 span의 크기만큼 반드시 존재해야한다. 
* android : layout_column=“3” 이면 열 위치로 이동한다. 
* android : stretchColumns=“*”  * 대신에 숫자가 들어가면 그 열에 해당되는 버튼의 크기가 변경된다.&#x20; &#x2A;이면 화면에 맞추어서 버튼의 크기가 여백없이 조절된다.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin)


## Views
* TextView가 단순히 Text를 보여주는 역할을 한다면 EditText는 Text를 입력 및 수정까지 가능한 뷰(View) 위젯이다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin)



## TIPS
* android : hint 로 텍스트 박스에 회색 글자가 보이게 할 수 있다.
* android:checkedButton 는 옵션의 디폴트 설정을 지정.
* 엔터를 누르면 자동으로 키보드가 내려가는 동작.
* importantForAccessibility="no" . 를 입력하면 아이콘같은 상호작용이 필요없는 요소는 배제시킨다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin)

---
# 개발 관련
## Activity
* 화면이 회전해 가로/세로모드가 변경될 때에는 onDestroy() 이후 onCreate()가 다시 시작된다. AndroidManifest.xml 파일에 configChanges을 변경하면 액티비티가 재시작되지 않는다. 이렇게 하면, onDestroy(), onCreate() 대신에 onConfigurationChanged() 메서드가 호출된다.
* Implicit Intent 는 링크나 공유와 같이 다른 앱에서 열거나 시스템 동작.
* Explicot Intent 는 앱 내에서의 화면 전환.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin)


## Directory
* res안에 있는 string.xml로 문자열을 객체화 시킨다. 이를 위해서 name 속성값을 지정해야 하며 name 속성값은 문자열의 이름으로 ID로 사용된다. 
* 스타일 스크립트를 만들어놓으면 모든 텍스트뷰에 적용가능하다.
```
<style name="Widget.TipTime.TextView" parent="Widget.MaterialComponents.TextView">

<item name="android:minHeight">48dp</item>

<item name="android:gravity">center_vertical</item>

<item name="android:textAppearance">?attr/textAppearanceBody1</item>

</style>
```

```
<TextView

android:id="@+id/service_question"

style="@style/Widget.TipTime.TextView"

... />
```

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin)


## Debugging
* 안드로이드 스튜디오 하단의 logcat을 통해 디버그를 하며 null일 때 crash가 발생하나 kotlin은 null에 대처하는 메소드들을 가지고 있다. toDoubleOrNull()와 같은...
* 이미지view에 onclick 이벤트가 안되는 현상. 함수의 접근제한자를 public으로 변경.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin) 


## DATA
* 앱 내부 DB를 이용하려면 oncreate 함수에 loadData함수를 만들고 onDestroy함수에다가는 savadata를 만든다.
* inten시 데이터 저장. 앱 내부 DB를 이용하는 방법으로는 intent.putExtra로 데이터를 저장하다. hasExtra로 데이터 존재 유무를 체크하고 getStringExtra로 불러들인다.
* adapter는 view와 data간의 브릿지 역할을 한다.
* 화면 회전시 데이터 저장은 onSaveInstanceState()을 사용한다.
* A Bundle is a collection of key-value pairs, where the keys are always strings. You can put simple data, such as Int and Boolean values
```
outState.putInt(KEY_REVENUE, revenue) [putInt 말고 putfloat, putstring 등이 있다.

outState.putInt(KEY_DESSERT_SOLD, dessertsSold)

 

if (savedInstanceState != null) {

revenue = savedInstanceState.getInt(KEY_REVENUE, 0)

}
```
* 액티비티에서 데이터 전달
```
MAIN
    fun open_black_letter(view : View){
        var intent = Intent(this, Quest::class.java)
        intent.putExtra("color","black")
        startActivity(intent)
    }

받을 떄
when(intent.getStringExtra("color")){
}

```

* 프래그먼트에서 데이터 전달
```
프레그먼트 데이터 전달
  supportFragmentManager.beginTransaction().replace(
    R.id.fragment_my_container,
    MyFragment().apply {
      arguments = Bundle().apply { 
        putString("KEY", "value")
      }
    }
  ).commit()

 받을 때는 

override fun onCreate(savedInstanceState: Bundle?) {
  super.onCreate(savedInstanceState)
  Log.d("data : ", arguments?.getString("KEY"))
}

```

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin) 

## 단축키
* ctrl + o 하면 오버라이드할 함수가 호출된다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin) 

## 특이한 문법 
* val diceRange = 1..6 는 diceRange 가 1~6의 값을 갖는다.
* " " 안에 변수를 넣을 때에는 ${객체} 의 형태를 취한다. 
* with라는 문법으로 객체.파라미터(메소드)를 호출할 때 객체를 생략할 수 있다. 아래의 코드는 squareCabin의 capacity, buildingMaterial, hasRoom()를 온점(.)없이 다음과 같이 호출한다. 
```
with(squareCabin) {

println("\nSquare Cabin\n============")

println("Capacity: ${capacity}")

println("Material: ${buildingMaterial}")

println("Has room? ${hasRoom()}")

}
```
* 코틀린에서 Class의 접근제한자가 보통 Final이라서 자식 클래스를 가질 수 없다. 그러나 자식을 생성할 부모클래스에 open키워드를 사용하면 가질 수 있다. 자식클래스는 class선언을 할 수 있다.
* super 객체를 사용하면 부모의 클래스의 멤버를 호출할 수 있다.
* 뷰 바인딩을 사용하려면 
```
// Old way with findViewById()

val myButton: Button = findViewById(R.id.my_button)
myButton.text = "A button"

 

// Better way with view binding


val myButton: Button = binding.myButton
myButton.text = "A button"

 

// Best way with view binding and no extra variable

binding.myButton.text = "A button"
```
* 리스트

Read-only list: 생성 후에 수정이 안된다.

Mutable list: 생성 후에 삭제, 갱신, 추가가 가능하다.


* 리스트 선언

val numbers: List &#x3C;Int> = listOf(1, 2, 3, 4, 5, 6)

val numbers = listOf(1, 2, 3, 4, 5, 6)

* list메소드 

list메소드에는 first, last, get, contains, reversed, sorted, shuffled, startwith, take 등이 있다. contains은 리스트에 멤버가 있는지 검색해준다.

reversed, sorted 등은 리스트를 하나 더 생성하지만 기존의 리스트를 변경하지는 못한다. list는 read-only이다.

take(n)하면 리스트 안에 n개의 멤버를 가져온다.
val entrees = mutableListOf&#x3C;String>()

val entrees: MutableList&#x3C;String> = mutableListOf()

add를 사용하여 하나씩 추가하거나 addall을 사용하여 리스트쨰로 추가하거나 가능하다. 반대로 remove, removeAt, clear을 사용하여 삭제
리스트 검색은 for (name in names){} 으로 한다.

 

joinToString(" ")를 사용하면 스페이스로 구분짖는 리스트의 항목들을 모두 호출

joinToString()이라면 콤마로 구분지어서 호출된다.
list에서 toset명령어는 중복된 멤버를 제거한다. 생성할 떄는 setof()를 사용할 수 있다.

* $$ 두번 반복하면 $ 하나가 출력됨.
* println("$set1 == $set2: ${set1 == set2}") 는 [1, 2, 3] == [3, 2, 1]: true
* intersect()는 차집합. union()은 교집합.
* map
```
map은 key와 value로 구성되어 있다.

fun main() {

val peopleAges = mutableMapOf<String, Int>(
"Fred" to 30,
"Ann" to 23
)

println(peopleAges)
}

{Fred=30, Ann=23}

To add more entries to the map, you can use the put() function, passing in the key and the value:


peopleAges.put("Barbara", 42)

or peopleAges["Joe"] = 51

peopleAges.forEach { print("${it.key} is ${it.value}, ")

forEach uses the special identifier it.

println(peopleAges.map { "${it.key} is ${it.value}" }.joinToString(", ") )

val filteredNames = peopleAges.filter { it.key.length < 4 }

println(filteredNames)
```
* 람다식
람다식은 함수없이 function을 구현하는 것

fun main() {

val triple: (Int) -> Int = { a: Int -> a * 3 }

println(triple(5))

}

 

val triple: (Int) -> Int = { it * 3 }

* 제너릭

fun<T> genericFunc(param:T), class GenericClass<T>(var pref:T) 캐스팅은 비용이 들어가는데 그래서 캐스팅을 사용하지 않고 제너릭을 사용하면 고정된 자료형이 아닌 실제 데이터에 맞는 타입파라미터를 받아서 사용하는 것.

* ?. 연산자는 앞에있는 객체가 null인지 확인하고 null이라면 뒤따라오는 구문은 실행자지 않는다.
* ?:"객체" 객체가 null이 아니라면 그대로 사용하지만 null이라면 연산자 뒤쪽의 객체로 대신 실행됨.
* !!. 은 컴파일시 검토하여 null이면 중지시킴.
* ==는 내용의 동일성 ===는 객체의 동일성까지 판단.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin) 

## Kotlin 언어 특징
* 기본적으로 모든 fun은 tostring이라는 함수를 상속하고 있다. 때문에 이것을 커스터마이징하면 override을 사용하여 커스텀마이징이 가능하다.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#index-of-android-studio-/-kotlin) 






