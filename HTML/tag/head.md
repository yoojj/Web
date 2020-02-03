# head
: 문서 제목, 메타 데이터, CSS나 JS 파일 링크, 파비콘 등을 포함하는 컨테이너 엘리먼트  
: 문서에 대한 정보 제공   


**포함 요소**  
- title
- base
- [link](./link.md)
- [meta](./meta.md)
- style
- script
- noscript


```html
<head>

    <meta charset="utf-8">


    <title>문서 제목</title>
    <!--
    : 브라우저 탭이나 타이틀 바에 노출
    : 검색 엔진 결과 페이지에서 제목으로 노출
    : 50자 이하로 입력해야 제목에서 짤리지 않음  
    -->


    <base href="" target="">
    <!--
    : 문서에 포함되는 모든 url의 기준이 되는 url
    : 문서에 한 번만 정의
    : base 요소가 여러번 정의될 경우 첫번째 요소가 사용됨
    -->


    <meta name="" content="">
    <link rel="" herf="">
    <script src=""></script>

</head>
```



[top](#)
