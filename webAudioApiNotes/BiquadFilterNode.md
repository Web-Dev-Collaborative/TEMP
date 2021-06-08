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
2.  <a href="https://developer.mozilla.org/en-US/docs/Web/API" class="breadcrumb-penultimate"><span data-property="name">Web APIs</span></a>
3.  <a href="BiquadFilterNode.html" class="breadcrumb-current-page"><span data-property="name">BiquadFilterNode</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

BiquadFilterNode
================

<span class="seoSummary">The `BiquadFilterNode` interface represents a simple low-order filter, and is created using the [`BaseAudioContext/createBiquadFilter`](BaseAudioContext/createBiquadFilter.html) method. It is an [`AudioNode`](AudioNode.html) that can represent different kinds of filters, tone control devices, and graphic equalizers.</span> A `BiquadFilterNode` always has exactly one input and one output.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code> (not used in the default count mode)</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`BiquadFilterNode()`](BiquadFilterNode/BiquadFilterNode.html "BiquadFilterNode()")  
Creates a new instance of a `BiquadFilterNode` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`AudioNode`](AudioNode.html)*.

**Note**: Though the `AudioParam` objects returned are read-only, the values they represent are not.

[`BiquadFilterNode.frequency`](BiquadFilterNode/frequency.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an [a-rate](AudioParam.html#a-rate) [`AudioParam`](AudioParam.html), a double representing a frequency in the current filtering algorithm measured in hertz (Hz).

[`BiquadFilterNode.detune`](BiquadFilterNode/detune.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an [a-rate](AudioParam.html#a-rate) [`AudioParam`](AudioParam.html) representing detuning of the frequency in <a href="https://en.wikipedia.org/wiki/Cent_(music)" class="external external-icon">cents</a>.

[`BiquadFilterNode.Q`](BiquadFilterNode/Q.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an [a-rate](AudioParam.html#a-rate) [`AudioParam`](AudioParam.html), a double representing a <a href="https://en.wikipedia.org/wiki/Q_factor" class="external">Q factor</a>, or *quality factor*.

[`BiquadFilterNode.gain`](BiquadFilterNode/gain.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an [a-rate](AudioParam.html#a-rate) [`AudioParam`](AudioParam.html), a double representing the <a href="https://en.wikipedia.org/wiki/Gain" class="external">gain</a> used in the current filtering algorithm.

[`BiquadFilterNode.type`](BiquadFilterNode/type.html)  
Is a string value defining the kind of filtering algorithm the node is implementing.  

<table><caption>The meaning of the different parameters depending of the type of the filter (detune has the same meaning regardless, so isn't listed below)</caption><thead><tr class="header"><th><code>type</code></th><th>Description</th><th><code>frequency</code></th><th><code>Q</code></th><th><code>gain</code></th></tr></thead><tbody><tr class="odd"><td><code>lowpass</code></td><td>Standard second-order resonant lowpass filter with 12dB/octave rolloff. Frequencies below the cutoff pass through; frequencies above it are attenuated.</td><td>The cutoff frequency.</td><td>Indicates how peaked the frequency is around the cutoff. The greater the value is, the greater is the peak.</td><td><em>Not used</em></td></tr><tr class="even"><td><code>highpass</code></td><td>Standard second-order resonant highpass filter with 12dB/octave rolloff. Frequencies below the cutoff are attenuated; frequencies above it pass through.</td><td>The cutoff frequency.</td><td>Indicates how peaked the frequency is around the cutoff. The greater the value, the greater the peak.</td><td><em>Not used</em></td></tr><tr class="odd"><td><code>bandpass</code></td><td>Standard second-order bandpass filter. Frequencies outside the given range of frequencies are attenuated; the frequencies inside it pass through.</td><td>The center of the range of frequencies.</td><td>Controls the width of the frequency band. The greater the <code>Q</code> value, the smaller the frequency band.</td><td><em>Not used</em></td></tr><tr class="even"><td><code>lowshelf</code></td><td>Standard second-order lowshelf filter. Frequencies lower than the frequency get a boost, or an attenuation; frequencies over it are unchanged.</td><td>The upper limit of the frequencies getting a boost or an attenuation.</td><td><em>Not used</em></td><td>The boost, in dB, to be applied; if negative, it will be an attenuation.</td></tr><tr class="odd"><td><code>highshelf</code></td><td>Standard second-order highshelf filter. Frequencies higher than the frequency get a boost or an attenuation; frequencies lower than it are unchanged.</td><td>The lower limit of the frequencies getting a boost or an attenuation.</td><td><em>Not used</em></td><td>The boost, in dB, to be applied; if negative, it will be an attenuation.</td></tr><tr class="even"><td><code>peaking</code></td><td>Frequencies inside the range get a boost or an attenuation; frequencies outside it are unchanged.</td><td>The middle of the frequency range getting a boost or an attenuation.</td><td>Controls the width of the frequency band. The greater the <code>Q</code> value, the smaller the frequency band.</td><td>The boost, in dB, to be applied; if negative, it will be an attenuation.</td></tr><tr class="odd"><td><code>notch</code></td><td>Standard <a href="https://en.wikipedia.org/wiki/Band-stop_filter" class="external">notch</a> filter, also called a <em>band-stop</em> or <em>band-rejection</em> filter. It is the opposite of a bandpass filter: frequencies outside the give range of frequencies pass through; frequencies inside it are attenuated.</td><td>The center of the range of frequencies.</td><td>Controls the width of the frequency band. The greater the <code>Q</code> value, the smaller the frequency band.</td><td><em>Not used</em></td></tr><tr class="even"><td><code>allpass</code></td><td>Standard second-order <a href="https://en.wikipedia.org/wiki/All-pass_filter#Digital_Implementation" class="external">allpass</a> filter. It lets all frequencies through, but changes the phase-relationship between the various frequencies.</td><td>The frequency with the maximal <a href="https://en.wikipedia.org/wiki/Group_delay_and_phase_delay" class="external">group delay</a>, that is, the frequency where the center of the phase transition occurs.</td><td>Controls how sharp the transition is at the medium frequency. The larger this parameter is, the sharper and larger the transition will be.</td><td><em>Not used</em></td></tr></tbody></table>

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent, [`AudioNode`](AudioNode.html)*.

[`BiquadFilterNode.getFrequencyResponse()`](BiquadFilterNode/getFrequencyResponse.html)  
From the current filter parameter settings this method calculates the frequency response for frequencies specified in the provided array of frequencies.

[Example](#example "Permalink to Example")
------------------------------------------

See [`AudioContext.createBiquadFilter`](BaseAudioContext/createBiquadFilter.html#example) for example code that shows how to use an `AudioContext` to create a Biquad filter node.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#biquadfilternode" class="external">Web Audio API<br />
<span class="small">The definition of 'BiquadFilterNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/biquadfilternode/index.html "Folder: en-us/web/api/biquadfilternode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBiquadFilterNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fbiquadfilternode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FBiquadFilterNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fbiquadfilternode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F591362776c1ef3ad42942777979939e511dd811f%0A*+Document+last+modified%3A+2021-05-29T03%3A45%3A05.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22BiquadFilterNode%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](BiquadFilterNode/contributors.txt)

Change your languageSelect your preferred language English (US)Français한국어Português (do Brasil)中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`BiquadFilterNode`](BiquadFilterNode.html)**
3.  Constructor
    1.  [`BiquadFilterNode()`](BiquadFilterNode/BiquadFilterNode.html)
4.  Properties
    1.  [`detune`](BiquadFilterNode/detune.html)
    2.  [`frequency`](BiquadFilterNode/frequency.html)
    3.  [`gain`](BiquadFilterNode/gain.html)
    4.  [`Q`](BiquadFilterNode/Q.html)
    5.  [`type`](BiquadFilterNode/type.html)
5.  Methods
    1.  [`getFrequencyResponse()`](BiquadFilterNode/getFrequencyResponse.html)
6.  Inheritance:
    1.  [`AudioNode`](AudioNode.html)
    2.  [`EventTarget`](EventTarget.html)
7.  Related pages for Web Audio API
    1.  [`AnalyserNode`](AnalyserNode.html)
    2.  [`AudioBuffer`](AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](AudioBufferSourceNode.html)
    4.  [`AudioContext`](AudioContext.html)
    5.  [`AudioContextOptions`](AudioContextOptions.html)
    6.  [`AudioDestinationNode`](AudioDestinationNode.html)
    7.  [`AudioListener`](AudioListener.html)
    8.  [`AudioNode`](AudioNode.html)
    9.  [`AudioNodeOptions`](AudioNodeOptions.html)
    10. [`AudioParam`](AudioParam.html)
    11. [`AudioProcessingEvent`](AudioProcessingEvent.html)
    12. [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)
    13. [`AudioWorklet`](AudioWorklet.html)
    14. [`AudioWorkletGlobalScope`](AudioWorkletGlobalScope.html)
    15. [`AudioWorkletNode`](AudioWorkletNode.html)
    16. [`AudioWorkletProcessor`](AudioWorkletProcessor.html)
    17. [`BaseAudioContext`](BaseAudioContext.html)
    18. [`ChannelMergerNode`](ChannelMergerNode.html)
    19. [`ChannelSplitterNode`](ChannelSplitterNode.html)
    20. [`ConstantSourceNode`](ConstantSourceNode.html)
    21. [`ConvolverNode`](ConvolverNode.html)
    22. [`DelayNode`](DelayNode.html)
    23. [`DynamicsCompressorNode`](DynamicsCompressorNode.html)
    24. [`GainNode`](GainNode.html)
    25. [`IIRFilterNode`](IIRFilterNode.html)
    26. [`MediaElementAudioSourceNode`](MediaElementAudioSourceNode.html)
    27. [`MediaStreamAudioDestinationNode`](MediaStreamAudioDestinationNode.html)
    28. [`MediaStreamAudioSourceNode`](MediaStreamAudioSourceNode.html)
    29. [`OfflineAudioCompletionEvent`](OfflineAudioCompletionEvent.html)
    30. [`OfflineAudioContext`](OfflineAudioContext.html)
    31. [`OscillatorNode`](OscillatorNode.html)
    32. [`PannerNode`](PannerNode.html)
    33. [`PeriodicWave`](PeriodicWave.html)
    34. [`StereoPannerNode`](StereoPannerNode.html)
    35. [`WaveShaperNode`](WaveShaperNode.html)

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
