vim 9.x 버전대 기준

* [Configuration](#configuration)
* [Modes](#modes)
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

visual block mode : ctrl + v

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
