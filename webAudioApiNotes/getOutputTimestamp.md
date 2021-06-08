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
3.  <a href="../AudioContext.html" class="breadcrumb-penultimate"><span data-property="name">AudioContext</span></a>
4.  <a href="getOutputTimestamp.html" class="breadcrumb-current-page"><span data-property="name">AudioContext.getOutputTimestamp()</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

AudioContext.getOutputTimestamp()
=================================

<span class="seoSummary">The **`getOutputTimestamp()`** property of the [`AudioContext`](../AudioContext.html) interface returns a new `AudioTimestamp` object containing two audio timestamp values relating to the current audio context.</span>

The two values are as follows:

-   `AudioTimestamp.contextTime`: The time of the sample frame currently being rendered by the audio output device (i.e., output audio stream position), in the same units and origin as the context's [`AudioContext.currentTime`](../BaseAudioContext/currentTime.html "AudioContext.currentTime"). Basically, this is the time after the audio context was first created.
-   `AudioTimestamp.performanceTime`: An estimation of the moment when the sample frame corresponding to the stored `contextTime` value was rendered by the audio output device, in the same units and origin as [`performance.now()`](../Performance/now.html). This is the time after the document containing the audio context was first rendered.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var timestamp = context.getOutputTimestamp()

### [Parameters](#parameters "Permalink to Parameters")

None.

### [Returns](#returns "Permalink to Returns")

An `AudioTimestamp` object, which has the following properties.

-   `contextTime`: A point in the time coordinate system of the [`currentTime`](../BaseAudioContext/currentTime.html "currentTime") for the `BaseAudioContext`; the time after the audio context was first created.
-   `performanceTime`: A point in the time coordinate system of a `Performance` interface; the time after the document containing the audio context was first rendered

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In the following code we start to play an audio file after a play button is clicked, and start off a `requestAnimationFrame` loop running, which constantly outputs the `contextTime` and `performanceTime`.

You can see full code of this <a href="https://github.com/mdn/webaudio-examples/blob/master/output-timestamp/index.html" class="external">example at output-timestamp</a> (<a href="https://mdn.github.io/webaudio-examples/output-timestamp/" class="external">see it live also</a>).

    play.addEventListener('click', () => {
      if(!audioCtx) {
        audioCtx = new window.AudioContext();
      }

      getData();
      source.start(0);
      play.setAttribute('disabled', 'disabled');

      rAF = requestAnimationFrame(outputTimestamps);
    });

    stop.addEventListener('click', () => {
      source.stop(0);
      play.removeAttribute('disabled');
      cancelAnimationFrame(rAF);
    });

    // function to output timestamps

    function outputTimestamps() {
      let ts = audioCtx.getOutputTimestamp()
      console.log('Context time: ' + ts.contextTime + ' | Performance time: ' + ts.performanceTime);
      rAF = requestAnimationFrame(outputTimestamps);
    }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-getoutputtimestamp" class="external">Web Audio API<br />
<span class="small">The definition of 'getOutputTimestamp()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audiocontext/getoutputtimestamp/index.html "Folder: en-us/web/api/audiocontext/getoutputtimestamp (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioContext%2FgetOutputTimestamp%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudiocontext%2Fgetoutputtimestamp%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioContext%2FgetOutputTimestamp%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudiocontext%2Fgetoutputtimestamp%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioContext.getOutputTimestamp%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](getOutputTimestamp/contributors.txt)

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  **[`AudioContext`](../AudioContext.html)**
3.  Constructor
    1.  [`AudioContext()`](AudioContext.html)
4.  Properties
    1.  [`baseLatency`](baseLatency.html)
    2.  [`outputLatency`](outputLatency.html)
5.  Methods
    1.  [`close()`](close.html)
    2.  [`createJavaScriptNode()`](createJavaScriptNode.html)
    3.  [`createMediaElementSource()`](createMediaElementSource.html)
    4.  [`createMediaStreamDestination()`](createMediaStreamDestination.html)
    5.  [`createMediaStreamSource()`](createMediaStreamSource.html)
    6.  [`createMediaStreamTrackSource()`](createMediaStreamTrackSource.html)
    7.  *`getOutputTimestamp()`*
    8.  [`resume()`](resume.html)
    9.  [`suspend()`](suspend.html)
6.  Inheritance:
    1.  [`BaseAudioContext`](../BaseAudioContext.html)
    2.  [`EventTarget`](../EventTarget.html)
7.  Related pages for Web Audio API
    1.  [`AnalyserNode`](../AnalyserNode.html)
    2.  [`AudioBuffer`](../AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](../AudioBufferSourceNode.html)
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
