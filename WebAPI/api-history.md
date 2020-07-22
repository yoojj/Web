# History API
: 사용자의 방문 기록 저장   

속성 | 설명
---|---
history.length | 방문 기록 스택에 저장된 목록 개수 반환


- history.back()
- history.forward()
- history.go()



## history.go()
: 전달된 값만큼 history이동   


```js
// 새로고침
history.go()
history.go(0)

history.go(-1) === history.back()
history.go(1) === history.forward()
```
