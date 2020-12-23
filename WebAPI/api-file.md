# File API
: 파일 객체를 표현하고 파일 데이터에 접근하기 위한 API  


https://www.w3.org/TR/FileAPI/


## API  

- [Blob](#blob)
- [File](#file)
- [FileList](#filelist)
- [FileReader](#filereader)



### Blob
: Binary Large Object   
: 텍스트 파일 데이터나 이진 데이터를 담는 객체  


**Blob**
- constructor(BufferSource | Blob | USVString, BlobPropertyBag)
- size
- type
- slice(start, end, type) : 해당 범위의 바이트를 복제해 새   Blob 객체로 생성하고 반환
- stream()
- text()
- arrayBuffer()


**BlobPropertyBag**
- type
- endings : EndingType 지정


**EndingType**
- 'transparent' : 기본 줄바꿈 문자 지정   
- 'native' : OS에 맞춰 줄바꿈 문자 지정   


ex.
```js
var data = JSON.stringify({});
var blob = new Blob([data], {type: 'text/plain'});
```



### File
: 파일 시스템에서 얻은 파일에 대한 정보 제공    


**File** implements Blob  
- constructor(BlobPart, USVString, FilePropertyBag)
- name
- lastModified


**FilePropertyBag** implements BlobPropertyBag  
- lastModified


ex.
```html
<input type="file" id="input">
<input type="file" id="input" accept=".jpg, .jpeg">

<script>
var input = document.getElementById('input');
var file = input.files[0];
</script>
```



### FileList
: 파일 시스템에서 얻은 파일 리스트에 대한 정보 제공


**FileList**
- item(index) : File 객체 반환
- length


ex.
```html
<input type="file" id="input" multiple>

<script>
var input = document.getElementById('input');
var files = input.files;

for (var i = 0, len = files.length; i < len; i++) {
    files.item(i);
}
</script>
```



### FileReader


**FileReader**
- constructor()
- readAsArrayBuffer(Blob)
- readAsBinaryString(Blob)
- readAsText(Blob, encoding)
- readAsDataUrl(Blob)
- abort()
- EMPTY
- LOADING
- DONE
- readyState
- result
- error : DOMException 객체 반환


**FileReaderSync**
- constructor()
- readAsArrayBuffer(Blob)
- readAsBinaryString(Blob)
- readAsText(Blob, encoding)
- readAsDataUrl(Blob)


ex.
```html
<input type="file" id="input" multiple>

<script>
var input = document.getElementById('input');

input.addEventListener('change', (e) => {

    var files = e.target.files;
    var reader = new FileReader();

    for (var i = 0, len = files.length; i < len; i++) {
        reader.readAsText(files[i]);
    }

});
</script>
```



[top](#)
