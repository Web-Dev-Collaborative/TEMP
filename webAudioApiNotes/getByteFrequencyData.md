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
2.  <a href="https://developer.mozilla.org/en-US/docs/Web/API" class="breadcrumb"><span data-property="name">Web APIs</span></a>
3.  <a href="../AnalyserNode.html" class="breadcrumb-penultimate"><span data-property="name">AnalyserNode</span></a>
4.  <a href="getByteFrequencyData.html" class="breadcrumb-current-page"><span data-property="name">AnalyserNode.getByteFrequencyData()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Parameters](#parameters_2)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AnalyserNode.getByteFrequencyData()
===================================

The **`getByteFrequencyData()`** method of the [`AnalyserNode`](../AnalyserNode.html) interface copies the current frequency data into a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) (unsigned byte array) passed into it.

The frequency data is composed of integers on a scale from 0 to 255.

Each item in the array represents the decibel value for a specific frequency. The frequencies are spread linearly from 0 to 1/2 of the sample rate. For example, for `48000` sample rate, the last item of the array will represent the decibel value for `24000` Hz.

If the array has fewer elements than the [`AnalyserNode.frequencyBinCount`](frequencyBinCount.html), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var audioCtx = new AudioContext();
    var analyser = audioCtx.createAnalyser();
    var dataArray = new Uint8Array(analyser.frequencyBinCount); // Uint8Array should be the same length as the frequencyBinCount

    void analyser.getByteFrequencyData(dataArray); // fill the Uint8Array with data returned from getByteFrequencyData()

### [Parameters](#parameters "Permalink to Parameters")

`array`  
The [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) that the frequency domain data will be copied to. For any sample which is silent, the value is `-Infinity`.  
If the array has fewer elements than the [`AnalyserNode.frequencyBinCount`](frequencyBinCount.html), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

### [Return value](#return_value "Permalink to Return value")

None.

[Example](#example "Permalink to Example")
------------------------------------------

The following example shows basic usage of an [`AudioContext`](../AudioContext.html) to create an `AnalyserNode`, then [`requestAnimationFrame`](../window/requestAnimationFrame.html "requestAnimationFrame") and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to collect frequency data repeatedly and draw a "winamp bargraph style" output of the current audio input. For more examples/information, check out our <a href="https://mdn.github.io/voice-change-o-matic/" class="external">Voice-change-O-matic</a> demo (see <a href="../../../../../../github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.html#L128-L205" class="external">app.js lines 128–205</a> for relevant code).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var analyser = audioCtx.createAnalyser();

      ...

    analyser.fftSize = 256;
    var bufferLength = analyser.frequencyBinCount;
    console.log(bufferLength);
    var dataArray = new Uint8Array(bufferLength);

    canvasCtx.clearRect(0, 0, WIDTH, HEIGHT);

    function draw() {
      drawVisual = requestAnimationFrame(draw);

      analyser.getByteFrequencyData(dataArray);

      canvasCtx.fillStyle = 'rgb(0, 0, 0)';
      canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);

      var barWidth = (WIDTH / bufferLength) * 2.5;
      var barHeight;
      var x = 0;

      for(var i = 0; i < bufferLength; i++) {
        barHeight = dataArray[i];

        canvasCtx.fillStyle = 'rgb(' + (barHeight+100) + ',50,50)';
        canvasCtx.fillRect(x,HEIGHT-barHeight/2,barWidth,barHeight/2);

        x += barWidth + 1;
      }
    };

    draw();

[Parameters](#parameters_2 "Permalink to Parameters")
-----------------------------------------------------

array  
The [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) that the frequency domain data will be copied to.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-getbytefrequencydata" class="external">Web Audio API<br />
<span class="small">The definition of 'getByteFrequencyData()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](../Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/analysernode/getbytefrequencydata/index.html "Folder: en-us/web/api/analysernode/getbytefrequencydata (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAnalyserNode%2FgetByteFrequencyData%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fanalysernode%2Fgetbytefrequencydata%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAnalyserNode%2FgetByteFrequencyData%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fanalysernode%2Fgetbytefrequencydata%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AnalyserNode.getByteFrequencyData%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](getByteFrequencyData/contributors.txt)

Change your language Select your preferred language English (US) Français Русский 中文 (简体) 正體中文 (繁體)

Change language

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  **[`AnalyserNode`](../AnalyserNode.html)**
3.  Constructor
    1.  [`AnalyserNode()`](AnalyserNode.html)
4.  Properties
    1.  [`fftSize`](fftSize.html)
    2.  [`frequencyBinCount`](frequencyBinCount.html)
    3.  [`maxDecibels`](maxDecibels.html)
    4.  [`minDecibels`](minDecibels.html)
    5.  [`smoothingTimeConstant`](smoothingTimeConstant.html)
5.  Methods
    1.  *`getByteFrequencyData()`*
    2.  [`getByteTimeDomainData()`](getByteTimeDomainData.html)
    3.  [`getFloatFrequencyData()`](getFloatFrequencyData.html)
    4.  [`getFloatTimeDomainData()`](getFloatTimeDomainData.html)
6.  Inheritance:
    1.  [`AudioNode`](../AudioNode.html)
    2.  [`EventTarget`](../EventTarget.html)
7.  Related pages for Web Audio API
    1.  [`AudioBuffer`](../AudioBuffer.html)
    2.  [`AudioBufferSourceNode`](../AudioBufferSourceNode.html)
    3.  [`AudioContext`](../AudioContext.html)
    4.  [`AudioContextOptions`](../AudioContextOptions.html)
    5.  [`AudioDestinationNode`](../AudioDestinationNode.html)
    6.  [`AudioListener`](../AudioListener.html)
    7.  [`AudioNode`](../AudioNode.html)
    8.  [`AudioNodeOptions`](../AudioNodeOptions.html)
    9.  [`AudioParam`](../AudioParam.html)
    10. [`AudioProcessingEvent`](../AudioProcessingEvent.html)
    11. [`AudioScheduledSourceNode`](../AudioScheduledSourceNode.html)
    12. [`AudioWorklet`](../AudioWorklet.html)
    13. [`AudioWorkletGlobalScope`](../AudioWorkletGlobalScope.html)
    14. [`AudioWorkletNode`](../AudioWorkletNode.html)
    15. [`AudioWorkletProcessor`](../AudioWorkletProcessor.html)
    16. [`BaseAudioContext`](../BaseAudioContext.html)
    17. [`BiquadFilterNode`](../BiquadFilterNode.html)
    18. [`ChannelMergerNode`](../ChannelMergerNode.html)
    19. [`ChannelSplitterNode`](../ChannelSplitterNode.html)
    20. [`ConstantSourceNode`](../ConstantSourceNode.html)
    21. [`ConvolverNode`](../ConvolverNode.html)
    22. [`DelayNode`](../DelayNode.html)
    23. [`DynamicsCompressorNode`](../DynamicsCompressorNode.html)
    24. [`GainNode`](../GainNode.html)
    25. [`IIRFilterNode`](../IIRFilterNode.html)
    26. [`MediaElementAudioSourceNode`](../MediaElementAudioSourceNode.html)
    27. [`MediaStreamAudioDestinationNode`](../MediaStreamAudioDestinationNode.html)
    28. [`MediaStreamAudioSourceNode`](../MediaStreamAudioSourceNode.html)
    29. [`OfflineAudioCompletionEvent`](../OfflineAudioCompletionEvent.html)
    30. [`OfflineAudioContext`](../OfflineAudioContext.html)
    31. [`OscillatorNode`](../OscillatorNode.html)
    32. [`PannerNode`](../PannerNode.html)
    33. [`PeriodicWave`](../PeriodicWave.html)
    34. [`StereoPannerNode`](../StereoPannerNode.html)
    35. [`WaveShaperNode`](../WaveShaperNode.html)

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
