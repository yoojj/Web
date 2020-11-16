# layout
: 문서의 구조 표현을 위한 태그들   
: 다른 요소를 포함하는 컨테이너 엘리먼트   


태그 | 설명
---|---
body    | 문서의 본문
header  | 문서의 머리 글을 위한 태그
footer  | 문서의 바닥 글을 위한 태그
main    | 문서의 주요 컨텐츠 영역을 위한 태그  
nav     | 링크 모음
section | 문서의 섹션을 위한 태그  
aside   | 문서와 관련있는 콘텐츠 영역을 위한 태그  
article | 문서와 다른 독립적인 콘텐츠 영역을 위한 태그
div     | 의미있는 태그가 아니며 요소를 스타일링 목적으로 그룹화하는 경우 사용


```html
<body>
    <header>
        <h1>title</h1>
    </header>


    <!-- 한 문서에 하나만 존재하며 header, footer, nav, article, aside 하위에 존재하면 안됨 -->
    <main>
        <section>
            <h2>title</h2>
        </section>
    </main>


    <footer>
        <em>Copyright &copy;</em>
    </footer>
</body>
```



[top](#)
