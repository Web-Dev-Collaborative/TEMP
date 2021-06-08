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
3.  <a href="../AudioParam.html" class="breadcrumb-penultimate"><span data-property="name">AudioParam</span></a>
4.  <a href="setTargetAtTime.html" class="breadcrumb-current-page"><span data-property="name">AudioParam.setTargetAtTime()</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Description](#description)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioParam.setTargetAtTime()
============================

The `setTargetAtTime()` method of the [`AudioParam`](../AudioParam.html) interface schedules the start of a gradual change to the `AudioParam` value. This is useful for decay or release portions of ADSR envelopes.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var paramRef = param.setTargetAtTime(target, startTime, timeConstant);

### [Parameters](#parameters "Permalink to Parameters")

target  
The value the parameter will start to transition towards at the given start time.

startTime  
The time that the exponential transition will begin, in the same time coordinate system as [`AudioContext.currentTime`](../BaseAudioContext/currentTime.html "AudioContext.currentTime"). If it is less than or equal to `AudioContext.currentTime`, the parameter will start changing immediately.

timeConstant  
The time-constant value, given in seconds, of an exponential approach to the target value. The larger this value is, the slower the transition will be.

### [Returns](#returns "Permalink to Returns")

A reference to this `AudioParam` object. Some older browser implementations of this interface return void.

[Description](#description "Permalink to Description")
------------------------------------------------------

The change starts at the time specified in `startTime` and exponentially moves towards the value given by the `target` parameter. The decay rate as defined by the `timeConstant` parameter is exponential; therefore the value will never reach `target` completely, but after each timestep of length `timeConstant`, the value will have approached `target` by another 1 − *e*<sup> − 1</sup> ≈ 63.2%. For the complete formula (which uses a first-order linear continuous time-invariant system), check the <a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-settargetattime" class="external">Web Audio specification</a>.

If you absolutely need to reach the target value by a specific time, you can use [`AudioParam.exponentialRampToValueAtTime()`](exponentialRampToValueAtTime.html). However, for mathematical reasons, that method does not work if the current value or the target value is `0`.

### [Choosing a good `timeConstant`](#choosing_a_good_timeconstant "Permalink to Choosing a good timeConstant")

As mentioned above, the value changes exponentially, with each `timeConstant` bringing you another 63.2% toward the target value. You don't have to worry about reaching the target value; once you are close enough, any further changes will be imperceptible to a human listener.

Depending on your use case, getting 95% toward the target value may already be enough; in that case, you could set `timeConstant` to one third of the desired duration.

For more details, check the following table on how the value changes from 0% to 100% as the time progresses.

<table><thead><tr class="header"><th>Time since <code>startTime</code></th><th style="text-align: right;">Value</th></tr></thead><tbody><tr class="odd"><td><code>0 * timeConstant</code></td><td style="text-align: right;">0%</td></tr><tr class="even"><td><code>0.5 * timeConstant</code></td><td style="text-align: right;">39.3%</td></tr><tr class="odd"><td><code>1 * timeConstant</code></td><td style="text-align: right;">63.2%</td></tr><tr class="even"><td><code>2 * timeConstant</code></td><td style="text-align: right;">86.5%</td></tr><tr class="odd"><td><code>3 * timeConstant</code></td><td style="text-align: right;">95.0%</td></tr><tr class="even"><td><code>4 * timeConstant</code></td><td style="text-align: right;">98.2%</td></tr><tr class="odd"><td><code>5 * timeConstant</code></td><td style="text-align: right;">99.3%</td></tr><tr class="even"><td><code>n * timeConstant</code></td><td style="text-align: right;"><span class="math inline">1 − <em>e</em><sup> − <em>n</em></sup></span></td></tr></tbody></table>

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In this example, we have a media source with two control buttons (see the <a href="https://github.com/mdn/webaudio-examples/blob/master/audio-param/index.html" class="external external-icon">webaudio-examples repo</a> for the source code, or <a href="https://mdn.github.io/webaudio-examples/audio-param/" class="external external-icon">view the example live</a>.) When these buttons are pressed, `setTargetAtTime()` is used to fade the gain value up to 1.0, and down to 0, respectively, with the effect starting after 1 second, and the length of time the effect lasts being controlled by the timeConstant.

    // create audio context
    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    // set basic variables for example
    var myAudio = document.querySelector('audio');
    var pre = document.querySelector('pre');
    var myScript = document.querySelector('script');

    pre.innerHTML = myScript.innerHTML;

    var atTimePlus = document.querySelector('.at-time-plus');
    var atTimeMinus = document.querySelector('.at-time-minus');

    // Create a MediaElementAudioSourceNode
    // Feed the HTMLMediaElement into it
    var source = audioCtx.createMediaElementSource(myAudio);

    // Create a gain node and set it's gain value to 0.5
    var gainNode = audioCtx.createGain();
    gainNode.gain.value = 0.5;
    var currGain = gainNode.gain.value;

    // connect the AudioBufferSourceNode to the gainNode
    // and the gainNode to the destination
    source.connect(gainNode);
    gainNode.connect(audioCtx.destination);

    // set buttons to do something onclick
    atTimePlus.onclick = function() {
      currGain = 1.0;
      gainNode.gain.setTargetAtTime(1.0, audioCtx.currentTime + 1, 0.5);
    }

    atTimeMinus.onclick = function() {
      currGain = 0;
      gainNode.gain.setTargetAtTime(0, audioCtx.currentTime + 1, 0.5);
    }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-settargetattime" class="external">Web Audio API<br />
<span class="small">The definition of 'setTargetAtTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](../Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audioparam/settargetattime/index.html "Folder: en-us/web/api/audioparam/settargetattime (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioParam%2FsetTargetAtTime%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudioparam%2Fsettargetattime%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioParam%2FsetTargetAtTime%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudioparam%2Fsettargetattime%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioParam.setTargetAtTime%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](setTargetAtTime/contributors.txt)

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  **[`AudioParam`](../AudioParam.html)**
3.  Properties
    1.  [`defaultValue`](defaultValue.html)
    2.  [`maxValue`](maxValue.html)
    3.  [`minValue`](minValue.html)
    4.  [`value`](value.html)
4.  Methods
    1.  [`cancelAndHoldAtTime()`](cancelAndHoldAtTime.html)
    2.  [`cancelScheduledValues()`](cancelScheduledValues.html)
    3.  [`exponentialRampToValueAtTime()`](exponentialRampToValueAtTime.html)
    4.  [`linearRampToValueAtTime()`](linearRampToValueAtTime.html)
    5.  *`setTargetAtTime()`*
    6.  [`setValueAtTime()`](setValueAtTime.html)
    7.  [`setValueCurveAtTime()`](setValueCurveAtTime.html)
5.  Related pages for Web Audio API
    1.  [`AnalyserNode`](../AnalyserNode.html)
    2.  [`AudioBuffer`](../AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](../AudioBufferSourceNode.html)
    4.  [`AudioContext`](../AudioContext.html)
    5.  [`AudioContextOptions`](../AudioContextOptions.html)
    6.  [`AudioDestinationNode`](../AudioDestinationNode.html)
    7.  [`AudioListener`](../AudioListener.html)
    8.  [`AudioNode`](../AudioNode.html)
    9.  [`AudioNodeOptions`](../AudioNodeOptions.html)
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
