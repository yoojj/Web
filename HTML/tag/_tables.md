# tables
: 행과 열로 이루어진 이차원 표를 표현하기 위한 태그들      

태그 | 설명
---|---  
table    | 테이블 정의
caption  | 테이블 설명
colgroup | 열-컬럼 그룹 정의
col      | 공통적인 열 정의
thead    | 테이블 머리 콘텐츠 그룹 정의
tbody    | 테이블 본문 콘텐츠 그룹 정의
tfoot    | 테이블 바닥 콘텐츠 그룹 정의
tr       | 테이블 행 정의
th       | 테이블 헤더 셀 정의
td       | 테이블 셀 정의


```html
<style>
table {display:table;}
caption {display:table-caption;}
colgroup {display:table-column-group;}
col {display:table-column;}
thead {display:table-header-group;}
tbody {display:table-row-group;}
tfoot {display:table-footer-group;}
tr {display:table-row;}
th {display:table-cell;}
td {display:table-cell;}
</style>


<table border="1">
	<caption>테이블 설명</caption>

	<colgroup>
		<!-- 단일 태그 -->
		<col span="2">
		<col>
	</colgroup>

	<thead>
    <tr>
		<th></th>
		<th></th>
		<th></th>
    </tr>
    </thead>

    <tbody>
    <tr>
        <td rowspan="2">행 병합</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td colspan="3">열 병합</td>
    </tr>
    </tbody>

	<!-- 데이터에 따라 접근성을 위해 tbody 요소 전에 위치할 수 있음 -->
	<tfoot>
	<tr>
		<td></td>
		<td></td>
		<td></td>
	</tr>
	</tfoot>
</table>
```



[top](#)
