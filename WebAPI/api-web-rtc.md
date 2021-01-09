# WebRTC API
Web Real-Time Communications  
: 텍스트, 이미지, 음성, 영상같은 리소스를 별도의 플러그인없이 주고 받을 수 있는 규격    
: IETE에서 프로토콜 표준을 정의하고 W3C에서 API 표준을 정의  

https://www.w3.org/TR/webrtc/


**api**
- RTCPeerConnection
- RTCSctpTransport
- RTCDataChannel
- RTCError


**RFC**      
https://tools.ietf.org/html/rfc7478



## RTCPeerConnection

```webidl
[Exposed=Window]
interface RTCPeerConnection : EventTarget  {
  constructor(optional RTCConfiguration configuration = {});
  Promise<RTCSessionDescriptionInit> createOffer(optional RTCOfferOptions options = {});
  Promise<RTCSessionDescriptionInit> createAnswer(optional RTCAnswerOptions options = {});
  Promise<undefined> setLocalDescription(optional RTCLocalSessionDescriptionInit description = {});
  readonly attribute RTCSessionDescription? localDescription;
  readonly attribute RTCSessionDescription? currentLocalDescription;
  readonly attribute RTCSessionDescription? pendingLocalDescription;
  Promise<undefined> setRemoteDescription(RTCSessionDescriptionInit description);
  readonly attribute RTCSessionDescription? remoteDescription;
  readonly attribute RTCSessionDescription? currentRemoteDescription;
  readonly attribute RTCSessionDescription? pendingRemoteDescription;
  Promise<undefined> addIceCandidate(optional RTCIceCandidateInit candidate = {});
  readonly attribute RTCSignalingState signalingState;
  readonly attribute RTCIceGatheringState iceGatheringState;
  readonly attribute RTCIceConnectionState iceConnectionState;
  readonly attribute RTCPeerConnectionState connectionState;
  readonly attribute boolean? canTrickleIceCandidates;
  undefined restartIce();
  RTCConfiguration getConfiguration();
  undefined setConfiguration(optional RTCConfiguration configuration = {});
  undefined close();
  attribute EventHandler onnegotiationneeded;
  attribute EventHandler onicecandidate;
  attribute EventHandler onicecandidateerror;
  attribute EventHandler onsignalingstatechange;
  attribute EventHandler oniceconnectionstatechange;
  attribute EventHandler onicegatheringstatechange;
  attribute EventHandler onconnectionstatechange;

  Promise<undefined> createOffer(RTCSessionDescriptionCallback successCallback,
    RTCPeerConnectionErrorCallback failureCallback,
    optional RTCOfferOptions options = {});
  Promise<undefined> setLocalDescription(RTCLocalSessionDescriptionInit description,
    VoidFunction successCallback, RTCPeerConnectionErrorCallback failureCallback);
  Promise<undefined> createAnswer(RTCSessionDescriptionCallback successCallback,
    RTCPeerConnectionErrorCallback failureCallback);
  Promise<undefined> setRemoteDescription(RTCSessionDescriptionInit description,
    VoidFunction successCallback, RTCPeerConnectionErrorCallback failureCallback);
  Promise<undefined> addIceCandidate(RTCIceCandidateInit candidate,
    VoidFunction successCallback, RTCPeerConnectionErrorCallback failureCallback);
};
```



[top](#)
