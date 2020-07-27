# BOM  
Browser Object Model   
: 브라우저 객체 모델     
: 브라우저 요소를 제어하기 위한 API    
: 벤더사별 구현으로 표준이 존재하지 않음   


객체 | 설명
---|---
window     | 최상위 객체  
navigator  | 브라우저 자체
screen	   | 화면
history	   | 기록
location   | 브라우저 주소
frames     | 프레임 셋
document   | 브라우저 상의 문서


```bash
Window
├─ # host object     
│   ├─ BOM
│   │   ├─ navigator
│   │   ├─ screen
│   │   ├─ history
│   │   ├─ location
│   │   ├─ frames
│   │   └─ document 
│   └─ Web API   
└─ # native object = JS Built-in Object
```



[top](#)
