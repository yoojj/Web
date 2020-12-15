# CSS Display

https://www.w3.org/TR/css-display/


속성 | 설명
---|---
display | 요소의 디스플레이 타입 지정  


**display type**  
- outer : 주요 박스(parent box)가 되어 레이아웃에 참여
- inner


용어 | 설명
---|---
parent box     | 요소의 가장 가까이에 있는 요소의 상자
anonymous box  | 어떤 요소와도 연결되지 않은 상자 (ex. table-cell)
principal box  | 콘텐츠를 포함해 생성되는 주요 박스로 위치 지정시 기준이 되는 박스
additional box | 일부 요소에서 주요 박스외 생성되는 추가 박스 (ex. list-item)
block box      | block 레이아웃과 관련된 상자
inline box     | inline 레이아웃과 관련된 상자


```css
E {display:keyword;}
/*
: display 속성이 요소의 의미(semantic)에 영향을 주지 않음
: 시각적 레이아웃에만 영향을 미침


display-outside : 요소의 레이아웃을 위한 박스 지정
- block : 블록 박스 생성
- inline : 인라인 박스 생성
- run-in : 주변에 따라 인라인 박스나 블록 박스로 생성  


display-inside : 요소의 콘텐츠 레이아웃을 위한 박스 지정
(flow | flow-root | table | flex | grid | ruby)


display-listitem
- list-item : 일부 요소의 마커 박스 생성  


display-internal : 특정 컨텍스트의 레이아웃을 위한 박스 지정
- 내부 테이블 박스 생성
  table-row-group | table-header-group | table-footer-group |
  table-row | table-cell | table-column-group | table-column

- 테이블 캡션 박스 생성
  table-caption

- 내부 루비 박스 생성
  ruby-base | ruby-text | ruby-base-container | ruby-text-container


display-box : 박스 생성 여부 지정
- contents
: 요소의 박스를 생성하지 않음
: 요소의 콘텐츠(하위 요소, 가상 엘리먼트, 텍스트)의 박스는 생성함  

- none
: 요소의 박스를 생성하지 않음
: 요소의 콘텐츠(하위 요소, 가상 엘리먼트, 텍스트)의 박스도 생성하지 않음  


display-legacy
- inline-block = inline flow-root
- inline-table = inline table
- inline-flex =  intline flex
- inline-grid = inline grid


ex.
table           {display:table}
caption         {display:table-caption}
colgroup        {display:table-column-group}
col             {display:table-column}
thead           {display:table-header-group}
tfoot           {display:table-footer-group}
tbody           {display:table-row-group}
tr              {display:table-row}
td, th          {display:table-cell}
*/
```



[top](#)
