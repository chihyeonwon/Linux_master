## 시험일정

## 24.05.04 1차 합격
![image](https://github.com/chihyeonwon/Linux_master/assets/58906858/9a80fafc-5686-4a49-a5c2-d48b27e57fb8)

## 2차 접수 24.06.08 Seoul 2시
![image](https://github.com/chihyeonwon/Linux_master/assets/58906858/6f47d706-6aa2-4280-ade9-e8369332b696)

## 1차 50문제 한 문제 CBT
## 2차 80문제 CBT
```
신분증, 수험표(가채점용)

Cent OS 7 -> 21년도 기출부터 적용, 기출풀고 틀린문제 개념 정리, 반복
21~23년 10회 기출
```
24.05.05
```
소유권 변경 -> chown(소유자, 그룹), chgrp(그룹만)
허가권 변경 -> chmod

-R 옵션으로 하위 모든 파일에 대한 소유권과 허가권을 변경할 수 있음

chown 옵션 소유자or:그룹명 파일명 (앞에 콜론으로 소유자와 그룹을 구분함)

ls -l 파일형식과 허가권을 알 수 있다.
파일 형식은 허가권 맨 앞 한자리

- : 일반파일, d 디렉토리파일, s 소켓, p 파이프, I 바로가기 아이콘(심볼릭), c 문자 특수

허가권은 rwx로 8진수 숫자모드로 지정한다.
```
24.05.06
```
ext3 : ex2의 확장판, 저널링 파일 시스템 
저널링 파일 시스템 : 저널(로그)를 이용한 빠르면서도 안정적인 복구
JFS : IBM사의 독자적인 저널링 파일 시스템

네트워크 파일 시스템
CIFS : SMB를 확장한 파일 시스템
NFS : 네트워크 파일 시스템

기타 파일 시스템
NTFS : 윈도우 기반 파일 시스템
UDF : ISO 9660 파일 시스템 대체용

mount : 디바이스와 디렉터리를 연결하는 명령어
unmount : 디바이스와 디렉터리 연결을 해제하는 명령어

mount -t smbfs : 삼파 파일 시스템 마운트
mount -o loop : iso 마운트
-o remount : 파티션을 재마운트
-o noatime : 파일이 변경되기 전까지 access time이 변경되지 않음

eject : 보조기억장치의 미디어를 해제하고 장치를 제거하는 명령어
eject -r : 시디롬 마운트 해제
eject -f : 플로피 마운트 해제

fdisk : 파티션의 생성, 기존 파티션 삭제 등을 수행
fdisk -v : fdisk 버전 표시
fdisk -n : 파티션 생성
fdisk -d : 파티션 삭제
fdsik -p : 디스크 정보 표시

mkfs : 리눅스 파일 시스템 생성하는 명령어
mkfs -t 파일 시스템 : 생성할 파일 시스템 타입 지정
mkfs -c : 파일 시스템 생성 전 배드블록을 검사

mke2fs : ext2, 3, 4 타입의 파일 시스템을 생성하는 명령어
mke2fs -t 파일 시스템 타입 지정
mke2fs -j : 저널링 파일 시스템 ext3로 지정

fsck : 무결성을 검증하고 대화식으로 복구하는 명령어
/lost+found 디렉토리에서 오류를 수정하게 되며 복구되면 파일은 사라진다.

du : 디스크 사용량을 확인하는 명령어
df : 마운트된 디스크의 하드디스크 용량 확인 명령어

-h : 용량 단위로 표시
-T : 파일 시스템 유형과 파티션 정보 출력
-k : 1K 블록사이즈
-i : inode 사용률 확인

셸 : 명령어 해석기, 스크립트 언어, 자체 프로그래밍 기능
$ : 본셸 , % C셸

본셸

ksh : AT&T사의 데이비드 콘이 개발
bash : 리눅스 기본 쉘, GNU 프로젝트, Posix와 호환

C셸

csh : C언어의 특징, 빌조이가 개발, 히스토리, 별명, 작업제어
tcsh : csh의 확장판, 명령어 편집 기능 제공

셸 확인 명령어 : /etc/shells = chsh -l : 사용 가능한 셸을 나열한다.

셸 변경 명령어 :
chsh -s 계정명 셸(일반 사용자 환경)
usermod -s 셸 계정명(관리자 환경)

환경변수(전역변수) : env 대문자
셸 변수(지역변수) : set

PS1 : 셸 프롬프트 선언 시 사용
PS2 : 2차 셸 프롬프트 선언 시 사용
USER : 사용자이름
PWD : 현재 디렉토리 절대경로명
TERM : 터미널 종류의 이름
LANG : 기본 지원 언어

프롬프트 설정 방식
\W : 마지막 디렉터리만 표시
\w : 현재 작업중인 디렉터리 절대 경로
\u : 현재 사용자의 이름
\h : 호스트 이름

전역 설정 파일 : etc로 시작
지역 설정 파일 : 홈디렉토리에서 숨김파일로 시작

/etc/profile : 전역, 모든 사용자 환경설정
/etc/bashrc : 별칭과 bash에 관련한 함수 모음 전역

~/.bash_profile : 지역, 개개인 사용자 환경설정
~/bashrc : 별칭과 bash에 관련한 함수 모음 지역

bash History
!! : 마지막 실행한 명령어
!n : n번째 실행
!string : string으로 시작하는 명령문
!?문자열? : 문자열을 포함하는 명령문

HISTSIZE : 히스토리의 스택크기
HISTFILESIZE : 히스토리의 물리적인 크기
HISTFILE : 히스토리 파일 위치
HISTTIMEFORMAT : 히스토리 수행 시간 출력 형태 지정
```
## 24.05.07
```
가장 먼저 실행되는 프로세스 : init init의 pid는 1
fork() :새로운 프로세스를 만들때 기존 프로세스를 복제한다.
exec() : 새로운 프로세스를 만들때 기존 프로세스에 코드를 덮어씌운다.

데몬 : 리눅스 시스템이 부팅 시 자동으로 실행되는 백그라운드 프로세스

stand alone(단독실행) : 서비스 요청이 많은 것을 메모리에 상주시킨다
ex) http, mysql, nameserver, sendmail
실행 스크립트 위치 : /etc/inetd.d

inetd 데몬(슈퍼데몬) : 다른 데몬들의 상위에 존재하는 stand alone 데몬
보안상의 이유로 리눅스 커널 2.4부터 xinetd 가 inetd 역할을 수행
ex) FTP, telnet,rlogin

시그널
2 - SIGINT Ctrl+C 입력시 종료
3 - SIGQUIT Ctrl+\ 입력시 코어덤프
9 - SIGKILL 종료
15 - SIGTERM 종료
19 - SIGSTOP 종료
20 - SIGTSTP Ctrl+Z 입력 시 프로세스 대기로 전환
```
## 24.05.07
```
ps -Z : 작업 종료 후 회수되지 않아 메모리에 적재되어 있는 상태
RSS: 실제 사용하는 메모리의 량을 나타낸다.
ps -aux : 현재 실행디ㅗ고 있는 모든 프로세스의 정보를 알 수 있다.
pstree -p : 프로세스 id 값을 프로세스의 정보를 트리구조로 출력한다.
pstree : 실행 중인 프로세스들을 트리 구조로 나타낸다.

jobs : 백그라운드로 실행 중인 프로세스를 확인한다, 프로세스 대기 상태를 확인한다.
ctrl + z : 프로세스 대기 상태로 전환(포어그라운드 프로세스를 백그라운드 프로세스로 전환)
fg 작업번호 혹은 fg %작업번호

백그라운드로 작업하고자 할 때 명령어 뒤에 &를 붙인다.

kill -1 %6 = kill -HUP : 6번인 프로세스에게 재시작요청을 한 번 보낸다.
KILL -9 : 강제 종료
Killall -l : 시그널 목록
Kill -l : 시그널 옵션, 더 자세함
nice : 일반 사용자는 nice값을 증가시킬 수 밖에 없다. 우선순위를 낮출 수 밖에 없다.
renice -0 5546 <- 기존의 값에서 -0으로 변경한다.
nice -10 bash <- 기존 -5에서 +10 -> 5
프로세스 ni값의 범위 : -20 ~ 19 우선순위는 낮을 수록 높다.
top : 운영 상태를 실시간 모니터링 하는 명령어
top 명령어로 실행 중인 상태에서 다양한 명령어를 사용하여 프로세스 상태를 제어할 수 있다.

top -T : 명령어 라인 항목을 ON/OFF 할 수 있다.
top k : 특정 프로세스를 종료할 수 있다.

nohup : 터미널이 닫혀도 실행 중인 프로세스를 백그라운드 프로세스로 작업할 수 있게 해준다.
(명령어 맨 뒤에 &을 붙인다)

crontab : 분, 시, 일, 월, 요일, 명령어
crontab : -u 특정 사용자
-e : 수정
```
## 24.05.08
```
pico편집기 : 복제 프로그램 nano, Aboil Kasar, Pine이라는 e-mail 클라이언트와 같이 배포
pico Ctrl + O : 파일 저장, Ctrl + A : 시작 부분으로 이동 Ctrl + X : 프로그램 종료

emacs 편집기 : 리처드 스톨만이 개발한 고성능 문서 편집기, 강력한 질의, 치환 명령
명령어의 형태가 alt, ctrl 키와의 조합, LISP에 기반의 환경 설정 언어
Ctrl + F: 커서를 오른쪽으로 이동

vi 편집기 : 모드 편집기
vi 편집기에서 특정 문자열 치환 방식 s/바꿀문자열/바뀔문자열/g

vi +num  num으로 이동, 생략일 때는 마지막 줄로 이동한다.
vi :$ : 편집 중인 텍스트 파일의 가장 마지막 줄로 이동
vi n 같은 방향으로 다음 문자열 검색
/ 아래방향으로 검색, ? 위 방향으로 검색

vi -r : 비정상적인 종료되었을 때 파일 복구

.exrc 는 vi 편집기의 환경 설정 등록, 해당 파일에서 set 명령 사용 시에는 :콜론을 붙임
:set nu

vi : 빌조이, vim : 브람 무레나르가 개발

set ai <- 자동 들여쓰기 기능
nano 편집기 <- 윈도우의 메모장과 유사

리눅스에서 사용하는 편집기의 종류 : vi, vim, emacs

gedit 드로그앤 드롭이 가능하고 그롬 데스크톱 환경용으로 개발된 자유 소프트웨어 텍스트 편집기
```
## 24.05.09
```
패키지의 파일 형식 : 패버릴아 패키지명-번호-릴리즈번호-아키텍처번호
아키텍처 : i686 or i586 인텔 cpu 아키텍처

rpm -h : 패키지 설치 과정을 #로 표시한다.
rpm -V 검증 결과 -> S 파일 크기, -V 권한(다이제스트 값)변경, -T 수정일 변경

rpm --force 옵션에 포함되는 옵션 3개 : replacepkgs(재설치), replacefiles(이미설치된것을덮어씀), oldpackage(구버전 다운그레이드)
-qip : rpm 파일에 대한 정보
rpm -e : 패키지 삭제

rpm -Uvh : -U 설치되어있다면 업그레이드, 없다면 설치
rpm -v 검사할때 사용
rpm -ql : 패키지목록
rpm -qi : 패키지정보

데비안 계열 우분투 의존성 해결 -> apt-get
레드햇 계열 의존성 해결 -> yum

yum remove : 패키지 제거
yum search : 패키지에서 문자열 포함된 것 찾기
yum groupinstall : 그룹을 설치하기 위한 방법

데비안 패키지 관리인 deb 파일의 형식 : 패버릴아

dpkg -s : 패키지의 정보 출력
dpkg -i : 지정된 패키지를 설치

apt-get 명령어가 의존성과 충돌성 해결을 위해 참조하는 파일 : /etc/apt/sources.list

데비안 우분투 : dpkg , apt-get
레드햇 : rpm , yum
```
## 24.05.10
```
파일 아카이브 : 다수 개의 파일이나 디렉터리를 하나로 묶는 것
명령어 tar
tar -c : 새로운 아카이브 파일 tar 생성
tar -x : tar로 묶은 것을 원본으로 복원 (묶음 해제)
tar -t : 아키이브 파일 안의 목록 나열
tar -f : 아카이브 파일명 지정
tar -v : 처리하고 있는 파일 정보를 출력
tar -z : gzip으로 압축하거나 해제
tar -J : xz 옵션으로 압축 파일인 tar.xz에 사용

압축률 compress < gzip < bzip2 < xz

.Z compress
.gz gzip
gzip -l 파일 정보를 나타냄
gunzip 파일 압축 해제
zcat 압축 파일의 내용을 출력

.bz2 bzip2, bunzip2

xz -d 강한 파일 압축 해제

컴파일 순서 configure -> make -> make install (일반 파일)
Mysql의 cmake 는 생성과 설치만 한다. cmake -> make install
cmake는 크로스컴파일을 지원, 평행 빌드 지원, 타임스탬프 지원
```
## 24.05.11
```
프린터 인쇄 시스템 LPRng, CUPS

LPRng : BSD 유닉스 계열, 프린터 스풀링과 네트워크 프린터 서버 지원
설정 파일 : /etc/printcap

CUPS : 애플이 개발한 오픈 소스 프린팅 시스템
HTTP 기반의 IPP (포트: 631)를 사용하여 웹 기반으로 프린터를 제어
설정 파일 : /etc/cups

/etc/cups/cupsd.conf : 프린터 데몬 환경 설정 파일
/etc/cups/printers.conf : 프린터 큐 환경 설정
/etc/cups/classes.conf : CUPS 프린터 데몬의 클래스 설정 파일
cupsd : CUPS의 프린터 데몬

cups 인쇄 시스템 : 로컬 접속으로 프린터를 직접 연결할 수 있다.
직렬 포트 : /dev/lp0 파일로 가능
usb 포트 : /dev/usb/lp0 파일로 가능

windows printer via samba : 윈도우 <-> 리눅스 프린터 설정 시 사용 삼바 기반의 smb 프로토콜 사용 smb/cifs

사운드 카드 지원 시스템 : OSS, ALSA

OSS :표준 유닉스에 기반, 유닉스 운영체제에서 사운드를 만들고 캡처

ALSA : 사운드 카드용 장치 드라이버를 제공, gpl 라이센스를 따른다, 사운드 여러 개 장치를 관리

스캐너 지원 : SANE, XSANE

SANE : 이미지 관련 하드웨어를 제워하는 API
SCSI 스캐너 : /dev/sg0, /dev/scanner로 인식
usb 스캐너 : /dev/usb/scanner, /dev/usbscanner로 인식

XSANE : X-Windows 기반의 스캐너 프로그램
x-windows에서 xsane이라고 입력하면 실행
다양한 장치, 이미지 수정 작업을 할 수 있다.
```
## 24.05.14
```
bsd 계열 : lpr, lpq, lprm, lpc
system V 계열 : lp, lpstat, cancel

lpr, lp : 프린터 요청을 한다.
lpr -# : 인쇄할 매수를 지정
lp -n : 인쇄할 매수를 지정

lpq : 큐에 있는 작업 목록을 출력
lpc : 라인프린터 컨트롤 프로그램

lpstat : 프린터 큐의 상태를 확인

alsactl : alsa 사운드 카드를 제어
alsamixer : 커서 라이브러리 기반의 오디오 프로그램
cdparanoia : 오디오 CD로 부터 음악 파일 추출

sane-find-scanner : scsi 스캐너와 usb 스캐너 관련 장치 파일을 찾아주는 명령어
scanimage : 이미지를 스캔
scanimage -d : sane 장치 파일명 입력
scanimage --format : 이미지 형식 지정
scanimage -L : 사용가능한 스캐너 목록 출력

scandf : 여러 개의 사진을 스캔

xcam : GUI 기반으로 스캐너나 카메라로부터 이미지를 스캔
```
## 24.05.15
```








```

## 21년 3월 13일 1회 기출
```

```
## 21년 9월 11일 3회 기출
```

```
## 21년 12월 11일 4회 기출
```

```
## 22년 3월 12일 1회 기출
```

```
## 22년 6월 11일 2회 기출
```

```
## 22년 9월 3일 3회 기출
```

```
## 23년 3월 11일 1회 기출
```

```
## 23년 6월 10일 2회 기출
```

```
## 23년 9월 9일 3회 기출
```

```
## 23년 12월 9일 4회 기출
```

```
