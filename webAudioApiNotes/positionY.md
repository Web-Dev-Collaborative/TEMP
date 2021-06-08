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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode" class="breadcrumb-penultimate"><span data-property="name">PannerNode</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionY" class="breadcrumb-current-page"><span data-property="name">PannerNode.positionY</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

PannerNode.positionY
====================

The **`positionY`** property of the [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode) interface specifies the Y coordinate of the audio source's position in 3D Cartesian coordinates, corresponding to the *vertical* axis (top-bottom). The complete vector is defined by the position of the audio source, given as ([`positionX`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionX "positionX"), [`positionY`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionY "positionY"), [`positionZ`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionZ "positionZ")), and the orientation of the audio source (that is, the direction in which it's facing), given as ([`orientationX`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationX "orientationX"), [`orientationY`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationY "orientationY"), [`orientationZ`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationZ "orientationZ")).

Depending on the directionality of the sound (as specified using the attributes [`coneInnerAngle`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneInnerAngle "coneInnerAngle"), [`coneOuterAngle`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneOuterAngle "coneOuterAngle"), and [`codeOuterGain`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneOuterGain "codeOuterGain")), the orientation of the sound may alter the perceived volume of the sound as it's being played. If the sound is pointing toward the listener, it will be louder than if the sound is pointed away from the listener.

The [`AudioParam`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParam) contained by this property is read only; however, you can still change the value of the parameter by assigning a new value to its [`AudioParam.value`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/value) property.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var positionY = PannerNode.positionY;

    PannerNode.positionY.value = newPositionY;

### [Value](#value "Permalink to Value")

An [`AudioParam`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParam) whose `value` is the Y coordinate of the audio source's position, in 3D Cartesian coordinates.

[Example](#example "Permalink to Example")
------------------------------------------

The following example starts an oscillator and pans it above the listener after 1 second, below the listener after 2 seconds, and back to the center after 3 seconds. Note that in this case, the change will mainly affect the timbre of the oscillator, as it's a simple mono wave.

    const context = new AudioContext();

    const osc = new OscillatorNode(context);
    const panner = new PannerNode(context);
    panner.panningModel = 'HRTF';

    panner.positionY.setValueAtTime(1, context.currentTime + 1);
    panner.positionY.setValueAtTime(-1, context.currentTime + 2);
    panner.positionY.setValueAtTime(0, context.currentTime + 3);

    osc.connect(panner)
       .connect(context.destination);

    osc.start(0);

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-pannernode-positiony" class="external">Web Audio API<br />
<span class="small">The definition of 'positionY' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)
-   [Web Audio spatialisation basics](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Web_audio_spatialization_basics)
-   [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/pannernode/positiony/index.html "Folder: en-us/web/api/pannernode/positiony (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FPannerNode%2FpositionY%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fpannernode%2Fpositiony%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FPannerNode%2FpositionY%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fpannernode%2Fpositiony%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fa2282aa45be910a103b93ad06396ee195a10f456%0A*+Document+last+modified%3A+2021-06-01T11%3A47%3A53.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22PannerNode.positionY%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionY/contributors.txt)

#### Related Topics

1.  **[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)**
2.  **[`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode)**
3.  Constructor
    1.  [`PannerNode()`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/PannerNode)
4.  Properties
    1.  [`coneInnerAngle`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneInnerAngle)
    2.  [`coneOuterAngle`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneOuterAngle)
    3.  [`coneOuterGain`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneOuterGain)
    4.  [`distanceModel`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/distanceModel)
    5.  [`maxDistance`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/maxDistance)
    6.  [`orientationX`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationX)
    7.  [`orientationY`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationY)
    8.  [`orientationZ`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationZ)
    9.  [`panningModel`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/panningModel)
    10. [`positionX`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionX)
    11. *`positionY`*
    12. [`positionZ`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionZ)
    13. [`refDistance`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/refDistance)
    14. [`rolloffFactor`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/rolloffFactor)
5.  Methods
    1.  [`setOrientation()`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/setOrientation)
    2.  [`setPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/setPosition)
    3.  [`setVelocity()`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/setVelocity)
6.  Inheritance:
    1.  [`AudioNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioNode)
    2.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
7.  Related pages for Web Audio API
    1.  [`AnalyserNode`](https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode)
    2.  [`AudioBuffer`](https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer)
    3.  [`AudioBufferSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode)
    4.  [`AudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext)
    5.  [`AudioContextOptions`](https://developer.mozilla.org/en-US/docs/Web/API/AudioContextOptions)
    6.  [`AudioDestinationNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioDestinationNode)
    7.  [`AudioListener`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener)
    8.  [`AudioNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioNode)
    9.  [`AudioNodeOptions`](https://developer.mozilla.org/en-US/docs/Web/API/AudioNodeOptions)
    10. [`AudioParam`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParam)
    11. [`AudioProcessingEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AudioProcessingEvent)
    12. [`AudioScheduledSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode)
    13. [`AudioWorklet`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorklet)
    14. [`AudioWorkletGlobalScope`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletGlobalScope)
    15. [`AudioWorkletNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode)
    16. [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor)
    17. [`BaseAudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext)
    18. [`BiquadFilterNode`](https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode)
    19. [`ChannelMergerNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChannelMergerNode)
    20. [`ChannelSplitterNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChannelSplitterNode)
    21. [`ConstantSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/ConstantSourceNode)
    22. [`ConvolverNode`](https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode)
    23. [`DelayNode`](https://developer.mozilla.org/en-US/docs/Web/API/DelayNode)
    24. [`DynamicsCompressorNode`](https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode)
    25. [`GainNode`](https://developer.mozilla.org/en-US/docs/Web/API/GainNode)
    26. [`IIRFilterNode`](https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode)
    27. [`MediaElementAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaElementAudioSourceNode)
    28. [`MediaStreamAudioDestinationNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioDestinationNode)
    29. [`MediaStreamAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode)
    30. [`OfflineAudioCompletionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioCompletionEvent)
    31. [`OfflineAudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext)
    32. [`OscillatorNode`](https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode)
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

#### Mozilla

-   <a href="https://twitter.com/mozilla" class="social-icon twitter"><span class="visually-hidden">Mozilla on Twitter</span></a>
-   <a href="https://www.instagram.com/mozillagram/" class="social-icon instagram"><span class="visually-hidden">Mozilla on Instagram</span></a>

© 2005-2021 Mozilla and individual contributors. Content is available under [these licenses](https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
