# HTML Microdata
≒ Microformats, RDFa, JSON-LD     
: 태그 속성에 메타데이터를 명시해 컴퓨터에게 추가 정보 전달     
: 마이크로 데이터의 주 목적은 검색 엔진 최적화


속성 | 설명
---|---
itemscope | 컨테이너 요소 정의 (불리언 속성)
itemtype  | 요소에 대한 어휘 지정  
itemprop  | 속성 추가
itemref   | 특성 지정  


```html
<section itemscope itemtype="http://schema.org/Person">
<h1>User Information</h1>
<dl>
    <dt>name
    <dd itemprop="name">이름

    <dt>age
    <dd itemprop="age">나이
</dl>
</section>
```


마이크로 데이터 생성기   
https://seoscout.com/tools/schema-generator


마이크로 데이터 시각화   
https://www.webmoves.net/tools/microdata



[top](#)
