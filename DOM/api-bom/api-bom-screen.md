# Screen

https://www.w3.org/TR/cssom-view/#the-screen-interface


```webidl
[Exposed=Window]
interface Screen {
  readonly attribute long availWidth;
  readonly attribute long availHeight;
  readonly attribute long width;
  readonly attribute long height;
  readonly attribute unsigned long colorDepth;
  readonly attribute unsigned long pixelDepth;
};
```


속성 | 설명
---|---
availWidth  | 작업 표시줄 등을 제외한 사용 가능한 화면 너비 반환  
availHeight | 작업 표시줄 등을 제외한 사용 가능한 화면 높이 반환
width       | 전체 화면 너비 반환
height      | 전체 화면 높이 반환
colorDepth  | 화면의 색상 비트 수 반환
pixelDepth  | 화면의 해상도 반환



## partial interface

```webidl
partial interface Screen {
  [SameObject] readonly attribute ScreenOrientation orientation;
};
```

속성 | 설명
---|---
orientation | 화면의 방향에 대한 정보를 담은 ScreenOrientation 객체 반환   



# ScreenOrientation

https://www.w3.org/TR/screen-orientation/#screenorientation-interface


```webidl
[Exposed=Window]
interface ScreenOrientation : EventTarget {
  Promise<undefined> lock(OrientationLockType orientation);
  undefined unlock();
  readonly attribute OrientationType type;
  readonly attribute unsigned short angle;
  attribute EventHandler onchange;
};

enum OrientationLockType {
  "any",
  "natural",
  "landscape",
  "portrait",
  "portrait-primary",
  "portrait-secondary",
  "landscape-primary",
  "landscape-secondary"
};

enum OrientationType {
  "portrait-primary",
  "portrait-secondary",
  "landscape-primary",
  "landscape-secondary"
};
```


속성 | 설명
---|---
type   | 화면의 방향 유형 반환
angle  | 화면의 방향 각도 반환

```js
// 기본 화면 + 세로 모드  
screen.orientation.type = 'portrait-primary';

// 보조 화면 + 세로 모드
screen.orientation.type = 'portrait-secondary';

// 기본 화면 + 가로 모드
screen.orientation.type = 'landscape-primary';

// 보조 화면 + 가로 모드  
screen.orientation.type = 'landscape-secondary';
```


**lock()**   
: 화면의 방향을 주어진 값으로 잠금   

```js
// landscape-primary + landscape-secondary
screen.orientation.lock('landscape');

// portrait-primary + portrait-secondary
screen.orientation.lock('portrait');
```


**unlock()**   
: 화면 방향 잠금 해제   



[top](#)
