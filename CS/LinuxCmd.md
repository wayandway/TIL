# Linux 명령어 정리
`명령어 [옵션] [인자]` : 리눅스 명령어 기본 구조
<br>

`Ctrl + w` : 단어지우기  <br>
`Ctrl + u` : 행 지우기  <br>
`Ctral + d` : 터미널 끄기1  <br>
`exit` : 터미널 끄기2
<br>

`date` : 현재 날짜 및 시간  <br>
`clear` : 터미널 화면 지우기  <br>
`man [설명 보고싶은 명령어]` : 명령 사용법 상세 설명  <br>
`passwd [로그인ID]` : 사용자 계정 비밀번호 변경
<br>

## 디렉터리 관련 명령
### 현재 디렉터리 확인
`pwd` : 현재 디렉터리의 절대 경로 출력
<br>

### 디렉터리 이동
`cd [디렉터리 (상대경로 or 절대 경로]` : 지정한 디렉터리로 이동
<br>

### 디렉터리 내용 확인
**`ls [옵션] [디렉터리(파일)]` : 디렉터리의 내용 출력**  <br>
[option]  
`ls -a` : 숨김파일까지 확인 <br>
`ls -F` : 파일의 종류 구분 기호까지 출력 - 파일명/ (디렉터리), 파일명@ (심볼릭링크), 파일명\* (실행파일), 파일명 (일반파일)<br>
`ls -aF` : 숨김파일과 파일의 종류 구분 기호까지 출력 (옵션을 순서 상관 없음)  <br>
`ls -l` : 파일들의 (inode에 저장된)상세 정보 출력 (long) <br>
`ls -d` : 디렉터리 자체 정보 확인 (루트 디렉터리 정보 확인할 때 주로 사용)  <br>
`ls -R` : 디렉터리의 서브 디렉터리 내용까지 출력<br>
`ls -i` : 파일의 inode 번호 확인<br>
`dir`, `vdir` : `ls`와 호환 가능, 옵션도 그대로 사용가능
<br>

### 디렉터리 생성
`mkdir [옵션] [디렉터리 (상대경로 or 절대경로)]` : 디렉터리 생성  
ex) `mkdir tmp1 tmp2` 등 여러 개의 디렉터리 생성가능  
[option]  
`mkdir -p temp/mid/han` : 중간 디렉터리를 생성한 후 최종 디렉터리를 만듦 (계층 구조의 디렉터리 한 방에 만들 수 있다는 뜻)
<br>

### 디렉터리 삭제
`rmdir [옵션] [디렉터리]` : 디렉터리 삭제. **디렉터리가 비어있야** 사용가능. 동시에 여러 개 삭제 가능  
`rm -r [디렉터리]`

## 파일 관련 명령
### 파일 내용 출력
**cat** <br>
`cat [옵션] [파일(이 있는 절대경로or상대경로]` : 파일 내용을 출력. 실행파일(바이너리)는 확인 불가. <br>
[option]  
`cat -n [파일]` : 행 번호가 붙어서 출력

**more, less** <br>
`more [옵션] [파일]` : 화면 단위로 출력. `Space Bar` : 다음 화면 출력. `Enter` : 한 행씩 스크롤. `q` : 종료 <br>
`less [파일]` : 화면 단위로 출력. 앞뒤 스크롤 가능. `j` : 다음 행 스크롤. `k` : 이전 행 스크롤. `Space Bar` or `Ctrl+f` : 다음 화면 이동. `Ctrl+b` : 이전 화면 이동

**tail** <br>
`tail [옵션] [파일]` : 파일 뒷부분의 몇 행(기본 값 10행)을 출력  
[option]  
`tail -숫자 [파일]` : (숫자)만큼 뒷부분 행을 출력  
`tail -f [파일]` : 파일 내용이 주기적으로 반복 출력. 파일의 뒷부분에 내용이 추가되면 그 내용이 자동으로 출력되므로, 파일 내용의 변화를 확인할 때 편리. `Ctrl+C`로 종료

**file** <br>
`file [파일의 절대 or 상대경로]` : 파일의 종류 출력. 

<br>

### 파일 복사
**cp** <br>
`cp [옵션] [원본 파일(디렉터리)] [목적 파일(디렉터리)]`  
1. `cp [파일1] [파일2]` : `cp text1 text2` - text1의 내용을 text2라는 새로운 파일로 복사 및 생성  
2. `cp [파일] [디렉터리(미리 만들어져 있어야 함)]` : 해당 파일을 디렉터리 아래에 복사. `cp [파일] [디렉터리/새로운파일명]`으로 하면 새로운 이름으로 설정 가능. 파일을 다른 디렉터리에 복사할 때는 해당 디렉터리에 대한 **쓰기 권한**이 있어야 한다.  
3. `cp [파일1] [파일2] [반드시 디렉터리]` : 해당 디렉터리 아래에 파일들이 복사된다.  
[option]  
`cp -i [파일1] [파일2]` : 파일2가 이미 있다면, 덮어서 복사할 것인지 물어본다. y는 덮어서 복사하고 n은 복사하지 않는다.  
4. `cp -r [디렉터리1] [디렉터리2(없으면 새로 만듦)]` : 디렉터리1을 디렉터리2 아래에 복사. -r 옵션은 필수이다.
<br>

### 파일 이동과 파일명 변경
**mv** <br>
`mv [옵션] [원본 파일(디렉터리)] [목적 파일(디렉터리)]`  
1. `mv [파일1] [파일2]` : 파일1의 이름을 파일2로 변경. 파일2가 이미 존재하면 원본파일의 내용으로 덮어쓰고 기존의 내용이 삭제된다.  
2. `mv [파일] [디렉터리]` : 파일을 지정 디렉터리로 이동  
3. `mv [파일1] [디렉터리/파일2]` : 파일1이 파일2 이름으로 디렉터리 아래로 이동. 파일을 이동할 디렉터리에 **쓰기 권한**이 있어야 한다.  
4. `mv [파일1] [파일2] [반드시 디렉터리]` : 여러 파일을 디렉터리로 이동  
[option]  
`mv -i [파일1] [파일2]` : 파일2가 이미 있다면, 덮어서 이동할 것인지 묻는다. y는 덮어서 이동하고 n은 이동하지 않는다.  
`mv [디렉터리1] [디렉터리2]` : 디렉터리1의 이름이 디렉터리2로 변경된다. 이미 디렉터리2가 있다면, 디렉터리1은 디렉터리2 아래로로 이동한다.
<br>

### 파일 삭제
**rm** <br>
`rm  [옵션] [파일or디렉터리]`

[option] <br>
`rm -i [파일]` : 정말 삭제할 것인지 묻는다. y는 삭제하고 n은 삭제하지 않는다. <br>
`rm -r [디렉터리]` : 빈 디렉터리(rmdir)가 아니어도 삭제 가능. 휴지통 복원 등 복구할 수 없다.
<br>

### 파일 링크 (하드 링크, 심볼릭 링크)
**ln** <br>
`ln [파일1] [파일2]` : 하드 링크 생성. 파일1에 대한 하드 링크 파일2 생성 (하드 링크 : 기존 파일에 새로운 이름을 붙이는 것. 기존 파일과 **inode가 같다**.) <br>
`ls -s [파일1] [파일2]` : 심볼릭 링크 생성. 파일1에 대한 심볼릭 링크 파일2 생성 (심볼릭 링크 : 윈도의 바로가기처럼 원본파일을 가리키는 파일. 기존 파일과 **inode가 다르다**.)

### 파일 관련 기타 명령
**touch** : 빈 파일 만들기, 접근/수정 시간 변경하기<br>
`touch [파일]` : 빈 파일 생성. <br>
`touch [이미 있는 파일]` : 파일의 수정 시간이 현재 시간으로 변경 <br>
`touch -t [[CC]YY]MMDDhhmm[.ss] [파일]` : 파일의 수정 시간 변경 <br>

**grep** : 파일 내용 검색하기 <br>
`grep [옵션] [패턴] [파일]` : 파일 속 지정 문자열(패턴) 검색 <br>
`grep -n [패턴] [파일]` : 행 번호와 함께 출력 <br>

**find** : 파일 찾기<br>
`find [경로] [검색 조건] [동작]` : 디렉터리 계층 구조에서 특정 파일이 어느 디렉터리에 있는지 검색<br>
`find /usr -name ls` : /usr 디렉터리에서 ls파일의 위치 검색 <br>
`find /home -user user1` : user1이 소유한 모든 파일을 검색 <br>
`find /tmp -user user1 -exec rm {} \;` : rm {'/tmp 디렉터리에서 찾은 user1의 모든파일의 경로'} <br>
`find /tmp -user user1 -ok rm {} \;` : rm {'/tmp 디렉터리에서 찾은 user1의 모든파일의 경로'}를 수행하기 전, 파일을 하나씩 확인. y로 답하면 파일 삭제 <br>

**file** : 파일 종류 출력 <br>
`file [파일1] [파일2] ..` : 지정한 파일(들)의 종류를 알려준다.

**whereis, which** : 명령의 위치 찾기 <br>
`whereis [옵션] [명령]` : 환경변수 $PATH와 $MANPATH에 지정된 디렉터리르 검색해 명령파일의 절대경로를 찾는다. <br>
`which [명령]` : 앨리어스나 $PATH 환경변수로 지정된 경로에서 명령파일의 절대경로를 찾는다.

## vi
**vi** <br>
`vi [파일]` : 지정 파일을 편집한다. 파일명을 지정하지 않으면 빈 파일이 열리며, 파일명은 나중에 마지막 행 모드에서 정할 수 있다.

## 셸

### 셸 지정 및 변경
**chsh** <br>
`chsh [-s 지정 셸(절대경로)] [사용자명]` : 사용자 로그인셸을 바꾼다. <br>
`chsh -s /bin/sh user1` : 예시. user1 계정의 로그인셸을 본셸로 변경. <br>

### 출력 명령
**echo, printf** <br>
`echo [-n] [문자열]` : 화면에 한 줄의 문자열을 출력. 모든 셸에서 공통적으로 사용가능하다. (-n : 마지막에 줄바꿈을 하지 않음) <br>
`printf [서식지정자] [인수]` : C언어 출력함수랑 동일하다.

### 표준 출력 리다이렉션
**>, 1>** : 파일 덮어쓰기 <br>
`[명령] (1)> [파일]` : 지정 파일에 명령의 표준 출력 결과물을 저장. ex) `ls -al 1> text` <br>
`set -o noclobber` : 예상치 않게 파일 내용을 덮어쓰는 일을 막아줌. 해제하려면 `set +o noclobber` <br>
`cat > [파일명]` : 키보드의 입력을 새로운 파일로 저장 <br>

**>>** : 파일에 내용 추가하기 <br>
`[명령] >> [파일]` : 명령의 실행 결과를 파일의 끝에 덧붙인다. ex) `date >> text` <br>

### 표준 오류 리다이렉션
**2>** <br>
`[명령] 2> [파일]` : 지정 파일에 표준 오류 결과물을 저장.

### 표준 출력&오류 한 번에 리다이렉션 
`ls . /abc > ls.out 2> ls.err`

### 표준 출력&오류 한 파일로 리다이렉션
`ls . /abc > ls.out 2>&1` : 2>&1 는 2번 파일(표준 오류)을 1번 파일(표준 출력)으로 리다이렉션하라는 뜻이다.

### 오류 메시지 버리기
`[오류 명령] 2> /dev/null`

### 표준 입력 리다이렉션 
`명령 (0)< [파일]` : ex) `cat [파일명]` - 파일의 내용이나 키보드로 입력을 받아 화면에 출력. <를 생략한 것이다.

## 배시셸 환경 설정
### 셸 변수와 환경 변수 출력
**set, env** <Br>
`set` : 셸 변수와 환경 변수 모두 출력. ex)`set | grep '셸 변수/환경 변수` <br>
`env` : 환경변수만 출력. ex) `env | grep 환경변수`

**echo** : 특정 변수 출력 <br>
`echo $SHELL` : 환경변수 SHELL 변수의 값 출력. 변수명 앞에 $를 붙여야 한다.

### 셸 변수와 환경 변수 설정
**셀 변수 정의** <br>
`변수명=문자열` : 변수명과 문자열 사이에 공백 X. 

**export** : 환경 변수 설정 <br>
`export [옵션] [셸 변수]` <br>
`export [셸 변수]`  : 먼저 지정한 셸 변수를 환경 변수로 바꾼다. <br>
`export 변수명=문자열` : 한 번에 환경 변수로 설정 <br>
`export -n [환경 변수]` : 환경 변수 → 셸 변수 로 변경

### 변수 해제
**unset** <br>
`unset [변수]` : 지정한 변수를 해제 <br>

## 앨리어스와 히스토리
### 앨리어스
**alias**  <br>
`alias 이름='명령'` <br>
1. `alias` : 현재 설정된 별칭 목록 출력
2. `alias 이름='명령'` : 명령을 수정해 사용
3. `alias 이름='명령1;명령2;...` : 여러 명령들을 하나의 이름으로 사용

**unalias**  <br>
`unalias 앨리어스` : 앨리어스 삭제

### 히스토리 
**history** <br>
`history` : 명령 입력 기록을 출력한다. <br>
`!!` : 바로 직전의 명령을 재실행한다. <br>
`!번호` : 히스토리에서 해당 번호의 명령을 재실행한다. <br>
`!문자열` : 히스토리에서 해당 문자열로 시작하는 마지막 명령을 재실행한다.

