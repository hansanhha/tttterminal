vim 9.x 버전대 기준

* [Help](help)
* [Pattern](#pattern)
* [Movement](#movement)
* [Write](#write)
* [Copy, Paste](#copy,-paste)
* [Edits](#edits)
* [Undo, Redo](#undo,-redo)
* [Repeat](#repeat)
* [Joining, Replacing, Changing](#joining,-replacing,-changing)
* [Macro](#macro)

## Help

:help <query>, :h <help> : 도움말 보기

##  Pattern

##  Movement

###  Line Movement

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

## Copy, Paste

y(yank) : 복사 - vim에서는 register라고 함

p(put, paste) : 붙여넣기

d(delete) : 잘라내기 

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

motion + c + char: motion 만큼 삭제 후 insert 모드 변경

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

