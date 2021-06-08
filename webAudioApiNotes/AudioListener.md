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
3.  <a href="AudioListener.html" class="breadcrumb-current-page"><span data-property="name">AudioListener</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Deprecated features](#deprecated_features)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioListener
=============

The `AudioListener` interface represents the position and orientation of the unique person listening to the audio scene, and is used in [audio spatialization](Web_Audio_API/Web_audio_spatialization_basics.html). All [`PannerNode`](PannerNode.html)s spatialize in relation to the `AudioListener` stored in the [`BaseAudioContext.listener`](BaseAudioContext/listener.html) attribute.

It is important to note that there is only one listener per context and that it isn't an [`AudioNode`](AudioNode.html).

<img src="AudioListener/webaudiolistenerreduced.png" alt="We see the position, up and front vectors of an AudioListener, with the up and front vectors at 90° from the other." width="634" height="250" />

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

The position, forward, and up value are set and retrieved using different syntaxes. Retrieval is done by accessing, for example, `AudioListener.positionX`, while setting the same property is done with `AudioListener.positionX.value`. This is why these values are not marked read only, which is how they appear in the specification's IDL.

[`AudioListener.positionX`](AudioListener/positionX.html)  
Represents the horizontal position of the listener in a right-hand cartesian coordinate system. The default is 0.

[`AudioListener.positionY`](AudioListener/positionY.html)  
Represents the vertical position of the listener in a right-hand cartesian coordinate system. The default is 0.

[`AudioListener.positionZ`](AudioListener/positionZ.html)  
Represents the longitudinal (back and forth) position of the listener in a right-hand cartesian coordinate system. The default is 0.

[`AudioListener.forwardX`](AudioListener/forwardX.html)  
Represents the horizontal position of the listener's forward direction in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 0.

[`AudioListener.forwardY`](AudioListener/forwardY.html)  
Represents the vertical position of the listener's forward direction in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 0.

[`AudioListener.forwardZ`](AudioListener/forwardZ.html)  
Represents the longitudinal (back and forth) position of the listener's forward direction in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is -1.

[`AudioListener.upX`](AudioListener/upX.html)  
Represents the horizontal position of the top of the listener's head in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 0.

[`AudioListener.upY`](AudioListener/upY.html)  
Represents the vertical position of the top of the listener's head in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 1.

[`AudioListener.upZ`](AudioListener/upZ.html)  
Represents the longitudinal (back and forth) position of the top of the listener's head in the same cartesian coordinate system as the position (`positionX`, `positionY`, and `positionZ`) values. The forward and up values are linearly independent of each other. The default is 0.

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`AudioListener.setOrientation()`](AudioListener/setOrientation.html)   
Sets the orientation of the listener.

[`AudioListener.setPosition()`](AudioListener/setPosition.html)   
Sets the position of the listener.

**Note**: Although these methods are deprecated they are currently the only way to set the orientation and position in Firefox, Internet Explorer and Safari.

[Deprecated features](#deprecated_features "Permalink to Deprecated features")
------------------------------------------------------------------------------

[`AudioListener.dopplerFactor`](AudioListener/dopplerFactor.html)   
A double value representing the amount of pitch shift to use when rendering a <a href="https://en.wikipedia.org/wiki/Doppler_effect" class="external">doppler effect</a>.

[`AudioListener.speedOfSound`](AudioListener/speedOfSound.html)   
Is a double value representing the speed of sound, in *meters per second*.

In a previous version of the specification, the `dopplerFactor` and `speedOfSound` properties and the `setPosition()` method could be used to control the doppler effect applied to [`AudioBufferSourceNode`](AudioBufferSourceNode.html)s connected downstream — these would be pitched up and down according to the relative speed of the [`PannerNode`](PannerNode.html) and the [`AudioListener`](AudioListener.html). These features had a number of problems:

-   Only [`AudioBufferSourceNode`](AudioBufferSourceNode.html)s were pitched up or down, not other source nodes.
-   The behavior to adopt when an [`AudioBufferSourceNode`](AudioBufferSourceNode.html) was connected to multiple [`PannerNode`](PannerNode.html)s was unclear.
-   Because the velocity of the panner and the listener were not [`AudioParam`](AudioParam.html)s, the pitch modification could not be smoothly applied, resulting in audio glitches.

Because of these issues, these properties and methods have been removed.

The `setOrientation()` and `setPosition()` methods have been replaced by setting their property value equivilents. For example `setPosition(x, y, z)` can be achieved by setting `positionX.value`, `positionY.value`, and `positionZ.value` respectively.

[Example](#example "Permalink to Example")
------------------------------------------

See [`BaseAudioContext.createPanner()`](BaseAudioContext/createPanner.html#example) for example code.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audiolistener" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioListener' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audiolistener/index.html "Folder: en-us/web/api/audiolistener (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioListener%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudiolistener%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioListener%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudiolistener%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioListener%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](AudioListener/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioListener`](AudioListener.html)**
3.  Properties
    1.  [`dopplerFactor`](AudioListener/dopplerFactor.html)
    2.  [`forwardX`](AudioListener/forwardX.html)
    3.  [`forwardY`](AudioListener/forwardY.html)
    4.  [`forwardZ`](AudioListener/forwardZ.html)
    5.  [`positionX`](AudioListener/positionX.html)
    6.  [`positionY`](AudioListener/positionY.html)
    7.  [`positionZ`](AudioListener/positionZ.html)
    8.  [`speedOfSound`](AudioListener/speedOfSound.html)
    9.  [`upX`](AudioListener/upX.html)
    10. [`upY`](AudioListener/upY.html)
    11. [`upZ`](AudioListener/upZ.html)
4.  Methods
    1.  [`setOrientation()`](AudioListener/setOrientation.html)
    2.  [`setPosition()`](AudioListener/setPosition.html)
5.  Related pages for Web Audio API
    1.  [`AnalyserNode`](AnalyserNode.html)
    2.  [`AudioBuffer`](AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](AudioBufferSourceNode.html)
    4.  [`AudioContext`](AudioContext.html)
    5.  [`AudioContextOptions`](AudioContextOptions.html)
    6.  [`AudioDestinationNode`](AudioDestinationNode.html)
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
