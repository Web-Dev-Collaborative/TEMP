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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/process" class="breadcrumb-current-page"><span data-property="name">AudioWorkletProcessor.process</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AudioWorkletProcessor.process
=============================

<span class="seoSummary">The **`process()`** method of an [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor)-derived class implements the audio processing algorithm for the audio processor worklet.</span> Although the method is not a part of the [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor) interface, any implementation of `AudioWorkletProcessor` must provide a `process()` method.

The method is called synchronously from the audio rendering thread, once for each block of audio (also known as a rendering quantum) being directed through the processor's corresponding [`AudioWorkletNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode). In other words, every time a new block of audio is ready for your processor to manipulate, your `process()` function is invoked to do so.

**Important:** Currently, audio data blocks are always 128 frames long—that is, they contain 128 32-bit floating-point samples for each of the inputs' channels. However, plans are already in place to revise the specification to allow the size of the audio blocks to be changed depending on circumstances (for example, if the audio hardware or CPU utilization is more efficient with larger block sizes). Therefore, you *must always check the size of the sample array* rather than assuming a particular size.

This size may even be allowed to change over time, so you mustn't look at just the first block and assume the sample buffers will always be the same size.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var isActivelyProcessing = audioWorkletProcessor.process(inputs, outputs, parameters);

### [Parameters](#parameters "Permalink to Parameters")

`inputs`  
An array of *inputs* connected to the node, each item of which is, in turn, an array of *channels*. Each *channel* is a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing 128 samples. For example, `inputs[n][m][i]` will access *n*-th input, *m*-th channel of that input, and *i*-th sample of that channel.

Each sample value is in range of `[-1 .. 1]`.

The number of *inputs* and thus the length of that array is fixed at the construction of the node (see [`AudioWorkletNodeOptions`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNodeOptions)). If there is no active node connected to the *n*-th input of the node, `inputs[n]` will be an empty array (zero input channels available).

The number of *channels* in each input may vary, depending on [`channelCount`](https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/channelCount "channelCount") and [`channelCountMode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/channelCountMode "channelCountMode") properties.

`outputs`  
An array of *outputs* that is similar to the `inputs` parameter in structure. It is intended to be filled during the execution of the `process()` method. Each of the output channels is filled with zeros by default — the processor will output silence unless the output arrays are modified.

`parameters`  
An object containing string keys and [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) values. For each custom [`AudioParam`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParam) defined using the [`parameterDescriptors`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/parameterDescriptors "parameterDescriptors") getter, the key in the object is a `name` of that [`AudioParam`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParam), and the value is a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array). The values of the array are calculated by taking scheduled automation events into consideration.

If the automation rate of the parameter is `"a-rate"`, the array will contain 128 values — one for each frame in the current audio block. If there's no automation happening during the time represented by the current block, the array may contain a single value that is constant for the entire block, instead of 128 identical values.

If the automation rate is `"k-rate"`, the array will contain a single value, which is to be used for each of 128 frames.

### [Return value](#return_value "Permalink to Return value")

A Boolean value indicating whether or not to force the [`AudioWorkletNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode) to remain active even if the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) internal logic would otherwise decide that it's safe to shut down the node.

The returned value lets your processor have influence over the lifetime policy of the [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor) and the node that owns it. If the combination of the return value and the state of the node causes the browser to decide to stop the node, `process()` will not be called again.

Returning `true` forces the Web Audio API to keep the node alive, while returning `false` allows the browser to terminate the node if it is neither generating new audio data nor receiving data through its inputs that it is processing.

The 3 most common types of audio node are:

1.  A source of output. An [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor) implementing such a node should return `true` from the `process` method as long as it produces an output. The method should return `false` as soon as it's known that it will no longer produce an output. For example, take the [`AudioBufferSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode) — the processor behind such a node should return `true` from the `process` method while the buffer is playing, and start returning `false` when the buffer playing has ended (there's no way to call `play` on the same [`AudioBufferSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode) again).
2.  A node that transforms its input. A processor implementing such a node should return `false` from the `process` method to allow the presence of active input nodes and references to the node to determine whether it can be garbage-collected. An example of a node with this behavior is the [`GainNode`](https://developer.mozilla.org/en-US/docs/Web/API/GainNode). As soon as there are no inputs connected and references retained, gain can no longer be applied to anything, so it can be safely garbage-collected.
3.  A node that transforms its input, but has a so-called *tail-time* — this means that it will produce an output for some time even after its inputs are disconnected or are inactive (producing zero-channels). A processor implementing such a node should return `true` from the `process` method for the period of the *tail-time*, beginning as soon as inputs are found that contain zero-channels. An example of such a node is the [`DelayNode`](https://developer.mozilla.org/en-US/docs/Web/API/DelayNode) — it has a *tail-time* equal to its [`delayTime`](https://developer.mozilla.org/en-US/docs/Web/API/DelayNode/delayTime "delayTime") property.

**Note**: An absence of the `return` statement means that the method returns `undefined`, and as this is a falsy value, it is like returning `false`. Omitting an explicit `return` statement may cause hard-to-detect problems for your nodes.

### [Exceptions](#exceptions "Permalink to Exceptions")

As the `process()` method is implemented by the user, it can throw anything. If an uncaught error is thrown, the node will emit an [`onprocessorerror`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/onprocessorerror "onprocessorerror") event and will output silence for the rest of its lifetime.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In this example we create an `AudioWorkletProcessor` that outputs white noise to its first output. The gain can be controlled by the `customGain` parameter.

    class WhiteNoiseProcessor extends AudioWorkletProcessor {
      process (inputs, outputs, parameters) {
        // take the first output
        const output = outputs[0]
        // fill each channel with random values multiplied by gain
        output.forEach(channel => {
          for (let i = 0; i < channel.length; i++) {
            // generate random value for each sample
            // Math.random range is [0; 1); we need [-1; 1]
            // this won't include exact 1 but is fine for now for simplicity
            channel[i] = (Math.random() * 2 - 1) *
              // the array can contain 1 or 128 values
              // depending on if the automation is present
              // and if the automation rate is k-rate or a-rate
              (parameters['customGain'].length > 1
                ? parameters['customGain'][i]
                : parameters['customGain'][0])
          }
        })
        // as this is a source node which generates its own output,
        // we return true so it won't accidentally get garbage-collected
        // if we don't have any references to it in the main thread
        return true
      }
      // define the customGain parameter used in process method
      static get parameterDescriptors () {
        return [{
          name: 'customGain',
          defaultValue: 1,
          minValue: 0,
          maxValue: 1,
          automationRate: 'a-rate'
        }]
      }
    }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioworkletprocessor-process" class="external">Web Audio API<br />
<span class="small">The definition of 'process()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

No compatibility data found for `api.AudioWorkletProcessor.process`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/audioworkletprocessor/process/index.html "Folder: en-us/web/api/audioworkletprocessor/process (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioWorkletProcessor%2Fprocess%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Faudioworkletprocessor%2Fprocess%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAudioWorkletProcessor%2Fprocess%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Faudioworkletprocessor%2Fprocess%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AudioWorkletProcessor.process%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/process/contributors.txt)

#### Related Topics

1.  **[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)**
2.  **[`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor)**
3.  Constructor
    1.  [`AudioWorkletProcessor()`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/AudioWorkletProcessor)
4.  Properties
    1.  [`parameterDescriptors (static getter)`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/parameterDescriptors)
    2.  [`port`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/port)
5.  Methods
    1.  *`process`*
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
