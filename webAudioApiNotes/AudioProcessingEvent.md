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
3.  <a href="AudioProcessingEvent.html" class="breadcrumb-current-page"><span data-property="name">AudioProcessingEvent</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Example](#example)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioProcessingEvent
====================

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

<span class="seoSummary">The [Web Audio API](Web_Audio_API.html) `AudioProcessingEvent` represents events that occur when a [`ScriptProcessorNode`](ScriptProcessorNode.html) input buffer is ready to be processed.</span>

**Note**: As of the August 29 2014 Web Audio API spec publication, this feature has been marked as deprecated, and is soon to be replaced by <a href="https://webaudio.github.io/web-audio-api/#audioworklet" class="external">AudioWorklet</a>.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*The list below includes the properties inherited from its parent, [`Event`](Event.html)*.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Property</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>target</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><a href="EventTarget.html"><code>EventTarget</code></a></td><td>The event target (the topmost target in the DOM tree).</td></tr><tr class="even"><td><code>type</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><a href="DOMString.html"><code>DOMString</code></a></td><td>The type of event.</td></tr><tr class="odd"><td><code>bubbles</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>boolean</code></td><td>Does the event normally bubble?</td></tr><tr class="even"><td><code>cancelable</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>boolean</code></td><td>Is it possible to cancel the event?</td></tr><tr class="odd"><td><code>playbackTime</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><code>double</code></td><td>The time when the audio will be played, as defined by the time of <a href="BaseAudioContext/currentTime.html" title="AudioContext.currentTime"><code>AudioContext.currentTime</code></a></td></tr><tr class="even"><td><code>inputBuffer</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><a href="AudioBuffer.html"><code>AudioBuffer</code></a></td><td>The buffer containing the input audio data to be processed. The number of channels is defined as a parameter, <code>numberOfInputChannels</code>, of the factory method <a href="BaseAudioContext/createScriptProcessor.html" title="AudioContext.createScriptProcessor()"><code>AudioContext.createScriptProcessor()</code></a>. Note the returned <code>AudioBuffer</code> is only valid in the scope of the <code>onaudioprocess</code> function.</td></tr><tr class="odd"><td><code>outputBuffer</code> <span class="badge inline readonly" title="This value may not be changed.">Read only </span></td><td><a href="AudioBuffer.html"><code>AudioBuffer</code></a></td><td><p>The buffer where the output audio data should be written. The number of channels is defined as a parameter, <code>numberOfOutputChannels</code>, of the factory method <a href="BaseAudioContext/createScriptProcessor.html" title="AudioContext.createScriptProcessor()"><code>AudioContext.createScriptProcessor()</code></a>. Note the returned <code>AudioBuffer</code> is only valid in the scope of the <code>onaudioprocess</code> function.</p></td></tr></tbody></table>

[Example](#example "Permalink to Example")
------------------------------------------

See [`BaseAudioContext.createScriptProcessor()`](BaseAudioContext/createScriptProcessor.html#example) for example code that uses an `AudioProcessingEvent`.

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audioprocessingevent/index.html "Folder: en-us/web/api/audioprocessingevent (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioProcessingEvent%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudioprocessingevent%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioProcessingEvent%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudioprocessingevent%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F16a7bae62bb0780802aa32d31e073664a8b3b15f%0A*+Document+last+modified%3A+2021-05-25T08%3A30%3A14.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioProcessingEvent%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 25, 2021, [by MDN contributors](AudioProcessingEvent/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioProcessingEvent`](AudioProcessingEvent.html)**
3.  Inheritance:
    1.  [`Event`](Event.html)
4.  Related pages for Web Audio API
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
