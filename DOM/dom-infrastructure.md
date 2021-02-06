# DOM Infrastructure


```
문서 --> 파싱 --> 문서 객체 모델 --> 렌더링   


1. 브라우저가 웹 문서를 로드
2. 파서를 통해 로드된 문서를 파싱
3. 문서의 요소를 객체로 만들고(DOM) 요소의 계층 관계를 트리 구조로 표현(DOM Tree)
4. 이때 요소나 요소의 계층 관계가 유효하지 않을 경우 수정됨
4. 필요에 따라 DOM API를 통해 DOM Tree에 접근해 객체 조작
5. DOM과 CSSOM을 통해 렌더 트리를 생성하고 이를 렌더링
```

![dom process image](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/images/full-process.png)



## Tree
: 데이터를 트리 형태의 계층 구조로 표현하는 자료 구조          
: 문서의 요소를 구조화하기 위해 사용하는 모델     

https://dom.spec.whatwg.org/#trees


용어 | 설명
---|---
Node         | 트리 구성 요소 (문서 구성 요소 = 태그, 속성, 텍스트, 주석)   
Root Node    | 트리 구조에서 최상위에 존재하는 노드   
Parent Node  | 트리 구조에서 다른 노드를 포함하는 상위 노드  
Child Node   | 부모 노드에 포함되는 모든 노드  
Sibling Node | 같은 부모 노드를 갖는 노드   


**Node Type**
- 문서 노드
- 요소 노드
- 속성 노드
- 텍스트 노드
- 주석 노드



## Node Tree

- DOM Tree
- CSSOM Tree



### DOM Tree

ex.
```html
<!doctype html>
<html>
<head lang="en">
    <title>title text</title>
</head>

<body>
    <!-- comment text -->
</body>

</html>

<!--
Document
  Doctype: html
    Element: html
      Element: head lang="en"
        Element: title
          Text: title text
      Element: body
        Comment: comment text
-->
```



[top](#)
