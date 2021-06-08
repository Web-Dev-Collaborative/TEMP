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
4.  <a href="minValue.html" class="breadcrumb-current-page"><span data-property="name">AudioParam.minValue</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioParam.minValue
===================

<span class="seoSummary">The **`minValue`** read-only property of the [`AudioParam`](../AudioParam.html) interface represents the minimum possible value for the parameter's nominal (effective) range.</span>

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var minVal = audioParam.minValue;

### [Value](#value "Permalink to Value")

A floating-point [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) indicating the minimum value permitted for the parameter's nominal range.

The default value of `minValue` is the minimum negative single-precision floating-point value (-340,282,346,638,528,859,811,704,183,484,516,925,440).

[Example](#example "Permalink to Example")
------------------------------------------

    const audioCtx = new AudioContext();
    const gainNode = audioCtx.createGain();
    console.log(gainNode.gain.minValue); // -3.4028234663852886e38

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-minvalue" class="external">Web Audio API<br />
<span class="small">The definition of 'minValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`AudioParam.maxValue`](maxValue.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audioparam/minvalue/index.html "Folder: en-us/web/api/audioparam/minvalue (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioParam%2FminValue%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudioparam%2Fminvalue%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioParam%2FminValue%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudioparam%2Fminvalue%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioParam.minValue%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](minValue/contributors.txt)

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  **[`AudioParam`](../AudioParam.html)**
3.  Properties
    1.  [`defaultValue`](defaultValue.html)
    2.  [`maxValue`](maxValue.html)
    3.  *`minValue`*
    4.  [`value`](value.html)
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
