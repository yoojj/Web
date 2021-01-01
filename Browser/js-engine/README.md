# JS Engine
: JS 코드와 WebAssembly 코드를 해석하고 실행   
: 최근 엔진은 바이트 코드를 생성하고 실행하는 가상 머신     


- [SpiderMonkey](./spider-monkey.md)
- [Rhino](./Rhino.md)
- [JavaScriptCore](./jscore.md)
- [V8](./V8.md)


플랫폼 | 엔진
---|---
IE, 이전 Edge         | Chakra(JScript)   
이전 Opera            | Carakan
Safari,              | JavaScriptCore(Nitro)
Mozilla 재단          | Rhino, SpiderMonkey
Chrome, Opera, Edge  | V8
Node                 | V8, SpiderNode
사물 인터넷            | JerryScript



**js engine**
```
code --> parse --> AST --> Interpreter
                       --> JIT Compiler

1. Parsing
: 코드를 로드하고 구문 분석을 함  

- 어휘 분석 : 토크나이저나 렉서를 통해 코드를 토큰으로 분리하고 공백같은 필요없는 문자 제거
- 구문 분석 : 파서가 토큰 목록을 구문 규칙에 따라 검증하고 트리화하여 parse tree 생성  


2. AST
Abstract Syntax Tree
: JS 엔진에 따라 parse tree에서 필수 내용 추출하여 트리 구조로 변환
: AST를 기반으로 바이트 코드나 네이티브 코드 생성


3. Interpreters and Compilers
: JS 엔진에 따라 하나 이상의 인터프리터와 컴파일러로 구성
: JS 엔진에 따라 바이트 코드나 네이티브 코드를 생성하고 코드를 최적화함     
```


**JS to AST**     
https://astexplorer.net/



[top](#)
