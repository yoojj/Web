# Web Share API
: 텍스트, 링크, 파일같은 데이터를 사용자가 선택한 대상에 공유하기 위한 API     

https://www.w3.org/TR/web-share/


```webidl
partial interface Navigator {
  [SecureContext] Promise<undefined> share(optional ShareData data = {});
};

dictionary ShareData {
  sequence<File> files;
  USVString title;
  USVString text;
  USVString url;
};
```


File API    
https://github.com/yoojj/Web/blob/master/WebAPI/api-file.md


ex.
```js
el.addEventListener('click', () => {

    navigator.share({
        files: [],
        title: '',
        text: '',
        url: '',

    }).then( () => {

    }).catch( (err) => {

    });

});
```

https://w3c.github.io/web-share/demos/share-files.html



[top](#)
