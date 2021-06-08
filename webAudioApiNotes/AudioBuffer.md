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
3.  <a href="AudioBuffer.html" class="breadcrumb-current-page"><span data-property="name">AudioBuffer</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioBuffer
===========

The **`AudioBuffer`** interface represents a short audio asset residing in memory, created from an audio file using the [`AudioContext.decodeAudioData()`](BaseAudioContext/decodeAudioData.html "AudioContext.decodeAudioData()") method, or from raw data using [`AudioContext.createBuffer()`](BaseAudioContext/createBuffer.html "AudioContext.createBuffer()"). Once put into an AudioBuffer, the audio can then be played by being passed into an [`AudioBufferSourceNode`](AudioBufferSourceNode.html).

Objects of these types are designed to hold small audio snippets, typically less than 45 s. For longer sounds, objects implementing the [`MediaElementAudioSourceNode`](MediaElementAudioSourceNode.html) are more suitable. The buffer contains data in the following format: non-interleaved IEEE754 32-bit linear PCM with a nominal range between `-1` and `+1`, that is, a 32-bit floating point buffer, with each sample between -1.0 and 1.0. If the [`AudioBuffer`](AudioBuffer.html) has multiple channels, they are stored in separate buffers.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

 [`AudioBuffer()`](AudioBuffer/AudioBuffer.html "AudioBuffer()")   
Creates and returns a new `AudioBuffer` object instance.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

 [`AudioBuffer.sampleRate`](AudioBuffer/sampleRate.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a float representing the sample rate, in samples per second, of the PCM data stored in the buffer.

 [`AudioBuffer.length`](AudioBuffer/length.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns an integer representing the length, in sample-frames, of the PCM data stored in the buffer.

 [`AudioBuffer.duration`](AudioBuffer/duration.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a double representing the duration, in seconds, of the PCM data stored in the buffer.

 [`AudioBuffer.numberOfChannels`](AudioBuffer/numberOfChannels.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns an integer representing the number of discrete audio channels described by the PCM data stored in the buffer.

[Methods](#methods "Permalink to Methods")
------------------------------------------

 [`AudioBuffer.getChannelData()`](AudioBuffer/getChannelData.html)   
Returns a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing the PCM data associated with the channel, defined by the `channel` parameter (with `0` representing the first channel).

 [`AudioBuffer.copyFromChannel()`](AudioBuffer/copyFromChannel.html)   
Copies the samples from the specified channel of the <span class="idlType">`AudioBuffer`</span> to the `destination` array.

 [`AudioBuffer.copyToChannel()`](AudioBuffer/copyToChannel.html)   
Copies the samples to the specified channel of the <span class="idlType">`AudioBuffer`</span>, from the `source` array.

[Example](#example "Permalink to Example")
------------------------------------------

The following simple example shows how to create an `AudioBuffer` and fill it with random white noise. You can find the full source code at our <a href="https://github.com/mdn/webaudio-examples" class="external">webaudio-examples</a> repository; a <a href="https://mdn.github.io/webaudio-examples/audio-buffer/" class="external">running live</a> version is also available.

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // Create an empty three-second stereo buffer at the sample rate of the AudioContext
    var myArrayBuffer = audioCtx.createBuffer(2, audioCtx.sampleRate * 3, audioCtx.sampleRate);

    // Fill the buffer with white noise;
    // just random values between -1.0 and 1.0
    for (var channel = 0; channel < myArrayBuffer.numberOfChannels; channel++) {
      // This gives us the actual array that contains the data
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

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audiobuffer" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioBuffer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audiobuffer/index.html "Folder: en-us/web/api/audiobuffer (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioBuffer%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudiobuffer%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioBuffer%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudiobuffer%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioBuffer%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](AudioBuffer/contributors.txt)

Change your language Select your preferred language English (US) Español Français 日本語 한국어 Polski Русский 中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioBuffer`](AudioBuffer.html)**
3.  Constructor
    1.  [`AudioBuffer()`](AudioBuffer/AudioBuffer.html)
4.  Properties
    1.  [`duration`](AudioBuffer/duration.html)
    2.  [`length`](AudioBuffer/length.html)
    3.  [`numberOfChannels`](AudioBuffer/numberOfChannels.html)
    4.  [`sampleRate`](AudioBuffer/sampleRate.html)
5.  Methods
    1.  [`copyFromChannel()`](AudioBuffer/copyFromChannel.html)
    2.  [`copyToChannel()`](AudioBuffer/copyToChannel.html)
    3.  [`getChannelData()`](AudioBuffer/getChannelData.html)
6.  Related pages for Web Audio API
    1.  [`AnalyserNode`](AnalyserNode.html)
    2.  [`AudioBufferSourceNode`](AudioBufferSourceNode.html)
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
