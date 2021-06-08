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
3.  <a href="Web_Audio_API.html" class="breadcrumb-current-page"><span data-property="name">Web Audio API</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Web audio concepts and usage](#web_audio_concepts_and_usage)
-   [Web Audio API target audience](#web_audio_api_target_audience)
-   [Web Audio API interfaces](#web_audio_api_interfaces)
-   [Guides and tutorials](#guides_and_tutorials)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

Web Audio API
=============

The Web Audio API provides a powerful and versatile system for controlling audio on the Web, allowing developers to choose audio sources, add effects to audio, create audio visualizations, apply spatial effects (such as panning) and much more.

[Web audio concepts and usage](#web_audio_concepts_and_usage "Permalink to Web audio concepts and usage")
---------------------------------------------------------------------------------------------------------

The Web Audio API involves handling audio operations inside an **audio context**, and has been designed to allow **modular routing**. Basic audio operations are performed with **audio nodes**, which are linked together to form an **audio routing graph**. Several sources — with different types of channel layout — are supported even within a single context. This modular design provides the flexibility to create complex audio functions with dynamic effects.

Audio nodes are linked into chains and simple webs by their inputs and outputs. They typically start with one or more sources. Sources provide arrays of sound intensities (samples) at very small timeslices, often tens of thousands of them per second. These could be either computed mathematically (such as [`OscillatorNode`](OscillatorNode.html)), or they can be recordings from sound/video files (like [`AudioBufferSourceNode`](AudioBufferSourceNode.html) and [`MediaElementAudioSourceNode`](MediaElementAudioSourceNode.html)) and audio streams ([`MediaStreamAudioSourceNode`](MediaStreamAudioSourceNode.html)). In fact, sound files are just recordings of sound intensities themselves, which come in from microphones or electric instruments, and get mixed down into a single, complicated wave.

Outputs of these nodes could be linked to inputs of others, which mix or modify these streams of sound samples into different streams. A common modification is multiplying the samples by a value to make them louder or quieter (as is the case with [`GainNode`](GainNode.html)). Once the sound has been sufficiently processed for the intended effect, it can be linked to the input of a destination ([`BaseAudioContext.destination`](BaseAudioContext/destination.html)), which sends the sound to the speakers or headphones. This last connection is only necessary if the user is supposed to hear the audio.

A simple, typical workflow for web audio would look something like this:

1.  Create audio context
2.  Inside the context, create sources — such as `<audio>`, oscillator, stream
3.  Create effects nodes, such as reverb, biquad filter, panner, compressor
4.  Choose final destination of audio, for example your system speakers
5.  Connect the sources up to the effects, and the effects to the destination.

<img src="Web_Audio_API/audio-context_.png" alt="A simple box diagram with an outer box labeled Audio context, and three inner boxes labeled Sources, Effects and Destination. The three inner boxes have arrow between them pointing from left to right, indicating the flow of audio information." width="1200" height="400" />

Timing is controlled with high precision and low latency, allowing developers to write code that responds accurately to events and is able to target specific samples, even at a high sample rate. So applications such as drum machines and sequencers are well within reach.

The Web Audio API also allows us to control how audio is *spatialized*. Using a system based on a *source-listener model*, it allows control of the *panning model* and deals with *distance-induced attenuation* induced by a moving source (or moving listener).

You can read about the theory of the Web Audio API in a lot more detail in our article [Basic concepts behind Web Audio API](Web_Audio_API/Basic_concepts_behind_Web_Audio_API.html).

[Web Audio API target audience](#web_audio_api_target_audience "Permalink to Web Audio API target audience")
------------------------------------------------------------------------------------------------------------

The Web Audio API can seem intimidating to those that aren't familiar with audio or music terms, and as it incorporates a great deal of functionality it can prove difficult to get started if you are a developer.

It can be used to incorporate audio into your website or application, by <a href="https://www.futurelibrary.no/" class="external">providing atmosphere like futurelibrary.no</a>, or <a href="https://css-tricks.com/form-validation-web-audio/" class="external">auditory feedback on forms</a>. However, it can also be used to create *advanced* interactive instruments. With that in mind, it is suitable for both developers and musicians alike.

We have a [simple introductory tutorial](Web_Audio_API/Using_Web_Audio_API.html) for those that are familiar with programming but need a good introduction to some of the terms and structure of the API.

There's also a [Basic Concepts Behind Web Audio API](Web_Audio_API/Basic_concepts_behind_Web_Audio_API.html) article, to help you understand the way digital audio works, specifically in the realm of the API. This also includes a good introduction to some of the concepts the API is built upon.

Learning coding is like playing cards — you learn the rules, then you play, then you go back and learn the rules again, then you play again. So if some of the theory doesn't quite fit after the first tutorial and article, there's an [advanced tutorial](Web_Audio_API/Advanced_techniques.html) which extends the first one to help you practice what you've learnt, and apply some more advanced techniques to build up a step sequencer.

We also have other tutorials and comprehensive reference material available that covers all features of the API. See the sidebar on this page for more.

If you are more familiar with the musical side of things, are familiar with music theory concepts, want to start building instruments, then you can go ahead and start building things with the advance tutorial and others as a guide (the above linked tutorial covers scheduling notes, creating bespoke oscillators and envelopes, as well as an LFO among other things.)

If you aren't familiar with the programming basics, you might want to consult some beginner's JavaScript tutorials first and then come back here — see our [Beginner's JavaScript learning module](https://developer.mozilla.org/en-US/docs/Learn/JavaScript) for a great place to begin.

[Web Audio API interfaces](#web_audio_api_interfaces "Permalink to Web Audio API interfaces")
---------------------------------------------------------------------------------------------

The Web Audio API has a number of interfaces and associated events, which we have split up into nine categories of functionality.

### [General audio graph definition](#general_audio_graph_definition "Permalink to General audio graph definition")

General containers and definitions that shape audio graphs in Web Audio API usage.

[`AudioContext`](AudioContext.html)  
The **`AudioContext`** interface represents an audio-processing graph built from audio modules linked together, each represented by an [`AudioNode`](AudioNode.html). An audio context controls the creation of the nodes it contains and the execution of the audio processing, or decoding. You need to create an `AudioContext` before you do anything else, as everything happens inside a context.

[`AudioContextOptions`](AudioContextOptions.html)  
The `AudioContextOptions` dictionary is used to provide options when instantiating a new `AudioContext`.

[`AudioNode`](AudioNode.html)  
The **`AudioNode`** interface represents an audio-processing module like an *audio source* (e.g. an HTML [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element), *audio destination*, *intermediate processing module* (e.g. a filter like [`BiquadFilterNode`](BiquadFilterNode.html), or *volume control* like [`GainNode`](GainNode.html)).

[`AudioParam`](AudioParam.html)  
The **`AudioParam`** interface represents an audio-related parameter, like one of an [`AudioNode`](AudioNode.html). It can be set to a specific value or a change in value, and can be scheduled to happen at a specific time and following a specific pattern.

[`AudioParamMap`](AudioParamMap.html)  
Provides a maplike interface to a group of [`AudioParam`](AudioParam.html) interfaces, which means it provides the methods `forEach()`, `get()`, `has()`, `keys()`, and `values()`, as well as a `size` property.

[`BaseAudioContext`](BaseAudioContext.html)  
The **`BaseAudioContext`** interface acts as a base definition for online and offline audio-processing graphs, as represented by [`AudioContext`](AudioContext.html) and [`OfflineAudioContext`](OfflineAudioContext.html) respectively. You wouldn't use `BaseAudioContext` directly — you'd use its features via one of these two inheriting interfaces.

The `ended` event  
The `ended` event is fired when playback has stopped because the end of the media was reached.

### [Defining audio sources](#defining_audio_sources "Permalink to Defining audio sources")

Interfaces that define audio sources for use in the Web Audio API.

[`AudioScheduledSourceNode`](AudioScheduledSourceNode.html)  
The **`AudioScheduledSourceNode`** is a parent interface for several types of audio source node interfaces. It is an [`AudioNode`](AudioNode.html).

[`OscillatorNode`](OscillatorNode.html)  
The **`OscillatorNode` **interface represents a periodic waveform, such as a sine or triangle wave. It is an [`AudioNode`](AudioNode.html) audio-processing module that causes a given *frequency* of wave to be created.

[`AudioBuffer`](AudioBuffer.html)  
The **`AudioBuffer`** interface represents a short audio asset residing in memory, created from an audio file using the [`BaseAudioContext.decodeAudioData`](BaseAudioContext/decodeAudioData.html) method, or created with raw data using [`BaseAudioContext.createBuffer`](BaseAudioContext/createBuffer.html). Once decoded into this form, the audio can then be put into an [`AudioBufferSourceNode`](AudioBufferSourceNode.html).

[`AudioBufferSourceNode`](AudioBufferSourceNode.html)  
The **`AudioBufferSourceNode`** interface represents an audio source consisting of in-memory audio data, stored in an [`AudioBuffer`](AudioBuffer.html). It is an [`AudioNode`](AudioNode.html) that acts as an audio source.

[`MediaElementAudioSourceNode`](MediaElementAudioSourceNode.html)  
The `MediaElementAudioSourceNode` interface represents an audio source consisting of an HTML5 [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element. It is an [`AudioNode`](AudioNode.html) that acts as an audio source.

[`MediaStreamAudioSourceNode`](MediaStreamAudioSourceNode.html)  
The `MediaStreamAudioSourceNode` interface represents an audio source consisting of a [`MediaStream`](MediaStream.html) (such as a webcam, microphone, or a stream being sent from a remote computer). If multiple audio tracks are present on the stream, the track whose [`id`](MediaStreamTrack/id.html "id") comes first lexicographically (alphabetically) is used. It is an [`AudioNode`](AudioNode.html) that acts as an audio source.

[`MediaStreamTrackAudioSourceNode`](MediaStreamTrackAudioSourceNode.html)  
A node of type [`MediaStreamTrackAudioSourceNode`](MediaStreamTrackAudioSourceNode.html) represents an audio source whose data comes from a [`MediaStreamTrack`](MediaStreamTrack.html). When creating the node using the [`createMediaStreamTrackSource()`](AudioContext/createMediaStreamTrackSource.html "createMediaStreamTrackSource()") method to create the node, you specify which track to use. This provides more control than `MediaStreamAudioSourceNode`.

### [Defining audio effects filters](#defining_audio_effects_filters "Permalink to Defining audio effects filters")

Interfaces for defining effects that you want to apply to your audio sources.

[`BiquadFilterNode`](BiquadFilterNode.html)  
The **`BiquadFilterNode`** interface represents a simple low-order filter. It is an [`AudioNode`](AudioNode.html) that can represent different kinds of filters, tone control devices, or graphic equalizers. A `BiquadFilterNode` always has exactly one input and one output.

[`ConvolverNode`](ConvolverNode.html)  
The `Convolver`**`Node`** interface is an <span style="line-height: 1.5;">[`AudioNode`](AudioNode.html) that</span><span style="line-height: 1.5;"> performs a Linear Convolution on a given [`AudioBuffer`](AudioBuffer.html), and is often used to achieve a reverb effect</span><span style="line-height: 1.5;">.</span>

[`DelayNode`](DelayNode.html)  
The **`DelayNode`** interface represents a <a href="https://en.wikipedia.org/wiki/Digital_delay_line" class="external">delay-line</a>; an [`AudioNode`](AudioNode.html) audio-processing module that causes a delay between the arrival of an input data and its propagation to the output.

[`DynamicsCompressorNode`](DynamicsCompressorNode.html)  
The **`DynamicsCompressorNode`** interface provides a compression effect, which lowers the volume of the loudest parts of the signal in order to help prevent clipping and distortion that can occur when multiple sounds are played and multiplexed together at once.

[`GainNode`](GainNode.html)  
The **`GainNode`** interface represents a change in volume. It is an [`AudioNode`](AudioNode.html) audio-processing module that causes a given *gain* to be applied to the input data before its propagation to the output.

[`WaveShaperNode`](WaveShaperNode.html)  
The **`WaveShaperNode`** interface represents a non-linear distorter. It is an [`AudioNode`](AudioNode.html) that use a curve to apply a waveshaping distortion to the signal. Beside obvious distortion effects, it is often used to add a warm feeling to the signal.

[`PeriodicWave`](PeriodicWave.html)  
Describes a periodic waveform that can be used to shape the output of an [`OscillatorNode`](OscillatorNode.html).

[`IIRFilterNode`](IIRFilterNode.html)  
Implements a general **<a href="https://en.wikipedia.org/wiki/infinite%20impulse%20response" class="external external-icon" title="infinite impulse response">infinite impulse response</a>** (IIR)  filter; this type of filter can be used to implement tone control devices and graphic equalizers as well.

### [Defining audio destinations](#defining_audio_destinations "Permalink to Defining audio destinations")

Once you are done processing your audio, these interfaces define where to output it.

[`AudioDestinationNode`](AudioDestinationNode.html)  
The **`AudioDestinationNode`** interface represents the end destination of an audio source in a given context — usually the speakers of your device.

[`MediaStreamAudioDestinationNode`](MediaStreamAudioDestinationNode.html)  
The `MediaStreamAudio`**`DestinationNode`** interface represents an audio destination consisting of a [WebRTC](WebRTC_API.html) [`MediaStream`](MediaStream.html) with a single `AudioMediaStreamTrack`, which can be used in a similar way to a [`MediaStream`](MediaStream.html) obtained from [`getUserMedia()`](MediaDevices/getUserMedia.html "getUserMedia()"). It is an [`AudioNode`](AudioNode.html) that acts as an audio destination.

### [Data analysis and visualization](#data_analysis_and_visualization "Permalink to Data analysis and visualization")

If you want to extract time, frequency, and other data from your audio, the `AnalyserNode` is what you need.

[`AnalyserNode`](AnalyserNode.html)  
The **`AnalyserNode`** interface represents a node able to provide real-time frequency and time-domain analysis information, for the purposes of data analysis and visualization.

### [Splitting and merging audio channels](#splitting_and_merging_audio_channels "Permalink to Splitting and merging audio channels")

To split and merge audio channels, you'll use these interfaces.

[`ChannelSplitterNode`](ChannelSplitterNode.html)  
The `ChannelSplitterNode` interface separates the different channels of an audio source out into a set of *mono* outputs.

[`ChannelMergerNode`](ChannelMergerNode.html)  
The `ChannelMergerNode` interface reunites different mono inputs into a single output. Each input will be used to fill a channel of the output.

### [Audio spatialization](#audio_spatialization "Permalink to Audio spatialization")

These interfaces allow you to add audio spatialization panning effects to your audio sources.

[`AudioListener`](AudioListener.html)  
The **`AudioListener`** interface represents the position and orientation of the unique person listening to the audio scene used in audio spatialization.

[`PannerNode`](PannerNode.html)  
The `PannerNode` interface represents the position and behavior of an audio source signal in 3D space, allowing you to create complex panning effects.

[`StereoPannerNode`](StereoPannerNode.html)  
The `StereoPannerNode` interface represents a simple stereo panner node that can be used to pan an audio stream left or right.

### [Audio processing in JavaScript](#audio_processing_in_javascript "Permalink to Audio processing in JavaScript")

Using audio worklets, you can define custom audio nodes written in JavaScript or [WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly). Audio worklets implement the [`Worklet`](Worklet.html) interface, a lightweight version of the [`Worker`](Worker.html) interface.

[`AudioWorklet`](AudioWorklet.html)  
The `AudioWorklet` interface is available through the [`AudioContext`](AudioContext.html) object's [`audioWorklet`](BaseAudioContext/audioWorklet.html "audioWorklet"), and lets you add modules to the audio worklet to be executed off the main thread.

[`AudioWorkletNode`](AudioWorkletNode.html)  
The `AudioWorkletNode` interface represents an [`AudioNode`](AudioNode.html) that is embedded into an audio graph and can pass messages to the corresponding `AudioWorkletProcessor`.

[`AudioWorkletProcessor`](AudioWorkletProcessor.html)  
The `AudioWorkletProcessor` interface represents audio processing code running in a `AudioWorkletGlobalScope` that generates, processes, or analyses audio directly, and can pass messages to the corresponding `AudioWorkletNode`.

[`AudioWorkletGlobalScope`](AudioWorkletGlobalScope.html)  
The `AudioWorkletGlobalScope` interface is a `WorkletGlobalScope`-derived object representing a worker context in which an audio processing script is run; it is designed to enable the generation, processing, and analysis of audio data directly using JavaScript in a worklet thread rather than on the main thread.

#### Obsolete: script processor nodes

Before audio worklets were defined, the Web Audio API used the `ScriptProcessorNode`  for JavaScript-based audio processing. Because the code runs in the main thread, they have bad performance. The `ScriptProcessorNode` is kept for historic reasons but is marked as deprecated.

[`ScriptProcessorNode`](ScriptProcessorNode.html)   
The **`ScriptProcessorNode`** interface allows the generation, processing, or analyzing of audio using JavaScript. It is an [`AudioNode`](AudioNode.html) audio-processing module that is linked to two buffers, one containing the current input, one containing the output. An event, implementing the [`AudioProcessingEvent`](AudioProcessingEvent.html) interface, is sent to the object each time the input buffer contains new data, and the event handler terminates when it has filled the output buffer with data.

`audioprocess` (event)   
The `audioprocess` event is fired when an input buffer of a Web Audio API [`ScriptProcessorNode`](ScriptProcessorNode.html) is ready to be processed.

[`AudioProcessingEvent`](AudioProcessingEvent.html)   
The [Web Audio API](Web_Audio_API.html) `AudioProcessingEvent` represents events that occur when a [`ScriptProcessorNode`](ScriptProcessorNode.html) input buffer is ready to be processed.

### [Offline/background audio processing](#offlinebackground_audio_processing "Permalink to Offline/background audio processing")

It is possible to process/render an audio graph very quickly in the background — rendering it to an [`AudioBuffer`](AudioBuffer.html) rather than to the device's speakers — with the following.

[`OfflineAudioContext`](OfflineAudioContext.html)  
The **`OfflineAudioContext`** interface is an [`AudioContext`](AudioContext.html) interface representing an audio-processing graph built from linked together [`AudioNode`](AudioNode.html)s. In contrast with a standard `AudioContext`, an `OfflineAudioContext` doesn't really render the audio but rather generates it, *as fast as it can*, in a buffer.

`complete` (event)  
The `complete` event is fired when the rendering of an [`OfflineAudioContext`](OfflineAudioContext.html) is terminated.

[`OfflineAudioCompletionEvent`](OfflineAudioCompletionEvent.html)  
The `OfflineAudioCompletionEvent` represents events that occur when the processing of an [`OfflineAudioContext`](OfflineAudioContext.html) is terminated. The `complete` event implements this interface.

[Guides and tutorials](#guides_and_tutorials "Permalink to Guides and tutorials")
---------------------------------------------------------------------------------

[Advanced techniques: Creating and sequencing audio](Web_Audio_API/Advanced_techniques.html)  
In this tutorial, we're going to cover sound creation and modification, as well as timing and scheduling. We're going to introduce sample loading, envelopes, filters, wavetables, and frequency modulation. If you're familiar with these terms and you're looking for an introduction to their application within with the Web Audio API, you've come to the right place.

[Background audio processing using AudioWorklet](Web_Audio_API/Using_AudioWorklet.html)  
The process of creating an audio processor using JavaScript, establishing it as an audio worklet processor, and then using that processor within a Web Audio application is the topic of this article.

[Basic concepts behind Web Audio API](Web_Audio_API/Basic_concepts_behind_Web_Audio_API.html)  
<span class="seoSummary">This article explains some of the audio theory behind how the features of the Web Audio API work, to help you make informed decisions while designing how audio is routed through your app.</span> It won't turn you into a master sound engineer, but it will give you enough background to understand why the Web Audio API works like it does.

[Controlling multiple parameters with ConstantSourceNode](Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode.html)  
This article demonstrates how to use a `ConstantSourceNode` to link multiple parameters together so they share the same value, which can be changed by setting the value of the `ConstantSourceNode.offset` parameter.

[Example and tutorial: Simple synth keyboard](Web_Audio_API/Simple_synth.html)  
This article presents the code and working demo of a video keyboard you can play using the mouse. The keyboard allows you to switch among the standard waveforms as well as one custom waveform, and you can control the main gain using a volume slider beneath the keyboard. This example makes use of the following Web API interfaces: `AudioContext`, `OscillatorNode`, `PeriodicWave`, and `GainNode`.

[Migrating from webkitAudioContext](Web_Audio_API/Migrating_from_webkitAudioContext.html)  
In this article, we cover the differences in Web Audio API since it was first implemented in WebKit and how to update your code to use the modern Web Audio API.

[Tools for analyzing Web Audio usage](Web_Audio_API/Tools.html)  
While working on your Web Audio API code, you may find that you need tools to analyze the graph of nodes you create or to otherwise debug your work. This article discusses tools available to help you do that.

[Using IIR filters](Web_Audio_API/Using_IIR_filters.html)  
The **`IIRFilterNode`** interface of the [Web Audio API](Web_Audio_API.html) is an `AudioNode` processor that implements a general <a href="https://en.wikipedia.org/wiki/infinite%20impulse%20response" class="external">infinite impulse response</a> (IIR) filter; this type of filter can be used to implement tone control devices and graphic equalizers, and the filter response parameters can be specified, so that it can be tuned as needed. This article looks at how to implement one, and use it in a simple example.

[Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)  
<span class="seoSummary">Let's take a look at getting started with the [Web Audio API](Web_Audio_API.html). We'll briefly look at some concepts, then study a simple boombox example that allows us to load an audio track, play and pause it, and change its volume and stereo panning.</span>

[Visualizations with Web Audio API](Web_Audio_API/Visualizations_with_Web_Audio_API.html)  
One of the most interesting features of the Web Audio API is the ability to extract frequency, waveform, and other data from your audio source, which can then be used to create visualizations. This article explains how, and provides a couple of basic use cases.

[Web Audio API best practices](Web_Audio_API/Best_practices.html)  
There's no strict right or wrong way when writing creative code. As long as you consider security, performance, and accessibility, you can adapt to your own style. In this article, we'll share a number of *best practices* — guidelines, tips, and tricks for working with the Web Audio API.

[Web audio spatialization basics](Web_Audio_API/Web_audio_spatialization_basics.html)  
<span class="seoSummary">As if its extensive variety of sound processing (and other) options wasn't enough, the Web Audio API also includes facilities to allow you to emulate the difference in sound as a listener moves around a sound source, for example panning as you move around a sound source inside a 3D game. The official term for this is **spatialization**, and this article will cover the basics of how to implement such a system.</span>

[Examples](#examples "Permalink to Examples")
---------------------------------------------

You can find a number of examples at our <a href="https://github.com/mdn/webaudio-examples/" class="external">webaudio-example repo</a> on GitHub.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/" class="external" title="The &#39;Web Audio API&#39; specification">Web Audio API</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

### [Tutorials/guides](#tutorialsguides "Permalink to Tutorials/guides")

-   [Basic concepts behind Web Audio API](Web_Audio_API/Basic_concepts_behind_Web_Audio_API.html)
-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)
-   [Advanced techniques: creating sound, sequencing, timing, scheduling](Web_Audio_API/Advanced_techniques.html)
-   [Autoplay guide for media and Web Audio APIs](https://developer.mozilla.org/en-US/docs/Web/Media/Autoplay_guide)
-   [Using IIR filters](Web_Audio_API/Using_IIR_filters.html)
-   [Visualizations with Web Audio API](Web_Audio_API/Visualizations_with_Web_Audio_API.html)
-   [Web audio spatialisation basics](Web_Audio_API/Web_audio_spatialization_basics.html)
-   [Controlling multiple parameters with ConstantSourceNode](Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode.html)
-   <a href="https://www.html5rocks.com/tutorials/webaudio/positional_audio/" class="external">Mixing Positional Audio and WebGL</a>
-   <a href="https://www.html5rocks.com/tutorials/webaudio/games/" class="external">Developing Game Audio with the Web Audio API</a>
-   [Porting webkitAudioContext code to standards based AudioContext](Web_Audio_API/Migrating_from_webkitAudioContext.html)

### [Libraries](#libraries "Permalink to Libraries")

-   <a href="https://github.com/bit101/tones" class="external">Tones</a>: a simple library for playing specific tones/notes using the Web Audio API.
-   <a href="https://tonejs.github.io/" class="external">Tone.js</a>: a framework for creating interactive music in the browser.
-   <a href="https://github.com/goldfire/howler.js/" class="external">howler.js</a>: a JS audio library that defaults to <a href="https://webaudio.github.io/web-audio-api/" class="external">Web Audio API</a> and falls back to <a href="https://www.whatwg.org/specs/web-apps/current-work/#the-audio-element" class="external">HTML5 Audio</a>, as well as providing other useful features.
-   <a href="https://github.com/mattlima/mooog" class="external">Mooog</a>: jQuery-style chaining of AudioNodes, mixer-style sends/returns, and more.
-   <a href="https://korilakkuma.github.io/XSound/" class="external">XSound</a>: Web Audio API Library for Synthesizer, Effects, Visualization, Recording ... etc
-   <a href="https://github.com/chrisjohndigital/OpenLang" class="external external-icon">OpenLang</a>: HTML5 video language lab web application using the Web Audio API to record and combine video and audio from different sources into a single file (<a href="https://github.com/chrisjohndigital/OpenLang" class="external external-icon">source on GitHub</a>)
-   <a href="https://ptsjs.org/" class="external">Pts.js</a>: Simplifies web audio visualization (<a href="https://ptsjs.org/guide/sound-0800" class="external">guide</a>)

### [Related topics](#related_topics "Permalink to Related topics")

-   [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)
-   [Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/index.html "Folder: en-us/web/api/web_audio_api (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F99d16ce8ca7f21331fa17c92b9c4b496f0b4a82f%0A*+Document+last+modified%3A+2021-03-25T00%3A49%3A17.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Web+Audio+API%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Mar 25, 2021, [by MDN contributors](Web_Audio_API/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어PolskiPortuguês (do Brasil)Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  Guides
    1.  [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)
    2.  [Basic concepts behind Web Audio API](Web_Audio_API/Basic_concepts_behind_Web_Audio_API.html)
    3.  [Web Audio API best practices](Web_Audio_API/Best_practices.html)
    4.  [Advanced techniques: Creating and sequencing audio](Web_Audio_API/Advanced_techniques.html)
    5.  [Controlling multiple parameters with ConstantSourceNode](Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode.html)
    6.  [Migrating from webkitAudioContext](Web_Audio_API/Migrating_from_webkitAudioContext.html)
    7.  [Example and tutorial: Simple synth keyboard](Web_Audio_API/Simple_synth.html)
    8.  [Tools for analyzing Web Audio usage](Web_Audio_API/Tools.html)
    9.  [Using IIR filters](Web_Audio_API/Using_IIR_filters.html)
    10. [Visualizations with Web Audio API](Web_Audio_API/Visualizations_with_Web_Audio_API.html)
    11. [Web audio spatialization basics](Web_Audio_API/Web_audio_spatialization_basics.html)
3.  Interfaces
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
    21. [`ConstantSourceNode`](ConstantSourceNode.html)
    22. [`ConvolverNode`](ConvolverNode.html)
    23. [`DelayNode`](DelayNode.html)
    24. [`DynamicsCompressorNode`](DynamicsCompressorNode.html)
    25. [`GainNode`](GainNode.html)
    26. [`IIRFilterNode`](IIRFilterNode.html)
    27. [`MediaElementAudioSourceNode`](MediaElementAudioSourceNode.html)
    28. [`MediaStreamAudioDestinationNode`](MediaStreamAudioDestinationNode.html)
    29. [`MediaStreamAudioSourceNode`](MediaStreamAudioSourceNode.html)
    30. [`OfflineAudioCompletionEvent`](OfflineAudioCompletionEvent.html)
    31. [`OfflineAudioContext`](OfflineAudioContext.html)
    32. [`OscillatorNode`](OscillatorNode.html)
    33. [`PannerNode`](PannerNode.html)
    34. [`PeriodicWave`](PeriodicWave.html)
    35. [`WaveShaperNode`](WaveShaperNode.html)
    36. [`StereoPannerNode`](StereoPannerNode.html)

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
