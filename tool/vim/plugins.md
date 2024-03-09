[Ultisnips](#ultisnips)

# Ultisnips

[Ultisnips docs](https://github.com/SirVer/ultisnips/blob/master/doc/UltiSnips.txt)

vim 자동완성 스니펫 plugin

ultisnips - vim 스니펫 엔진 플러그인

vim-snippets - 미리 만들어둔 스니펫 플러그인

## Installation

```
plug#begin()
Plug 'SirVer/ultisnips'
Plug 'honza/vim-snippets'
plug#end()
```

## Usage

trigger 키 입력 후 tab을 누르면 파일 타입에 따라 자동완성 기능 적용

tab : 스니펫 적용

### Instructions

```
snippet <trigger> [<snippet-name>, [<option>]]
endsnippet
```

snippet-name : 파일 내에서 스니펫을 참조하는 데 사용

trigger : 스니펫 활성화 용도

Option
* A : 스니펫 자동 활성화
* t : 탭스톱없이 활성화
* r : 정규표현식 사용
* i : 단어 중간에서도 활성화
* w : 단어 경계에서만 활성화
* b : 문서 시작 부분에서만 활성화
* e : 문서 끝부분에서만 활성화

```
snippet sout "System.out.println(); shortcut" A
System.out.println(${1});
endsnippet
```

${1} : 커서 위치, ${2}, ${3} 등 다음 커서 위치를 지정할 수 있음

## Tabstops, Placeholders

탭스탑은 스니펫 중 특정 위치로 빠르게 이동할 수 있도록 하는 기능임

$n : 1부터 시작하며 0은 특별한 탭스탑으로 항상 마지막을 가리킴, ${0}을 지정하지 않으면 자동으로 스니펫의 맨 마지막을 가리킴

${n: default text} : 기본 값 지정한 탭스탑

CTRL + j : 다음 탭스탑으로 이동

CTRL + k : 이전 탭스탑으로 이동

## Mirrors

Tapstop 변수 값에 따라 값이 변경되는 변수

탭스탑과 동일한 번호를 지정하면 Mirror로 사용할 수 있음

스니펫 안에서 여러 번 참조 가능

```
snippet setter
    public void set${1:Name}(${2:String} $1) {
        this.$1 = $1;
    }
endsnippet
```

${1:Name} 탭스탑을 $1으로 여러 번 참조함

## Custom snippets

커스텀 스니펫 파일 위치 : ~/.vim/Ultisnips 디렉토리

파일명 : 언어.snippets (java.snippets)

## vim-snippets

### java.snippets

#### Access Modifiers

po : protected ${0}

pu : public ${0}

pr : private ${0}

#### Modifiers

ab : abstract ${0}

fi : final ${0}

st : static ${0}

sy : synchronized ${0}

#### Class 

cl : class ${1:filename} ${0}

pcl : public class ${1: filename} ${0}

tc : public class ${1: filename} extends ${0: TestCase}

in : interface ${1: filename} ${2: extends Parent}

---

ext : extends ${0}

imp : implements ${0}

#### Comments

/* : 주석

#### Variables

co : public static final ${1: String} ${2: var} = ${3};

cos : public statc final String ${1: var} = "${2}";

v : ${1: String} ${2: var} ${3: = null}${4};

#### Methods

m : ${1: void} ${2: method}(${3}) ${4: throws}

psvm, main : public static void main(String[] args){ ${0} }

findall : List<${1: listName}> ${2: items} = $1.findAll();

findbyid : ${1: var} ${2: item} = $1.findById(${3});

#### Control Statements

case
```
case ${1}:  
    ${0}
```

def
```
default :  
     ${0}
```

el : else

eif : else if (${1}) ${0}

if : if (${1}) ${0}

sw
```
switch (${1}) {
    ${0}
}
```
#### Loops

enfor : for (${1} : ${2}) ${0}

for : for (${1}; ${2}; ${3}) ${0}

wh : while (${1: true}) ${0}

wht (true) ${0}

#### Property

set
```
	${1:public} void set${3:}(${2:String} ${0:}){
		this.$4 = $4;
	}
```

get
```
	${1:public} ${2:String} get${3:}(){
		return this.${0:};
	}
```

