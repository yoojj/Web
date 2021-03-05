# Navigator

https://html.spec.whatwg.org/multipage/system-state.html#the-navigator-object


```webidl
[Exposed=Window]
interface Navigator {
  below
};

Navigator includes NavigatorID;
Navigator includes NavigatorLanguage;
Navigator includes NavigatorOnLine;
Navigator includes NavigatorContentUtils;
Navigator includes NavigatorCookies;
Navigator includes NavigatorPlugins;
Navigator includes NavigatorConcurrentHardware;
```


- [NavigatorID](#navigatorid)
- [NavigatorLanguage](#navigatorlanguage)
- [NavigatorOnLine](#navigator)
- [NavigatorContentUtils](#navigatorcontentutils)
- [NavigatorCookies](#navigatorcookies)
- [NavigatorPlugins](#navigatorplugins)
- [NavigatorConcurrentHardware](#navigatorconcurrenthardware)



## partial interface

```webidl
partial interface Navigator {
  [SameObject] readonly attribute Geolocation geolocation;
};


partial interface Navigator {
  [SecureContext] Promise<undefined> share(optional ShareData data = {});
};


[Exposed=(Window)]
partial interface Navigator {
  [SameObject] readonly attribute Permissions permissions;
};


partial interface Navigator {
  [SecureContext, SameObject] readonly attribute Clipboard clipboard;
};
```

Geolocation API   
https://github.com/yoojj/Web/blob/master/WebAPI/api-geolocation.md  

Web Share API    
https://github.com/yoojj/Web/blob/master/WebAPI/api-web-share.md

Permission API  
https://github.com/yoojj/Web/blob/master/WebAPI/api-permission.md

Clipboard API    
https://github.com/yoojj/Web/blob/master/WebAPI/api-clipboard.md



# NavigatorID

```webidl
interface mixin NavigatorID {
  readonly attribute DOMString appCodeName;
  readonly attribute DOMString appName;
  readonly attribute DOMString appVersion;
  readonly attribute DOMString platform;
  readonly attribute DOMString product;
  [Exposed=Window] readonly attribute DOMString productSub;
  readonly attribute DOMString userAgent;
  [Exposed=Window] readonly attribute DOMString vendor;
  [Exposed=Window] readonly attribute DOMString vendorSub;
};

partial interface mixin NavigatorID {
  [Exposed=Window] boolean taintEnabled();
  [Exposed=Window] readonly attribute DOMString oscpu;
};
```


속성 | 설명
---|---
appCodeName  | 브라우저 코드 이름 반환
appName      | 브라우저 이름 반환
appVersion   | 브라우저 버전 반환
platform     | 브라우저를 실행하는 운영체제 반환
product      | 브라우저 사용 엔진 반환
productSub   | 브라우저의 빌드 번호 반환
userAgent    | 유저 에이전트 헤더를 문자열로 반환
vendor       | 벤더사 이름 반환
vendorSub    | 벤더사 빌드 번호 반환  


**taintEnabled()**   
: 브라우저에서 data tainting이 가능한지 여부 반환

**+ data tainting**   
: 데이터를 오염된 것으로 표시하는 기능   
: XSS 유형 공격 방지를 위해 사용   



# NavigatorLanguage

```webidl
interface mixin NavigatorLanguage {
  readonly attribute DOMString language;
  readonly attribute FrozenArray<DOMString> languages;
};
```

속성 | 설명
---|---
language     | 선호하는 언어 반환
languages    | 선호하는 언어 목록 반환



# NavigatorOnLine

```webidl
interface mixin NavigatorOnLine {
  readonly attribute boolean onLine;
};
```

**onLine**   
: 유저 에이전트가 온라인 상태면 true 반환  
: 유저 에이전트가 오프라인 상태면 false 반환  



# NavigatorContentUtils

```webidl
interface mixin NavigatorContentUtils {
  [SecureContext] undefined registerProtocolHandler(DOMString scheme, USVString url);
  [SecureContext] undefined unregisterProtocolHandler(DOMString scheme, USVString url);
};
```


**registerProtocolHandler()**    
: 지정한 스키마(URL protocol)로 URL 처리        

```html
<script>
navigator.registerProtocolHandler('mailto',
    'https://example.com/mail?data=%s');
</script>

<a href="mailto:send+data">mail</a>
```

scheme   
https://html.spec.whatwg.org/multipage/system-state.html#safelisted-scheme



# NavigatorCookies

```webidl
interface mixin NavigatorCookies {
  readonly attribute boolean cookieEnabled;
};
```

**cookieEnabled**  
: 쿠키 사용 여부 반환   



# NavigatorPlugins

```webidl
interface mixin NavigatorPlugins {
  [SameObject] readonly attribute PluginArray plugins;
  [SameObject] readonly attribute MimeTypeArray mimeTypes;
  boolean javaEnabled();
};


[Exposed=Window,LegacyUnenumerableNamedProperties]
interface PluginArray {
  undefined refresh(optional boolean reload = false);
  readonly attribute unsigned long length;
  getter Plugin? item(unsigned long index);
  getter Plugin? namedItem(DOMString name);
};


[Exposed=Window,LegacyUnenumerableNamedProperties]
interface MimeTypeArray {
  readonly attribute unsigned long length;
  getter MimeType? item(unsigned long index);
  getter MimeType? namedItem(DOMString name);
};


[Exposed=Window,LegacyUnenumerableNamedProperties]
interface Plugin {
  readonly attribute DOMString name;
  readonly attribute DOMString description;
  readonly attribute DOMString filename;
  readonly attribute unsigned long length;
  getter MimeType? item(unsigned long index);
  getter MimeType? namedItem(DOMString name);
};


[Exposed=Window]
interface MimeType {
  readonly attribute DOMString type;
  readonly attribute DOMString description;
  readonly attribute DOMString suffixes;
  readonly attribute Plugin enabledPlugin;
};
```


**plugins**    
: 브라우저에 설치된 플러그인 목록 반환    
: 보안 문제로 일부 브라우저에서는 기능이 제한됨   


**mimeTypes**   
: 브라우저가 인식 가능한 MIME 유형 반환   


**javaEnabled()**    
: 브라우저가 Java를 제어하는 환경 설정이 되어있는지 여부 반환    



# NavigatorConcurrentHardware

```webidl
interface mixin NavigatorConcurrentHardware {
  readonly attribute unsigned long long hardwareConcurrency;
};
```


**hardwareConcurrency**   
: 생성 가능한 스레드 수 반환  



[top](#)
