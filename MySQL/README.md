

# Index of MySQL


* [기본 지식](#기본-지식)


## 기본 지식
* 데이터 베이스는 table을 기능별로 구분한 것.
* CREATE DATABASE 이름; 은 데이터베이스 생성. 
* DROP DATABASE 이름; 은 데이터베이스 삭제. 
* SHOW DATABASES 은 데이터베이스 확인.
* USE 데이터베이스 이름; 데이터 베이스 선택.

* CREATE TABLE 
```
CREATE TABLE 테이블 이름(
id INT(11) NOT NULL AUTO_INCREMENT, -> id 열을 만들고 빈칸 허용 안하고 자동으로 증가 및 생성
title VARCHAR(100) NOT NULL, -> 타이틀 열을 만들고 100글자 미만만 민칸 허용 안하고
description TEXT NULL, ->TEXT 데이터 타입이 허용하는 만큼만 허용하고 공백 ㅇ
created DATETIME NOT NULL, -> 시간과 날짜 표시
PRIMARY KEY(id) -> id를 키값으로 지정.
);
```

* DESC 테이블이름; 테이블의 각 항목의 이름이 나온다. 
행을 추가하려면 
* INSERT INTO 테이블이름 (열 항목1, 열 항목2) VALUES('내용1','내용2') '내용' 대신에 NOW()함수가 들어갈 수 있음.


* 입력된 데이터를 보려면 SELECT * FROM 테이블 이름; 
* 필터링된 데이터를 보려면 SELECT 열항목의 이름 FROM 테이블 이름; -> 선택되지 않은 열항목은 나타나지 않는다. 
* 혹은 SELECT 열항목의 이름 FROM 테이블 이름 WHERE 열항목='조건'; -> 조건이 하나 더 추가된 테이블 열거.  추가로 ORDER BY 열항목 DESC 혹은 LIMIT 2 와 같은 것도 추가할 수 있고 이러한 문법을 sintax라고 한다.

* UPDATE 테이블 이름 SET 열항목='내용', 열항목2='내용' WHERE 열항목=조건; 수정한다. #WHERE을 절대 잊지 않도록한다.

* DELETE FROM 테이블 이름 WHERE 열항목=조건; 삭제한다. #WHERE을 절대 잊지 않도록한다.

* RENAME TABLE 테이블이름 TO 변경할 테이블 이름; 테이블 이름 변경.

* JOIN 기능을 사용하기 위해서는 SELECT * FROM 기준 테이블이름 LEFT JOIN 참조할 테이블이름 ON 기준 테이블이름.참조열 = 참조할 테이블이름.참조열; 
* 위에 코드에서 *을 반점으로 구분된 열항목 이름으로 나열하면 원하는 데이터만 나오게 해서 가독성을 높일 수 있다.
* 열이름을 AS 새로운 이름으로 사용하면 새로운 이름으로 출력된다.

* 서버를 설치하면 MYSQL monitor가 자동으로 설치된다. 
* workbench가 gui기능을 제공하여 더 편하게 느낄 수 있지만 서버에 설치가 안되어 있을 확율이 높다.

* SCHEMA 는 테이블의 집합.

* ALTER TABLE '테이블이름' ADD COLUMN '행명' INT NULL ALTER '들어갈 데이트' 하여 테이블에 열을 추가해 준다.
* .sql 확장자를 가지고 있다. 

*  install --s mysql 해야지 팩키지에 코드가 저장됨.

* ./mysql -uroot 유저권한 -p 패스워드 입력하겠다

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-MySQL)