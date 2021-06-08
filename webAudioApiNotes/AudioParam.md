-   <a href="#content" id="skip-main">Skip to main content</a>
-   <a href="#main-q" id="skip-search">Skip to search</a>
-   <a href="#select-language" id="skip-select-language">Skip to select language</a>

-   Technologies
    -   [Technologies Overview](https://developer.mozilla.org/en-US/docs/Web)
    -   [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
    -   [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
    -   [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
    -   [Graphics](https://developer.mozilla.org/en-US/docs/Web/Guide/Graphics)
    -   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)
    -   [APIs](https://developer.mozilla.org/en-US/docs/Web/API)
    -   [Browser Extensions](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions)
    -   [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML)
-   References & Guides
    -   [Learn web development](https://developer.mozilla.org/en-US/docs/Learn)
    -   [Tutorials](https://developer.mozilla.org/en-US/docs/Web/Tutorials)
    -   [References](https://developer.mozilla.org/en-US/docs/Web/Reference)
    -   [Developer Guides](https://developer.mozilla.org/en-US/docs/Web/Guide)
    -   [Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
    -   [Game development](https://developer.mozilla.org/en-US/docs/Games)
    -   [...more docs](https://developer.mozilla.org/en-US/docs/Web)
-   Feedback
    -   [Send Feedback](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Feedback)
    -   [Contribute to MDN](https://developer.mozilla.org/en-US/docs/MDN/Contribute)
    -   [Report a content issue 🌐](https://github.com/mdn/content/issues/new)
    -   [Report a platform issue 🌐](https://github.com/mdn/yari/issues/new)

Search MDN

1.  <a href="https://developer.mozilla.org/en-US/docs/Web" class="breadcrumb"><span data-property="name">Web technology for developers</span></a>
2.  <a href="https://developer.mozilla.org/en-US/docs/Web/API" class="breadcrumb-penultimate"><span data-property="name">Web APIs</span></a>
3.  <a href="AudioParam.html" class="breadcrumb-current-page"><span data-property="name">AudioParam</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioParam
==========

<span class="seoSummary">The Web Audio API's `AudioParam` interface represents an audio-related parameter, usually a parameter of an [`AudioNode`](AudioNode.html) (such as [`GainNode.gain`](GainNode/gain.html)).</span> An `AudioParam` can be set to a specific value or a change in value, and can be scheduled to happen at a specific time and following a specific pattern.

There are two kinds of `AudioParam`, *a-rate* and *k-rate* parameters:

-   <span id="a-rate">An *a-rate* `AudioParam` takes the current audio parameter value for each [sample frame](Web_Audio_API/Basic_concepts_behind_Web_Audio_API.html#audio_buffers.3a_frames.2c_samples_and_channels) of the audio signal.</span>
-   <span id="k-rate">A *k-rate* `AudioParam` uses the same initial audio parameter value for the whole block processed, that is 128 sample frames. In other words, the same value applies to every frame in the audio as it's processed by the node.</span>

Each [`AudioNode`](AudioNode.html) defines which of its parameters are *a-rate* or *k-rate* in the spec.

Each `AudioParam` has a list of events, initially empty, that define when and how values change. When this list is not empty, changes using the `AudioParam.value` attributes are ignored. This list of events allows us to schedule changes that have to happen at very precise times, using arbitrary timelime-based automation curves. The time used is the one defined in [`AudioContext.currentTime`](BaseAudioContext/currentTime.html "AudioContext.currentTime").

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`AudioParam.defaultValue`](AudioParam/defaultValue.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Represents the initial volume of the attribute as defined by the specific [`AudioNode`](AudioNode.html) creating the `AudioParam`.

[`AudioParam.maxValue`](AudioParam/maxValue.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Represents the maximum possible value for the parameter's nominal (effective) range. 

[`AudioParam.minValue`](AudioParam/minValue.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Represents the minimum possible value for the parameter's nominal (effective) range. 

[`AudioParam.value`](AudioParam/value.html)  
Represents the parameter's current value as of the current time; initially set to the value of [`defaultValue`](AudioParam/defaultValue.html "defaultValue").

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`AudioParam.setValueAtTime()`](AudioParam/setValueAtTime.html)  
Schedules an instant change to the value of the `AudioParam` at a precise time, as measured against [`AudioContext.currentTime`](BaseAudioContext/currentTime.html "AudioContext.currentTime"). The new value is given by the `value` parameter.

[`AudioParam.linearRampToValueAtTime()`](AudioParam/linearRampToValueAtTime.html)  
Schedules a gradual linear change in the value of the `AudioParam`. The change starts at the time specified for the *previous* event, follows a linear ramp to the new value given in the `value` parameter, and reaches the new value at the time given in the `endTime` parameter.

[`AudioParam.exponentialRampToValueAtTime()`](AudioParam/exponentialRampToValueAtTime.html)  
Schedules a gradual exponential change in the value of the `AudioParam`. The change starts at the time specified for the *previous* event, follows an exponential ramp to the new value given in the `value` parameter, and reaches the new value at the time given in the `endTime` parameter.

[`AudioParam.setTargetAtTime()`](AudioParam/setTargetAtTime.html)  
Schedules the start of a change to the value of the `AudioParam`. The change starts at the time specified in `startTime` and exponentially moves towards the value given by the `target` parameter. The exponential decay rate is defined by the `timeConstant` parameter, which is a time measured in seconds.

[`AudioParam.setValueCurveAtTime()`](AudioParam/setValueCurveAtTime.html)  
Schedules the values of the `AudioParam` to follow a set of values, defined by an array of floating-point numbers scaled to fit into the given interval, starting at a given start time and spanning a given duration of time.

[`AudioParam.cancelScheduledValues()`](AudioParam/cancelScheduledValues.html)  
Cancels all scheduled future changes to the `AudioParam`.

[`AudioParam.cancelAndHoldAtTime()`](AudioParam/cancelAndHoldAtTime.html)  
Cancels all scheduled future changes to the `AudioParam` but holds its value at a given time until further changes are made using other methods.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

First, a basic example showing a [`GainNode`](GainNode.html) having its `gain` value set. `gain` is an example of an a-rate AudioParam, as the value can potentially be set differently for each sample frame of the audio.

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    var gainNode = audioCtx.createGain();
    gainNode.gain.value = 0;

Next, an example showing a [`DynamicsCompressorNode`](DynamicsCompressorNode.html) having some param values manipulated. These are examples of k-rate AudioParam's, as the values are set for the entire audio block at once.

    var compressor = audioCtx.createDynamicsCompressor();
    compressor.threshold.setValueAtTime(-50, audioCtx.currentTime);
    compressor.knee.setValueAtTime(40, audioCtx.currentTime);
    compressor.ratio.setValueAtTime(12, audioCtx.currentTime);
    compressor.attack.setValueAtTime(0, audioCtx.currentTime);
    compressor.release.setValueAtTime(0.25, audioCtx.currentTime);

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioParam" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioParam' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audioparam/index.html "Folder: en-us/web/api/audioparam (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioParam%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudioparam%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioParam%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudioparam%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioParam%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](AudioParam/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語한국어PolskiРусский中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioParam`](AudioParam.html)**
3.  Properties
    1.  [`defaultValue`](AudioParam/defaultValue.html)
    2.  [`maxValue`](AudioParam/maxValue.html)
    3.  [`minValue`](AudioParam/minValue.html)
    4.  [`value`](AudioParam/value.html)
4.  Methods
    1.  [`cancelAndHoldAtTime()`](AudioParam/cancelAndHoldAtTime.html)
    2.  [`cancelScheduledValues()`](AudioParam/cancelScheduledValues.html)
    3.  [`exponentialRampToValueAtTime()`](AudioParam/exponentialRampToValueAtTime.html)
    4.  [`linearRampToValueAtTime()`](AudioParam/linearRampToValueAtTime.html)
    5.  [`setTargetAtTime()`](AudioParam/setTargetAtTime.html)
    6.  [`setValueAtTime()`](AudioParam/setValueAtTime.html)
    7.  [`setValueCurveAtTime()`](AudioParam/setValueCurveAtTime.html)
5.  Related pages for Web Audio API
    1.  [`AnalyserNode`](AnalyserNode.html)
    2.  [`AudioBuffer`](AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](AudioBufferSourceNode.html)
    4.  [`AudioContext`](AudioContext.html)
    5.  [`AudioContextOptions`](AudioContextOptions.html)
    6.  [`AudioDestinationNode`](AudioDestinationNode.html)
    7.  [`AudioListener`](AudioListener.html)
    8.  [`AudioNode`](AudioNode.html)
    9.  [`AudioNodeOptions`](AudioNodeOptions.html)
    10. [`AudioProcessingEvent`](AudioProcessingEvent.html)
    11. [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)
    12. [`AudioWorklet`](AudioWorklet.html)
    13. [`AudioWorkletGlobalScope`](AudioWorkletGlobalScope.html)
    14. [`AudioWorkletNode`](AudioWorkletNode.html)
    15. [`AudioWorkletProcessor`](AudioWorkletProcessor.html)
    16. [`BaseAudioContext`](BaseAudioContext.html)
    17. [`BiquadFilterNode`](BiquadFilterNode.html)
    18. [`ChannelMergerNode`](ChannelMergerNode.html)
    19. [`ChannelSplitterNode`](ChannelSplitterNode.html)
    20. [`ConstantSourceNode`](ConstantSourceNode.html)
    21. [`ConvolverNode`](ConvolverNode.html)
    22. [`DelayNode`](DelayNode.html)
    23. [`DynamicsCompressorNode`](DynamicsCompressorNode.html)
    24. [`GainNode`](GainNode.html)
    25. [`IIRFilterNode`](IIRFilterNode.html)
    26. [`MediaElementAudioSourceNode`](MediaElementAudioSourceNode.html)
    27. [`MediaStreamAudioDestinationNode`](MediaStreamAudioDestinationNode.html)
    28. [`MediaStreamAudioSourceNode`](MediaStreamAudioSourceNode.html)
    29. [`OfflineAudioCompletionEvent`](OfflineAudioCompletionEvent.html)
    30. [`OfflineAudioContext`](OfflineAudioContext.html)
    31. [`OscillatorNode`](OscillatorNode.html)
    32. [`PannerNode`](PannerNode.html)
    33. [`PeriodicWave`](PeriodicWave.html)
    34. [`StereoPannerNode`](StereoPannerNode.html)
    35. [`WaveShaperNode`](WaveShaperNode.html)

-   [Web Technologies](https://developer.mozilla.org/en-US/docs/Web)
-   [Learn Web Development](https://developer.mozilla.org/en-US/docs/Learn)
-   [About MDN](https://developer.mozilla.org/en-US/docs/MDN/About)
-   [Feedback](https://developer.mozilla.org/en-US/docs/MDN/Feedback)

<!-- -->

-   [About](https://www.mozilla.org/about/)
-   [MDN Web Docs Store](https://shop.spreadshirt.com/mdn-store/)
-   [Contact Us](https://www.mozilla.org/contact/)
-   [Firefox](https://www.mozilla.org/firefox/?utm_source=developer.mozilla.org&utm_campaign=footer&utm_medium=referral)

#### MDN

-   <a href="https://twitter.com/mozdevnet" class="social-icon twitter"><span class="visually-hidden">MDN on Twitter</span></a>
-   <a href="https://github.com/mdn/" class="social-icon github"><span class="visually-hidden">MDN on Github</span></a>
