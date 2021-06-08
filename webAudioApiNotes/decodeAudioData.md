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
3.  <a href="../BaseAudioContext.html" class="breadcrumb-penultimate"><span data-property="name">BaseAudioContext</span></a>
4.  <a href="decodeAudioData.html" class="breadcrumb-current-page"><span data-property="name">BaseAudioContext.decodeAudioData()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

BaseAudioContext.decodeAudioData()
==================================

The `decodeAudioData()` method of the [`BaseAudioContext`](../BaseAudioContext.html) Interface is used to asynchronously decode audio file data contained in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer). In this case the `ArrayBuffer` is loaded from [`XMLHttpRequest`](../XMLHttpRequest.html) and [`FileReader`](../FileReader.html). The decoded [`AudioBuffer`](../AudioBuffer.html) is resampled to the [`AudioContext`](../AudioContext.html)'s sampling rate, then passed to a callback or promise.

This is the preferred method of creating an audio source for Web Audio API from an audio track. This method only works on complete file data, not fragments of audio file data.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

Older callback syntax:

    baseAudioContext.decodeAudioData(ArrayBuffer, successCallback, errorCallback);

Newer promise-based syntax:

    Promise<decodedData> baseAudioContext.decodeAudioData(ArrayBuffer);

### [Parameters](#parameters "Permalink to Parameters")

ArrayBuffer  
An ArrayBuffer containing the audio data to be decoded, usually grabbed from [`XMLHttpRequest`](../XMLHttpRequest.html), [`WindowOrWorkerGlobalScope.fetch()`](../WindowOrWorkerGlobalScope/fetch.html) or [`FileReader`](../FileReader.html).

successCallback  
A callback function to be invoked when the decoding successfully finishes. The single argument to this callback is an [`AudioBuffer`](../AudioBuffer.html) representing the decodedData (the decoded PCM audio data). Usually you'll want to put the decoded data into an [`AudioBufferSourceNode`](../AudioBufferSourceNode.html), from which it can be played and manipulated how you want.

errorCallback  
An optional error callback, to be invoked if an error occurs when the audio data is being decoded.

### [Return value](#return_value "Permalink to Return value")

Void, or a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) object that fulfills with the decodedData.

[Example](#example "Permalink to Example")
------------------------------------------

In this section we will first cover the older callback-based system and then the newer promise-based syntax.

### [Older callback syntax](#older_callback_syntax "Permalink to Older callback syntax")

In this example, the `getData()` function uses XHR to load an audio track, setting the `responseType` of the request to `arraybuffer` so that it returns an array buffer as its `response` that we then store in the `audioData` variable . We then pass this buffer into a `decodeAudioData()` function; the success callback takes the successfully decoded PCM data, puts it into an [`AudioBufferSourceNode`](../AudioBufferSourceNode.html) created using [`AudioContext.createBufferSource()`](createBufferSource.html "AudioContext.createBufferSource()"), connects the source to the [`AudioContext.destination`](destination.html "AudioContext.destination") and sets it to loop.

The buttons in the example run `getData()` to load the track and start it playing, and stop it playing, respectively. When the `stop()` method is called on the source, the source is cleared out.

**Note**: You can <a href="https://mdn.github.io/webaudio-examples/decode-audio-data/" class="external">run the example live</a> (or <a href="https://github.com/mdn/webaudio-examples/tree/master/decode-audio-data" class="external">view the source</a>.)

    // define variables

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var source;

    var pre = document.querySelector('pre');
    var myScript = document.querySelector('script');
    var play = document.querySelector('.play');
    var stop = document.querySelector('.stop');

    // use XHR to load an audio track, and
    // decodeAudioData to decode it and stick it in a buffer.
    // Then we put the buffer into the source

    function getData() {
      source = audioCtx.createBufferSource();
      var request = new XMLHttpRequest();

      request.open('GET', 'viper.ogg', true);

      request.responseType = 'arraybuffer';

      request.onload = function() {
        var audioData = request.response;

        audioCtx.decodeAudioData(audioData, function(buffer) {
            source.buffer = buffer;

            source.connect(audioCtx.destination);
            source.loop = true;
          },

          function(e){ console.log("Error with decoding audio data" + e.err); });

      }

      request.send();
    }

    // wire up buttons to stop and play audio

    play.onclick = function() {
      getData();
      source.start(0);
      play.setAttribute('disabled', 'disabled');
    }

    stop.onclick = function() {
      source.stop(0);
      play.removeAttribute('disabled');
    }

    // dump script to pre element

    pre.innerHTML = myScript.innerHTML;

### [New promise-based syntax](#new_promise-based_syntax "Permalink to New promise-based syntax")

    ctx.decodeAudioData(audioData).then(function(decodedData) {
     // use the decoded data here
    });

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-decodeaudiodata" class="external">Web Audio API<br />
<span class="small">The definition of 'decodeAudioData()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](../Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/baseaudiocontext/decodeaudiodata/index.html "Folder: en-us/web/api/baseaudiocontext/decodeaudiodata (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBaseAudioContext%2FdecodeAudioData%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fbaseaudiocontext%2Fdecodeaudiodata%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBaseAudioContext%2FdecodeAudioData%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fbaseaudiocontext%2Fdecodeaudiodata%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F591362776c1ef3ad42942777979939e511dd811f%0A*+Document+last+modified%3A+2021-05-29T03%3A45%3A05.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22BaseAudioContext.decodeAudioData%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](decodeAudioData/contributors.txt)

Change your languageSelect your preferred language English (US)Deutsch日本語Русский中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  **[`BaseAudioContext`](../BaseAudioContext.html)**
3.  Properties
    1.  [`audioWorklet`](audioWorklet.html)
    2.  [`currentTime`](currentTime.html)
    3.  [`destination`](destination.html)
    4.  [`listener`](listener.html)
    5.  [`sampleRate`](sampleRate.html)
    6.  [`state`](state.html)
4.  Methods
    1.  [`createAnalyser()`](createAnalyser.html)
    2.  [`createBiquadFilter()`](createBiquadFilter.html)
    3.  [`createBuffer()`](createBuffer.html)
    4.  [`createBufferSource()`](createBufferSource.html)
    5.  [`createChannelMerger()`](createChannelMerger.html)
    6.  [`createChannelSplitter()`](createChannelSplitter.html)
    7.  [`createConstantSource()`](createConstantSource.html)
    8.  [`createConvolver()`](createConvolver.html)
    9.  [`createDelay()`](createDelay.html)
    10. [`createDynamicsCompressor()`](createDynamicsCompressor.html)
    11. [`createGain()`](createGain.html)
    12. [`createIIRFilter()`](createIIRFilter.html)
    13. [`createOscillator()`](createOscillator.html)
    14. [`createPanner()`](createPanner.html)
    15. [`createPeriodicWave()`](createPeriodicWave.html)
    16. [`createScriptProcessor()`](createScriptProcessor.html)
    17. [`createStereoPanner()`](createStereoPanner.html)
    18. [`createWaveShaper()`](createWaveShaper.html)
    19. *`decodeAudioData()`*
5.  Inheritance:
    1.  [`EventTarget`](../EventTarget.html)
6.  Related pages for Web Audio API
    1.  [`AnalyserNode`](../AnalyserNode.html)
    2.  [`AudioBuffer`](../AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](../AudioBufferSourceNode.html)
    4.  [`AudioContext`](../AudioContext.html)
    5.  [`AudioContextOptions`](../AudioContextOptions.html)
    6.  [`AudioDestinationNode`](../AudioDestinationNode.html)
    7.  [`AudioListener`](../AudioListener.html)
    8.  [`AudioNode`](../AudioNode.html)
    9.  [`AudioNodeOptions`](../AudioNodeOptions.html)
    10. [`AudioParam`](../AudioParam.html)
    11. [`AudioProcessingEvent`](../AudioProcessingEvent.html)
    12. [`AudioScheduledSourceNode`](../AudioScheduledSourceNode.html)
    13. [`AudioWorklet`](../AudioWorklet.html)
    14. [`AudioWorkletGlobalScope`](../AudioWorkletGlobalScope.html)
    15. [`AudioWorkletNode`](../AudioWorkletNode.html)
    16. [`AudioWorkletProcessor`](../AudioWorkletProcessor.html)
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
