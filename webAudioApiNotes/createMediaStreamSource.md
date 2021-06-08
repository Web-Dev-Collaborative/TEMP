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
4.  <a href="createMediaStreamSource.html" class="breadcrumb-current-page"><span data-property="name">AudioContext.createMediaStreamSource()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioContext.createMediaStreamSource()
======================================

The `createMediaStreamSource()` method of the [`AudioContext`](../AudioContext.html) Interface is used to create a new [`MediaStreamAudioSourceNode`](../MediaStreamAudioSourceNode.html) object, given a media stream (say, from a [`MediaDevices.getUserMedia`](../MediaDevices/getUserMedia.html) instance), the audio from which can then be played and manipulated.

For more details about media stream audio source nodes, check out the [`MediaStreamAudioSourceNode`](../MediaStreamAudioSourceNode.html) reference page.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    audioSourceNode = audioContext.createMediaStreamSource(stream);

### [Parameters](#parameters "Permalink to Parameters")

`stream`  
A [`MediaStream`](../MediaStream.html) to serve as an audio source to be fed into an audio processing graph for use and manipulation.

### [Return value](#return_value "Permalink to Return value")

A new [`MediaStreamAudioSourceNode`](../MediaStreamAudioSourceNode.html) object representing the audio node whose media is obtained from the specified source stream.

[Example](#example "Permalink to Example")
------------------------------------------

In this example, we grab a media (audio + video) stream from [`navigator.getUserMedia`](../Navigator/getUserMedia.html), feed the media into a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element to play then mute the audio, but then also feed the audio into a [`MediaStreamAudioSourceNode`](../MediaStreamAudioSourceNode.html). Next, we feed this source audio into a low pass [`BiquadFilterNode`](../BiquadFilterNode.html) (which effectively serves as a bass booster), then a [`AudioDestinationNode`](../AudioDestinationNode.html).

The range slider below the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element controls the amount of gain given to the lowpass filter — increase the value of the slider to make the audio sound more bass heavy!

**Note**: You can see this <a href="https://mdn.github.io/webaudio-examples/stream-source-buffer/" class="external">example running live</a>, or <a href="https://github.com/mdn/webaudio-examples/tree/master/stream-source-buffer" class="external">view the source</a>.

    var pre = document.querySelector('pre');
    var video = document.querySelector('video');
    var myScript = document.querySelector('script');
    var range = document.querySelector('input');

    // getUserMedia block - grab stream
    // put it into a MediaStreamAudioSourceNode
    // also output the visuals into a video element

    if (navigator.mediaDevices) {
        console.log('getUserMedia supported.');
        navigator.mediaDevices.getUserMedia ({audio: true, video: true})
        .then(function(stream) {
            video.srcObject = stream;
            video.onloadedmetadata = function(e) {
                video.play();
                video.muted = true;
            };

            // Create a MediaStreamAudioSourceNode
            // Feed the HTMLMediaElement into it
            var audioCtx = new AudioContext();
            var source = audioCtx.createMediaStreamSource(stream);

            // Create a biquadfilter
            var biquadFilter = audioCtx.createBiquadFilter();
            biquadFilter.type = "lowshelf";
            biquadFilter.frequency.value = 1000;
            biquadFilter.gain.value = range.value;

            // connect the AudioBufferSourceNode to the gainNode
            // and the gainNode to the destination, so we can play the
            // music and adjust the volume using the mouse cursor
            source.connect(biquadFilter);
            biquadFilter.connect(audioCtx.destination);

            // Get new mouse pointer coordinates when mouse is moved
            // then set new gain value

            range.oninput = function() {
                biquadFilter.gain.value = range.value;
            }
        })
        .catch(function(err) {
            console.log('The following gUM error occurred: ' + err);
        });
    } else {
       console.log('getUserMedia not supported on your browser!');
    }

    // dump script to pre element

    pre.innerHTML = myScript.innerHTML;

**Note**: As a consequence of calling `createMediaStreamSource()`, audio playback from the media stream will be re-routed into the processing graph of the [`AudioContext`](../AudioContext.html). So playing/pausing the stream can still be done through the media element API and the player controls.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-createmediastreamsource" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioContext.createMediaStreamSource()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](../Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audiocontext/createmediastreamsource/index.html "Folder: en-us/web/api/audiocontext/createmediastreamsource (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioContext%2FcreateMediaStreamSource%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudiocontext%2Fcreatemediastreamsource%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioContext%2FcreateMediaStreamSource%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudiocontext%2Fcreatemediastreamsource%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioContext.createMediaStreamSource%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](createMediaStreamSource/contributors.txt)

Change your languageSelect your preferred language English (US)日本語中文 (简体)

Change language

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
    5.  *`createMediaStreamSource()`*
    6.  [`createMediaStreamTrackSource()`](createMediaStreamTrackSource.html)
    7.  [`getOutputTimestamp()`](getOutputTimestamp.html)
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
