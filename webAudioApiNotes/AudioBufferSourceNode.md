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
3.  <a href="AudioBufferSourceNode.html" class="breadcrumb-current-page"><span data-property="name">AudioBufferSourceNode</span></a>

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

AudioBufferSourceNode
=====================

<span class="seoSummary">The **`AudioBufferSourceNode`** interface is an [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html) which represents an audio source consisting of in-memory audio data, stored in an [`AudioBuffer`](AudioBuffer.html). It's especially useful for playing back audio which has particularly stringent timing accuracy requirements, such as for sounds that must match a specific rhythm and can be kept in memory rather than being played from disk or the network.</span> To play sounds which require accurate timing but must be streamed from the network or played from disk, use a [`AudioWorkletNode`](AudioWorkletNode.html) to implement its playback.

An `AudioBufferSourceNode` has no inputs and exactly one output, which has the same number of channels as the `AudioBuffer` indicated by its [`buffer`](AudioBufferSourceNode/buffer.html "buffer") property. If there's no buffer set—that is, if `buffer` is `null`—the output contains a single channel of silence (every sample is 0).

An `AudioBufferSourceNode` can only be played once; after each call to [`start()`](AudioScheduledSourceNode/start.html "start()"), you have to create a new node if you want to play the same sound again. Fortunately, these nodes are very inexpensive to create, and the actual `AudioBuffer`s can be reused for multiple plays of the sound. Indeed, you can use these nodes in a "fire and forget" manner: create the node, call `start()` to begin playing the sound, and don't even bother to hold a reference to it. It will automatically be garbage-collected at an appropriate time, which won't be until sometime after the sound has finished playing.

Multiple calls to [`stop()`](AudioScheduledSourceNode/stop.html "stop()") are allowed. The most recent call replaces the previous one, if the `AudioBufferSourceNode` has not already reached the end of the buffer.

  
<img src="AudioBufferSourceNode/webaudioaudiobuffersourcenode.png" alt="The AudioBufferSourceNode takes the content of an AudioBuffer and m" width="365" height="193" />

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>0</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count</td><td>defined by the associated <a href="AudioBuffer.html"><code>AudioBuffer</code></a></td></tr></tbody></table>

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

 [`AudioBufferSourceNode()`](AudioBufferSourceNode/AudioBufferSourceNode.html "AudioBufferSourceNode()")   
Creates and returns a new `AudioBufferSourceNode` object. An [`AudioBufferSourceNode`](AudioBufferSourceNode.html) can be instantiated using the [`AudioContext.createBufferSource()`](BaseAudioContext/createBufferSource.html "AudioContext.createBufferSource()") method.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)*.

 [`AudioBufferSourceNode.buffer`](AudioBufferSourceNode/buffer.html)   
An [`AudioBuffer`](AudioBuffer.html) that defines the audio asset to be played, or when set to the value `null`, defines a single channel of silence (in which every sample is 0.0).

 [`AudioBufferSourceNode.detune`](AudioBufferSourceNode/detune.html)   
Is a [k-rate](AudioParam.html#k-rate) [`AudioParam`](AudioParam.html) representing detuning of playback in <a href="https://en.wikipedia.org/wiki/Cent_(music)" class="external">cents</a>. This value is compounded with `playbackRate` to determine the speed at which the sound is played. Its default value is `0` (meaning no detuning), and its nominal range is -∞ to ∞.

 [`AudioBufferSourceNode.loop`](AudioBufferSourceNode/loop.html)   
A Boolean attribute indicating if the audio asset must be replayed when the end of the [`AudioBuffer`](AudioBuffer.html) is reached. Its default value is `false`.

 [`AudioBufferSourceNode.loopStart`](AudioBufferSourceNode/loopStart.html) <span class="badge inline optional">Optional</span>   
A floating-point value indicating the time, in seconds, at which playback of the [`AudioBuffer`](AudioBuffer.html) must begin when `loop` is `true`. Its default value is `0` (meaning that at the beginning of each loop, playback begins at the start of the audio buffer).

 [`AudioBufferSourceNode.loopEnd`](AudioBufferSourceNode/loopEnd.html) <span class="badge inline optional">Optional</span>   
A floating-point number indicating the time, in seconds, at which playback of the [`AudioBuffer`](AudioBuffer.html) stops and loops back to the time indicated by `loopStart`, if `loop` is `true`. The default value is `0`.

 [`AudioBufferSourceNode.playbackRate`](AudioBufferSourceNode/playbackRate.html)   
An [a-rate](AudioParam.html#a-rate) [`AudioParam`](AudioParam.html) that defines the speed factor at which the audio asset will be played, where a value of 1.0 is the sound's natural sampling rate. Since no pitch correction is applied on the output, this can be used to change the pitch of the sample. This value is compounded with `detune` to determine the final playback rate.

### [Event handlers](#event_handlers "Permalink to Event handlers")

*Inherits event handlers from its parent, [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)*.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent, [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)*.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In this example, we create a two-second buffer, fill it with white noise, and then play it using an `AudioBufferSourceNode`. The comments should clearly explain what is going on.

You can also <a href="https://mdn.github.io/webaudio-examples/audio-buffer/" class="external external-icon">run the code live</a>, or <a href="https://github.com/mdn/webaudio-examples/blob/master/audio-buffer/index.html" class="external external-icon">view the source</a>.

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // Create an empty three-second stereo buffer at the sample rate of the AudioContext
    var myArrayBuffer = audioCtx.createBuffer(2, audioCtx.sampleRate * 3, audioCtx.sampleRate);

    // Fill the buffer with white noise;
    //just random values between -1.0 and 1.0
    for (var channel = 0; channel < myArrayBuffer.numberOfChannels; channel++) {
      // This gives us the actual ArrayBuffer that contains the data
      var nowBuffering = myArrayBuffer.getChannelData(channel);
      for (var i = 0; i < myArrayBuffer.length; i++) {
        // Math.random() is in [0; 1.0]
        // audio needs to be in [-1.0; 1.0]
        nowBuffering[i] = Math.random() * 2 - 1;
      }
    }

    // Get an AudioBufferSourceNode.
    // This is the AudioNode to use when we want to play an AudioBuffer
    var source = audioCtx.createBufferSource();
    // set the buffer in the AudioBufferSourceNode
    source.buffer = myArrayBuffer;
    // connect the AudioBufferSourceNode to the
    // destination so we can hear the sound
    source.connect(audioCtx.destination);
    // start the source playing
    source.start();

For a `decodeAudioData()` example, see the [`AudioContext.decodeAudioData()`](BaseAudioContext/decodeAudioData.html "AudioContext.decodeAudioData()") page.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioBufferSourceNode" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioBufferSourceNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)
-   [Web Audio API](Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audiobuffersourcenode/index.html "Folder: en-us/web/api/audiobuffersourcenode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioBufferSourceNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudiobuffersourcenode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioBufferSourceNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudiobuffersourcenode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioBufferSourceNode%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](AudioBufferSourceNode/contributors.txt)

Change your language Select your preferred language English (US) Français 日本語 한국어 中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioBufferSourceNode`](AudioBufferSourceNode.html)**
3.  Constructor
    1.  [`AudioBufferSourceNode()`](AudioBufferSourceNode/AudioBufferSourceNode.html)
4.  Properties
    1.  [`buffer`](AudioBufferSourceNode/buffer.html)
    2.  [`detune`](AudioBufferSourceNode/detune.html)
    3.  [`loop`](AudioBufferSourceNode/loop.html)
    4.  [`loopEnd`](AudioBufferSourceNode/loopEnd.html)
    5.  [`loopStart`](AudioBufferSourceNode/loopStart.html)
    6.  [`playbackRate`](AudioBufferSourceNode/playbackRate.html)
5.  Methods
    1.  [`start()`](AudioBufferSourceNode/start.html)
6.  Inheritance:
    1.  [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)
    2.  [`AudioNode`](AudioNode.html)
    3.  [`EventTarget`](EventTarget.html)
7.  Related pages for Web Audio API
    1.  [`AnalyserNode`](AnalyserNode.html)
    2.  [`AudioBuffer`](AudioBuffer.html)
    3.  [`AudioContext`](AudioContext.html)
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
