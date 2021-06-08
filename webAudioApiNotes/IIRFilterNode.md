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
3.  <a href="IIRFilterNode.html" class="breadcrumb-current-page"><span data-property="name">IIRFilterNode</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

IIRFilterNode
=============

The **`IIRFilterNode`** interface of the [Web Audio API](Web_Audio_API.html) is a [`AudioNode`](AudioNode.html) processor which implements a general **<a href="https://en.wikipedia.org/wiki/Infinite_impulse_response" class="external" title="infinite impulse response">infinite impulse response</a>** (IIR)  filter; this type of filter can be used to implement tone control devices and graphic equalizers as well. It lets the parameters of the filter response be specified, so that it can be tuned as needed.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td>Same as on the input</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

Typically, it's best to use the [`BiquadFilterNode`](BiquadFilterNode.html) interface to implement higher-order filters. There are several reasons why:

-   Biquad filters are typically less sensitive to numeric quirks.
-   The filter parameters of biquad filters can be automated.
-   All even-ordered IIR filters can be created using [`BiquadFilterNode`](BiquadFilterNode.html).

However, if you need to create an odd-ordered IIR filter, you'll need to use `IIRFilterNode`. You may also find this interface useful if you don't need automation, or for other reasons.

Once the node has been created, you can't change its coefficients.

`IIRFilterNode`s have a tail-time reference; they continue to output non-silent audio with zero input. As an IIR filter, the non-zero input continues forever, but this can be limited after some finite time in practice, when the output has approached zero closely enough. The actual time that takes depends on the filter coefficients provided.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`IIRFilterNode()`](IIRFilterNode/IIRFilterNode.html "IIRFilterNode()")  
Creates a new instance of an IIRFilterNode object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface has no properties of its own; however, it inherits properties from its parent, [`AudioNode`](AudioNode.html)*.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent, [`AudioNode`](AudioNode.html). It also has the following additional methods:*

[`getFrequencyResponse()`](IIRFilterNode/getFrequencyResponse.html "getFrequencyResponse()")  
Uses the filter's current parameter settings to calculate the response for frequencies specified in the provided array of frequencies.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

You can find a simple IIR filter demo live <a href="https://codepen.io/Rumyra/pen/oPxvYB/" class="external">on Codepen</a>. Also see the <a href="https://github.com/mdn/webaudio-examples/tree/master/iirfilter-node" class="external">source code on GitHub</a>. It includes some different coefficient values for different lowpass frequencies — you can change the value of the <span class="pl-s1">`filterNumber` constant to a value between 0 and 3 to check out the different available effects.</span>

<span class="pl-s1">Also see our [Using IIR filters](Web_Audio_API/Using_IIR_filters.html) guide for a full explanation.</span>

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#iirfilternode" class="external">Web Audio API<br />
<span class="small">The definition of 'IIRFilterNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial Definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)
-   [`AudioNode`](AudioNode.html)
-   [`BiquadFilterNode`](BiquadFilterNode.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/iirfilternode/index.html "Folder: en-us/web/api/iirfilternode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FIIRFilterNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fiirfilternode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FIIRFilterNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fiirfilternode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fafb900789aa9c9f3fb0192a9ea1ae6e5ffb0d231%0A*+Document+last+modified%3A+2021-05-31T00%3A59%3A40.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22IIRFilterNode%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](IIRFilterNode/contributors.txt)

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`IIRFilterNode`](IIRFilterNode.html)**
3.  Constructor
    1.  [`IIRFilterNode()`](IIRFilterNode/IIRFilterNode.html)
4.  Methods
    1.  [`getFrequencyResponse()`](IIRFilterNode/getFrequencyResponse.html)
5.  Related pages for Web Audio API
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
    18. [`BiquadFilterNode`](BiquadFilterNode.html)
    19. [`ChannelMergerNode`](ChannelMergerNode.html)
    20. [`ChannelSplitterNode`](ChannelSplitterNode.html)
    21. [`ConstantSourceNode`](ConstantSourceNode.html)
    22. [`ConvolverNode`](ConvolverNode.html)
    23. [`DelayNode`](DelayNode.html)
    24. [`DynamicsCompressorNode`](DynamicsCompressorNode.html)
    25. [`GainNode`](GainNode.html)
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
