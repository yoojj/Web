# DOMTokenList
: 공백으로 구분된 토큰 문자열 목록         

- Element.classList
- HTMLAnchorElement.relList
- HTMLLinkElement.relList
- ...

https://dom.spec.whatwg.org/#interface-domtokenlist


```webidl
[Exposed=Window]
interface DOMTokenList {
  readonly attribute unsigned long length;
  getter DOMString? item(unsigned long index);
  boolean contains(DOMString token);
  [CEReactions] undefined add(DOMString... tokens);
  [CEReactions] undefined remove(DOMString... tokens);
  [CEReactions] boolean toggle(DOMString token, optional boolean force);
  [CEReactions] boolean replace(DOMString token, DOMString newToken);
  boolean supports(DOMString token);
  [CEReactions] stringifier attribute DOMString value;
  iterable<DOMString>;
};
```


**value**   
: 객체의 토큰을 문자열로 반환하거나 지정       

```html
<tag class="a b c"></tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

var classList = tag.classList;
(classList.value === 'a b c') == true

classList.value = 'a';
(classList.value === 'a') == true
</script>
```


**item()**    
: 주어진 인덱스에 해당하는 토큰 반환  
: 인덱스가 목록의 길이를 벗어나면 null 반환  

```html
<tag class="a b c"></tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

var classList = tag.classList;
(classList.item(0) === 'a') == true
</script>
```


**contains()**   
: 주어진 토큰이 있으면 true를 반환하고 그렇지 않으면 false 반환  

```html
<tag class="a b c"></tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

var classList = tag.classList;
classList.contains('a') == true
</script>
```


**add()**    
: 주어진 토큰이 존재하면 무시하고 존재하지 않으면 목록 끝에 추가  

```html
<tag class="a b c"></tag>

<script>
var tag = document.getElementsByTagName('tag')[0];

var classList = tag.classList;
classList.add('d', 'e');
(classList.length === '5') == true
</script>
```


**remove()**   
: 주어진 토큰이 존재하면 이를 제거   


**toggle()**   
: 주어진 토큰이 존재하지 않으면 이를 추가하고 true 반환   
: 주어진 토큰이 존재하면 이를 삭제하고 false 반환


**replace()**   
: 기존 토큰을 주어진 토큰으로 변경되면 true 반환   
: 기존 토큰이 주어진 토큰으로 변경되지 않으면 false 반환    



[top](#)
