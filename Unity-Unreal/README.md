# Index of Unity-Unreal


### Unreal
* [오브젝트](#오브젝트)
* [UI / UX](#UI-/-UX)
* [개발 팁](#개발-팁)
---
### Unity
* [시행착오들(3D테트리스)](#시행착오들(3D테트리스))
* [개발 팁 (빌드할 때)](#개발-팁 (빌드할-때))
* [개발 팁 (2D 게임)](#개발-팁-(2D-게임))
* [개발 팁](#개발-팁)

# Unreal 
## 오브젝트
* 색상 변경
    * Material 에서 키보드 3과 왼쪽 클릭으로 베이스 컬러에 연결하면 색상을 변경할 수 있다. (값이 3가지로 이루어졌다는 이미)
    * 1과 왼쪽클릭으로 메탈릭과 러프니스를 변경할 수 있음.
    * 이미시브 컬러가 높으면 빛나는 표현을 할 수 가 있음.
    * 색상을 파라미터로 변경하면 실행중에 변경가능. ->머터리얼 인스탠스를 생성함
    * construction에 creat dynamic material instance를 생성하여 변수를 저장한다.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Unity-Unreal
)

## UI / UX 
* 새로운 정보를 인게임 화면에 띄우려면 위젯 블루프린터로 디자인할 수 있다.
* 블루프린터에서 입력을 받을려면 begin event에서 enable input과 player controller가 반드시 필요하다.
* 블루프린터의 creat widget을 사용하면 위젯 블루프린터로 디자인한 화면을 띄울 수 있다. 그후 반드시 변수로 지정해서 메모리를 할당해줘야함. 마지막으로 viewport를 생성하여 플로우와 변수를 할당한다.
* set show mouse cursor 하면 커서를 보여준다. 이때 타겟은 get player controller로 설정한다.
* set input mode를 이용하여 마우스 커서와 인게임 화면 움직임을 취사선택할 수 있다.
* 클릭은 onclick이벤트를 설정할 수 있음. 닫기는 remove from parent로 구현한다.
* set array elem 로 행렬 값을 지정. 인덱스는 칸의 순서, item은 내부의 값.
* 이벤트 발생을 사용함으로써 재사용성을 높일 수 있다. -> 이벤트 디스패처을 호출한다.
* 부모블루프린트로 이동한 후에 이벤트를 바인드 시켜줘야한다.
* set visuality 보이게 하는 것

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Unity-Unreal
)

## 개발 팁
* q,r + 왼쪽 마우스는 화면 높낮이 조절
* wasd + 오른쪽은 화면 이동.
* b + 왼쪽 클릭으로 분기가 생겨남.
* input -> 키보드 이벤트 -> 키할당.
* s+왼쪽 클릭 ->시퀀스를 생성할 수 있음. 2개 할당 가능. 이벤트 바인드시 최초 블루프린트 이벤트를 할당해줘야함.
* open level하면 레벨을 이동할 수 있음.
* 초기값은 –1로 주어서 초기화가 제대로 이루어졌는지 확인할 수 도 있음(-1은 들어갈 수 없으므러)
* 물체 생성시에 물체 내부에 무언가 있으면 생성안됨.
* life span을 이용하면 정해진 초 후에 소멸됨.
* collision을 형태 위에다 넣어서 총알을 표현함.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Unity-Unreal
)


# Unity
## 시행착오들(3D테트리스)
* transform.position, transform.translate 는 순간이동이라서 오브젝트안에 들어가는 경우가 생긴다. 반면 move는 선형적으로 이동한다.
* iskinetic이 체크되어있으면 충돌을 감지 못했음.
* 부모 오브젝트의 정보는 transform에서 가지고 있음.
* EventSystem 이 없을 경우 클릭이 안된다.
* float 0.5f 반드시 f를 붙여야지만 double오류가 나타나지 않음.
* 자식이 있는 오브젝트는 Destroy(this)하면 스크립트가 삭제
* 오브젝트 삭제는 Destroy(this.gameObject)로 한다.

* grid layout group 과 content size fitter를 사용하여 정렬.

* 텍스트에 shadow 컴포넌트를 넣어서 입체감을 추가

* monobehaviour 파일명 이상이 없으나 모든 인텔리센스가 작동하지 않고 유니티에서 모든 파일을 찾지 못하면 솔루션 빌드를 다시하면 된다.

* vector3.up은 로컬

* vector3(0,1,0) 은 글로벌

* box collider를 스케일로 다루면 축을 기준으로 줄어들어 한면은 계속 고정될 수도 있음.

* ctrl + m +m 코드 모두 접기

* ctrl + m +p 코드 모두 열기

* physic.ray 는 그 충돌의 유무로 true, false를 나타냄.

* for 함수까지만 쓰고 tab을 두 번 누르면 자동으로 형식이 완성된다.

* 왜 인지는 모르나 버튼이벤트와 트리거 이벤트가 실행되지 않는 경우가 있다. 이 경우 오브젝트 아래에 빈 이미지를 넣어서 해결하였다.

* 변하는 함수를 호출하기 위해선
```
GameObject.Find("StageManager").SendMessage("stage" + (stageManager.StageLevel + 1)); 가 효율적이다.
```
 

* 판넬은 SelectLevelPanel.GetComponent<RectTransform>().anchoredPosition += new Vector2(1000, 0);를 사용한다. 희안하게 awake에 컴포넌트를 불러오도 안됨. 그냥 transform을 사용하면 1000만큼 이동을 하라고 해도 400만큼 이동하는 경우가 생기기도 한다.


* [header(“”)] 인스펙터 창에 굵은 글씨로 나옴.
 

* lerp는 선형 보간 slerp는 구면 선형 보간이다.

* 카메라에 layer에 따라 보이게 혹은 안보이게 설정이 가능하다. Mask가 sms 부모 오브젝트에 따라 자식을 제한.

 
* array list는 list와 달리 자료형에 얽매이지 않으나 연산과 메모리 누수가 크다. 그래서 list를 쓰는 것이 보편적.

* 마찬가지로 hashtable은 dictionary에 비해 성능상 불리함을 가지고 있음.

* delegate 함수명를 사용하면 함수명+=함수들(매개변수), 로 함수들의 매개변수를 모두 입력할 수 있다.

* 무명 함수 는 굳이 함수를 안만들고 델리게이트에 직접 넣음. delegate 함수명+= delegate(){ print();};

* 람다식 지원 delegate 함수명 +=()=>print();

* 함수의 은닉화 -> 메소드안에 return 변수명; 을 넣어 읽어들임.

* stopcoroutine은 코루틴 선언을 한 것만 사용해야함, 혹은 문자열로 넣으면 그냥 넣어도 됨.

* #Region 이름 #endRegion 이름을 사용하면 코드를 접고 펼 수 있음. -> 전처리라고 함

 
* 형식매개변수(제너릭)
```
void print<T>(T value);
print<string>(“abc”);

void print<T>(T value); where T :　로 제약을 넣을 수도 있음.

 ```

* 예외처리
```
try{

}

catch(오류 이유 ie){
대처 방법
}

catch는 여러개 만들 수 있고 마지막에 finally을 사용
```
 
* protected 상속받은 자식 클래스만 사용가능 .

* 자식클래스에서 메소드를 재정의하고 싶다면 부모 클래스의 메소드를 protected virtual void 로 정의. 자식 클래스에서 protected override void를 한다. base는 부모 클래스

* drag중인 객체 내에서 커서를 놓을 때 호출되는 것이 drop

* 그냥 drag중인 커서를 놓을 때 호출되는 것이 end Draag


* 노말맵 -> 청록색에 가까울수록 질감이 강해짐.

* 헤이트맵 어두울수록 들어가고 밝을수록 돌출됨.

* 오브젝트 ctrl d를 하면 오브젝트가 복사가 되며 속성을 공유하게 된다.

* domove으로 부드러운 이동 가능/.

* 싱글턴 패턴 
```
public static CardManager Inst {get; private set;}

void Awake() => INst =this;
```
[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Unity-Unreal
)



## 개발 팁 (빌드할 때)
* 빌드할 때 필요한 것 아이콘, 회사 및 제품이름.
* 세로모드(portrait) 가로모드(landscape)를 체크 및 체크 해제 확인
* package name은 작성하기를 권장. 저장 경로로 됨.
* 64비트 빌드를 위해 mono를 IL2CPP로 변경 후 타겟 중 X86를 체크해제, ARMv7, ARM64를 체크.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Unity-Unreal
)




## 개발 팁 (2D 게임)
* 스프라이트는 불러들일 때 에디터에서 필터모드와 압축은 없는 편이 좋다. 슬라이스 할 때 pading은 1씩 주어서 간격확인.
* 기본 타일은 create -> tiles -> rule tile 로 제작하면 편하다. rule tile을 사용하려면 관련 라이브러리 설치해야한다.
* 애니메이션이 있는 타일이라면 스프라이트를 넣고 output를 animation으로 변경해줌. 그후 사이즈와 프레임을 집어넣음.
* 외부 경계를 집어넣을 때는 rigidbody 2d, tilemap collider 2d와 composite collider 2d를 넣고 주변 타입을 깜싸면 된다. 그후 아무 타일을 깔고 tilemap renderer에서 mask interaction을 변경
* 카메라와 충돌로 픽셀이 깨지는 경우가 있는데 windows – package manager – 2d pixel perfect를 사용하면 깨짐 없어짐. ->　메인카메라에 pixel perfect 콤포넌트를 넣고 해상도와 같은 숫자를 대입.
* 애니메이션은 방향에 따라서, 상태에 따라서 다 만들어주고 애니메이터 매개변수는 int형으로 두어서 방향과 움직임을 둘다 동시에 파악한다. 걷기같은 경우는 계속 입력이 들어와서 애니메이션이 정상적으로 작동이 힘들기 때문에 if조건과 bool 조건이 필요하다.

* canvas에도 pixel perfect를 설정해줘야한다.

* 이미지를 넣고 크게 하면 깨지는 경우가 있는데 이때 설정을 sliced로 바꾸어주고 sprite editor에 들어가 border를 설정해주어서 원형을 위치할 것을 결정해준다.

* int.Parse 문자열을 해당 타입으로 변환해주는 함수 (int)가 안먹힐 때

* 대화 사운드는 보통 띄어쓰기과 마침표 등을 제외.

* 애니메이션 중간에 클릭하면 모든 대화 나오기

* ui버튼은 보통 gamemanager의 void update에서 처리.

* 프로그램 종료 (에디터에선 실행 안됨)
```
public void GameExit()
{
Application.Quit()
}
```
* 게임 저장하기 로드하기 기능. -> 저장 데이터는 퀘스트, 플레이어 위치 ->playerprefs를 사용하여 저장하고 start에 로드 함수를 넣음. 이러한 정보는 레지스트리에 저장되어 있음.
* rigidbody -> dynamic이면 충돌시의 에너지도 받으나 kinetic이라면 스크립트 상의 힘만 적용 받음.
* getbutton은 연속적인 입력도 받으나 up이나 down은 일회성이다.
* 스프라이트 모양이 특이하면 스프라이트 에디터에서 custom physics shape로 콜라이더의 모양을 변경할 수 잇음. 변경된 콜라이더는 polygon collider 컴포넌트를 통해 불러들임.
* 다른 스크립트의 public으로 가져온 변수는 반드시 초기화를 해야함.
* sceneManager.LoadScene(0)을 실행하기 위해서는 buildSetting에 씬이로드된 것을 확인해야함. 여기서 씬 번호 또한 확인 가능.
* order in layer가 높을수록 더 잘보임. 음수도 가능.
* 카메라 크기(화면 높이의 1/2) -> Camera.amin.orthographicSize; // *2 해줌
* 스크롤러 -> 배경을 무한대로 만듬
```
void scrolling()

if(Sprites[endIndex].position.y<-5)

{

//스프라이트 재사용

Vector3 backSpritesPos = Sprites[startIndex].localPosition;

Vector3 frontSpritesPos = Sprites[endIndex].localPosition;

Sprites[endIndex].transform.localPosition = backSpritesPos + Vector3.up * 5;

 

//커서 인덱스 변경

int startIndexSave = startIndex;

startIndex = endIndex;

endIndex = (startIndexSave - 1 == -1) ? SpriteSortPoint.Length - 1 : startIndexSave - 1;

//아래가 end이고 인덱스는 0, 위에서 아래로 흐림

}
```
 

* parallax -> 멀리 있는 걸 천천히 움직이게하여 원근감을 표현.

* 인스턴스를 생성, 삭제시 메모리에 남게 되는데 이것을 지우는 작업이 가비지컬렉트(GC)임. 이 때문에 메모리를 위한 오브젝트 풀링이 필요함.게임에 로딩시간이 나오는 것이 바로 오브젝트 풀로 인한 것이다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Unity-Unreal
)



## 개발 팁 (공통)
* 조이 스틱이 특정 지점을 벗어나지 못하게 최대 벡터의 길이를 제한.
* 이동에 normalied를 사용하지 않으면 대각성 이동시 루트2 만큼 더 빨리 이동을 한다.
* 물리 충돌 판정은 fixed update이기 때문에 udated가 더 빠르면 가끔씩 무시되는 경우가 있다. ->rigidbody component에서 discrete에서 continous로 옵션 변경. -> 이때 지형도 static 으로 변경해주면 더욱 효과적.
* transform.LookAt(transform.position + moveVec); 지정된 벡터를 향해서 회전시켜주는 함수
* prefeb 설정시 반드시 초기 포지션은 (0,0,0)으로 초기화 시켜준다.
* RotateAround() 타켓 주위를 회전하는 함수
* trail renderer를 사용하여 잔상을 남김.
```
IEnumerator Swing()
{
yield return null; //1 프레임 대기

//혹은

yield return new WaitForSeconds();

yield break;//를 통해서 탈출 가능

}
```
* yield를 여러개 사용하여 시간차 로직 작성이 가능하다.
* 코루틴 함수는 StartCoroutine(“함수명”) 를 사용
* 레이어를 활용하여 의도하지 않은 물리적인 충돌 방지.
* 회전력이 관성에 의해서 남아 있는 경우를 vector3.zero를 이용하여 제거.
* 수류탄과 같은 모든 범위에 피격하기 위해서는
```
IEnumerator Explosion()

RaycastHit[] rayhits = Physics.SphereCastAll(transform.position, 15, vector3.up, 0f,Layermask.Getmask(“Enemy”));


foreach(RaycastHit hitobj in rayhits){

hitobj.transform.GetComponent<Enemy>().HitByGrenade(transform.position);

}
```

* using UnityEngine.AI

적의 인공지능을 장착 NavMeshAgent navigation을 사용하는 인공지능 컴포넌트 또한 navagent에서 추적, 속도 가속도를 조정할 수 잇음.
 
* 월드좌표들은 transform 이나 스크린좌표는 rectTransform이다.
* UI가 도트라면 canvas의 pixel perfect 항목을 체크 해줘야함.
* 모든 화면에서 동일한 비율로 버튼을 표현하기 위해 canvas scaler의 ui scale mode를 scale with screen size로 변경해준다. 해상도는 1920x 1080으로 설정
* 텍스트는 콘텐츠 박스를 넘치면 글자가 사라지게 된다. 그러므로 overflow를 세로, 가로로 설정해 주면 이러한 일이 없어진다.
* 텍스트 위치를 맞추어 주어도 삐틀어지게 나오는데 이때 alignment를 중앙, 센터로 설정해주면 된다. 무조건 중앙으로 맞추면 글자가 많아지면 왼쪽 오른쪽으로 커지는 것에 유의
* 폰트가 흐려보인다면 scale을 줄이고 크기를 늘려서 더욱 또렷하게 보이게 가능하다.
* 버튼은 이미지에 스프라이트를 넣고 slice를 simple로 바꾸고 SetNativeSize로 변경후 simple을 다시 slice로 변경한다.
* 앵커모드일때 shift는 ui중심 alt는 ui위치 오브젝트에 크기가 이미 크다면 정렬에 제약이 생기므로 0,0 으로 설정하고 정렬 먼저 한 후에 크기 조절을 해주는 것이 좋다.
* 그룹채로 이동해도 자식 오브젝트는 앵커가 그대로 유지되어 있으니 자식 앵커도 변경해줘야한다.
* 보스 체력 게이지 이미지를 줄일때에는 앵커 shift 왼쪽을 눌러 중심을 왼쪽으로 바꾼채로 사용.
* 파티클 시스템 도넛을 이용하여 상점 존을 표현할 수도 있음.
* UI로직을 만들때에는 각 UI마다 카메라가 필요하다.
* alt+ wheel 하면 타임라인 간격 조절가능.
* 최고 점수는 player 스크립트에 awake에 playerPrefs을 사용하여 저장 기능을 활용.
* game manager는 게임에서 관리해야할 요소들을 총 관리하는 스크립트. //주로 인게임의 모든 UI요소들. 빈 오브젝트에 스크립트을 넣고 각각에 요소에 대응하는 오브젝트를 하이러키에서 찾아서 대입.
* 천자리수 마다 점을 찍고 싶다면
```
maxScoreTxt.text = string.Format("{0:n0},",PlayerPrefs.GetInt("MaxScore"));
```
 

* 2자리 마다 :를 찍으려면
```
playTimeTxt.text = string.Format("{0:00},", player.score);
```

* ui는 update보다는 lateupdate를 사용한다.

* Color(1, 1, 1)은 색상에 변화가 없음.

* 씬을 관리하려면 
```
using UnityEngine.SceneManagement;

 
public void Restart()

{

SceneManager.LoadScene(0); //씬의 개수를 구분하며,

}
```

* 버튼 navigation을 none으로 하면 스페이스 엔터로 메뉴가 선택되는 일이 없어짐.


* 소리를 집어넣을때는 빈 오브젝트(jump sound)를 만들고
```
player에

public AudioSource jumpsound; 선언

함수 안에 jumpSound,Play(); 입력

콤포넌트도 audio source를 추가하고 기본적으로 play on awake이 체크되어 있는데 체크 해제해줘야함.
```
 

* 빌드를 할때는 메인화면 상태에서 빌드를 함.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Unity-Unreal
)