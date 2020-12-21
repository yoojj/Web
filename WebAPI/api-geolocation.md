# Geolocation API
: 유저 에이전트의 장치나 지리적 위치에 대한 정보를 식별하고 반환하는 API    
: IP 주소, 무선 네트워크 연결, 셀 타워, GPS 등의 정보를 통해 사용자 위치 파악   
: 이를 위해 사용자 동의가 필요하며 동의 없이는 사용 불가  
: 정확한 위치 정보가 필요한지 덜 정확한 위치 정보가 필요한지 구분        
&nbsp; (ex. 실시간 지도 탐색, 지리별 정보 제공, 지리별 광고 제공 등)


https://w3c.github.io/geolocation-api/


**+ GPS**  
: 정확한 위치 식별이 가능하나 GPS 칩은 전력을 많이 사용하여   
&nbsp; 기기에서 해당 기능을 끄고 필요시 GPS 위성 연결을 하므로 지연 시간이 발생   


**Geolocation**
- getCurrentPosition(Position, PositionError, PositionOptions)
- watchPosition(Position, PositionError, PositionOptions)
- clearWatch(watchId)


**GeolocationPosition**
- coords : 위치 좌표 정보
    - latitude : 위도 정보
    - longitude : 경도 정보
    - accuracy : 위도와 경도 정보의 정확도
    - altitude : 해수면 기준 고도 정보 (값을 보장 할 수 없음)
    - altitudeAccuracy : 고도 정보의 정확도 (값을 보장 할 수 없음)
    - heading : 북을 기준으로 방향 정보 (값을 보장 할 수 없음)
    - speed : 초당 속도 정보 (값을 보장 할 수 없음)
- timestamp : GeolocationPosition 객체 획득 시간  


**GeolocationPositionError**
- PERMISSION_DENIED
- POSITION_UNAVAILABLE
- TIMEOUT
- code
- message


**PositionOptions**
- maximumAge
- timeout


ex.
```js
interface Navigator {
    Geolocation geolocation;
};

navigator.geolocation.getCurrentPosition((data)=> {
    // 좌표 정보
    data.coords.latitude;
    data.coords.longitude;
});
```



[top](#)
