# Navigator API
: 브라우저 정보와 운영체제 정보 제공

- NavigatorID
- NavigatorLanguage
- NavigatorOnLine
- NavigatorContentUtils
- NavigatorCookies
- NavigatorPlugins
- NavigatorConcurrentHardware



## NavigatorID

속성 | 설명
---|---
navigator.appCodeName    | 브라우저 코드 이름 반환
navigator.appName        | 브라우저 이름 반환
navigator.appVersion     | 브라우저 버전 반환
navigator.platform       | 브라우저를 실행하는 운영체제 반환
navigator.product        | 브라우저 사용 엔진 반환
navigator.userAgent      | 브라우저와 운영체제 종합 정보 반환



## NavigatorLanguage

속성 | 설명
---|---
navigator.language       | 선호하는 언어 반환
navigator.languages      | 선호하는 언어 목록 반환
navigator.userLanguage   | only ie
navigator.systemLanguage | only ie



## NavigatorContentUtils

- navigator.registerProtocolHandler(scheme, url)
- navigator.unregisterProtocolHandler(scheme, url)



[top](#)
