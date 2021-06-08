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
3.  <a href="../OscillatorNode.html" class="breadcrumb-penultimate"><span data-property="name">OscillatorNode</span></a>
4.  <a href="setPeriodicWave.html" class="breadcrumb-current-page"><span data-property="name">OscillatorNode.setPeriodicWave()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

OscillatorNode.setPeriodicWave()
================================

The **`setPeriodicWave()`** method of the [`OscillatorNode`](../OscillatorNode.html) interface is used to point to a [`PeriodicWave`](../PeriodicWave.html) defining a periodic waveform that can be used to shape the oscillator's output, when [`type`](type.html "type") is `custom`.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    OscillatorNode.setPeriodicWave(wave);

### [Parameters](#parameters "Permalink to Parameters")

`wave`  
A [`PeriodicWave`](../PeriodicWave.html) object representing the waveform to use as the shape of the oscillator's output.

### [Returns](#returns "Permalink to Returns")

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

[Example](#example "Permalink to Example")
------------------------------------------

The following example illustrates simple usage of `createPeriodicWave()`, recreating a sine wave from a periodic wave.

    var real = new Float32Array(2);
    var imag = new Float32Array(2);
    var ac = new AudioContext();
    var osc = ac.createOscillator();

    real[0] = 0;
    imag[0] = 0;
    real[1] = 1;
    imag[1] = 0;

    var wave = ac.createPeriodicWave(real, imag);

    osc.setPeriodicWave(wave);

    osc.connect(ac.destination);

    osc.start();
    osc.stop(2);

This works because a sound that contains only a fundamental tone is by definition a sine wave.  
  
Here, we create a [`PeriodicWave`](../PeriodicWave.html) with two values. The first value is the DC offset, which is the value at which the oscillator starts. 0 is good here, because we want to start the curve at the middle of the \[-1.0; 1.0\] range.

The second and subsequent values are sine and cosine components. You can think of it as the result of a Fourier transform, where you get frequency domain values from time domain value. Here, with `createPeriodicWave()`, you specify the frequencies, and the browser performs a an inverse Fourier transform to get a time domain buffer for the frequency of the oscillator. Here, we only set one component at full volume (1.0) on the fundamental tone, so we get a sine wave.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-oscillatornode-setperiodicwave" class="external">Web Audio API<br />
<span class="small">The definition of 'setPeriodicWave' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](../Web_Audio_API/Using_Web_Audio_API.html)
-   [AudioContext.createPeriodicWave](../BaseAudioContext/createPeriodicWave.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/oscillatornode/setperiodicwave/index.html "Folder: en-us/web/api/oscillatornode/setperiodicwave (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FOscillatorNode%2FsetPeriodicWave%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Foscillatornode%2Fsetperiodicwave%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FOscillatorNode%2FsetPeriodicWave%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Foscillatornode%2Fsetperiodicwave%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fa2282aa45be910a103b93ad06396ee195a10f456%0A*+Document+last+modified%3A+2021-06-01T11%3A47%3A53.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22OscillatorNode.setPeriodicWave%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](setPeriodicWave/contributors.txt)

Change your languageSelect your preferred language English (US)中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  **[`OscillatorNode`](../OscillatorNode.html)**
3.  Constructor
    1.  [`OscillatorNode()`](OscillatorNode.html)
4.  Properties
    1.  [`detune`](detune.html)
    2.  [`frequency`](frequency.html)
    3.  [`onended`](onended.html)
    4.  [`type`](type.html)
5.  Methods
    1.  *`setPeriodicWave()`*
    2.  [`start()`](start.html)
    3.  [`stop()`](stop.html)
6.  Inheritance:
    1.  [`AudioNode`](../AudioNode.html)
    2.  [`EventTarget`](../EventTarget.html)
7.  Related pages for Web Audio API
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
    17. [`BaseAudioContext`](../BaseAudioContext.html)
    18. [`BiquadFilterNode`](../BiquadFilterNode.html)
    19. [`ChannelMergerNode`](../ChannelMergerNode.html)
    20. [`ChannelSplitterNode`](../ChannelSplitterNode.html)
    21. [`ConstantSourceNode`](../ConstantSourceNode.html)
    22. [`ConvolverNode`](../ConvolverNode.html)
    23. [`DelayNode`](../DelayNode.html)
    24. [`DynamicsCompressorNode`](../DynamicsCompressorNode.html)
    25. [`GainNode`](../GainNode.html)
    26. [`IIRFilterNode`](../IIRFilterNode.html)
    27. [`MediaElementAudioSourceNode`](../MediaElementAudioSourceNode.html)
    28. [`MediaStreamAudioDestinationNode`](../MediaStreamAudioDestinationNode.html)
    29. [`MediaStreamAudioSourceNode`](../MediaStreamAudioSourceNode.html)
    30. [`OfflineAudioCompletionEvent`](../OfflineAudioCompletionEvent.html)
    31. [`OfflineAudioContext`](../OfflineAudioContext.html)
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

#### Mozilla

-   <a href="https://twitter.com/mozilla" class="social-icon twitter"><span class="visually-hidden">Mozilla on Twitter</span></a>
-   <a href="https://www.instagram.com/mozillagram/" class="social-icon instagram"><span class="visually-hidden">Mozilla on Instagram</span></a>

© 2005-2021 Mozilla and individual contributors. Content is available under [these licenses](https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
