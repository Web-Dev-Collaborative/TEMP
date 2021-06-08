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
3.  <a href="AudioWorkletProcessor.html" class="breadcrumb-current-page"><span data-property="name">AudioWorkletProcessor</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Usage notes](#usage_notes)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioWorkletProcessor
=====================

The **`AudioWorkletProcessor`** interface of the [Web Audio API](Web_Audio_API.html) represents an audio processing code behind a custom [`AudioWorkletNode`](AudioWorkletNode.html). It lives in the [`AudioWorkletGlobalScope`](AudioWorkletGlobalScope.html) and runs on the Web Audio rendering thread. In turn, an [`AudioWorkletNode`](AudioWorkletNode.html) based on it runs on the main thread.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

The `AudioWorkletProcessor` and classes that derive from it cannot be instantiated directly from a user-supplied code. Instead, they are created only internally by the creation of an associated [`AudioWorkletNode`](AudioWorkletNode.html)s. The constructor of the deriving class is getting called with an options object, so you can perform a custom initialization procedures — see constructor page for details.

[`AudioWorkletProcessor()`](AudioWorkletProcessor/AudioWorkletProcessor.html "AudioWorkletProcessor()")  
Creates a new instance of an `AudioWorkletProcessor` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`port`](AudioWorkletProcessor/port.html "port") <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`MessagePort`](MessagePort.html) used for bidirectional communication between the processor and the [`AudioWorkletNode`](AudioWorkletNode.html) which it belongs to. The other end is available under the [`port`](AudioWorkletNode/port.html "port") property of the node.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*The `AudioWorkletProcessor` interface does not define any methods of its own. However, you must provide a [`process()`](AudioWorkletProcessor/process.html "process()") method, which is called in order to process the audio stream.*

[Events](#events "Permalink to Events")
---------------------------------------

*The `AudioWorkletProcessor` interface doesn't respond to any events.*

[Usage notes](#usage_notes "Permalink to Usage notes")
------------------------------------------------------

### [Deriving classes](#deriving_classes "Permalink to Deriving classes")

To define custom audio processing code you have to derive a class from the `AudioWorkletProcessor` interface. Although not defined on the interface, the deriving class must have the [`process`](AudioWorkletProcessor/process.html "process") method. This method gets called for each block of 128 sample-frames and takes input and output arrays and calculated values of custom [`AudioParam`](AudioParam.html)s (if they are defined) as parameters. You can use inputs and audio parameter values to fill the outputs array, which by default holds silence.

Optionally, if you want custom [`AudioParam`](AudioParam.html)s on your node, you can supply a [`parameterDescriptors`](AudioWorkletProcessor/parameterDescriptors.html "parameterDescriptors") property as a *static getter* on the processor. The array of [`AudioParamDescriptor`](AudioParamDescriptor.html)-based objects returned is used internally to create the [`AudioParam`](AudioParam.html)s during the instantiation of the `AudioWorkletNode`.

The resulting `AudioParam`s reside in the [`parameters`](AudioWorkletNode/parameters.html "parameters") property of the node and can be automated using standard methods such as `linearRampToValueAtTime`. Their calculated values will be passed into the [`process()`](AudioWorkletProcessor/process.html "process()") method of the processor for you to shape the node output accordingly.

### [Processing audio](#processing_audio "Permalink to Processing audio")

An example algorithm of creating a custom audio processing mechanism is:

1.  Create a separate file;
2.  In the file:
    1.  Extend the `AudioWorkletProcessor` class (see ["Deriving classes" section](#deriving_classes)) and supply your own [`process()`](AudioWorkletProcessor/process.html "process()") method in it;
    2.  Register the processor using [`AudioWorkletGlobalScope.registerProcessor()`](AudioWorkletGlobalScope/registerProcessor.html) method;
3.  Load the file using [`addModule()`](Worklet/addModule.html "addModule()") method on your audio context's [`audioWorklet`](BaseAudioContext/audioWorklet.html "audioWorklet") property;
4.  Create an [`AudioWorkletNode`](AudioWorkletNode.html) based on the processor. The processor will be instantiated internally by the `AudioWorkletNode` constructor.
5.  Connect the node to the other nodes.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In the example below we create a custom [`AudioWorkletNode`](AudioWorkletNode.html) that outputs white noise.

First, we need to define a custom `AudioWorkletProcessor`, which will output white noise, and register it. Note that this should be done in a separate file.

    // white-noise-processor.js
    class WhiteNoiseProcessor extends AudioWorkletProcessor {
      process (inputs, outputs, parameters) {
        const output = outputs[0]
        output.forEach(channel => {
          for (let i = 0; i < channel.length; i++) {
            channel[i] = Math.random() * 2 - 1
          }
        })
        return true
      }
    }

    registerProcessor('white-noise-processor', WhiteNoiseProcessor)

Next, in our main script file we'll load the processor, create an instance of [`AudioWorkletNode`](AudioWorkletNode.html), passing it the name of the processor, then connect the node to an audio graph.

    const audioContext = new AudioContext()
    await audioContext.audioWorklet.addModule('white-noise-processor.js')
    const whiteNoiseNode = new AudioWorkletNode(audioContext, 'white-noise-processor')
    whiteNoiseNode.connect(audioContext.destination)

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audioworkletprocessor" class="external">Web Audio API<br />
<span class="small">The definition of 'AudioWorkletProcessor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Web Audio API](Web_Audio_API.html)
-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audioworkletprocessor/index.html "Folder: en-us/web/api/audioworkletprocessor (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioWorkletProcessor%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudioworkletprocessor%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioWorkletProcessor%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudioworkletprocessor%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioWorkletProcessor%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](AudioWorkletProcessor/contributors.txt)

Change your languageSelect your preferred language English (US)中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`AudioWorkletProcessor`](AudioWorkletProcessor.html)**
3.  Constructor
    1.  [`AudioWorkletProcessor()`](AudioWorkletProcessor/AudioWorkletProcessor.html)
4.  Properties
    1.  [`parameterDescriptors (static getter)`](AudioWorkletProcessor/parameterDescriptors.html)
    2.  [`port`](AudioWorkletProcessor/port.html)
5.  Methods
    1.  [`process`](AudioWorkletProcessor/process.html)
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
