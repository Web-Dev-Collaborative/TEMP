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
3.  <a href="AudioWorkletGlobalScope.html" class="breadcrumb-current-page"><span data-property="name">AudioWorkletGlobalScope</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioWorkletGlobalScope
=======================

<span class="seoSummary">The **`AudioWorkletGlobalScope`** interface of the [Web Audio API](Web_Audio_API.html) represents a global execution context for user-supplied code, which defines custom [`AudioWorkletProcessor`](AudioWorkletProcessor.html)-derived classes.</span> Each [`BaseAudioContext`](BaseAudioContext.html) has a single [`AudioWorklet`](AudioWorklet.html) available under the [`audioWorklet`](BaseAudioContext/audioWorklet.html "audioWorklet") property, which runs its code in a single `AudioWorkletGlobalScope`.

As the global execution context is shared across the current `BaseAudioContext`, it's possible to define any other variables and perform any actions allowed in worklets — apart from defining `AudioWorkletProcessor`-derived classes.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

<span class="page-not-created">`currentFrame`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns an integer that represents the ever-increasing current sample-frame of the audio block being processed. It is incremented by 128 (the size of a render quantum) after the processing of each audio block.

<span class="page-not-created">`currentTime`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a double that represents the ever-increasing context time of the audio block being processed. It is equal to the [`currentTime`](BaseAudioContext/currentTime.html "currentTime") property of the [`BaseAudioContext`](BaseAudioContext.html) the worklet belongs to.

<span class="page-not-created">`sampleRate`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a float that represents the sample rate of the associated [`BaseAudioContext`](BaseAudioContext.html).

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`registerProcessor()`](AudioWorkletGlobalScope/registerProcessor.html "registerProcessor()")  
Registers a class derived from the [`AudioWorkletProcessor`](AudioWorkletProcessor.html) interface. The class can then be used by creating an [`AudioWorkletNode`](AudioWorkletNode.html), providing its registered name.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In this example we output all global properties into the console in the constructor of a custom [`AudioWorkletProcessor`](AudioWorkletProcessor.html).

First we need to define the processor, and register it. Note that this should be done in a separate file.

    // test-processor.js
    class TestProcessor extends AudioWorkletProcessor {
      constructor () {
        super()
        // current sample-frame and time at the moment of instantiation
        // to see values change, you can put these two lines in process method
        console.log(currentFrame)
        console.log(currentTime)
      }
      // the process method is required - output silence,
      // which the outputs are already filled with
      process (inputs, outputs, parameters) {
        return true
      }
    }

    // the sample rate is not going to change ever,
    // because it's a read-only property of a BaseAudioContext
    // and is set only during its instantiation
    console.log(sampleRate)

    // you can declare any variables and use them in your processors
    // for example it may be an ArrayBuffer with a wavetable
    const usefulVariable = 42
    console.log(usefulVariable)

    registerProcessor('test-processor', TestProcessor)

Next, in our main scripts file we'll load the processor, create an instance of `AudioWorkletNode` — passing the name of the processor to it — and connect the node to an audio graph. We should see the output of `console.log` calls in the console:

    const audioContext = new AudioContext()
    await audioContext.audioWorklet.addModule('test-processor.js')
    const testNode = new AudioWorkletNode(audioContext, 'test-processor')
    testNode.connect(audioContext.destination)

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audioworkletglobalscope" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioWorkletGlobalScope' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Web Audio API](Web_Audio_API.html)
-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audioworkletglobalscope/index.html "Folder: en-us/web/api/audioworkletglobalscope (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioWorkletGlobalScope%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudioworkletglobalscope%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioWorkletGlobalScope%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudioworkletglobalscope%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioWorkletGlobalScope%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](AudioWorkletGlobalScope/contributors.txt)

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioWorkletGlobalScope`](AudioWorkletGlobalScope.html)**
3.  Methods
    1.  [`registerProcessor`](AudioWorkletGlobalScope/registerProcessor.html)
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
    11. [`AudioProcessingEvent`](AudioProcessingEvent.html)
    12. [`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)
    13. [`AudioWorklet`](AudioWorklet.html)
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
