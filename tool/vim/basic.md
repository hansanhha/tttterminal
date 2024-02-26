vim 9.x 버전대 기준

## Basic modes (7가지)

vim은 mode-based workflow를 가지는 텍스트 에디터임(modal text editor)

일반적인 text editor처럼 키 입력이 텍스트로 간주되어 텍스트 파일에 입력되지 않고

각 키 입력(keystroke)이 vim 명령(command)과 짝을 이룸 

vim은 각 모드에 따라 사용자 입력과 처리를 진행함

### Normal mode (keystroke : ESC key)

vim으로 파일을 열면 동작하는 기본 모드임(Command mode라고도 함)

키를 입력하면 파일에 작성되는 대신, 키에 매핑되는 명령(복사, 삭제 등)을 실행하거나 다른 모드로 변경할 수 있음

다른 모드에서 ESC를 누르면 Normal mode로 변경됨

### Insert mode (keystroke : i)

Normal mode에서 i를 누르면 Insert mode로 변경됨

말그대로 입력 모드

텍스트를 입력하면 파일에 작성됨

### Visual mode (keystroke : v)

Normal mode에서 v를 누르면 visual mode로 변경됨

마우스가 없던 시절 visual mode를 통해 방향키로 텍스트 범위를 선택하여 명령을 실행함

visual mode는 라인을 기준으로 텍스트를 선택하고 visual block mode는 블록 단위로 텍스트를 선택함

visual block mode : ctrl + v

### Select mode (keystroke : gh)

Visual mode와 비슷하게 텍스트를 선택함

키를 입력하면 선택된 텍스트들이 삭제되면서 Insert mode로 변경됨

### Command line mode(Cmdline mode)

Ex 명령(keystroke : :)

Pattern search 명령 (keystroke : ?, /)

filter 명령

을 사용할 수 있는 모드임

Normal mode에서 매핑되는 키 입력을 누르면 된다

### Ex mode (keystroke : :)

Cmdline 모드와 유사하지만 명령을 입력한 후 Ex mode를 유지함

### Terminal-Job mode

## Additional modes (7가지)


## Commands

### Pattern

### Movement

#### Line Movement

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

nunmber + G : 특정 번호의 라인으로 이동

---

Ctrl + u(up) : 위로 스크롤

Ctrl + d(down) : 아래로 스크롤

#### Word Movement

mac os의 option + 방향키처럼 단어를 기준으로 이동할 수 있음

* 커서가 단어의 앞 쪽에 위치함
    * w : 다음 단어
     * b : 이전 단어

* 커서가 단어의 끝 쪽에 위치함
    * e : 다음 단어
    * ge : 이전 단어

### Undo, Redo

### inpust
