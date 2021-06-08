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
3.  <a href="../Web_Audio_API.html" class="breadcrumb-penultimate"><span data-property="name">Web Audio API</span></a>
4.  <a href="Using_AudioWorklet.html" class="breadcrumb-current-page"><span data-property="name">Background audio processing using AudioWorklet</span></a>

Table of contents
-----------------

Table of contents

-   [High level overview](#high_level_overview)
-   [Creating an audio worklet processor](#creating_an_audio_worklet_processor)
-   [Lifetime of an audio worklet processor](#lifetime_of_an_audio_worklet_processor)
-   [Creating an audio processor worklet node](#creating_an_audio_processor_worklet_node)
-   [Supporting audio parameters](#supporting_audio_parameters)
-   [See also](#see_also)

Background audio processing using AudioWorklet
==============================================

When the Web Audio API was first introduced to browsers, it included the ability to use JavaScript code to create custom audio processors that would be invoked to perform real-time audio manipulations. The drawback to `ScriptProcessorNode` was simple: it ran on the main thread, thus blocking everything else going on until it completed execution. This was far less than ideal, especially for something that can be as computationally expensive as audio processing.

Enter [`AudioWorklet`](../AudioWorklet.html). An audio context's audio worklet is a [`Worklet`](../Worklet.html) which runs off the main thread, executing audio processing code added to it by calling the context's [`audioWorklet.addModule()`](../Worklet/addModule.html "audioWorklet.addModule()") method. Calling `addModule()` loads the specified JavaScript file, which should contain the implementation of the audio processor. With the processor registered, you can create a new [`AudioWorkletNode`](../AudioWorkletNode.html) which passes the audio through the processor's code when the node is linked into the chain of audio nodes along with any other audio nodes.

<span class="seoSummary">The process of creating an audio processor using JavaScript, establishing it as an audio worklet processor, and then using that processor within a Web Audio application is the topic of this article.</span>

It's worth noting that because audio processing can often involve substantial computation, your processor may benefit greatly from being built using [WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly), which brings near-native or fully native performance to web apps. Implementing your audio processing algorithm using WebAssembly can make it perform markedly better.

[High level overview](#high_level_overview "Permalink to High level overview")
------------------------------------------------------------------------------

Before we start looking at the use of AudioWorklet on a step-by-step basis, let's start with a brief high-level overview of what's involved.

1.  Create module that defines a audio worklet processor class, based on [`AudioWorkletProcessor`](../AudioWorkletProcessor.html) which takes audio from one or more incoming sources, performs its operation on the data, and outputs the resulting audio data.
2.  Access the audio context's [`AudioWorklet`](../AudioWorklet.html) through its [`audioWorklet`](../BaseAudioContext/audioWorklet.html "audioWorklet") property, and call the audio worklet's [`addModule()`](../Worklet/addModule.html "addModule()") method to install the audio worklet processor module.
3.  As needed, create audio processing nodes by passing the processor's name (which is defined by the module) to the [`AudioWorkletNode()`](../AudioWorkletNode/AudioWorkletNode.html "AudioWorkletNode()") constructor.
4.  Set up any audio parameters the [`AudioWorkletNode`](../AudioWorkletNode.html) needs, or that you wish to configure. These are defined in the audio worklet processor module.
5.  Connect the created `AudioWorkletNode`s into your audio processing pipeline as you would any other node, then use your audio pipeline as usual.

Throughout the remainder of this article, we'll look at these steps in more detail, with examples (including working examples you can try out on your own).

The example code found on this page is derived from <a href="https://glitch.com/~audioworkletnode-sample" class="external">this working example</a> which is available on <a href="https://glitch.me/" class="external">Glitch</a>. The example creates an oscillator node and adds white noise to it using an [`AudioWorkletNode`](../AudioWorkletNode.html) before playing the resulting sound out. Slider controls are available to allow controlling the gain of both the oscillator and the audio worklet's output.

<a href="https://glitch.com/~audioworkletnode-sample" class="external"><strong>Glitch Project Page</strong></a>

<a href="https://glitch.com/edit/#!/audioworkletnode-sample" class="external"><strong>See the Code</strong></a>

<a href="https://audioworkletnode-sample.glitch.me/" class="external"><strong>Try it Live</strong></a>

[Creating an audio worklet processor](#creating_an_audio_worklet_processor "Permalink to Creating an audio worklet processor")
------------------------------------------------------------------------------------------------------------------------------

Fundamentally, an audio worklet processor (which we'll refer to usually as either an "audio processor" or as a "processor" because otherwise this article will be about twice as long) is implemented using a JavaScript module that defines and installs the custom audio processor class.

### [Structure of an audio worklet processor](#structure_of_an_audio_worklet_processor "Permalink to Structure of an audio worklet processor")

An audio worklet processor is a JavaScript module which consists of the following:

-   A JavaScript class which defines the audio processor. This class extends the [`AudioWorkletProcessor`](../AudioWorkletProcessor.html) class.
-   The audio processor class must implement a [`process()`](../AudioWorkletProcessor/process.html "process()") method, which receives incoming audio data and writes back out the data as manipulated by the processor.
-   The module installs the new audio worklet processor class by calling [`registerProcessor()`](../AudioWorkletGlobalScope/registerProcessor.html "registerProcessor()"), specifying a name for the audio processor and the class that defines the processor.

A single audio worklet processor module may define multiple processor classes, registering each of them with individual calls to `registerProcessor()`. As long as each has its own unique name, this will work just fine. It's also more efficient than loading multiple modules from over the network or even the user's local disk.

### [Basic code framework](#basic_code_framework "Permalink to Basic code framework")

The barest framework of an audio processor class looks like this:

    class MyAudioProcessor extends AudioWorkletProcessor {
      constructor() {
        super();
      }

      process(inputList, outputList, parameters) {
        /* using the inputs (or not, as needed), write the output
           into each of the outputs */

        return true;
      }
    };

    registerProcessor("my-audio-processor", MyAudioProcessor);

After the implementation of the processor comes a call to the global function [`registerProcessor()`](../AudioWorkletGlobalScope/registerProcessor.html "registerProcessor()"), which is only available within the scope of the audio context's [`AudioWorklet`](../AudioWorklet.html), which is the invoker of the processor script as a result of your call to [`audioWorklet.addModule()`](../Worklet/addModule.html "audioWorklet.addModule()"). This call to `registerProcessor()` registers your class as the basis for any [`AudioWorkletProcessor`](../AudioWorkletProcessor.html)s created when [`AudioWorkletNode`](../AudioWorkletNode.html)s are set up.

This is the barest framework and actually has no effect until code is added into `process()` to do something with those inputs and outputs. Which brings us to talking about those inputs and outputs.

### [The input and output lists](#the_input_and_output_lists "Permalink to The input and output lists")

The lists of inputs and outputs can be a little confusing at first, even though they're actually very simple once you realize what's going on.

Let's start at the inside and work our way out. Fundamentally, the audio for a single audio channel (such as the left speaker or the subwoofer, for example) is represented as a `Float32Array` whose values are the individual audio samples. By specification, each block of audio your `process()` function receives contains 128 frames (that is, 128 samples for each channel), but it is planned that *this value will change in the future*, and may in fact vary depending on circumstances, so you should *always* check the array's `length` rather than assuming a particular size. It is, however, guaranteed that the inputs and outputs will have the same block length.

Each input can have a number of channels. A mono input has a single channel; stereo input has two channels. Surround sound might have six or more channels. So each input is, in turn, an array of channels. That is, an array of `Float32Array` objects.

Then, there can be multiple inputs, so the `inputList` is an array of arrays of `Float32Array` objects. Each input may have a different number of channels, and each channel has its own array of samples.

Thus, given the input list `inputList`:

    const numberOfInputs = inputList.length;
    const firstInput = inputList[0];

    const firstInputChannelCount = firstInput.length;
    const firstInputFirstChannel = firstInput[0]; // (or inputList[0][0])

    const firstChannelByteCount = firstInputFirstChannel.length;
    const firstByteOfFirstChannel = firstInputFirstChannel[0]; // (or inputList[0][0][0])

The output list is structured in exactly the same way; it's an array of outputs, each of which is an array of channels, each of which is an array of `Float32Array` objects, which contain the samples for that channel.

How you use the inputs and how you generate the outputs depends very much on your processor. If your processor is just a generator, it can ignore the inputs and just replace the contents of the outputs with the generated data. Or you can process each input independently, applying an algorithm to the incoming data on each channel of each input and writing the results into the corresponding outputs' channels (keeping in mind that the number of inputs and outputs may differ, and the channel counts on those inputs and outputs may also differ). Or you can take all the inputs and perform mixing or other computations that result in a single output being filled with data (or all the outputs being filled with the same data).

It's entirely up to you. This is a very powerful tool in your audio programming toolkit.

### [Processing multiple inputs](#processing_multiple_inputs "Permalink to Processing multiple inputs")

Let's take a look at an implementation of `process()` that can process multiple inputs, with each input being used to generate the corresponding output. Any excess inputs are ignored.

    process(inputList, outputList, parameters) {
      const sourceLimit = Math.min(inputList.length, outputList.length);

      for (let inputNum = 0; inputNum < sourceLimit; inputNum++) {
        let input = inputList[inputNum];
        let output = outputList[inputNum];
        let channelCount = Math.min(input.length, output.length);

        for (let channelNum = 0; channelNum < channelCount; channelNum++) {
          let sampleCount = input[channelNum].length;

          for (let i = 0; i < sampleCount; i++) {
            let sample = input[channelNum][i];

            /* Manipulate the sample */

            output[channelNum][i] = sample;
          }
        }
      };

      return true;
    }

Note that when determining the number of sources to process and send through to the corresponding outputs, we use `Math.min()` to ensure that we only process as many channels as we have room for in the output list. The same check is performed when determining how many channels to process in the current input; we only process as many as there are room for in the destination output. This avoids errors due to overrunning these arrays.

### [Mixing inputs](#mixing_inputs "Permalink to Mixing inputs")

Many nodes perform **mixing** operations, where the inputs are combined in some way into a single output. This is demonstrated in the following example.

    process(inputList, outputList, parameters) {
      const sourceLimit = Math.min(inputList.length, outputList.length);
       for (let inputNum = 0; inputNum < sourceLimit; inputNum++) {
         let input = inputList[inputNum];
         let output = outputList[0];
         let channelCount = Math.min(input.length, output.length);

         for (let channelNum = 0; channelNum < channelCount; channelNum++) {
           let sampleCount = input[channelNum].length;

           for (let i = 0; i < sampleCount; i++) {
             let sample = output[channelNum][i] + input[channelNum][i];

             if (sample > 1.0) {
               sample = 1.0;
             } else if (sample < -1.0) {
               sample = -1.0;
             }

             output[channelNum][i] = sample;
           }
         }
       };

      return true;
    }

This is similar code to the previous sample in many ways, but only the first output—`outputList[0]`—is altered. Each sample is added to the corresponding sample in the output buffer, with a simple code fragment in place to prevent the samples from exceeding the legal range of -1.0 to 1.0 by capping the values; there are other ways to avoid clipping that are perhaps less prone to distortion, but this is a simple example that's better than nothing.

[Lifetime of an audio worklet processor](#lifetime_of_an_audio_worklet_processor "Permalink to Lifetime of an audio worklet processor")
---------------------------------------------------------------------------------------------------------------------------------------

The only means by which you can influence the lifespan of your audio worklet processor is through the value returned by `process()`, which should be a Boolean value indicating whether or not to override the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)'s decision-making as to whether or not your node is still in use.

In general, the lifetime policy of any audio node is simple: if the node is still considered to be actively processing audio, it will continue to be used. In the case of an [`AudioWorkletNode`](../AudioWorkletNode.html), the node is considered to be active if its `process()` function returns `true` *and* the node is either generating content as a source for audio data, or is receiving data from one or more inputs.

Specifying a value of `true` as the result from your `process()` function in essence tells the Web Audio API that your processor needs to keep being called even if the API doesn't think there's anything left for you to do. In other words, `true` overrides the API's logic and gives you control over your processor's lifetime policy, keeping the processor's owning [`AudioWorkletNode`](../AudioWorkletNode.html) running even when it would otherwise decide to shut down the node.

Returning `false` from the `process()` method tells the API that it should follow its normal logic and shut down your processor node if it deems it appropriate to do so. If the API determines that your node is no longer needed, `process()` will not be called again.

**Note:** At this time, unfortunately, Chrome does not implement this algorithm in a manner that matches the current standard. Instead, it keeps the node alive if you return `true` and shuts it down if you return `false`. Thus for compatibility reasons you must always return `true` from `process()`, at least on Chrome. However, once <a href="https://bugs.chromium.org/p/chromium/issues/detail?id=921354" class="external">this Chrome issue</a> is fixed, you will want to change this behavior if possible as it may have a slight negative impact on performance.

[Creating an audio processor worklet node](#creating_an_audio_processor_worklet_node "Permalink to Creating an audio processor worklet node")
---------------------------------------------------------------------------------------------------------------------------------------------

To create an audio node that pumps blocks of audio data through an [`AudioWorkletProcessor`](../AudioWorkletProcessor.html), you need to follow these simple steps:

1.  Load and install the audio processor module
2.  Create an [`AudioWorkletNode`](../AudioWorkletNode.html), specifying the audio processor module to use by its name
3.  Connect inputs to the `AudioWorkletNode` and its outputs to appropriate destinations (either other nodes or to the [`AudioContext`](../AudioContext.html) object's [`destination`](../BaseAudioContext/destination.html "destination") property.

To use an audio worklet processor, you can use code similar to the following:

    let audioContext = null;

    async function createMyAudioProcessor() {
      if (!audioContext) {
        try {
          audioContext = new AudioContext();
          await audioContext.resume();
          await audioContext.audioWorklet.addModule("module-url/module.js");
        } catch(e) {
          return null;
        }
      }

      return new AudioWorkletNode(audioContext, "processor-name");
    }

This `createMyAudioProcessor()` function creates and returns a new instance of [`AudioWorkletNode`](../AudioWorkletNode.html) configured to use your audio processor. It also handles creating the audio context if it hasn't already been done.

In order to ensure the context is usable, this starts by creating the context if it's not already available, then adds the module containing the processor to the worklet. Once that's done, it instantiates and returns a new `AudioWorkletNode`. Once you have that in hand, you connect it to other nodes and otherwise use it just like any other node.

You can then create a new audio processor node by doing this:

    let newProcessorNode = createMyAudioProcessor();

If the returned value, `newProcessorNode`, is non-`null`, we have a valid audio context with its hiss processor node in place and ready to use.

[Supporting audio parameters](#supporting_audio_parameters "Permalink to Supporting audio parameters")
------------------------------------------------------------------------------------------------------

Just like any other Web Audio node, [`AudioWorkletNode`](../AudioWorkletNode.html) supports parameters, which are shared with the [`AudioWorkletProcessor`](../AudioWorkletProcessor.html) that does the actual work.

### [Adding parameter support to the processor](#adding_parameter_support_to_the_processor "Permalink to Adding parameter support to the processor")

To add parameters to an [`AudioWorkletNode`](../AudioWorkletNode.html), you need to define them within your [`AudioWorkletProcessor`](../AudioWorkletProcessor.html)-based processor class in your module. This is done by adding the static getter [`parameterDescriptors`](../AudioWorkletProcessor/parameterDescriptors.html "parameterDescriptors") to your class. This function should return an array of [`AudioParam`](../AudioParam.html) objects, one for each parameter supported by the processor.

In the following implementation of `parameterDescriptors()`, the returned array has two `AudioParam` objects. The first defines `gain` as a value between 0 and 1, with a default value of 0.5. The second parameter is named `frequency` and defaults to 440.0, with a range from 27.5 to 4186.009, inclusively.

    static get parameterDescriptors() {
      return [
       {
          name: "gain",
          defaultValue: 0.5,
          minValue: 0,
          maxValue: 1
        },
        {
          name: "frequency",
          defaultValue: 440.0;
          minValue: 27.5,
          maxValue: 4186.009
        }
      ];
    }

Accessing your processor node's parameters is as simple as looking them up in the `parameters` object passed into your implementation of [`process()`](../AudioWorkletProcessor/process.html "process()"). Within the `parameters` object are arrays, one for each of your parameters, and sharing the same names as your parameters.

A-rate parameters  
For a-rate parameters—parameters whose values automatically change over time—the parameter's entry in the `parameters` object is an array of [`AudioParam`](../AudioParam.html) objects, one for each frame in the block being processed. These values are to be applied to the corresponding frames.

K-rate parameters  
K-rate parameters, on the other hand, can only change once per block, so the parameter's array has only a single entry. Use that value for every frame in the block.

In the code below, we see a `process()` function that handles a `gain` parameter which can be used as either an a-rate or k-rate parameter. Our node only supports one input, so it just takes the first input in the list, applies the gain to it, and writes the resulting data to the first output's buffer.

    process(inputList, outputList, parameters) {
      const input = inputList[0];
      const output = outputList[0];
      const gain = parameters.gain;

      for (let channelNum = 0; channelNum < input.length; channel++) {
        const inputChannel = input[channel];
        const outputChannel = output[channel];

        // If gain.length is 1, it's a k-rate parameter, so apply
        // the first entry to every frame. Otherwise, apply each
        // entry to the corresponding frame.

        if (gain.length === 1) {
          for (let i = 0; i < inputChannel.length; i++) {
            outputChannel[i] = inputChannel[i] * gain[0];
          }
        } else {
          for (let i = 0; i < inputChannel.length; i++) {
            outputChannel[i] = inputChannel[i] * gain[i];
          }
        }
      }

      return true;
    }

Here, if `gain.length` indicates that there's only a single value in the `gain` parameter's array of values, the first entry in the array is applied to every frame in the block. Otherwise, for each frame in the block, the corresponding entry in `gain[]` is applied.

### [Accessing parameters from the main thread script](#accessing_parameters_from_the_main_thread_script "Permalink to Accessing parameters from the main thread script")

Your main thread script can access the parameters just like it can any other node. To do so, first you need to get a reference to the parameter by calling the [`AudioWorkletNode`](../AudioWorkletNode.html)'s [`parameters`](../AudioWorkletNode/parameters.html "parameters") property's <span class="page-not-created">`get()`</span> method:

    let gainParam = myAudioWorkletNode.parameters.get("gain");

The value returned and stored in `gainParam` is the [`AudioParam`](../AudioParam.html) used to store the `gain` parameter. You can then change its value effective at a given time using the [`AudioParam`](../AudioParam.html) method [`setValueAtTime()`](../AudioParam/setValueAtTime.html "setValueAtTime()").

Here, for example, we set the value to `newValue`, effective immediately.

    gainParam.setValueAtTime(newValue, audioContext.currentTime);

You can similarly use any of the other methods in the [`AudioParam`](../AudioParam.html) interface to apply changes over time, to cancel scheduled changes, and so forth.

Reading the value of a parameter is as simple as looking at its [`value`](../AudioParam/value.html "value") property:

    let currentGain = gainParam.value;

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Web Audio API](../Web_Audio_API.html)
-   <a href="https://developers.google.com/web/updates/2017/12/audio-worklet" class="external">Enter Audio Worklet</a> (Google Developers blog)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/using_audioworklet/index.html "Folder: en-us/web/api/web_audio_api/using_audioworklet (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FUsing_AudioWorklet%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%2Fusing_audioworklet%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FUsing_AudioWorklet%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Fusing_audioworklet%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F2c6f017de416f5817a109191417d549c60e90055%0A*+Document+last+modified%3A+2021-04-14T07%3A08%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Background+audio+processing+using+AudioWorklet%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Apr 14, 2021, [by MDN contributors](Using_AudioWorklet/contributors.txt)

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  **[`Web_Audio_API`](../Web_Audio_API.html)**
3.  Related pages for Web Audio API
    1.  [`AnalyserNode`](../AnalyserNode.html)
    2.  [`AudioBuffer`](../AudioBuffer.html)
    3.  [`AudioBufferSourceNode`](../AudioBufferSourceNode.html)
    4.  [`AudioContext`](../AudioContext.html)
    5.  [`AudioContextOptions`](../AudioContextOptions.html)
    6.  [`AudioDestinationNode`](../AudioDestinationNode.html)
    7.  [`AudioListener`](../AudioListener.html)
    8.  [`AudioNode`](../AudioNode.html)
    9.  [`AudioNodeOptions`](../AudioNodeOptions.html)
    10. [`AudioParam`](../AudioParam.html)
    11. [`AudioProcessingEvent`](../AudioProcessingEvent.html)
    12. [`AudioScheduledSourceNode`](../AudioScheduledSourceNode.html)
    13. [`AudioWorklet`](../AudioWorklet.html)
    14. [`AudioWorkletGlobalScope`](../AudioWorkletGlobalScope.html)
    15. [`AudioWorkletNode`](../AudioWorkletNode.html)
    16. [`AudioWorkletProcessor`](../AudioWorkletProcessor.html)
    17. [`BaseAudioContext`](../BaseAudioContext.html)
    18. [`BiquadFilterNode`](../BiquadFilterNode.html)
    19. [`ChannelMergerNode`](../ChannelMergerNode.html)
    20. [`ChannelSplitterNode`](../ChannelSplitterNode.html)
    21. [`ConstantSourceNode`](../ConstantSourceNode.html)
    22. [`ConvolverNode`](../ConvolverNode.html)
    23. [`DelayNode`](../DelayNode.html)
    24. [`DynamicsCompressorNode`](../DynamicsCompressorNode.html)
    25. [`GainNode`](../GainNode.html)
    26. [`IIRFilterNode`](../IIRFilterNode.html)
    27. [`MediaElementAudioSourceNode`](../MediaElementAudioSourceNode.html)
    28. [`MediaStreamAudioDestinationNode`](../MediaStreamAudioDestinationNode.html)
    29. [`MediaStreamAudioSourceNode`](../MediaStreamAudioSourceNode.html)
    30. [`OfflineAudioCompletionEvent`](../OfflineAudioCompletionEvent.html)
    31. [`OfflineAudioContext`](../OfflineAudioContext.html)
    32. [`OscillatorNode`](../OscillatorNode.html)
    33. [`PannerNode`](../PannerNode.html)
    34. [`PeriodicWave`](../PeriodicWave.html)
    35. [`StereoPannerNode`](../StereoPannerNode.html)
    36. [`WaveShaperNode`](../WaveShaperNode.html)

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
