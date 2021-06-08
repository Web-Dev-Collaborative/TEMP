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
3.  <a href="AudioContext.html" class="breadcrumb-current-page"><span data-property="name">AudioContext</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioContext
============

<span class="seoSummary">The `AudioContext` interface represents an audio-processing graph built from audio modules linked together, each represented by an [`AudioNode`](AudioNode.html).</span> An audio context controls both the creation of the nodes it contains and the execution of the audio processing, or decoding. You need to create an `AudioContext` before you do anything else, as everything happens inside a context. It's recommended to create one AudioContext and reuse it instead of initializing a new one each time, and it's OK to use a single `AudioContext` for several different audio sources and pipeline concurrently.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

 [`AudioContext()`](AudioContext/AudioContext.html "AudioContext()")   
Creates and returns a new `AudioContext` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Also inherits properties from its parent interface, [`BaseAudioContext`](BaseAudioContext.html).*

 [`AudioContext.baseLatency`](AudioContext/baseLatency.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns the number of seconds of processing latency incurred by the [`AudioContext`](AudioContext.html) passing the audio from the [`AudioDestinationNode`](AudioDestinationNode.html) to the audio subsystem.

 [`AudioContext.outputLatency`](AudioContext/outputLatency.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns an estimation of the output latency of the current audio context.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Also inherits methods from its parent interface, [`BaseAudioContext`](BaseAudioContext.html).*

 [`AudioContext.close()`](AudioContext/close.html)   
Closes the audio context, releasing any system audio resources that it uses.

 [`AudioContext.createMediaElementSource()`](AudioContext/createMediaElementSource.html)   
Creates a [`MediaElementAudioSourceNode`](MediaElementAudioSourceNode.html) associated with an [`HTMLMediaElement`](HTMLMediaElement.html). This can be used to play and manipulate audio from [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) or [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) elements.

 [`AudioContext.createMediaStreamSource()`](AudioContext/createMediaStreamSource.html)   
Creates a [`MediaStreamAudioSourceNode`](MediaStreamAudioSourceNode.html) associated with a [`MediaStream`](MediaStream.html) representing an audio stream which may come from the local computer microphone or other sources.

 [`AudioContext.createMediaStreamDestination()`](AudioContext/createMediaStreamDestination.html)   
Creates a [`MediaStreamAudioDestinationNode`](MediaStreamAudioDestinationNode.html) associated with a [`MediaStream`](MediaStream.html) representing an audio stream which may be stored in a local file or sent to another computer.

 [`AudioContext.createMediaStreamTrackSource()`](AudioContext/createMediaStreamTrackSource.html)   
Creates a [`MediaStreamTrackAudioSourceNode`](MediaStreamTrackAudioSourceNode.html) associated with a [`MediaStream`](MediaStream.html) representing an media stream track.

 [`AudioContext.getOutputTimestamp()`](AudioContext/getOutputTimestamp.html)   
Returns a new `AudioTimestamp` object containing two audio timestamp values relating to the current audio context.

 [`AudioContext.resume()`](AudioContext/resume.html)   
Resumes the progression of time in an audio context that has previously been suspended/paused.

 [`AudioContext.suspend()`](AudioContext/suspend.html)   
Suspends the progression of time in the audio context, temporarily halting audio hardware access and reducing CPU/battery usage in the process.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

Basic audio context declaration:

    var audioCtx = new AudioContext();

Cross browser variant:

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    var oscillatorNode = audioCtx.createOscillator();
    var gainNode = audioCtx.createGain();
    var finish = audioCtx.destination;
    // etc.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioContext" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioContext' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)
-   [`OfflineAudioContext`](OfflineAudioContext.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audiocontext/index.html "Folder: en-us/web/api/audiocontext (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioContext%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudiocontext%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioContext%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudiocontext%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioContext%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](AudioContext/contributors.txt)

Change your language Select your preferred language English (US) Deutsch Français 日本語 한국어 Polski Português (do Brasil) Русский 中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioContext`](AudioContext.html)**
3.  Constructor
    1.  [`AudioContext()`](AudioContext/AudioContext.html)
4.  Properties
    1.  [`baseLatency`](AudioContext/baseLatency.html)
    2.  [`outputLatency`](AudioContext/outputLatency.html)
5.  Methods
    1.  [`close()`](AudioContext/close.html)
    2.  [`createJavaScriptNode()`](AudioContext/createJavaScriptNode.html)
    3.  [`createMediaElementSource()`](AudioContext/createMediaElementSource.html)
    4.  [`createMediaStreamDestination()`](AudioContext/createMediaStreamDestination.html)
    5.  [`createMediaStreamSource()`](AudioContext/createMediaStreamSource.html)
    6.  [`createMediaStreamTrackSource()`](AudioContext/createMediaStreamTrackSource.html)
    7.  [`getOutputTimestamp()`](AudioContext/getOutputTimestamp.html)
    8.  [`resume()`](AudioContext/resume.html)
    9.  [`suspend()`](AudioContext/suspend.html)
6.  Inheritance:
    1.  [`BaseAudioContext`](BaseAudioContext.html)
    2.  [`EventTarget`](EventTarget.html)
7.  Related pages for Web Audio API
    1.  [`AnalyserNode`](AnalyserNode.html)
    2.  [`AudioBuffer`](AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](AudioBufferSourceNode.html)
    4.  [`AudioContextOptions`](AudioContextOptions.html)
    5.  [`AudioDestinationNode`](AudioDestinationNode.html)
    6.  [`AudioListener`](AudioListener.html)
    7.  [`AudioNode`](AudioNode.html)
    8.  [`AudioNodeOptions`](AudioNodeOptions.html)
    9.  [`AudioParam`](AudioParam.html)
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
