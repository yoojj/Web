# img
: 이미지 리소스를 표현하기 위한 엘리먼트   
: 이미지는 HTML과 CSS가 로드 된 후 적용   

> 이미지 다운로드 > 디코딩 > 렌더링


속성 | 설명
---|---
src            | 이미지 경로 지정 (필수 속성)
width, height  | 이미지 크기 지정  
alt            | 이미지 대체 텍스트 지정  
srcset         | 디스플레이별 사용할 이미지 지정
sizes          | 레이아웃별 이미지 크기 지정
decoding       | 이미지 디코딩 프로세스 명시
loading        | 이미지 로드 방법 명시
ismap          | 서버측 이미지맵인지 여부 지정 (불리언 속성)
usemap         | 이미지맵 이름
crossorigin    | crossorigin 요청 처리 방식 지정
referrerpolicy | HTTP 리퍼러 정책 설정



```html
<style>
/* img 태그는 인라인 요소이나 일반 인라인 요소와 다르게 너비와 높이를 갖음 */
img {width:100px;height:100px;margin:100px;}


img {
    image-rendering:auto;
    image-rendering:crisp-edges;
    image-rendering:pixelated;
}
</style>


<img src="" alt="이미지 설명">
<!--
: 여러 이유로 이미지 누락시 이미지 대신 보여지는 텍스트
: 검색 엔진, 텍스트 리더기는 alt 속성에 의존하여 이미지 정보 파악  
-->

<img src="" alt="">
<!--
: 이미지에 의미가 없다면 alt 속성 값을 빈 값으로 지정  
-->


<img src="" alt="이미지 설명" title="이미지 추가 설명">
<!--
: 이미지 위에 툴팁으로 표현되는 문구
: 이미지가 표현하는 정보가 복잡한 경우 전역 속성 title을 사용하여 추가 정보 제공
: title 속성은 SEO에 영향을 미치지 않음
-->


<img src="" alt=""
     srcset="img-900.png 900w, img-600.png 600w"
     sizes="(max-width: 660px) 600px, 900px">


<img src="" alt="" decoding="auto | sync | async">
<!--
: decoding 속성을 사용하여 상황에 따라 동기나 비동기 적으로 이미지 디코딩

- auto : 디코딩 모드 사용하지 않음
- sync : 이미지를 동기적으로 디코딩
- async : 이미지를 비동기적으로 디코딩
-->


<img src="" alt="" loading="auto | lazy | eager">
<!--
- auto : 브라우저 기본 지연 동작
- lazy : 이미지 로드 연기  
- eager : 이미지 즉시 로드  
-->
```


**+ Lazy Loading Images**    
https://github.com/yoojj/Web/blob/master/WebOptimization/lazy-load-images.md

**+ Image Decoding**    
https://github.com/yoojj/Web/blob/master/WebOptimization/image-decoding.md



[top](#)
