# Geolocation API
: 유저 에이전트의 장치나 지리적 위치에 대한 정보를 식별하고 반환하는 API    
: IP 주소, 무선 네트워크 연결, 셀 타워, GPS 등의 정보를 통해 사용자 위치 파악   
: 이를 위해 사용자 동의가 필요하며 동의 없이는 사용 불가       
&nbsp; (ex. 실시간 지도 탐색, 지리별 정보 제공, 지리별 광고 제공 등)

**+ GPS**  
: 정확한 위치 식별이 가능하나 GPS 칩은 전력을 많이 사용하여   
&nbsp; 기기에서 해당 기능을 끄고 필요시 GPS 위성 연결을 하므로 지연 시간이 발생   
: 서비스에 따라 정확한 위치 정보가 필요한지 덜 정확한 위치 정보가 필요한지 구분이 필요     


https://www.w3.org/TR/geolocation-API/


**api**
- [Geolocation](#geolocation)
- [GeolocationPosition](#geolocationposition)
- [GeolocationCoordinates](#geolocationcoordinates)
- [GeolocationPositionError](#geolocationpositionerror)


ex.
```js
navigator.geolocation.getCurrentPosition((data)=> {
    // 좌표 정보
    data.coords.latitude;
    data.coords.longitude;
});
```



## Geolocation

```webidl
partial interface Navigator {
  [SameObject] readonly attribute Geolocation geolocation;
};


[Exposed=Window]
interface Geolocation {
  undefined getCurrentPosition(PositionCallback successCallback,
    optional PositionErrorCallback errorCallback,
    optional PositionOptions options = {});

  long watchPosition(PositionCallback successCallback,
    optional PositionErrorCallback errorCallback,
    optional PositionOptions options = {});

  undefined clearWatch(long watchId);
};

callback PositionCallback = undefined (GeolocationPosition position);

callback PositionErrorCallback = undefined (GeolocationPositionError positionError);


dictionary PositionOptions {
  boolean enableHighAccuracy = false;
  [Clamp] unsigned long timeout = 0xFFFFFFFF;
  [Clamp] unsigned long maximumAge = 0;
};
```


**getCurrentPosition()**   
: 장치의 현재 위치를 반환   



## GeolocationPosition

```webidl
[Exposed=Window, SecureContext]
interface GeolocationPosition {
  readonly attribute GeolocationCoordinates coords;
  readonly attribute DOMTimeStamp timestamp;
};
```


**timestamp**   
: GeolocationPosition 객체 획득 시간 반환  



## GeolocationCoordinates

```webidl
[Exposed=Window, SecureContext]
interface GeolocationCoordinates {
  readonly attribute double latitude;
  readonly attribute double longitude;
  readonly attribute double? altitude;
  readonly attribute double accuracy;
  readonly attribute double? altitudeAccuracy;
  readonly attribute double? heading;
  readonly attribute double? speed;
};
```


속성 | 설명
---|---
latitude | 위도 정보
longitude| 경도 정보
accuracy | 위도와 경도 정보의 정확도
altitude | 해수면 기준 고도 정보 (값을 보장 할 수 없음)
altitudeAccuracy | 고도 정보의 정확도 (값을 보장 할 수 없음)
heading  | 북을 기준으로 방향 정보 (값을 보장 할 수 없음)
speed    | 초당 속도 정보 (값을 보장 할 수 없음)



## GeolocationPositionError

```webidl
[Exposed=Window]
interface GeolocationPositionError {
  const unsigned short PERMISSION_DENIED = 1;
  const unsigned short POSITION_UNAVAILABLE = 2;
  const unsigned short TIMEOUT = 3;
  readonly attribute unsigned short code;
  readonly attribute DOMString message;
};
```



[top](#)
