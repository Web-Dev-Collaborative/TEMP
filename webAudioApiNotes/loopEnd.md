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
3.  <a href="../AudioBufferSourceNode.html" class="breadcrumb-penultimate"><span data-property="name">AudioBufferSourceNode</span></a>
4.  <a href="loopEnd.html" class="breadcrumb-current-page"><span data-property="name">AudioBufferSourceNode.loopEnd</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioBufferSourceNode.loopEnd
=============================

The `loopEnd` property of the [`AudioBufferSourceNode`](../AudioBufferSourceNode.html) interface specifies is a floating point number specifying, in seconds, at what offset into playing the [`AudioBuffer`](../AudioBuffer.html) playback should loop back to the time indicated by the [`loopStart`](loopStart.html "loopStart") property. This is only used if the [`loop`](loop.html "loop") property is `true`.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    AudioBufferSourceNode.loopEnd = endOffsetInSeconds;

    var endOffsetInSeconds = AudioBufferSourceNode.loopEnd;

### [Value](#value "Permalink to Value")

A floating-point number indicating the offset, in seconds, into the audio buffer at which each loop will loop return to the beginning of the loop (that is, the current play time gets reset to [`AudioBufferSourceNode.loopStart`](loopStart.html)). This property is only used if the [`loop`](loop.html "loop") property is `true`.

The default value is 0.

[Example](#example "Permalink to Example")
------------------------------------------

In this example, the [`AudioContext.decodeAudioData()`](../BaseAudioContext/decodeAudioData.html "AudioContext.decodeAudioData()") function is used to decode an audio track and put it into an [`AudioBufferSourceNode`](../AudioBufferSourceNode.html). Buttons are provided to play and stop the audio playback, and slider controls are used to change the `playbackRate`, `loopStart` and `loopEnd` properties on the fly.

When the audio is played to the end, it loops, but you can control how long the loops last by altering `loopStart` and `loopEnd`. For example, if you set their values to 20 and 25, respectively, then begin playback, the sound will play normally until it reaches the 25 second mark. Then the current play position will loop back to the 20 second mark and continue playing until the 25 second mark, ad infinitum (or at least until [`stop()`](../AudioScheduledSourceNode/stop.html "stop()") is called).

For a full working example, see <a href="https://mdn.github.io/webaudio-examples/decode-audio-data/" class="external external-icon">this code running live</a>, or <a href="https://github.com/mdn/webaudio-examples/tree/master/decode-audio-data" class="external external-icon">view the source</a>.

    function getData() {
      source = audioCtx.createBufferSource();
      request = new XMLHttpRequest();

      request.open('GET', 'viper.ogg', true);

      request.responseType = 'arraybuffer';

      request.onload = function() {
        var audioData = request.response;

        audioCtx.decodeAudioData(audioData, function(buffer) {
            myBuffer = buffer;
            songLength = buffer.duration;
            source.buffer = myBuffer;
            source.playbackRate.value = playbackControl.value;
            source.connect(audioCtx.destination);
            source.loop = true;

            loopstartControl.setAttribute('max', Math.floor(songLength));
            loopendControl.setAttribute('max', Math.floor(songLength));
          },

          function(e){"Error with decoding audio data" + e.err});

      }

      request.send();
    }

      ...

    loopstartControl.oninput = function() {
      source.loopStart = loopstartControl.value;
      loopstartValue.innerHTML = loopstartControl.value;
    }

    loopendControl.oninput = function() {
      source.loopEnd = loopendControl.value;
      loopendValue.innerHTML = loopendControl.value;
    }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffersourcenode-loopend" class="external">Web Audio API<br />
<span class="small">The definition of 'loopEnd' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](../Web_Audio_API/Using_Web_Audio_API.html)
-   [Web Audio API](../Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audiobuffersourcenode/loopend/index.html "Folder: en-us/web/api/audiobuffersourcenode/loopend (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioBufferSourceNode%2FloopEnd%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudiobuffersourcenode%2Floopend%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioBufferSourceNode%2FloopEnd%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudiobuffersourcenode%2Floopend%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioBufferSourceNode.loopEnd%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](loopEnd/contributors.txt)

Change your language Select your preferred language English (US) Français

Change language

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  **[`AudioBufferSourceNode`](../AudioBufferSourceNode.html)**
3.  Constructor
    1.  [`AudioBufferSourceNode()`](AudioBufferSourceNode.html)
4.  Properties
    1.  [`buffer`](buffer.html)
    2.  [`detune`](detune.html)
    3.  [`loop`](loop.html)
    4.  *`loopEnd`*
    5.  [`loopStart`](loopStart.html)
    6.  [`playbackRate`](playbackRate.html)
5.  Methods
    1.  [`start()`](start.html)
6.  Inheritance:
    1.  [`AudioScheduledSourceNode`](../AudioScheduledSourceNode.html)
    2.  [`AudioNode`](../AudioNode.html)
    3.  [`EventTarget`](../EventTarget.html)
7.  Related pages for Web Audio API
    1.  [`AnalyserNode`](../AnalyserNode.html)
    2.  [`AudioBuffer`](../AudioBuffer.html)
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
