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
3.  <a href="AudioDestinationNode.html" class="breadcrumb-current-page"><span data-property="name">AudioDestinationNode</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioDestinationNode
====================

The `AudioDestinationNode` interface represents the end destination of an audio graph in a given context — usually the speakers of your device. It can also be the node that will "record" the audio data when used with an `OfflineAudioContext`.

`AudioDestinationNode` has no output (as it *is* the output, no more `AudioNode` can be linked after it in the audio graph) and one input. The number of channels in the input must be between `0` and the `maxChannelCount` value or an exception is raised.

The `AudioDestinationNode` of a given `AudioContext` can be retrieved using the [`AudioContext.destination`](BaseAudioContext/destination.html "AudioContext.destination") property.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>0</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"explicit"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code></td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`AudioNode`](AudioNode.html)*.

[`AudioDestinationNode.maxChannelCount`](AudioDestinationNode/maxChannelCount.html)  
Is an `unsigned long` defining the maximum number of channels that the physical device can handle.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*No specific method; inherits methods from its parent, [`AudioNode`](AudioNode.html)*.

[Example](#example "Permalink to Example")
------------------------------------------

There is no complex set up for using an `AudioDestinationNode` — by default, this represents the output of the user's system (e.g. their speakers), so you can get it hooked up inside an audio graph using only a few lines of code:

    var audioCtx = new AudioContext();
    var source = audioCtx.createMediaElementSource(myMediaElement);
    source.connect(gainNode);
    gainNode.connect(audioCtx.destination);

To see a more complete implementation, check out one of our MDN Web Audio examples, such as <a href="https://mdn.github.io/voice-change-o-matic/" class="external">Voice-change-o-matic</a> or <a href="https://mdn.github.io/violent-theremin/" class="external">Violent Theremin</a>.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioDestinationNode" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioDestinationNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audiodestinationnode/index.html "Folder: en-us/web/api/audiodestinationnode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioDestinationNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudiodestinationnode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioDestinationNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudiodestinationnode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioDestinationNode%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](AudioDestinationNode/contributors.txt)

Change your languageSelect your preferred language English (US)Deutsch日本語한국어中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioDestinationNode`](AudioDestinationNode.html)**
3.  Properties
    1.  [`maxChannelCount`](AudioDestinationNode/maxChannelCount.html)
4.  Inheritance:
    1.  [`AudioNode`](AudioNode.html)
    2.  [`EventTarget`](EventTarget.html)
5.  Related pages for Web Audio API
    1.  [`AnalyserNode`](AnalyserNode.html)
    2.  [`AudioBuffer`](AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](AudioBufferSourceNode.html)
    4.  [`AudioContext`](AudioContext.html)
    5.  [`AudioContextOptions`](AudioContextOptions.html)
    6.  [`AudioListener`](AudioListener.html)
    7.  [`AudioNode`](AudioNode.html)
    8.  [`AudioNodeOptions`](AudioNodeOptions.html)
    9.  [`AudioParam`](AudioParam.html)
    10. [`AudioProcessingEvent`](AudioProcessingEvent.html)
    11. [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)
    12. [`AudioWorklet`](AudioWorklet.html)
    13. [`AudioWorkletGlobalScope`](AudioWorkletGlobalScope.html)
    14. [`AudioWorkletNode`](AudioWorkletNode.html)
    15. [`AudioWorkletProcessor`](AudioWorkletProcessor.html)
    16. [`BaseAudioContext`](BaseAudioContext.html)
    17. [`BiquadFilterNode`](BiquadFilterNode.html)
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
