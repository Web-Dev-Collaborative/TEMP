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
3.  <a href="BaseAudioContext.html" class="breadcrumb-current-page"><span data-property="name">BaseAudioContext</span></a>

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

BaseAudioContext
================

<span class="seoSummary">The `BaseAudioContext` interface of the [Web Audio API](Web_Audio_API.html) acts as a base definition for online and offline audio-processing graphs, as represented by [`AudioContext`](AudioContext.html) and [`OfflineAudioContext`](OfflineAudioContext.html) respectively.</span> You wouldn't use `BaseAudioContext` directly — you'd use its features via one of these two inheriting interfaces.

A `BaseAudioContext` can be a target of events, therefore it implements the [`EventTarget`](EventTarget.html) interface.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`BaseAudioContext.audioWorklet`](BaseAudioContext/audioWorklet.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span> <span class="notecard inline secure" title="This feature is available only in secure contexts (HTTPS)">Secure context</span>  
Returns the [`AudioWorklet`](AudioWorklet.html) object, which can be used to create and manage [`AudioNode`](AudioNode.html)s in which JavaScript code implementing the [`AudioWorkletProcessor`](AudioWorkletProcessor.html) interface are run in the background to process audio data.

[`BaseAudioContext.currentTime`](BaseAudioContext/currentTime.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a double representing an ever-increasing hardware time in seconds used for scheduling. It starts at `0`.

[`BaseAudioContext.destination`](BaseAudioContext/destination.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an [`AudioDestinationNode`](AudioDestinationNode.html) representing the final destination of all audio in the context. It can be thought of as the audio-rendering device.

[`BaseAudioContext.listener`](BaseAudioContext/listener.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the [`AudioListener`](AudioListener.html) object, used for 3D spatialization.

[`BaseAudioContext.sampleRate`](BaseAudioContext/sampleRate.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a float representing the sample rate (in samples per second) used by all nodes in this context. The sample-rate of an [`AudioContext`](AudioContext.html) cannot be changed.

[`BaseAudioContext.state`](BaseAudioContext/state.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the current state of the `AudioContext`.

### [Event handlers](#event_handlers "Permalink to Event handlers")

[`BaseAudioContext.onstatechange`](BaseAudioContext/onstatechange.html)  
An event handler that runs when an event of type `statechange` has fired. This occurs when the `AudioContext`'s state changes, due to the calling of one of the state change methods ([`AudioContext.suspend`](AudioContext/suspend.html), [`AudioContext.resume`](AudioContext/resume.html), or [`AudioContext.close`](AudioContext/close.html)).

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Also implements methods from the interface* [`EventTarget`](EventTarget.html).

[`BaseAudioContext.createAnalyser()`](BaseAudioContext/createAnalyser.html)  
Creates an [`AnalyserNode`](AnalyserNode.html), which can be used to expose audio time and frequency data and for example to create data visualisations.

[`BaseAudioContext.createBiquadFilter()`](BaseAudioContext/createBiquadFilter.html)  
Creates a [`BiquadFilterNode`](BiquadFilterNode.html), which represents a second order filter configurable as several different common filter types: high-pass, low-pass, band-pass, etc

[`BaseAudioContext.createBuffer()`](BaseAudioContext/createBuffer.html)  
Creates a new, empty [`AudioBuffer`](AudioBuffer.html) object, which can then be populated by data and played via an [`AudioBufferSourceNode`](AudioBufferSourceNode.html).

[`BaseAudioContext.createBufferSource()`](BaseAudioContext/createBufferSource.html)  
Creates an [`AudioBufferSourceNode`](AudioBufferSourceNode.html), which can be used to play and manipulate audio data contained within an [`AudioBuffer`](AudioBuffer.html) object. [`AudioBuffer`](AudioBuffer.html)s are created using [`AudioContext.createBuffer()`](BaseAudioContext/createBuffer.html "AudioContext.createBuffer()") or returned by [`AudioContext.decodeAudioData()`](BaseAudioContext/decodeAudioData.html "AudioContext.decodeAudioData()") when it successfully decodes an audio track.

[`BaseAudioContext.createConstantSource()`](BaseAudioContext/createConstantSource.html)  
Creates a [`ConstantSourceNode`](ConstantSourceNode.html) object, which is an audio source that continuously outputs a monaural (one-channel) sound signal whose samples all have the same value.

[`BaseAudioContext.createChannelMerger()`](BaseAudioContext/createChannelMerger.html)  
Creates a [`ChannelMergerNode`](ChannelMergerNode.html), which is used to combine channels from multiple audio streams into a single audio stream.

[`BaseAudioContext.createChannelSplitter()`](BaseAudioContext/createChannelSplitter.html)  
Creates a [`ChannelSplitterNode`](ChannelSplitterNode.html), which is used to access the individual channels of an audio stream and process them separately.

[`BaseAudioContext.createConvolver()`](BaseAudioContext/createConvolver.html)  
Creates a [`ConvolverNode`](ConvolverNode.html), which can be used to apply convolution effects to your audio graph, for example a reverberation effect.

[`BaseAudioContext.createDelay()`](BaseAudioContext/createDelay.html)  
Creates a [`DelayNode`](DelayNode.html), which is used to delay the incoming audio signal by a certain amount. This node is also useful to create feedback loops in a Web Audio API graph.

[`BaseAudioContext.createDynamicsCompressor()`](BaseAudioContext/createDynamicsCompressor.html)  
Creates a [`DynamicsCompressorNode`](DynamicsCompressorNode.html), which can be used to apply acoustic compression to an audio signal.

[`BaseAudioContext.createGain()`](BaseAudioContext/createGain.html)  
Creates a [`GainNode`](GainNode.html), which can be used to control the overall volume of the audio graph.

[`BaseAudioContext.createIIRFilter()`](BaseAudioContext/createIIRFilter.html)  
Creates an [`IIRFilterNode`](IIRFilterNode.html), which represents a second order filter configurable as several different common filter types.

[`BaseAudioContext.createOscillator()`](BaseAudioContext/createOscillator.html)  
Creates an [`OscillatorNode`](OscillatorNode.html), a source representing a periodic waveform. It basically generates a tone.

[`BaseAudioContext.createPanner()`](BaseAudioContext/createPanner.html)  
Creates a [`PannerNode`](PannerNode.html), which is used to spatialise an incoming audio stream in 3D space.

[`BaseAudioContext.createPeriodicWave()`](BaseAudioContext/createPeriodicWave.html)  
Creates a [`PeriodicWave`](PeriodicWave.html), used to define a periodic waveform that can be used to determine the output of an [`OscillatorNode`](OscillatorNode.html).

[`BaseAudioContext.createScriptProcessor()`](BaseAudioContext/createScriptProcessor.html)   
Creates a [`ScriptProcessorNode`](ScriptProcessorNode.html), which can be used for direct audio processing via JavaScript.

[`BaseAudioContext.createStereoPanner()`](BaseAudioContext/createStereoPanner.html)  
Creates a [`StereoPannerNode`](StereoPannerNode.html), which can be used to apply stereo panning to an audio source.

[`BaseAudioContext.createWaveShaper()`](BaseAudioContext/createWaveShaper.html)  
Creates a [`WaveShaperNode`](WaveShaperNode.html), which is used to implement non-linear distortion effects.

[`BaseAudioContext.decodeAudioData()`](BaseAudioContext/decodeAudioData.html)  
Asynchronously decodes audio file data contained in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer). In this case, the ArrayBuffer is usually loaded from an [`XMLHttpRequest`](XMLHttpRequest.html)'s `response` attribute after setting the `responseType` to `arraybuffer`. This method only works on complete files, not fragments of audio files.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

Basic audio context declaration:

    const audioContext = new AudioContext();

Cross browser variant:

    const AudioContext = window.AudioContext || window.webkitAudioContext;
    const audioContext = new AudioContext();

    const oscillatorNode = audioContext.createOscillator();
    const gainNode = audioContext.createGain();
    const finish = audioContext.destination;

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#BaseAudioContext" class="external">Web Audio API<br />
<span class="small">The definition of 'BaseAudioContext' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)
-   [`AudioContext`](AudioContext.html)
-   [`OfflineAudioContext`](OfflineAudioContext.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/baseaudiocontext/index.html "Folder: en-us/web/api/baseaudiocontext (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBaseAudioContext%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fbaseaudiocontext%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBaseAudioContext%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fbaseaudiocontext%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F591362776c1ef3ad42942777979939e511dd811f%0A*+Document+last+modified%3A+2021-05-29T03%3A45%3A05.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22BaseAudioContext%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](BaseAudioContext/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`BaseAudioContext`](BaseAudioContext.html)**
3.  Properties
    1.  [`audioWorklet`](BaseAudioContext/audioWorklet.html)
    2.  [`currentTime`](BaseAudioContext/currentTime.html)
    3.  [`destination`](BaseAudioContext/destination.html)
    4.  [`listener`](BaseAudioContext/listener.html)
    5.  [`sampleRate`](BaseAudioContext/sampleRate.html)
    6.  [`state`](BaseAudioContext/state.html)
4.  Methods
    1.  [`createAnalyser()`](BaseAudioContext/createAnalyser.html)
    2.  [`createBiquadFilter()`](BaseAudioContext/createBiquadFilter.html)
    3.  [`createBuffer()`](BaseAudioContext/createBuffer.html)
    4.  [`createBufferSource()`](BaseAudioContext/createBufferSource.html)
    5.  [`createChannelMerger()`](BaseAudioContext/createChannelMerger.html)
    6.  [`createChannelSplitter()`](BaseAudioContext/createChannelSplitter.html)
    7.  [`createConstantSource()`](BaseAudioContext/createConstantSource.html)
    8.  [`createConvolver()`](BaseAudioContext/createConvolver.html)
    9.  [`createDelay()`](BaseAudioContext/createDelay.html)
    10. [`createDynamicsCompressor()`](BaseAudioContext/createDynamicsCompressor.html)
    11. [`createGain()`](BaseAudioContext/createGain.html)
    12. [`createIIRFilter()`](BaseAudioContext/createIIRFilter.html)
    13. [`createOscillator()`](BaseAudioContext/createOscillator.html)
    14. [`createPanner()`](BaseAudioContext/createPanner.html)
    15. [`createPeriodicWave()`](BaseAudioContext/createPeriodicWave.html)
    16. [`createScriptProcessor()`](BaseAudioContext/createScriptProcessor.html)
    17. [`createStereoPanner()`](BaseAudioContext/createStereoPanner.html)
    18. [`createWaveShaper()`](BaseAudioContext/createWaveShaper.html)
    19. [`decodeAudioData()`](BaseAudioContext/decodeAudioData.html)
5.  Inheritance:
    1.  [`EventTarget`](EventTarget.html)
6.  Related pages for Web Audio API
    1.  [`AnalyserNode`](AnalyserNode.html)
    2.  [`AudioBuffer`](AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](AudioBufferSourceNode.html)
    4.  [`AudioContext`](AudioContext.html)
    5.  [`AudioContextOptions`](AudioContextOptions.html)
    6.  [`AudioDestinationNode`](AudioDestinationNode.html)
    7.  [`AudioListener`](AudioListener.html)
    8.  [`AudioNode`](AudioNode.html)
    9.  [`AudioNodeOptions`](AudioNodeOptions.html)
    10. [`AudioParam`](AudioParam.html)
    11. [`AudioProcessingEvent`](AudioProcessingEvent.html)
    12. [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)
    13. [`AudioWorklet`](AudioWorklet.html)
    14. [`AudioWorkletGlobalScope`](AudioWorkletGlobalScope.html)
    15. [`AudioWorkletNode`](AudioWorkletNode.html)
    16. [`AudioWorkletProcessor`](AudioWorkletProcessor.html)
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
