---
title: AudioContext: AudioContext() 构造函数
slug: Web/API/AudioContext/AudioContext
---

{{APIRef("Web Audio API")}}{{SeeCompatTable}}

**`AudioContext()`** 构造方法创建了一个新的 {{domxref("AudioContext")}} 对象 它代表了一个由音频模块链接而成的音频处理图，每一个模块由 {{domxref("AudioNode")}} 表示。

## 语法

```js-nolint
new AudioContext()
new AudioContext(options)
```

### 参数

- _options_ {{optional_inline}}
  - : Options 如下所示：
    - `latencyHint`: 这个参数表示了重放的类型，参数是播放效果和资源消耗的一种权衡。可接受的值有 "balanced", "interactive" 和"playback"，默认值为 "interactive"。意思是 "平衡音频输出延迟和资源消耗", "提供最小的音频输出延迟最好没有干扰"和 "对比音频输出延迟，优先重放不被中断"。我们也可以用一个双精度的值来定义一个秒级的延迟数值做到更精确的控制。
    - `sampleRate` {{optional_inline}}
      - : Indicates the sample rate to use for the new context. The value must be a floating-point value indicating the sample rate,
        in samples per second, for which to configure the new context;
        additionally, the value must be one which is supported by {{domxref("AudioBuffer.sampleRate")}}.
        The value will typically be between 8,000 Hz and 96,000 Hz; the default will vary depending on the output device, but the sample rate 44,100 Hz is the most common.
        If the `sampleRate` property is not included in the options, or the options are not specified when creating the audio context,
        the new context's output device's preferred sample rate is used by default.
    - `sinkId` {{optional_inline}} {{Experimental_Inline}}
      - : Specifies the sink ID of the audio output device to use for the `AudioContext`. This can take one of the following value types:
        - A string representing the sink ID, retrieved for example via the `deviceId` property of the {{domxref("MediaDeviceInfo")}} objects returned by {{domxref("MediaDevices.enumerateDevices()")}}.
        - An object representing different options for a sink ID. Currently, this takes a single property, `type`, with a value of `none`. Setting this parameter causes the audio to be processed without being played through any audio output device.


### 返回值

一个 {{domxref("AudioContext")}} 实例。

### Exceptions

- `NotSupportedError` {{domxref("DOMException")}}
  - : 在不支持指定的 `sampleRate` 时抛出。

## 规范

{{Specifications}}

## 浏览器兼容性

{{Compat}}
