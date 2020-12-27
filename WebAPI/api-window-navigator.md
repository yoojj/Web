# Navigator API

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



## NavigatorID

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
productSub   |
userAgent    | 유저 에이전트 헤더 반환
vendor       |
vendorSub    |


**taintEnabled()**   
: 브라우저에서 data tainting이 가능한지 여부 반환



## NavigatorLanguage

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



## NavigatorOnLine

```webidl
interface mixin NavigatorOnLine {
  readonly attribute boolean onLine;
};
```

**onLine**   
: 유저 에이전트가 온라인 상태면 true 반환  
: 유저 에이전트가 오프라인 상태면 false 반환  



## NavigatorContentUtils

```webidl
interface mixin NavigatorContentUtils {
  [SecureContext] undefined registerProtocolHandler(DOMString scheme, USVString url);
  [SecureContext] undefined unregisterProtocolHandler(DOMString scheme, USVString url);
};
```



## NavigatorCookies

```webidl
interface mixin NavigatorCookies {
  readonly attribute boolean cookieEnabled;
};
```

**cookieEnabled**  
: 쿠키 사용 여부 반환   



## NavigatorPlugins

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



## NavigatorConcurrentHardware

```webidl
interface mixin NavigatorConcurrentHardware {
  readonly attribute unsigned long long hardwareConcurrency;
};
```



[top](#)
