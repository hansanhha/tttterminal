vim 9.x 버전대 기준

* [Help](help)
* [Pattern](#pattern)
* [Movement](#movement)
* [Write](#write)
* [Copy, Paste](#copy,-paste)
* [Edits](#edits)
* [Undo, Redo](#undo,-redo)

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



