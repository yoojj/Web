# Document API


속성 | 설명
---|---
document.doctype  | 페이지의 DTD 반환
document.head     | 페이지의 head 요소 반환
document.dir      | 페이지의 텍스트 방향 반환  
document.title    | 페이지 제목 반환  
document.body     | 페이지의 body 요소 반환
document.images   | 페이지의 img 요소들을 반환하고 없으면 빈 배열 반환
document.embeds   | 페이지의 object 요소들을 반환하고 없으면 빈 배열 반환
document.plugins  | 페이지의 embed 요소들을 반환하고 없으면 빈 배열 반환
document.links    | 페이지의 href 속성을 갖는 a 요소들을 반환하고 없으면 빈 배열 반환
document.forms    | 페이지의 form 요소들을 반환하고 없으면 빈 배열 반환
document.scripts  | 페이지의 script 요소들을 반환하고 없으면 빈 배열 반환
document.domain   | 페이지의 도메인 반환하거나 설정  
document.referrer | 방문한 페이지의 url을 반환하고 방문한 페이지가 없다면 빈문자열 반환  
document.cookie   | 쿠키 반환
document.lastModified  | 페이지가 마지막으로 수정된 날짜와 시간 반환
document.readyState    | 페이지 로드 상태 반환  
document.currentScript | 현재 실행중인 스크립트의 요소 반환  



## document.readyState
: 페이지 로드 단계에 따라 3가지 상태를 반환    
: 상태가 변경될 때마다 readystatechange 이벤트 발생      

- loading : 페이지 로드중
- interactive : 페이지는 로드되었으나 css나 이미지같은 리소스가 로드 중
- complete : 페이지 로드 완료



## document.currentScript

```js
setTimeout(() => {
    console.log(document.currentScript);
}, 3000);
```



[top](#)
