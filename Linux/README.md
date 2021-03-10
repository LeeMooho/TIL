# Index of Linux

* [기본 지식](기본-지식)
* [git](#git)

## 기본 지식
* 후술의 [한글] 명령어에 포함된다는 의미.

* ls 현재 디렉토리의 파일 목록을 출력하는 명령어. (ls -al ls -l 같이 파라미터를 변경하여 더욱 다양한 명령을 내릴 수 있다.)
* pwd 현재 위치하고 있는 디렉토리를 알려주는 명령어
* mkdir [새로 생성할 디렉토리명]
* mkdir -p dir1/dir2/dir3/dir4 등 여러 디렉토리를 만들 수 있다.
* cd [이동할 디렉토리의 경로명] (기본적으로 자식 디렉토리로 이동하고 자유롭게 이동하기 위해서는 cd [(최상위디렉토리 생량)/파일명/파일명]으로 이동 가능하다. 한단계 위로 이동은 cd..하면 된다.)
tab을 누르면 자동완성 기능을 제공한다.
* rm [파일명] 파일을 삭제함. 
* 명령을 성공적으로 수행하면 아무것도 안 뜨고 오류가 발생할 시에만 에러 메세지가 나온다. 
* rm -r [디렉토리명/]  디렉토리를 삭제하기 위해서는 사용한다. 
* 명령어 --help하면 도움말이 나온다.
* man 명령어  명령어의 상세 설명을 알려줌. /키워드 를 치면 관련 키워드가 검색되고 q로 상세설명을 종료하고 n으로 이동가능. 
* 유닉스계열은 파일이나 디렉토리 앞에 .이 있으면 숨기파일이지만 ls -a하면 모두 볼 수 있다. 
* 리눅스는 대문자, 소문자를 구분하며 파라미터가 바뀐다.
* cp [파일 위치및 파일이름] (공백) [목적지 파일 위치및 파일 이름] -> 파일 복사
* mv는 파일을 이동시킴. 혹은 파일이름을 변경할 때도 사용가능.
* sudo 관리자 권한으로 실행. nano를 치면 nano 편집기를 사용할 수 있다. 
* nano 파일명 명령어로 파일을 생성할 수도 있다.
* cat [파일명] 파일의 내용을 현재 화면에 출력.
* ^는 ctrl 키이다.
* ^6으로 블록단위로 선택가능.


 grep [찾고싶은 키워드] 공백 [파일명] 으로 파일에 들어있는 키워드를 검색해주는 명령어.
 
 ps aux 현재 실행중인 프로그램.
 

 ls -l > result.txt standard 출력 결과를 파일로 저장. 꺽쇠로 명령. 1> 로 써도 된다.


package manager
* package manager가 기본적으로 설치되어 있다. 종류로는 apt와 yum이 있고 후술한 내용은 apt에 관한 내용들이다. 
apt-get update; 다운받을 수 있는 소프트웨어 목록 갱신
apt-cache search 로 소프트웨어 검색 가능.
apt-get install [소프트웨어 이름] 으로 다운.
apt-get upgrade 로 모든 소프트웨어 업그레이드.
apt-get remove [이름]으로 소프트웨어 삭제.


wget [다운로드주소]로 파일을 다운로드 할 수 있다.
wget -O [파일명] [주소] [다른이름]으로 저장.

 
 특징

 한 라인에 두 명령어를 넣으면 세미클론으로 구분한다. 명령 완료까지 오래 걸린다면 명령어로 제어했을 때 얻을 수 있는 이점. 
 
 파이프라인 하나의 프로세스의 결과를 다른 프로세스의 입력으로 사용하는 것. 역슬래쉬를 이용해서 사용.
 ls --help | grep sort help설명에서 sort 키워드를 검색.
 

만일 에러를 로그로 표시하고 싶다면 2>으로 명령해야한다.
 cat hello.txt 는 파일을 argument로 받아서 실행하는 것이고
 반대로 cat < hello.txt 는 파일안의 내용을 standard input으로 받아서 실행하는 것. 
 main의 argument가 명령어의 파라미터이다.
 
 head는  파일의 10줄 출력. head -n1는 1줄 출력.
 
 쉘은 사용자가 명령을 입력하면 그 명령을 컴퓨터가 이해할 수 있도록 하는 프로그램. 여러 쉘이 존재함.
 커널은 실제로 일을 하는 것
 모든 로그 파일은 *.log
 cd 탭 두번이면 현재 위치의 디렉토리를 표시함.
 bash는 쉘의 일종. zsh이라는 것도 존재.
 /bin에는 유닉스의 기본적인 프로그램들이 존재한다.

 


쉘 스크립트를 작성할 때에는 nano 파일명으로 스크립트를 열고
 #!/bin/bash (bash라는 프로그램이 읽어라는 명령.)
 if ! [ -d bak ] then; bak이라는 디렉토리가 존재하지 않는다면
탭 mkdir bak
fi 조건문이 종료.
cp *.log bak 

chmod +x 파일명 으로 실행가능한 권한을 부여.
실행가능한 프로그램은 바이너리 bin이라고 불림. linux directory 를 검색하면 각 폴더 이름의 의미를 알 수 있다.
맨 앞에 #, ##이 있으면 주석처리.
ps aux는 백그라운드에서 실행되는 모든 프로세스를 출력.
PID 프로세스 아이디.
sudo kill 프로세스아이디 를 넣으면 프로세스 강제 종료 가능.
top, htop으로 클릭도 가능하고 정렬도 가능함.


locate 파일명 은 파일명을 가진 모든 파일을 검색. 이때 디렉토리를 뒤져가며 찾는 것이아니라 mlocate라는 데이터베이스로 검색을 한다. mlocate는 updatedb로 정기적으로 갱신한다.

find는 다양하게 사용이 가능한 파일 탐색기
/ 루트. ./ 현재 디렉토리의 자식, ~는 홈디렉터리(권한이 필요없음.)
whereis 명령어 로 명령어의 위치를 알 수 있다. ls가 현재 디렉토리에 없어도 $path에 포함되어 있으므로 어디에서든 실행가능하다. $path는 리눅스에서 기본으로 설정되어 있는것이고 이런 것을 환경변수라고 한다.
ctrl + z로 현재 실행중인 프로그램을 백그라운드로 보내고 다른 작업을 할 수 있다. fg 명령어를 사용하면 다시 백그라운드 프로그램으로 돌아갈 수 있다.
jobs는 백그라운드에 존재하는 프로그램을 출력. 여러개가 존재하면 +,-가 존재하는데 +는 fg 실행시 나오는 것. -는 그 다음 실행할 것. 순서를 바꾸고 실행하고 싶으면 fg %숫자 로 원하는 백그라운드 프로그램을 호출할 수 있다.
백그라운드 종료는 kill %숫자 로 종료시킨다.
kill -9 %숫자 로 강력하게 종료시킨다.
ls -R(ls -alR) 는 모든 디렉토리와 파일을 출력. 
명령어 맨뒤에 &가 있으면 백그라운드로 명령 실행.


sudo service 파일명 start으로 daemon 즉 서버와 같이 계속 켜져있는 프로그램을 실행.
sudo service 파일명 stop daempn 종료.

시작프로그램으로 설정하려면 etc폴더의 CLI방식이면 rc3.d/ GUI 방식이면 rc5.d/ 폴더에서 S로 링크가 걸려있으면 자동으로 켜지고 숫자는 우선순위를 표시.

cron 정기적으로 명령을 실행하는 명령어(메일 시스템같이 일단 보냈다고 하고 서버에서 여유가 생기면 보냄.)
crontab -e 으로 들어가 설정 가능.
date는 현재 시간을 출력.
date >> date.log 는 현재 시간을 date.log파일에 끝에 추가됨. 
tail 파일명 파일의 마지막 줄을 출력.
tail -f 파일명은 파일을 모니터링하고 있다가 줄이 바뀌면 리프레시하고 출력해줌.
ctrl + c 취소

2>&1 은 표준 에러를 표준 출력으로 리다이렉션함.

alias l='ls -al' 하면 명령어를 다른 이름으로 사용가능.
취소는 ^C
echo $SHELL 쉘 확인
cd ~ 홈 디렉토리로 이동.
.bashrc 는 자동실행 스크립트이다.

 


id 자신의 사용자 정보를 확인할 수 있는 명령어로
who 현재 시스템에 누가 접속하는지 확인 가능. 
exit 컴퓨터를 빠져나가는 명령어.

명령어 앞에 $는 일반 사용자 #은 슈퍼유저이다. 슈퍼유저 이름은 보통 root.
su 사용자 변경, 슈퍼 유저도 될 수 있음(su - root) 일반사용자로 바꾸려면 exit 명령어
sudo passwd -u root 관리자 비번 해체
sudo passwd -l root 관리자 비번 락
/root 는 루트 사용자의 홈 디렉토리
/home에는 일반 사용자의 홈 디렉토리들이 있다.

sudo useradd -m 사용자이름 일반 사용자 생성. 처음에는 sudo를 사용할 수 없고 나중에 설정이 필요함. 처음에는 패스워드가 안 걸려있기 때문에 들어갈 수 없다.
sudo passwd 사용자이름 으로 패스워드를 설정가능.


권한
-rw-rw-r-- 1 사용자 그룹 0 날짜 파일명
- 일반 파일 rw-rw-r-- 1 사용자 그룹 0 날짜 파일명
d 디렉토리 rw-rw-r-- 1 사용자 그룹 0 날짜 파일명
 rw-rw-r--는 3칸씩 사용자의 권한, 그룹의 권한, other의 권한. acces mode라고 하며 chmod로 권한을 변경할 수 있다. 쓰기 권한을 가지고 있는 사용자가 chmod o-r 파일명 으로 파일의 권한에서 other의 권한 중 r를 제한. -가 아니라 +라면 권한 추가. 자신의 것이라도 권한을 제한할 수 있다.
rwx : read, write, excute 권한

sh확장자 파일에 
#!/bin/bash 
명령어들
로 실행하면 실행 권한 유무를 따지나 /bin/bash 파일명.sh로 실행하면 읽기 권한만 따짐.

디렉토리안에 파일을 확인하는 것은 r이고 파일 생성은 w, 디렉토리안에 들어가는 것은 x이다.
chmod -R o+w 파일명하면 파일명이 가지고 있는 모든 파일들의 권한을 변경한다. 
파일 권한은 세자리 숫자를 넣어서 user, group, other을 한꺼번에 변경 할 수 도 있다.
!!는 직전에 입력했던 명령어 재실행.
groupadd 그룹명 으로 그룹에 유저 추가.
/etc/group 을 열면 그룹의 종류를 확인할 수 있다.

elinks 로 쉘 환경에서 브라우징이 가능하다.
ip addr로 아이피 주소를 알 수 있다.
아파치 설치후에 elinks http://10.0.2.15
리눅스로 html를 만들고 업로드할 수 도 있다. 보통 /var/www/html에 있음.
/etc애 프로그램이 있고 config를 이용하여 환경 설정을 변경할 수 있다.


ssh는 원격으로 셀을 조종하는 것. 서버측에도 클라이언트 측에도 ssh가 있어야한다. 보통 윈도우에는 기본적으로 설치되어 있음.

apt-get install openssh-server openssh-client로 설치.
service ssh start 함.
클라이언트 측에서 ssh 컴퓨터이름@ 서버 아이피를 입력. 그러면 이제 클라이언트에서 서버를 제어할 수 있다. 명령을 내리면 그대로 따름.

rsync (remote) 원격으로 독립되어 있는 컴퓨터를 인터넷을 통해서 동기화 시킴. 모든 파일을 보내는 것이 아닌 없는 파일만 보냄.
rsync -a src dest 하면 dest라는 디렉토리 안에 src라는 파일이 생김.
rsync -a src/ dest src안의 파일들이 dest로 이동. 

 


touch는 파일 생성 명령어 touch test{1..10} 하면 test.1~test.10 생성됨.

ssh-keygen을 이용하면 비번 없이 연결가능.
id_rsa는 private키로 최우선 보안 사항.
id_rsa.pub 는 공개키이다. 이 파일을 가지고 있는 컴퓨터는 ssh인증없이 연결가능하다.
; 앞의 명령어가 실패해도 다음 명령어가 실행. && 앞의 명령어가 성공했을 떄 다음 명령어가 실행. & 앞의 명령어를 백그라운드로 돌리고 뒤의 명령어를 실행.

[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Linux)


## git
* 후술할 때 [한글] 은 명령어의 일부분이다.

* git clone [깃의 주소] [새로운 다이렉트주소] 로 다운받을 수 있다.
* git을 다운 받아서 git bash를 실행.
* git init 현재 위치한 빈 디렉토리를 리포지토리로 지정. 
* git status 현재 git의 상태. 변경하면 깃을 add해줘야만 staging area로 올라온다.
* git add [파일명] 이제 깃이 파일의 변경을 감지함. 폴더도 가능.
* git add . 하면 현재 위치의 모든 파일들을 stage에 올려놓음.
* git commit 하면 에디터가 나와서 장문의 커밋도 가능하다.
* git commit -m [contents] 커밋과 커밋내용을 에디터를 열지 않고 할 수도 있다.

* git commit -am [contents]  위와 동일하나 add와 commit도 같이함. 
* git log 파일의 버전 히스토리를 확인할 수 잇다. head는 현재 가르키고 있는 버전을 의미.
* git diff 파일 버전의 차이를 알려준다.
* git checkout [커밋아이디] 저장소가 커밋될 떄의 상태로 돌아간다. 커밋 아이디는 git log에서 확인할 수 있다.

* git chechout master 최신 버전으로 돌아간다. master말고 branch도 가능하다.

* git reset --hard [깃아이디] 그 버전의 깃으로 들어감. soft, mixed도 확인해 볼것.
* git revert 삭제와 보존을 둘 다 할 수 있다. revert는 reset과 한 버전 뒤의 내용은 삭제하고 그 전의 것으로 돌아감. 만일 오래된 버전으로  돌아가려면 한단계씩 역순으로 revert해줘야한다. 그 버전의 변경 사항만 돌려주는 기능이다.
* git checkout -b [이름] 이름으로 브런치를 만듬.

* git branch 이름 하면 이름을 가진 브랜치가 생성.

* git log --all --graph --oneline 이라는 옵션들이 존재한다.
* git branch 하면 브랜치의 목록을 보여줌. 앞에 *가 있으면 그 브랜치에 속해있다는 의미.

* branch가 생성전의 원본이되는 파일을 base라고 함. 합쳐지면 merge commit이라고 함.
* git commit --amend 하면 이미 커밋한 것도 커밋 메시지 내용 변경이 가능.
* merge하기 위해서는 master branch에서 git merge 병합할 branch이름 으로 새로운 깃 생성 가능.
* git 을 merge하면 보통 없는 부분을 추가함.
* 2way merge에서는 base와 관계 없이 branch 간의 내용이 다른 것은 모두 conflict가 일어나지만 기본이 되는  3way merge에서는 base와 비교하여 변화가 있는 것을 merge한다.
* checkout은 head를 제어하는 것.
* reset은 branch의 버전을 master가 가르키는 버전으로 roll-back하는 것.
* git remote add [원격저장소의별명] [https주소] 바로 push하면 안되고 master와 local 간에 동기화를 시켜주어야 함. 즉
* git push -u origin master 를 입력후에 push.
* git remote -v 연결된 저장소 목록을 출력.
* git push --set-upstream [깃의별명] master 하면 git push 자동으로 설정된 리포지토리의 마스터 브랜치로 자동으로 푸쉬됨.
* git pull은 변경사항만 가져온다.
* git pull 은 git fetch; git merge FETCH_HEAD와 같다. fetch는 원격저장소를 갱신.
* git cherry-pick [커밋아이디] 하면 커밋아이디의 내용을 가져올 수 있다.
* git rebase branch이동   이동하려는 브랜치에 head를 둔후에 명령. 단순히 이동시키는 것이 아닌 내용도 병합함.
* fork는 repository를 복사하는 것. 내가 repository의 권한이 없다면 push를 해서 권리자에게 merge를 요청


[뒤로](https://github.com/LeeMooho/TIL)/[위로](#Index-of-Linux)