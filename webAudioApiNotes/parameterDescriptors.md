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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor" class="breadcrumb-penultimate"><span data-property="name">AudioWorkletProcessor</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/parameterDescriptors" class="breadcrumb-current-page"><span data-property="name">AudioWorkletProcessor.parameterDescriptors (static getter)</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioWorkletProcessor.parameterDescriptors (static getter)
==========================================================

#### Experimental

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only **`parameterDescriptors`** property of an [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor)-derived class is a *static getter*, which returns an iterable of [`AudioParamDescriptor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParamDescriptor)-based objects.

The property is not a part of the [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor) interface, but, if defined, it is called internally by the [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor) constructor to create a list of custom [`AudioParam`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParam) objects in the [`parameters`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/parameters "parameters") property of the associated [`AudioWorkletNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode).

Defining the getter is optional.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    AudioWorkletProcessorSubclass.parameterDescriptors;

### [Value](#value "Permalink to Value")

An iterable of [`AudioParamDescriptor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParamDescriptor)-based objects. The properties of these objects are as follows:

`name`  
The [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which represents the name of the `AudioParam`. Under this name the `AudioParam` will be available in the [`parameters`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/parameters "parameters") property of the node, and under this name the [`AudioWorkletProcessor.process`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/process) method will acquire the calculated values of this `AudioParam`.

`automationRate` <span class="badge inline optional">Optional</span>  
Either `"a-rate"`, or `"k-rate"` string which represents an automation rate of this `AudioParam`. Defaults to `"a-rate"`.

`minValue` <span class="badge inline optional">Optional</span>  
A `float` which represents minimum value of the `AudioParam`. Defaults to `-3.4028235e38`.

`maxValue` <span class="badge inline optional">Optional</span>  
A `float` which represents maximum value of the `AudioParam`. Defaults to `3.4028235e38`.

`defaultValue` <span class="badge inline optional">Optional</span>  
A `float` which represents initial value of the `AudioParam`. Defaults to `0`.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

See [`AudioWorkletNode.parameters`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/parameters#examples) for example code showing how to add static `parameterDescriptors` getter to a custom `AudioWorkletProcessor`.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#parameterdescriptors" class="external">Web Audio API<br />
<span class="small">The definition of 'parameterDescriptors' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

No compatibility data found for `api.AudioWorkletProcessor.parameterDescriptors`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
-   [Using the Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audioworkletprocessor/parameterdescriptors/index.html "Folder: en-us/web/api/audioworkletprocessor/parameterdescriptors (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioWorkletProcessor%2FparameterDescriptors%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudioworkletprocessor%2Fparameterdescriptors%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioWorkletProcessor%2FparameterDescriptors%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudioworkletprocessor%2Fparameterdescriptors%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0cd2d5ad141ac8009ae34e14b97bc3914a48b9ea%0A*+Document+last+modified%3A+2021-05-25T08%3A31%3A51.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioWorkletProcessor.parameterDescriptors+%28static%E2%80%A6%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 25, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/parameterDescriptors/contributors.txt)

#### Related Topics

1.  **[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)**
2.  **[`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor)**
3.  Constructor
    1.  [`AudioWorkletProcessor()`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/AudioWorkletProcessor)
4.  Properties
    1.  *`parameterDescriptors (static getter)`*
    2.  [`port`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/port)
5.  Methods
    1.  [`process`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/process)
6.  Related pages for Web Audio API
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
