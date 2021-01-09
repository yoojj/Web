# Web Audio API


https://www.w3.org/TR/webaudio/  
https://webaudio.github.io/web-audio-api/  


**api**
- BaseAudioContext
- AudioContext
- OfflineAudioContext
- OfflineAudioCompletionEvent
- AudioBuffer
- AudioNode
- AudioParam
- AudioScheduledSourceNode
- AnalyserNode
- AudioBufferSourceNode
- AudioDestinationNode
- AudioListener
- AudioProcessingEvent
- BiquadFilterNode
- ChannelMergerNode
- ChannelSplitterNode
- ConstantSourceNode
- ConvolverNode
- DelayNode
- DynamicsCompressorNode
- GainNode
- IIRFilterNode
- ...



## BaseAudioContext

```webidl
[Exposed=Window]
interface BaseAudioContext : EventTarget {
  readonly attribute AudioDestinationNode destination;
  readonly attribute float sampleRate;
  readonly attribute double currentTime;
  readonly attribute AudioListener listener;
  readonly attribute AudioContextState state;
  readonly attribute AudioWorklet audioWorklet;
  attribute EventHandler onstatechange;

  AnalyserNode createAnalyser();
  BiquadFilterNode createBiquadFilter();
  AudioBuffer createBuffer(unsigned long numberOfChannels,
    unsigned long length, float sampleRate);
  AudioBufferSourceNode createBufferSource();
  ChannelMergerNode createChannelMerger(optional unsigned long
    numberOfInputs = 6);
  ChannelSplitterNode createChannelSplitter(optional unsigned long
    numberOfOutputs = 6);
  ConstantSourceNode createConstantSource();
  ConvolverNode createConvolver();
  DelayNode createDelay(optional double maxDelayTime = 1.0);
  DynamicsCompressorNode createDynamicsCompressor();
  GainNode createGain();
  IIRFilterNode createIIRFilter(sequence<double> feedforward,
    sequence<double> feedback);
  OscillatorNode createOscillator();
  PannerNode createPanner();
  PeriodicWave createPeriodicWave(sequence<float> real,
    sequence<float> imag, optional PeriodicWaveConstraints constraints = {});

  ScriptProcessorNode createScriptProcessor(
    optional unsigned long bufferSize = 0,
    optional unsigned long numberOfInputChannels = 2,
    optional unsigned long numberOfOutputChannels = 2);
  StereoPannerNode createStereoPanner();
  WaveShaperNode createWaveShaper();

  Promise<AudioBuffer> decodeAudioData(
    ArrayBuffer audioData,
    optional DecodeSuccessCallback? successCallback,
    optional DecodeErrorCallback? errorCallback);
};

enum AudioContextState { "suspended", "running", "closed" };
```



## AudioContext

```webidl
[Exposed=Window]
interface AudioContext : BaseAudioContext {
  constructor(optional AudioContextOptions contextOptions = {});
  readonly attribute double baseLatency;
  readonly attribute double outputLatency;
  AudioTimestamp getOutputTimestamp();
  Promise<void> resume();
  Promise<void> suspend();
  Promise<void> close();
  MediaElementAudioSourceNode createMediaElementSource(HTMLMediaElement
    mediaElement);
  MediaStreamAudioSourceNode createMediaStreamSource(MediaStream mediaStream);
  MediaStreamTrackAudioSourceNode createMediaStreamTrackSource(
    MediaStreamTrack mediaStreamTrack);
  MediaStreamAudioDestinationNode createMediaStreamDestination();
};

dictionary AudioContextOptions {
  (AudioContextLatencyCategory or double) latencyHint = "interactive";
  float sampleRate;
};

dictionary AudioTimestamp {
  double contextTime;
  DOMHighResTimeStamp performanceTime;
};

enum AudioContextLatencyCategory {
    "balanced",
    "interactive",
    "playback"
};
```



## OfflineAudioContext

```webidl
[Exposed=Window]
interface OfflineAudioContext : BaseAudioContext {
  constructor(OfflineAudioContextOptions contextOptions);
  constructor(unsigned long numberOfChannels, unsigned long length,
    float sampleRate);
  Promise<AudioBuffer> startRendering();
  Promise<void> resume();
  Promise<void> suspend(double suspendTime);
  readonly attribute unsigned long length;
  attribute EventHandler oncomplete;
};

dictionary OfflineAudioContextOptions {
  unsigned long numberOfChannels = 1;
  required unsigned long length;
  required float sampleRate;
};
```



## OfflineAudioCompletionEvent

```webidl
[Exposed=Window]
interface OfflineAudioCompletionEvent : Event {
  constructor (DOMString type, OfflineAudioCompletionEventInit
    eventInitDict);
  readonly attribute AudioBuffer renderedBuffer;
};

dictionary OfflineAudioCompletionEventInit : EventInit {
  required AudioBuffer renderedBuffer;
};
```



## AudioBuffer

```webidl
[Exposed=Window]
interface AudioBuffer {
  constructor (AudioBufferOptions options);
  readonly attribute float sampleRate;
  readonly attribute unsigned long length;
  readonly attribute double duration;
  readonly attribute unsigned long numberOfChannels;
  Float32Array getChannelData (unsigned long channel);
  void copyFromChannel (Float32Array destination,
    unsigned long channelNumber, optional unsigned long bufferOffset = 0);
  void copyToChannel (Float32Array source,
    unsigned long channelNumber, optional unsigned long bufferOffset = 0);
};

dictionary AudioBufferOptions {
  unsigned long numberOfChannels = 1;
  required unsigned long length;
  required float sampleRate;
};
```



[top](#)
