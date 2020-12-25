# File API
: 파일 객체를 표현하고 파일 데이터에 접근하기 위한 API  

https://www.w3.org/TR/FileAPI/    
http://trac.webkit.org/browser/webkit/trunk/Source/WebCore/fileapi


**api**
- [Blob](#blob)
- [File](#file)
- [FileList](#filelist)
- [FileReader](#filereader)



## Blob
: Binary Large Object   

```webidl
[Exposed=(Window,Worker), Serializable]
interface Blob {
  constructor(optional sequence<BlobPart> blobParts,
              optional BlobPropertyBag options = {});

  readonly attribute unsigned long long size;
  readonly attribute DOMString type;

  Blob slice(optional [Clamp] long long start,
            optional [Clamp] long long end,
            optional DOMString contentType);

  [NewObject] ReadableStream stream();
  [NewObject] Promise<USVString> text();
  [NewObject] Promise<ArrayBuffer> arrayBuffer();
};

enum EndingType { "transparent", "native" };

dictionary BlobPropertyBag {
  DOMString type = "";
  EndingType endings = "transparent";
};

typedef (BufferSource or Blob or USVString) BlobPart;
```


**slice(start, end, type)**  
: 해당 범위의 바이트를 복제해 새 Blob 객체를 생성하고 이를 반환


**EndingType**
- 'transparent' : 기본 줄바꿈 문자 사용   
- 'native' : OS에 맞춘 줄바꿈 문자 사용  


ex.
```js
var data = JSON.stringify({});
var blob = new Blob([data], {type: 'text/plain'});
```



## File
: 파일 시스템에서 얻은 파일에 대한 정보 제공  

```webidl
[Exposed=(Window,Worker), Serializable]
interface File : Blob {
  constructor(sequence<BlobPart> fileBits,
              USVString fileName,
              optional FilePropertyBag options = {});
  readonly attribute DOMString name;
  readonly attribute long long lastModified;
};

dictionary FilePropertyBag : BlobPropertyBag {
  long long lastModified;
};
```

ex.
```html
<input type="file" id="input">
<input type="file" id="input" accept=".jpg, .jpeg">

<script>
var input = document.getElementById('input');
var file = input.files[0];
</script>
```



## FileList
: 파일 시스템에서 얻은 파일 리스트에 대한 정보 제공

```webidl
[Exposed=(Window,Worker), Serializable]
interface FileList {
  getter File? item(unsigned long index);
  readonly attribute unsigned long length;
};
```


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



## FileReader

```webidl
[Exposed=(Window,Worker)]
interface FileReader: EventTarget {
  constructor();

  void readAsArrayBuffer(Blob blob);
  void readAsBinaryString(Blob blob);
  void readAsText(Blob blob, optional DOMString encoding);
  void readAsDataURL(Blob blob);

  void abort();

  const unsigned short EMPTY = 0;
  const unsigned short LOADING = 1;
  const unsigned short DONE = 2;

  readonly attribute unsigned short readyState;

  readonly attribute (DOMString or ArrayBuffer)? result;

  readonly attribute DOMException? error;

  attribute EventHandler onloadstart;
  attribute EventHandler onprogress;
  attribute EventHandler onload;
  attribute EventHandler onabort;
  attribute EventHandler onerror;
  attribute EventHandler onloadend;
};
```


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
