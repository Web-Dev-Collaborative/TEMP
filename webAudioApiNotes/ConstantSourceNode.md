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
3.  <a href="ConstantSourceNode.html" class="breadcrumb-current-page"><span data-property="name">ConstantSourceNode</span></a>

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

ConstantSourceNode
==================

The `ConstantSourceNode` interface—part of the Web Audio API—represents an audio source (based upon [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)) whose output is single unchanging value. This makes it useful for cases in which you need a constant value coming in from an audio source. In addition, it can be used like a constructible [`AudioParam`](AudioParam.html) by automating the value of its [`offset`](ConstantSourceNode/offset.html "offset") or by connecting another node to it; see [Controlling multiple parameters with ConstantSourceNode](Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode.html).

A `ConstantSourceNode` has no inputs and exactly one monaural (one-channel) output. The output's value is always the same as the value of the [`offset`](ConstantSourceNode/offset.html "offset") parameter.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>0</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr></tbody></table>

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`ConstantSourceNode()`](ConstantSourceNode/ConstantSourceNode.html "ConstantSourceNode()")  
Creates and returns a new `ConstantSourceNode` instance, optionally specifying an object which establishes initial values for the object's properties. You can also create a `ConstantSourceNode` whose properties are initialized to their default values by calling [`AudioContext.createConstantSource()`](BaseAudioContext/createConstantSource.html "AudioContext.createConstantSource()").

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent interface, [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html), and adds the following properties:*

[`offset`](ConstantSourceNode/offset.html "offset")  
An [`AudioParam`](AudioParam.html) which specifies the value that this source continuously outputs. The default value is 1.0.

### [Event handlers](#event_handlers "Permalink to Event handlers")

*Inherits event handlers from its parent interface, [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html).*

Some browsers' implementations of this event handler are part of the  [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html) interface.

[`onended`](AudioScheduledSourceNode/onended.html "onended")  
Fired whenever the [`ConstantSourceNode`](ConstantSourceNode.html) data has stopped playing.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent interface, [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html).*

Some browsers' implementations of these methods are part of the [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html) interface.

[`start()`](AudioScheduledSourceNode/start.html "start()")  
Schedules a sound to playback at an exact time.

[`stop()`](AudioScheduledSourceNode/stop.html "stop()")  
Schedules a sound to stop playback at an exact time.

[Example](#example "Permalink to Example")
------------------------------------------

In the article [Controlling multiple parameters with ConstantSourceNode](Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode.html), a `ConstantSourceNode` is created to allow one slider control to change the gain on two [`GainNode`](GainNode.html)s. The three nodes are set up like this:

    gainNode2 = context.createGain();
    gainNode3 = context.createGain();
    gainNode2.gain.value = gainNode3.gain.value = 0.5;
    volumeSliderControl.value = gainNode2.gain.value;

    constantNode = context.createConstantSource();
    constantNode.connect(gainNode2.gain);
    constantNode.connect(gainNode3.gain);
    constantNode.start();

    gainNode2.connect(context.destination);
    gainNode3.connect(context.destination);

This code starts by creating the gain nodes and setting them and the volume control that will adjust their value all to 0.5. Then the `ConstantSourceNode` is created by calling [`AudioContext.createConstantSource()`](BaseAudioContext/createConstantSource.html "AudioContext.createConstantSource()"), and the gain parameters of each of the two gain nodes are connected to the `ConstantSourceNode`. After starting the constant source by calling its [`start()`](AudioScheduledSourceNode/start.html "start()") method. Finally, the two gain nodes are connected to the audio destination (typically speakers or headphones).

Now, whenever the value of [`constantNode.offset`](ConstantSourceNode/offset.html "constantNode.offset") changes, the gain on both `gainNode2` and `gainNode3` will change to have that same value.

To see this example in action, as well as to read the rest of the code from which these snippets were derived, see [Controlling multiple parameters with ConstantSourceNode.](Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode.html)

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#ConstantSourceNode" class="external">Web Audio API<br />
<span class="small">The definition of 'ConstantSourceNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)
-   [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)
-   [`AudioNode`](AudioNode.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/constantsourcenode/index.html "Folder: en-us/web/api/constantsourcenode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FConstantSourceNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fconstantsourcenode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FConstantSourceNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fconstantsourcenode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fe085698aeab231f6d0c1d3bb7ea6288237946703%0A*+Document+last+modified%3A+2021-05-29T04%3A16%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22ConstantSourceNode%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](ConstantSourceNode/contributors.txt)

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`ConstantSourceNode`](ConstantSourceNode.html)**
3.  Constructor
    1.  [`ConstantSourceNode()`](ConstantSourceNode/ConstantSourceNode.html)
4.  Properties
    1.  [`offset`](ConstantSourceNode/offset.html)
5.  Inheritance:
    1.  [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)
    2.  [`AudioNode`](AudioNode.html)
    3.  [`EventTarget`](EventTarget.html)
6.  Related pages for Web Audio API
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
