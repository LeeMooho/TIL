# Network-Server


* [단편지식](#단편지식)
* [REST API](#REST-API)
* [GraphQL](#GraphQL)



[뒤로](https://github.com/LeeMooho/TIL)


## 단편지식
* 127.0.0.1 는 웹브라우저가 열고있는 각자의 컴퓨터의 ip 주소이다.
* 서버의 IP주소를 내 컴퓨터의 Hosts가 DNS주소를 가지고 있다.
* HTTPS 는 Hosts의 변조를 확인하고 보장하는 인증.
* ctrl + F5 쿠키까지 새로고침.
* WAN은 public ip address. ISP로부터 공급받은 아이피주소
* LAN은 192.168.0.1 private ip address 로 라우터(공유기)에 연결된 일종의 내선번호. 192.168.x.x 는 사설 아이피번호 규약
* NAT(network address translation)으로 사설 아이피와 광역 아이피 사이에서 다른 서버와 연결하는 아이피를 바끈다.
* 포트는 0~1023 까지 예약되어있다. 웹서버는 보통 80(defalut) 혹은 8080이다. 같은 컴퓨터라도 다른 웹서버를 호스팅하면 다른 포트를 갖는다. 서버와 호스트간에 같은 포트에 연결되어 있어야 한다.
* 포트포워딩은 외부 아이피:포트를 보고 들어온 서버의 리스폰을 사설 아이피:포트가 바로 받는 것이다.
* dynamic static IP의 차이가 dynamic은 ISP가 IP를 돌려가며 공급한다. 따라서 서버같은 걸 운영하기 위해서는 추가 요금을 지불해 static IP를 구매해야한다.
* DHCP(dynamic host configuration protocol) 사설 아이피와 DNS 아이피를 자동으로 지정해준다. 
* 공유기는 DHCP 서버가 깔려있고 각 네트워크 장비들은 DHCP 클라이언트가 있다. [8c:85:90:0c:cc] 와 같은 걸로 공유기와 클라이언트가 서로 식별할 수 있다.


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Network-Server)

## REST API

* HTTP Method 
    * get 데이터 조회
    * post 새로운 데이터 추가 
    * put 데이터 전체 수정
    * patch 데이터 일부 수정
    * delete 정보 삭재  

* REST API에 정보를 요청하면 필요없는 정보까지 받아버린다.
* 다른 객체에 저장된 정보라면 필요한 URI에 하나하나 요청해야한다. 
* REST API가 유리한 점은 받아야하는 정보가 정해져있다면 여러 항목을 적는 GraphQL보다는 URI 한줄로 해결 가능한 REST API가 좋다.
* 현재의 REST API는 완벽한 의미의 REST API가 아니다. self-description, HATEOAS하지 않는다. 전자는 IANA에 미디어 타입을 등록하여 명세를 만들어 KEY에 의미를 부여한다. 혹은 profile을 링크에 담아서 같이 통신한다. 후자는 링크를 담아 만족시킬 수 있다.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Network-Server)

## GraphQL

* GraphQL로 업데이트 삭제는 mutation으로 서버개발자가 구현한 클래스를 이용하여 한다.
* 둘중 어느 것을 사용할 지 고민된다면 둘 다 사용해도 괜찮다.



[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Network-Server)