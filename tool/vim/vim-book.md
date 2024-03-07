**참고**

vim 9.x 버전대 기준

[vim docs](https://vimhelp.org/)

[vim-book](https://www.truth.sk/vim/vimbook-OPL.pdf)

[learn vimscript the hard way](https://learnvimscriptthehardway.stevelosh.com/)

* [Configuration](#configuration)
* [Modes](#modes)
* [Help](help)
* [Seaching](#searching)
* [Movement](#movement)
* [Write](#write)
* [Copy, Paste, Cut](#copy,-paste,-cut)
* [Marks](#marks)
* [Filtering](#filtering)
* [Edits](#edits)
* [Multiple Files](#multiple-files)
* [Windows](#Windows)
* [Buffers](#buffers)
* [Visual Mode](#visual mode)
* [Undo, Redo](#undo,-redo)
* [Repeat](#repeat)
* [Joining, Replacing, Changing](#joining,-replacing,-changing)
* [Macro](#macro)
* [Digraphs](#digraphs)
* [Command for Programming](#command-for-programming)
* [Plugins](#plugins)
* [Key Mapping](#key-mapping)
* [Tabs](#tabs)
* [Fording](#folding)
* [Formatting, Linting](#formatting,-linting)
* [Language Server](#language-server)
* [With Git](#with-git)
* [Vim Scripts](#vim-scripts)
" Configuration  ========================================================= {{{

## Configuration

vim 설정 파일 : ~/.vimrc

직접 만들어서 설정해야됨

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

}}}

" Modes ========================================================= {{{

## Modes

### Basic modes (7가지)

vim은 mode-based workflow를 가지는 텍스트 에디터임(modal text editor)

일반적인 text editor처럼 키 입력이 텍스트로 간주되어 텍스트 파일에 입력되지 않고

각 키 입력(keystroke)이 vim 명령(command)과 짝을 이룸 

vim은 각 모드에 따라 사용자 입력과 처리를 진행함

#### Normal mode (keystroke : ESC key)

vim으로 파일을 열면 동작하는 기본 모드임(Command mode라고도 함)

키를 입력하면 파일에 작성되는 대신, 키에 매핑되는 명령(복사, 삭제 등)을 실행하거나 다른 모드로 변경할 수 있음

다른 모드에서 ESC를 누르면 Normal mode로 변경됨

#### Insert mode (keystroke : i)

Normal mode에서 i를 누르면 Insert mode로 변경됨

말그대로 입력 모드

텍스트를 입력하면 파일에 작성됨

#### Visual mode (keystroke : v)

Normal mode에서 v를 누르면 visual mode로 변경됨

마우스가 없던 시절 visual mode를 통해 방향키로 텍스트 범위를 선택하여 명령을 실행함

visual mode는 라인을 기준으로 텍스트를 선택하고 visual block mode는 블록 단위로 텍스트를 선택함

v : visual 모드

V : visual line 모드

CTRL + v : visual block 모드

#### Select mode (keystroke : gh)

Visual mode와 비슷하게 텍스트를 선택함

키를 입력하면 선택된 텍스트들이 삭제되면서 Insert mode로 변경됨

#### Command line mode(Cmdline mode)

Ex 명령(keystroke : :)

Pattern search 명령 (keystroke : ?, /)

filter 명령

을 사용할 수 있는 모드임

Normal mode에서 매핑되는 키 입력을 누르면 된다

#### Ex mode (keystroke : :)

Cmdline 모드와 유사하지만 명령을 입력한 후 Ex mode를 유지함

#### Terminal-Job mode

### Additional modes (7가지)

}}}

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

` + [ ] ' " : 미리 지정된 mark
* ^ : 현재 세션에서 마지막으로 놓인 커서 위치
* . : 마지막으로 변경된 라인 위치
* " : 파일을 닫았을 때 마지막 커서 위치 mark 
* [, ] : 파일을 닫았을 때 마지막으로 변경하거나 복사한 텍스트의 시작과 끝

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

## Edits

:w(write) : 저장

:q(quit) : 나가기

ZZ, :wq, :wqa : 파일 저장 후 나가기

ZQ, :q! : 저장하지 않고 나가기

:set autowrite : 자동저장 켜기

:set noautowrite : 자동저장 끄기

:vi file, :e file : 현재 파일닫고 다른 파일 열기(현재 파일을 저장하지 않고 사용하면 명령 무시됨)

:vi! file : 경고 무시하고 강제로 다른 파일 열기

:view file : read-only 모드로 파일 열기

## Multiple Files

vi file1 file2 file3 : 여러 개 파일 열기

:next, :n, `<Enter>` : 다음 파일 열기(현재 파일을 저장하지 않거나, 다음 파일이 없으면 동작 X)

:previous, N : 이전 파일 열기(현재 파일을 저장하지 않거나, 다음 파일이 없으면 동작 X)

:count + n, N : count만큼 next, previous 반복하기

:wn, N : 저장하고 이전, 다음 파일 열기

:n!, N! : 강제로 이전, 다음 파일 열기

:first, :last : 첫 파일 또는 마지막 파일 열기

:args : 현재 파일 작업 중인 파일 표시

count + CTRL + ^ : 지정한 번호의 파일 열기

## Windows

윈도우 관련 단축키는 모두 CTRL + w로 시작함(window key : CTRL + W)

대소문자 구분 필요(동작이 다름)

### Window Open, Close

:split, window key + s(split) : 현재 파일 새 윈도우 열기

:sview : 현재 파일 read-only 모드로 새 윈도우 열기

:new, window key + n(new) : 새로운 파일 새 윈도우 열기 

:sp(split) file : 다른 파일 열기

:sp +/command file : 다른 파일 열기(명령 적용)

:number split file : 다른 파일 열기(새 윈도우 사이즈 조절)

window key + c, q : 윈도우 닫기

### WIndow Movement

window key + H,J,K,L : 방향키 방향으로 윈도우 이동

### Cursor Movement

window key + h,j,k,l : 방향키 방향의 윈도우로 커서 이동

window key + w : 다음 윈도우로 커서 이동 

### Chainging Window Size

window key + + : 윈도우 크기 늘리기

window key + - : 윈도우 크기 줄이기

window key + = : 모든 윈도우 크기 통일

window key + _ : 현재 윈도우 최대 크기

## Buffers

Buffer는 편집하고 있는 파일의 복사본임

vim editor로 파일을 열면 메모리에 내용이 로드됨(파일마다 고유 버퍼 id를 가짐, 1:1 관계)

버퍼 변경을 마치면 버퍼의 내용(content)이 파일에 작성됨(marks, setting, 등 파일에 관련된 내용도 포함)

### Screen, Window, Buffer

screen : vim이 실행되는 터미널 전체 화면

window : screen 내에서 분할된 편집 화면(window당 하나의 버퍼를 보여줄 수 있음)

buffer : 메모리에 로드된 파일 내용

### Buffer State

buffer의 3가지 상태
* Active   : 현재 윈도우에 표시된 파일 (스크린에 윈도우가 있으면 버퍼가 있는 상태임)
* Hidden, InActive   : 버퍼가 메모리에 로드되어 있지만 윈도우에 표시되지 않는 상태
    * hidden 상태인 경우 파일을 변경하면 메모리에 임시 저장해두고, 다른 buffer로 스위칭할 수 있음
    * set hidden 설정 필요

buffer 상태 표시
* a : active buffer
* - : inactive buffer
* h : hidden buffer
* % : current window
* # : alternative buffer(현재 윈도우에서 마지막으로 수정한 파일)
* + : modified buffer
* = : read-only buffer
* x : read error buffer

### Selecting Buffer

:buffer number : 버퍼 번호로 선택

:b(buffer) file : 파일 이름으로 선택

:sb file, number : 새로운 윈도우로 열기

:bn, bN : 다음, 이전 버퍼 선택 

### Control Buffer

:buffers, :ls, :files : 버퍼 리스트 보기

:bdelete file : 특정 버퍼 삭제

:badd file : 특정 버퍼 추가

## Visual Mode

Visual, Line, Block 동일

텍스트 선택 + >, < : 들여쓰기(shift width)

shitfwidth 설정 값 만큼 공백 이동(set shitfwidth=4)

텍스트 선택 + = : 들여쓰기 통일

텍스트 선택 + K : 선택한 텍스트에 대해 man command 적용

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

## Command for Programming

### Syntax Coloring

:syntax on : 문법 coloring

### File Type

vim은 파일 확장자에 따라 파일 타입을 결정함

.java : java 파일

.c, .h : c 파일

:set filetype=c : 다른 확장자를 가진 파일을 c 파일 타입으로 설정

### Shifting

>>, << : 라인 들여쓰기(normal mode에서 동작)

### Auto Indentation

set cident : C 스타일 프로그램(c, c++, java 등)을 작성할 때 표준 C 스타일로 자동 들여쓰기 적용({}을 기준으로 적용)

set smartindent :

set autoindent : 


" Plugins  ========================================================= {{{

## Plugins

### Plugin manager - vim-plug 

[vim-plug github](https://github.com/junegunn/vim-plug)

#### installation

```
curl -fLo  ~/.vim/autoload/plug.vim --create-dirs \
     https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

#### Usage

1. .vimrc 파일에 이용할 플러그인 명시

* `call plug#begin([PLUGIN_DIR])` 
    1. Linux, macOs :  ~/.vim/plugged로 지정
    2. Windows : ~/vimfiles/plugged
* `Plug 설치할 플러그인 주소`
    1. 축약 : `Plug 'junegunn/fzf'`
    2. git url : `Plug 'https://github.com/junegunn/fzf'`
    3. on-demand : `Plug 'preservim/nerdtree', { 'on' : 'NERDTreeToggle'}'`
    4. specific branch : `Plug 'rdnetto/YCM-Generator', { 'branch' : 'stable }`
* `call plug#end()`

```
plug #begin()
lug 'junegunn/vim-easy-align'

Plug 'https://github.com/junegunn/vim-github-dashboard.git'

Plug 'SirVer/ultisnips' | Plug 'honza/vim-snippets'

" On-demand loading
Plug 'preservim/nerdtree', { 'on': 'NERDTreeToggle' }
Plug 'tpope/vim-fireplace', { 'for': 'clojure' }

" Using a non-default branch
Plug 'rdnetto/YCM-Generator', { 'branch': 'stable' }

plug#end()
```

2. .vimrc reload, `:PlugInstall` 실행

3. plugin 설치 후 수행해야 할 작업이 있을 경우

do 옵션으로 post-update hooks 수행

post-update hook은 해당 플러그인 디렉토리 안에서 실행됨

```
Plug 'Shougo/vimproc.vim', { 'do': 'make' }
Plug 'ycm-core/YouCompleteMe', { 'do': './install.py' }
```

plugin 설치 후 post-update hooks 수행 

```
Plug `'fatih/vim-go', { 'do': ':GoInstallBinaries' }`
```

do 옵션의 값이 ":" 로 시작하면 vim command로 인식함

```
Plug `'junegunn/fzf', { 'do': { -> fzf#install() } }`
```
람다 표현식을 vim 함수 호출


[vim-plug 옵션](https://github.com/junegunn/vim-plug?tab=readme-ov-file#plug-options)


#### Plugin Installation Step

1. `git clone` or `git fetch` from origin 
2. checkout branch, tag, commit
3. if the plugin was updated (or installed for the first time)
    1. update submodules
    2. execute post-update hooks

`:PluginInstall!`, `:PluginUpdate!`는 무조건 위 3단계를 수행함

}}}

" Key Mapping  ========================================================= {{{

## Key Mapping

}}}

" Tabs  ========================================================= {{{


## Tabs


}}}

" Fording  ========================================================= {{{

## Fording

}}}

" Formatting, Linting  ========================================================= {{{

## Formatting, Linting

}}}

" Code Completion  ========================================================= {{{

## Code Completion

}}}

" Language Server  ========================================================= {{{

## Language Server 

}}}

" With Git  ========================================================= {{{

## With Git

}}}

" Vim Scripts  ========================================================= {{{

## Vim Scripts

}}}


