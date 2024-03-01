vim 9.x 버전대 기준

* [Help](help)
* [Pattern](#pattern)
* [Movement](#movement)
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

## Edit

ZZ, :wq, :wqa : 파일 저장 후 나가기

ZQ, :q! : 저장하지 않고 나가기

## Undo, Redo

u : 되돌리기

Ctrl + r : 앞돌리기



