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
4.  <a href="createPeriodicWave.html" class="breadcrumb-current-page"><span data-property="name">BaseAudioContext.createPeriodicWave()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

BaseAudioContext.createPeriodicWave()
=====================================

The `createPeriodicWave()` method of the [`BaseAudioContext`](../BaseAudioContext.html) Interface is used to create a [`PeriodicWave`](../PeriodicWave.html), which is used to define a periodic waveform that can be used to shape the output of an [`OscillatorNode`](../OscillatorNode.html).

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var wave = AudioContext.createPeriodicWave(real, imag[, constraints]);

### [Returns](#returns "Permalink to Returns")

A [`PeriodicWave`](../PeriodicWave.html).

### [Parameters](#parameters "Permalink to Parameters")

`real`  
An array of cosine terms (traditionally the A terms).

`imag`  
An array of sine terms (traditionally the B terms).

The `real` and `imag` arrays have to have the same length, otherwise an error is thrown.

`constraints` <span class="badge inline optional">Optional</span>  
An dictionary object that specifies whether normalization should be disabled (if not specified, normalization is enabled by default.) It takes one property:

-   `disableNormalization`: If set to `true`, normalization is disabled for the periodic wave. The default is `false`.

If normalized, the resulting wave will have a maximum absolute peak value of 1.

[Example](#example "Permalink to Example")
------------------------------------------

The following example illustrates simple usage of `createPeriodicWave()`, to create a [`PeriodicWave`](../PeriodicWave.html) object containing a simple sine wave.

    var real = new Float32Array(2);
    var imag = new Float32Array(2);
    var ac = new AudioContext();
    var osc = ac.createOscillator();

    real[0] = 0;
    imag[0] = 0;
    real[1] = 1;
    imag[1] = 0;

    var wave = ac.createPeriodicWave(real, imag, {disableNormalization: true});

    osc.setPeriodicWave(wave);

    osc.connect(ac.destination);

    osc.start();
    osc.stop(2);

This works because a sound that contains only a fundamental tone is by definition a sine wave

Here, we create a `PeriodicWave` with two values. The first value is the DC offset, which is the value at which the oscillator starts. 0 is good here, because we want to start the curve at the middle of the \[-1.0; 1.0\] range.

The second and subsequent values are sine and cosine components. You can think of it as the result of a Fourier transform, where you get frequency domain values from time domain value. Here, with `createPeriodicWave()`, you specify the frequencies, and the browser performs an inverse Fourier transform to get a time domain buffer for the frequency of the oscillator. Here, we only set one component at full volume (1.0) on the fundamental tone, so we get a sine wave.

The coefficients of the Fourier transform should be given in *ascending* order (i.e. (*a*+*b**i*)*e*<sup>*i*</sup>, (*c*+*d**i*)*e*<sup>2*i*</sup>, (*f*+*g**i*)*e*<sup>3*i*</sup>etc.) and can be positive or negative.  A simple way of manually obtaining such coefficients (though not the best) is to use a graphing calculator.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createperiodicwave" class="external">Web Audio API<br />
<span class="small">The definition of 'createPeriodicWave' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](../Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/baseaudiocontext/createperiodicwave/index.html "Folder: en-us/web/api/baseaudiocontext/createperiodicwave (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBaseAudioContext%2FcreatePeriodicWave%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fbaseaudiocontext%2Fcreateperiodicwave%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBaseAudioContext%2FcreatePeriodicWave%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fbaseaudiocontext%2Fcreateperiodicwave%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F591362776c1ef3ad42942777979939e511dd811f%0A*+Document+last+modified%3A+2021-05-29T03%3A45%3A05.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22BaseAudioContext.createPeriodicWave%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](createPeriodicWave/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語中文 (简体)

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
    15. *`createPeriodicWave()`*
    16. [`createScriptProcessor()`](createScriptProcessor.html)
    17. [`createStereoPanner()`](createStereoPanner.html)
    18. [`createWaveShaper()`](createWaveShaper.html)
    19. [`decodeAudioData()`](decodeAudioData.html)
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
