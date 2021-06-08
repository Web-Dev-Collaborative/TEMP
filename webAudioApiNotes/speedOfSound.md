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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioListener" class="breadcrumb-penultimate"><span data-property="name">AudioListener</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/speedOfSound" class="breadcrumb-current-page"><span data-property="name">AudioListener.speedOfSound</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioListener.speedOfSound
==========================

#### Deprecated

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **`speedOfSound`** property of the [`AudioListener`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener) interface is a double value representing the speed of sound, in *meters per second*.

The `speedOfSound` property's default value is `343.3` m/s and is used to calculate the <a href="https://en.wikipedia.org/wiki/Doppler_effect" class="external">doppler shift</a> appropriate for the speed the panner is travelling at (as defined by [`PannerNode.setVelocity`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/setVelocity).)

**Note**: Bear in mind that no propagation delay is automatically applied to a sound far from the listener.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var audioCtx = new AudioContext();
    var myListener = audioCtx.listener;
    myListener.speedOfSound = 343.3;

### [Value](#value "Permalink to Value")

A double.

[Example](#example "Permalink to Example")
------------------------------------------

See [`BaseAudioContext.createPanner()`](https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createPanner#example) for example code.

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audiolistener/speedofsound/index.html "Folder: en-us/web/api/audiolistener/speedofsound (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioListener%2FspeedOfSound%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudiolistener%2Fspeedofsound%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioListener%2FspeedOfSound%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudiolistener%2Fspeedofsound%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioListener.speedOfSound%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/speedOfSound/contributors.txt)

#### Related Topics

1.  **[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)**
2.  **[`AudioListener`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener)**
3.  Properties
    1.  [`dopplerFactor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/dopplerFactor)
    2.  [`forwardX`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/forwardX)
    3.  [`forwardY`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/forwardY)
    4.  [`forwardZ`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/forwardZ)
    5.  [`positionX`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/positionX)
    6.  [`positionY`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/positionY)
    7.  [`positionZ`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/positionZ)
    8.  *`speedOfSound`*
    9.  [`upX`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/upX)
    10. [`upY`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/upY)
    11. [`upZ`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/upZ)
4.  Methods
    1.  [`setOrientation()`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/setOrientation)
    2.  [`setPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/setPosition)
5.  Related pages for Web Audio API
    1.  [`AnalyserNode`](https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode)
    2.  [`AudioBuffer`](https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer)
    3.  [`AudioBufferSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode)
    4.  [`AudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext)
    5.  [`AudioContextOptions`](https://developer.mozilla.org/en-US/docs/Web/API/AudioContextOptions)
    6.  [`AudioDestinationNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioDestinationNode)
    7.  [`AudioNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioNode)
    8.  [`AudioNodeOptions`](https://developer.mozilla.org/en-US/docs/Web/API/AudioNodeOptions)
    9.  [`AudioParam`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParam)
    10. [`AudioProcessingEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AudioProcessingEvent)
    11. [`AudioScheduledSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode)
    12. [`AudioWorklet`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorklet)
    13. [`AudioWorkletGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletGlobalScope)
    14. [`AudioWorkletNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode)
    15. [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor)
    16. [`BaseAudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext)
    17. [`BiquadFilterNode`](https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode)
    18. [`ChannelMergerNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChannelMergerNode)
    19. [`ChannelSplitterNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChannelSplitterNode)
    20. [`ConstantSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/ConstantSourceNode)
    21. [`ConvolverNode`](https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode)
    22. [`DelayNode`](https://developer.mozilla.org/en-US/docs/Web/API/DelayNode)
    23. [`DynamicsCompressorNode`](https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode)
    24. [`GainNode`](https://developer.mozilla.org/en-US/docs/Web/API/GainNode)
    25. [`IIRFilterNode`](https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode)
    26. [`MediaElementAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaElementAudioSourceNode)
    27. [`MediaStreamAudioDestinationNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioDestinationNode)
    28. [`MediaStreamAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode)
    29. [`OfflineAudioCompletionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioCompletionEvent)
    30. [`OfflineAudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext)
    31. [`OscillatorNode`](https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode)
    32. [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode)
    33. [`PeriodicWave`](https://developer.mozilla.org/en-US/docs/Web/API/PeriodicWave)
    34. [`StereoPannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/StereoPannerNode)
    35. [`WaveShaperNode`](https://developer.mozilla.org/en-US/docs/Web/API/WaveShaperNode)

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
