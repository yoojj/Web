# History API
: 방문 기록 스택에 저장된 브라우저 기록에 접근하고 조작하기 위한 API   

속성 | 설명
---|---
history.length  | 방문 기록 스택에 저장된 목록 개수 반환
history.scrollRestoration  |
history.state   |


- [history.go()](#historygo)
- history.back()
- history.forward()
- history.pushState()
- history.replaceState()



## history.go()
: 전달된 값만큼 이동   

```js
history.go(-1) === history.back()
history.go(1) === history.forward()

// 새로고침
history.go()
history.go(0)
```



[top](#)
