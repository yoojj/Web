# Layout
: 웹 문서의 구조 표현을 위한 태그들   
: 다른 요소를 포함하는 컨테이너 엘리먼트   


태그 | 설명
---|---
header  | 웹 문서의 머리, 콘텐츠의 머리
footer  | 웹 문서의 바닥, 콘텐츠의 바닥
main    | 웹 문서의 본문
nav     | 내비게이션 링크 그룹
section | 콘텐츠 그룹
aside   | 웹 문서와 관련있는 추가 콘텐츠 영역 (ex. 댓글, 각주, 광고)
article | 독립적인 콘텐츠 영역, 재사용 가능한 콘텐츠 영역  
div     | 의미있는 태그가 아니며 요소를 스타일링 목적으로 그룹화하는 경우 사용


```html
<body>

    <header>
        <h1>title</h1>
    </header>

    <main>
    <!--
    : 하나의 웹 문서에 하나만 존재
    : header, footer, nav, aside, article 하위에 존재하면 안됨
    -->

        <section>
            <h2>title</h2>

            <nav>
                <h3>title</h3>
                <a href="content1">1</a>
                <a href="content2">2</a>
            </nav>

            <section id="content1">
                <h3>title</h3>
            </section>

            <article id="content2">
                <h3>title</h3>
                <!-- 독립적으로 배포 가능 -->
            </article>

            <aside>
                <h3>title</h3>
            </aside>

        </section>

    </main>

    <footer>
        <em>Copyright &copy;</em>
    </footer>

</body>
```



[top](#)
