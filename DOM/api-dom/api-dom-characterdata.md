# CharacterData
: Text, ProcessingInstruction, Comment 인터페이스에서 사용

https://dom.spec.whatwg.org/#interface-characterdata


```webidl
[Exposed=Window]
interface CharacterData : Node {
  attribute [LegacyNullToEmptyString] DOMString data;
  readonly attribute unsigned long length;
  DOMString substringData(unsigned long offset, unsigned long count);
  undefined appendData(DOMString data);
  undefined insertData(unsigned long offset, DOMString data);
  undefined deleteData(unsigned long offset, unsigned long count);
  undefined replaceData(unsigned long offset, unsigned long count, DOMString data);
};
```


**length**   
: 데이터(텍스트, 공백, 줄바꿈) 길이 반환


**substringData()**   
: 주어진 인덱스에서 카운트 사이에 해당하는 문자열 반환   

```html
<tag>text</tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

var result = tag.firstChild.substringData(0, 1);
(result === 't') == true
</script>
```


**appendData()**   
: 텍스트의 끝에 주어진 데이터 삽입  

```html
<tag>text</tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

tag.firstChild.appendData('data');
(tag.data === 'textdata') == true
</script>
```


**insertData()**   
: 주어진 인덱스에 주어진 데이터 삽입   

```html
<tag>text</tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

tag.firstChild.insertData(0, 'data');
(tag.data === 'datatext') == true
</script>
```


**deleteData()**   
: 주어진 인덱스에서 카운트 사이에 해당하는 데이터 삭제  


**replaceData()**   
: 주어진 인덱스에서 카운트 사이에 주어진 데이터 삽입  
: insertData()와 다르게 기존 데이터 덮어 쓰기 가능  

```html
<tag>text</tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

tag.firstChild.insertData(0, 3, 'data');
(tag.data === 'data') == true
</script>
```



[top](#)
