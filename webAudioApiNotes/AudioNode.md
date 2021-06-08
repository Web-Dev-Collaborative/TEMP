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
3.  <a href="AudioNode.html" class="breadcrumb-current-page"><span data-property="name">AudioNode</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Description](#description)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioNode
=========

The **`AudioNode`** interface is a generic interface for representing an audio processing module.

Examples include:

-   an audio source (e.g. an HTML [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, an [`OscillatorNode`](OscillatorNode.html), etc.),
-   the audio destination,
-   intermediate processing module (e.g. a filter like [`BiquadFilterNode`](BiquadFilterNode.html) or [`ConvolverNode`](ConvolverNode.html)), or
-   volume control (like [`GainNode`](GainNode.html))

**Note**: An `AudioNode` can be target of events, therefore it implements the [`EventTarget`](EventTarget.html) interface.

[Description](#description "Permalink to Description")
------------------------------------------------------

### [The audio routing graph](#the_audio_routing_graph "Permalink to The audio routing graph")

<img src="AudioNode/webaudiobasics.png" alt="AudioNodes participating in an AudioContext create a audio routing graph." width="677" height="461" />

Each `AudioNode` has inputs and outputs, and multiple audio nodes are connected to build a *processing graph*. This graph is contained in an [`AudioContext`](AudioContext.html), and each audio node can only belong to one audio context.

A *source node* has zero inputs but one or multiple outputs, and can be used to generate sound. On the other hand, a *destination node* has no outputs; instead, all its inputs are directly played back on the speakers (or whatever audio output device the audio context uses). In addition, there are *processing nodes* which have inputs and outputs. The exact processing done varies from one `AudioNode` to another but, in general, a node reads its inputs, does some audio-related processing, and generates new values for its outputs, or lets the audio pass through (for example in the [`AnalyserNode`](AnalyserNode.html), where the result of the processing is accessed separately).

The more nodes in a graph, the higher the latency will be. For example, if your graph has a latency of 500ms, when the source node plays a sound, it will take half a second until that sound can be heard on your speakers (or even longer because of latency in the underlying audio device). Therefore, if you need to have interactive audio, keep the graph as small as possible, and put user-controlled audio nodes at the end of a graph. For example, a volume control (`GainNode`) should be the last node so that volume changes take immediate effect.

Each input and output has a given amount of *channels*. For example, mono audio has one channel, while stereo audio has two channels. The Web Audio API will up-mix or down-mix the number of channels as required; check the Web Audio spec for details.

For a list of all audio nodes, see the [Web Audio API](Web_Audio_API.html) homepage.

### [Creating an `AudioNode`](#creating_an_audionode "Permalink to Creating an AudioNode")

There are two ways to create an `AudioNode`: via the *constructor* and via the *factory method*.

    // constructor
    const analyserNode = new AnalyserNode(audioCtx, {
      fftSize: 2048,
      maxDecibels: -25,
      minDecibels: -60,
      smoothingTimeConstant: 0.5,
    });

    // factory method
    const analyserNode = audioCtx.createAnalyser();
    analyserNode.fftSize = 2048;
    analyserNode.maxDecibels = -25;
    analyserNode.minDecibels = -60;
    analyserNode.smoothingTimeConstant = 0.5;

You are free to use either constructors or factory methods, or mix both, however there are advantages to using the constructors:

-   All parameters can be set during construction time and don't need to be set individually.
-   You can <a href="https://github.com/WebAudio/web-audio-api/issues/251" class="external">sub-class an audio node</a>. While the actual processing is done internally by the browser and cannot be altered, you could write a wrapper around an audio node to provide custom properties and methods.
-   Slightly better performance: In both Chrome and Firefox, the factory methods call the constructors internally.

Keep in mind that Microsoft Edge does not yet appear to support the constructors; it will throw a "Function expected" error when you use the constructors.

*Brief history:* The first version of the Web Audio spec only defined the factory methods. After a <a href="https://github.com/WebAudio/web-audio-api/issues/250" class="external">design review in October 2013</a>, it was decided to add constructors because they have numerous benefits over factory methods. The constructors were added to the spec from August to October 2016. Factory methods continue to be included in the spec and are not deprecated.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`AudioNode.context`](AudioNode/context.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the associated [`BaseAudioContext`](BaseAudioContext.html), that is the object representing the processing graph the node is participating in.

[`AudioNode.numberOfInputs`](AudioNode/numberOfInputs.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the number of inputs feeding the node. Source nodes are defined as nodes having a `numberOfInputs` property with a value of `0`.

[`AudioNode.numberOfOutputs`](AudioNode/numberOfOutputs.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the number of outputs coming out of the node. Destination nodes — like [`AudioDestinationNode`](AudioDestinationNode.html) — have a value of `0` for this attribute.

[`AudioNode.channelCount`](AudioNode/channelCount.html)  
Represents an integer used to determine how many channels are used when [up-mixing and down-mixing](Web_Audio_API/Basic_concepts_behind_Web_Audio_API.html#up-mixing_and_down-mixing) connections to any inputs to the node. Its usage and precise definition depend on the value of [`AudioNode.channelCountMode`](AudioNode/channelCountMode.html).

[`AudioNode.channelCountMode`](AudioNode/channelCountMode.html)  
Represents an enumerated value describing the way channels must be matched between the node's inputs and outputs.

[`AudioNode.channelInterpretation`](AudioNode/channelInterpretation.html)  
Represents an enumerated value describing the meaning of the channels. This interpretation will define how audio [up-mixing and down-mixing](Web_Audio_API/Basic_concepts_behind_Web_Audio_API.html#up-mixing_and_down-mixing) will happen.  
The possible values are `"speakers"` or `"discrete"`.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Also implements methods from the interface* [`EventTarget`](EventTarget.html).

[`AudioNode.connect()`](AudioNode/connect.html)  
Allows us to connect the output of this node to be input into another node, either as audio data or as the value of an [`AudioParam`](AudioParam.html).

[`AudioNode.disconnect()`](AudioNode/disconnect.html)  
Allows us to disconnect the current node from another one it is already connected to.

[Example](#example "Permalink to Example")
------------------------------------------

This simple snippet of code shows the creation of some audio nodes, and how the `AudioNode` properties and methods can be used. You can find examples of such usage on any of the examples linked to on the [Web Audio API](Web_Audio_API.html) landing page (for example <a href="https://github.com/mdn/violent-theremin" class="external">Violent Theremin</a>.)<span class="p"> </span>

    const audioCtx = new AudioContext();

    const oscillator = new OscillatorNode(audioCtx);
    const gainNode = new GainNode(audioCtx);

    oscillator.connect(gainNode).connect(audioCtx.destination);

    oscillator.context;
    oscillator.numberOfInputs;
    oscillator.numberOfOutputs;
    oscillator.channelCount;

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audionode" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audionode/index.html "Folder: en-us/web/api/audionode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudionode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudionode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioNode%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](AudioNode/contributors.txt)

Change your languageSelect your preferred language English (US)DeutschEspañolFrançais日本語한국어Português (do Brasil)Русский中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioNode`](AudioNode.html)**
3.  Properties
    1.  [`channelCount`](AudioNode/channelCount.html)
    2.  [`channelCountMode`](AudioNode/channelCountMode.html)
    3.  [`channelInterpretation`](AudioNode/channelInterpretation.html)
    4.  [`context`](AudioNode/context.html)
    5.  [`numberOfInputs`](AudioNode/numberOfInputs.html)
    6.  [`numberOfOutputs`](AudioNode/numberOfOutputs.html)
4.  Methods
    1.  [`connect()`](AudioNode/connect.html)
    2.  [`disconnect()`](AudioNode/disconnect.html)
5.  Inheritance:
    1.  [`EventTarget`](EventTarget.html)
6.  Related pages for Web Audio API
    1.  [`AnalyserNode`](AnalyserNode.html)
    2.  [`AudioBuffer`](AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](AudioBufferSourceNode.html)
    4.  [`AudioContext`](AudioContext.html)
    5.  [`AudioContextOptions`](AudioContextOptions.html)
    6.  [`AudioDestinationNode`](AudioDestinationNode.html)
    7.  [`AudioListener`](AudioListener.html)
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
