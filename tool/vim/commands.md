vim 9.x 버전대 기준

* [Help](help)
* [Seaching](#searching)
* [Movement](#movement)
* [Write](#write)
* [Copy, Paste, Cut](#copy,-paste,-cut)
* [Marks](#marks)
* [Filtering](#filtering)
* [Edits](#edits)
* [Undo, Redo](#undo,-redo)
* [Repeat](#repeat)
* [Joining, Replacing, Changing](#joining,-replacing,-changing)
* [Macro](#macro)
* [Digraphs](#digraphs)

## Help

:help <query>, :h <help> : 도움말 보기

## Searching

### Simple Searches 

/string : 문자열 검색, 엔터 입력 시 문자열 입력 종료

/string\`*[]^%?~$` : 특수문자([]^%?~$`)를 포함해서 검색할 경우 특수문자 앞에 \ 명시

n : 검색된 다음 문자열로 이동

shift + n : 검색된 이전 문자열로 이동

/<Up>, /<Down> : Page Up,Down 키를 누르면 검색 history를 볼 수 있음

### Highlighting

hl - highlighting

:set hlsearch : 하이라이팅 켜기

:set nohlsearch : 하이라이팅 끄)기

:nohlsearch : 현재 검색된 문자열만 하이라이팅 끄기

### Incremental Searches

원래는 검색할 문자열을 모두 입력하고 엔터를 눌러야 검색이 됨

Incremental Search의 경우 문자열 검색 시 바로 검색됨(highlighting을 켜야 표시됨)

inc : incremental

:set incsearch : incremental search 켜기

:set noincsearch : incremental seach 끄기

### Regular Expressions

^ : 라인 시작, /^the - 라인 맨 앞에서 the로 시작하는 문자열 검색

$ : 라인 끝, /the% - 라인 맨 뒤에서 the로 끝나는 문자열 검색

. : 아무 단일 문자열 매칭, /t.e - the, tae 등의 문자열 검색

## Movement

### Line Movement

hjkl 왼쪽 아래 위 오른쪽

---

0 : 라인 맨 앞 

$ : 라인 맨 뒤

^ : 라인 텍스트 맨 앞(공백 제외)  

---

% : 매칭되는 괄호로 이동

---

gg : 파일의 맨 위

G : 파일의 맨 아래

number + G : 특정 번호의 라인으로 이동

---

Ctrl + u(up) : 위로 스크롤

Ctrl + d(down) : 아래로 스크롤

### Word Movement

mac os의 option + 방향키처럼 단어를 기준으로 이동할 수 있음

* 커서가 단어의 앞 쪽에 위치함
    * w : 다음 단어
     * b : 이전 단어

* 커서가 단어의 끝 쪽에 위치함
    * e : 다음 단어
    * ge : 이전 단어

## Write

i(insert) : 커서 기준 insert 모드 

a(append) : 커서를 character로 옮기고 insert 모드

I : 커서를 라인의 맨 앞으로 옮기고 insert 모드

A : 커서를 라인의 맨 뒤로 옮기고 insert 모드

o : 커서 기준 한 줄 내리고 insert 모드

O : 커서 기준 한 줄 올리고 insert 모드

## Copy, Paste, Cut

y(yanks) : 복사 - vim에서는 register라고 함

p(put, paste) : 붙여넣기(라인을 잘라낸 경우 커서의 다음 줄에 붙여넣고, 부분만 잘라낸 경우 커서의 다음에 붙여넣음)

d(delete) : 잘라내기

dd : 라인 잘라내기

x : 문자 잘라내기

## Marks

m + a-z 또는 0-9 : 커서가 있는 곳에 mark 설정, mark로 설정한 라인을 옮기거나 삭제하면 mark가 삭제됨

' + 설정문자 : 홑따옴표, 지정한 mark 라인으로 이동

` + 설정문자 : 백틱, 지정한 mark 라인과 컬럼으로 이동

:marks : 설정한 marks 표시

### Marks + Yanks

* 특정 라인 mark - ma
* 다른 라인으로 이동한 후 mark까지 복사 - y'a (현재 라인부터 mark a까지 복사)
* 붙여넣기 - p

## Filtering

UNIX에서 filter란 표준 입력으로 데이터를 받아 처리한 후 그 결과를 표준 출력으로 내보내는 프로그램을 의미함

비슷하게 vim의 filtering은 특정 텍스트 범위(input)를 외부 프로그램(command)에 주고, 그 결과를 해당 텍스트 범위에 반영함(output)

!motion + command : 현재 커서부터 motion으로 지정한 텍스트 범위만큼 외부 프로그램(command)을 적용함

!!motion command : 현재 라인에 외부 프로그램(command)의 결과를 반영함 - 표준 입력을 읽지 않기 때문에 filtering은 아니고, 해당 라인에 결과를 반영하기만 함

**예시**

!5jsort : 현재 커서 기준 5개 라인 정렬

!!date : 현재 라인에 date 명령 적용

!!ls : 현재 라인에 vim 파일이 위치한 디렉토리 ls 명령 적용

## Edit

:w(write) : 저장

:q(quit) : 나가기

ZZ, :wq, :wqa : 파일 저장 후 나가기

ZQ, :q! : 저장하지 않고 나가기

## Undo, Redo

u : undo

Ctrl + r : redo

## Repeat

. : 마지막 command 수행


## Joining, Replacing, Changing

### Joining

J : 커서가 위치한 곳과 아래 줄 join

### Replacing

r + char : 커서가 위치한 곳의 문자를 char로 변경

motion + r + char : 커서가 위치한 곳부터 motion만큼 char로 변경 

### Changing

cw : 단어 삭제 후 insert 모드 변경

motion + c + char: motio

n 만큼 삭제 후 insert 모드 변경

~ : 해당 char의 대소문자 변경(소문자 -> 대문자, 대문자 -> 소문자)

## Macro

.은 마지막에 수행한 하나의 명령을 반복하는 명령

매크로는 수행할 명령들을 기록해서 반복 수행하는 기능

### 동작과정

1. 매크로 키 지정 및 기록시작 : qkey
2. 수행할 명령 실행
3. 매크로 종료 : q

### 매크로 실행

@macroKey : 키에 매핑된 매크로 실행

### 예시

헤더 파일 명만 있는 텍스트들을 #include "filename"로 변경

**before**
```
stdio.h
fcntl.h
unistd.h
stdlib.h
```

**after**
```
#include “stdio.h”
#include “fcntl.h”
#include “unistd.h”
#include “stdlib.h”
```

1. 매크로 키 지정 및 기록 시작
    1. qa 입력, 하단에 recording @a라고 표시됨
2. 기록
    1. ^ : 라인의 맨 앞으로 커서 이동(공백 제외)
    2. i#include "<Esc> : 텍스트 입력
    3. A“<Esc> : 텍스트 입력
    4. j : 다음 줄로 이동
3. 기록 종료
    1. q 입력
4. 사용
    1. 매크로를 적용할 곳에 @a 입력

## Digraphs

이중 문자를 사용해야 될 경우

1. insert 모드 상태에서 CTRL + K 입력
2. 원하는 이중문자와 매핑된 문자 입력
3. 이중문자로 변환

매핑 문자는 :digraphs로 확인


