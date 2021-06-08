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
4.  <a href="value.html" class="breadcrumb-current-page"><span data-property="name">AudioParam.value</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Usage notes](#usage_notes)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioParam.value
================

<span class="seoSummary">The [Web Audio API's](../Web_Audio_API.html) [`AudioParam`](../AudioParam.html) interface property `value` gets or sets the value of this [`AudioParam`](../AudioParam.html) at the current time.</span> Initially, the value is set to [`AudioParam.defaultValue`](defaultValue.html).

Setting `value` has the same effect as calling [`AudioParam.setValueAtTime`](setValueAtTime.html) with the time returned by the `AudioContext`'s [`currentTime`](../BaseAudioContext/currentTime.html "currentTime") property..

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var curValue = audioParam.value;
    audioParam.value = newValue;

### [Value](#value "Permalink to Value")

A floating-point [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) indicating the parameter's value as of the current time. This value will be between the values specified by the [`minValue`](minValue.html "minValue") and [`maxValue`](maxValue.html "maxValue") properties.

[Usage notes](#usage_notes "Permalink to Usage notes")
------------------------------------------------------

### [Value precision and variation](#value_precision_and_variation "Permalink to Value precision and variation")

The data type used internally to store `value` is a single-precision (32-bit) floating point number, while JavaScript uses 64-bit double-precision floating point numbers. As a result, the value you read from the `value` property may not always exactly equal what you set it to.

Consider this example:

    const source = new AudioBufferSourceNode(...);
    const rate = 5.3;
    source.playbackRate.value = rate;
    console.log(source.playbackRate.value === rate);

The log output will be `false`, because the playback rate parameter, `rate`, was converted to the 32-bit floating-point number closest to 5.3, which yields 5.300000190734863. One solution is to use the [`Math.fround()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/fround) method, which returns the single-precision value equivalent to the 64-bit JavaScript value specified—when setting `value`, like this:

    const source = new AudioBufferSourceNode(...);
    const rate = Math.fround(5.3);
    source.playbackRate.value = rate;
    console.log(source.playbackRate.value === rate);

In this case, the log output will be `true`.

### [Value of a property which is changing over time](#value_of_a_property_which_is_changing_over_time "Permalink to Value of a property which is
  changing over time")

The `value` of an `AudioParam` can either be fixed or can vary over time. This is reflected by the `value` getter, which returns the value of the parameter as of the audio rendering engine's most recent **render quantum**, or moment at which audio buffers are processed and updated. In addition to processing audio buffers, each render quantum updates the `value` of each `AudioParam` as needed given the current time and any established time-based parameter value changes.

Upon first creating the parameter, its value is set to its default value, given by  [`AudioParam.defaultValue`](defaultValue.html). This is the parameter's value at a time of 0.0 seconds, and will remain the parameter's value until the first render quantum in which the value is altered.

During each render quantum, the browser does the following things related to managing the value of a parameter:

-   If the `value` setter has been used, the parameter's value is changed to the value given.
-   If the current time equals or exceeds the time specified by a previous call to [`setValueAtTime()`](setValueAtTime.html "setValueAtTime()"), the `value` is changed to the value passed into `setValueAtTime()`.
-   If any gradiated or ramped value changing methods have been called and the current time is within the time range over which the graduated change should occur, the value is updated based on the appropriate algorithm. These ramped or gradiated value-changing methods include [`linearRampToValueAtTime()`](linearRampToValueAtTime.html "linearRampToValueAtTime()"), [`setTargetAtTime()`](setTargetAtTime.html "setTargetAtTime()"), and [`setValueCurveAtTime()`](setValueCurveAtTime.html "setValueCurveAtTime()").

Thus, the `value` of a parameter is maintained to accurately reflect the state of the parameter over time.

[Example](#example "Permalink to Example")
------------------------------------------

This example instantly changes the volume of a [`GainNode`](../GainNode.html) to 40%.

    const audioCtx = new AudioContext();
    const gainNode = audioCtx.createGain();
    gainNode.gain.value = 0.4;
    //which is identical to:
    gainNode.gain.setValueAtTime(0.4, audioCtx.currentTime);

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-value" class="external">Web Audio API<br />
<span class="small">The definition of 'value' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

When changing the gain value of a [`GainNode`](../GainNode.html), Google Chrome prior to version 64 (January 2018) would perform a smooth interpolation to prevent dezippering. Starting with version 64, the value is changed instantly to bring it in line with the Web Audio spec. See <a href="https://www.chromestatus.com/feature/5287995770929152" class="external">Chrome Platform Status</a> for details.

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](../Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audioparam/value/index.html "Folder: en-us/web/api/audioparam/value (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioParam%2Fvalue%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudioparam%2Fvalue%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioParam%2Fvalue%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudioparam%2Fvalue%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioParam.value%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](value/contributors.txt)

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  **[`AudioParam`](../AudioParam.html)**
3.  Properties
    1.  [`defaultValue`](defaultValue.html)
    2.  [`maxValue`](maxValue.html)
    3.  [`minValue`](minValue.html)
    4.  *`value`*
4.  Methods
    1.  [`cancelAndHoldAtTime()`](cancelAndHoldAtTime.html)
    2.  [`cancelScheduledValues()`](cancelScheduledValues.html)
    3.  [`exponentialRampToValueAtTime()`](exponentialRampToValueAtTime.html)
    4.  [`linearRampToValueAtTime()`](linearRampToValueAtTime.html)
    5.  [`setTargetAtTime()`](setTargetAtTime.html)
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
