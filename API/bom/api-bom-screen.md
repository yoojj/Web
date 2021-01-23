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



/* ScreenOrientation */
partial interface Screen {
  [SameObject] readonly attribute ScreenOrientation orientation;
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
orientation | 화면의 방향 반환  



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



[top](#)
