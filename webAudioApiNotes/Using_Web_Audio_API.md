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
4.  <a href="Using_Web_Audio_API.html" class="breadcrumb-current-page"><span data-property="name">Using the Web Audio API</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Example code](#example_code)
-   [Browser support](#browser_support)
-   [Audio graphs](#audio_graphs)
-   [Audio context](#audio_context)
-   [Loading sound](#loading_sound)
-   [Controlling sound](#controlling_sound)
-   [Modifying sound](#modifying_sound)
-   [Adding stereo panning to our app](#adding_stereo_panning_to_our_app)
-   [Summary](#summary)
-   [More examples](#more_examples)

Using the Web Audio API
=======================

<span class="seoSummary">Let's take a look at getting started with the [Web Audio API](../Web_Audio_API.html). We'll briefly look at some concepts, then study a simple boombox example that allows us to load an audio track, play and pause it, and change its volume and stereo panning.</span>

The Web Audio API does not replace the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) media element, but rather complements it, just like [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) coexists alongside the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element. Your use case will determine what tools you use to implement audio. If you want to control playback of an audio track, the `<audio>` media element provides a better, quicker solution than the Web Audio API. If you want to carry out more complex audio processing, as well as playback, the Web Audio API provides much more power and control.

A powerful feature of the Web Audio API is that it does not have a strict "sound call limitation". For example, there is no ceiling of 32 or 64 sound calls at one time. Some processors may be capable of playing more than 1,000 simultaneous sounds without stuttering.

[Example code](#example_code "Permalink to Example code")
---------------------------------------------------------

Our boombox looks like this:

<img src="Using_Web_Audio_API/boombox.png" alt="A boombox with play, pan, and volume controls" width="1200" height="646" />

Note the retro cassette deck with a play button, and vol and pan sliders to allow you to alter the volume and stereo panning. We could make this a lot more complex, but this is ideal for simple learning at this stage.

<a href="https://codepen.io/Rumyra/pen/qyMzqN/" class="external">Check out the final demo here on Codepen</a>, or see the <a href="https://github.com/mdn/webaudio-examples/tree/master/audio-basics" class="external">source code on GitHub</a>.

[Browser support](#browser_support "Permalink to Browser support")
------------------------------------------------------------------

Modern browsers have good support for most features of the Web Audio API. There are a lot of features of the API, so for more exact information, you'll have to check the browser compatibility tables at the bottom of each reference page.

[Audio graphs](#audio_graphs "Permalink to Audio graphs")
---------------------------------------------------------

Everything within the Web Audio API is based around the concept of an audio graph, which is made up of nodes.

The Web Audio API handles audio operations inside an **audio context**, and has been designed to allow **modular routing**. Basic audio operations are performed with **audio nodes**, which are linked together to form an **audio routing graph**. You have input nodes, which are the source of the sounds you are manipulating, modification nodes that change those sounds as desired, and output nodes (destinations), which allow you to save or hear those sounds.

Several audio sources with different channel layouts are supported, even within a single context. Because of this modular design, you can create complex audio functions with dynamic effects.

[Audio context](#audio_context "Permalink to Audio context")
------------------------------------------------------------

To be able to do anything with the Web Audio API, we need to create an instance of the audio context. This then gives us access to all the features and functionality of the API.

    // for legacy browsers
    const AudioContext = window.AudioContext || window.webkitAudioContext;

    const audioContext = new AudioContext();

So what's going on when we do this? A [`BaseAudioContext`](../BaseAudioContext.html) is created for us automatically and extended to an online audio context. We'll want this because we're looking to play live sound.

**Note**: If you just want to process audio data, for instance, buffer and stream it but not play it, you might want to look into creating an [`OfflineAudioContext`](../OfflineAudioContext.html).

[Loading sound](#loading_sound "Permalink to Loading sound")
------------------------------------------------------------

Now, the audio context we've created needs some sound to play through it. There are a few ways to do this with the API. Let's begin with a simple method — as we have a boombox, we most likely want to play a full song track. Also, for accessibility, it's nice to expose that track in the DOM. We'll expose the song on the page using an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element.

    <audio src="myCoolTrack.mp3"></audio>

**Note**: If the sound file you're loading is held on a different domain you will need to use the `crossorigin` attribute; see [Cross Origin Resource Sharing (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) for more information.

To use all the nice things we get with the Web Audio API, we need to grab the source from this element and *pipe* it into the context we have created. Lucky for us there's a method that allows us to do just that — [`AudioContext.createMediaElementSource`](../AudioContext/createMediaElementSource.html):

    // get the audio element
    const audioElement = document.querySelector('audio');

    // pass it into the audio context
    const track = audioContext.createMediaElementSource(audioElement);

**Note**: The `<audio>` element above is represented in the DOM by an object of type [`HTMLMediaElement`](../HTMLMediaElement.html), which comes with its own set of functionality. All of this has stayed intact; we are merely allowing the sound to be available to the Web Audio API.

[Controlling sound](#controlling_sound "Permalink to Controlling sound")
------------------------------------------------------------------------

When playing sound on the web, it's important to allow the user to control it. Depending on the use case, there's a myriad of options, but we'll provide functionality to play/pause the sound, alter the track's volume, and pan it from left to right.

Controlling sound programmatically from JavaScript code is covered by browsers' autoplay support policies, as such is likely to be blocked without permission being granted by the user (or a whitelist). Autoplay policies typically require either explicit permission or a user engagement with the page before scripts can trigger audio to play.

These special requirements are in place essentially because unexpected sounds can be annoying and intrusive, and can cause accessibility problems. You can learn more about this in our article [Autoplay guide for media and Web Audio APIs](https://developer.mozilla.org/en-US/docs/Web/Media/Autoplay_guide).

Since our scripts are playing audio in response to a user input event (a click on a play button, for instance), we're in good shape and should have no problems from autoplay blocking. So, let's start by taking a look at our play and pause functionality. We have a play button that changes to a pause button when the track is playing:

    <button data-playing="false" role="switch" aria-checked="false">
        <span>Play/Pause</span>
    </button>

Before we can play our track we need to connect our audio graph from the audio source/input node to the destination.

We've already created an input node by passing our audio element into the API. For the most part, you don't need to create an output node, you can just connect your other nodes to [`BaseAudioContext.destination`](../BaseAudioContext/destination.html), which handles the situation for you:

    track.connect(audioContext.destination);

A good way to visualise these nodes is by drawing an audio graph so you can visualize it. This is what our current audio graph looks like:

<img src="Using_Web_Audio_API/graph1.jpg" alt="an audio graph with an audio element source connected to the default destination" width="1426" height="486" />

Now we can add the play and pause functionality.

    // select our play button
    const playButton = document.querySelector('button');

    playButton.addEventListener('click', function() {

        // check if context is in suspended state (autoplay policy)
        if (audioContext.state === 'suspended') {
            audioContext.resume();
        }

        // play or pause track depending on state
        if (this.dataset.playing === 'false') {
            audioElement.play();
            this.dataset.playing = 'true';
        } else if (this.dataset.playing === 'true') {
            audioElement.pause();
            this.dataset.playing = 'false';
        }

    }, false);

We also need to take into account what to do when the track finishes playing. Our `HTMLMediaElement` fires an `ended` event once it's finished playing, so we can listen for that and run code accordingly:

    audioElement.addEventListener('ended', () => {
        playButton.dataset.playing = 'false';
    }, false);

[Modifying sound](#modifying_sound "Permalink to Modifying sound")
------------------------------------------------------------------

Let's delve into some basic modification nodes, to change the sound that we have. This is where the Web Audio API really starts to come in handy. First of all, let's change the volume. This can be done using a [`GainNode`](../GainNode.html), which represents how big our sound wave is.

There are two ways you can create nodes with the Web Audio API. You can use the factory method on the context itself (e.g. `audioContext.createGain()`) or via a constructor of the node (e.g. `new GainNode()`). We'll use the factory method in our code:

    const gainNode = audioContext.createGain();

Now we have to update our audio graph from before, so the input is connected to the gain, then the gain node is connected to the destination:

    track.connect(gainNode).connect(audioContext.destination);

This will make our audio graph look like this:

<img src="Using_Web_Audio_API/graph2.jpg" alt="an audio graph with an audio element source, connected to a gain node that modifies the audio source, and then going to the default destination" width="1774" height="550" />

The default value for gain is 1; this keeps the current volume the same. Gain can be set to a minimum of about -3.4 and a max of about 3.4. Here we'll allow the boombox to move the gain up to 2 (double the original volume) and down to 0 (this will effectively mute our sound).

Let's give the user control to do this — we'll use a [range input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range):

    <input type="range" id="volume" min="0" max="2" value="1" step="0.01">

**Note**: Range inputs are a really handy input type for updating values on audio nodes. You can specify a range's values and use them directly with the audio node's parameters.

So let's grab this input's value and update the gain value when the input node has its value changed by the user:

    const volumeControl = document.querySelector('#volume');

    volumeControl.addEventListener('input', function() {
        gainNode.gain.value = this.value;
    }, false);

**Note**: The values of node objects (e.g. `GainNode.gain`) are not simple values; they are actually objects of type [`AudioParam`](../AudioParam.html) — these called parameters. This is why we have to set `GainNode.gain`'s `value` property, rather than just setting the value on `gain` directly. This enables them to be much more flexible, allowing for passing the parameter a specific set of values to change between over a set period of time, for example.

Great, now the user can update the track's volume! The gain node is the perfect node to use if you want to add mute functionality.

[Adding stereo panning to our app](#adding_stereo_panning_to_our_app "Permalink to Adding stereo panning to our app")
---------------------------------------------------------------------------------------------------------------------

Let's add another modification node to practice what we've just learnt.

There's a [`StereoPannerNode`](../StereoPannerNode.html) node, which changes the balance of the sound between the left and right speakers, if the user has stereo capabilities.

**Note**: The `StereoPannerNode` is for simple cases in which you just want stereo panning from left to right. There is also a [`PannerNode`](../PannerNode.html), which allows for a great deal of control over 3D space, or sound *spatialisation*, for creating more complex effects. This is used in games and 3D apps to create birds flying overhead, or sound coming from behind the user for instance.

To visualise it, we will be making our audio graph look like this:

<img src="Using_Web_Audio_API/graphpan.jpg" alt="An image showing the audio graph showing an input node, two modification nodes (a gain node and a stereo panner node) and a destination node." width="2236" height="532" />

Let's use the constructor method of creating a node this time. When we do it this way, we have to pass in the context and any options that the particular node may take:

    const pannerOptions = { pan: 0 };
    const panner = new StereoPannerNode(audioContext, pannerOptions);

**Note**: The constructor method of creating nodes is not supported by all browsers at this time. The older factory methods are supported more widely.

Here our values range from -1 (far left) and 1 (far right). Again let's use a range type input to vary this parameter:

    <input type="range" id="panner" min="-1" max="1" value="0" step="0.01">

We use the values from that input to adjust our panner values in the same way as we did before:

    const pannerControl = document.querySelector('#panner');

    pannerControl.addEventListener('input', function() {
        panner.pan.value = this.value;
    }, false);

Let's adjust our audio graph again, to connect all the nodes together:

    track.connect(gainNode).connect(panner).connect(audioContext.destination);

The only thing left to do is give the app a try: <a href="https://codepen.io/Rumyra/pen/qyMzqN/" class="external">Check out the final demo here on Codepen</a>.

[Summary](#summary "Permalink to Summary")
------------------------------------------

Great! We have a boombox that plays our 'tape', and we can adjust the volume and stereo panning, giving us a fairly basic working audio graph.

This makes up quite a few basics that you would need to start to add audio to your website or web app. There's a lot more functionality to the Web Audio API, but once you've grasped the concept of nodes and putting your audio graph together, we can move on to looking at more complex functionality.

[More examples](#more_examples "Permalink to More examples")
------------------------------------------------------------

There are other examples available to learn more about the Web Audio API.

The <a href="https://github.com/mdn/voice-change-o-matic" class="external">Voice-change-O-matic</a> is a fun voice manipulator and sound visualization web app that allows you to choose different effects and visualizations. The application is fairly rudimentary, but it demonstrates the simultaneous use of multiple Web Audio API features. (<a href="https://mdn.github.io/voice-change-o-matic/" class="external">run the Voice-change-O-matic live</a>).

<img src="Using_Web_Audio_API/voice-change-o-matic.png" alt="A UI with a sound wave being shown, and options for choosing voice effects and visualizations." width="640" height="500" />

Another application developed specifically to demonstrate the Web Audio API is the <a href="https://mdn.github.io/violent-theremin/" class="external">Violent Theremin</a>, a simple web application that allows you to change pitch and volume by moving your mouse pointer. It also provides a psychedelic lightshow (<a href="https://github.com/mdn/violent-theremin" class="external">see Violent Theremin source code</a>).

<img src="Using_Web_Audio_API/violent-theremin.png" alt="A page full of rainbow colors, with two buttons labeled Clear screen and mute." width="640" height="458" />

Also see our <a href="https://github.com/mdn/webaudio-examples" class="external">webaudio-examples repo</a> for more examples.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/using_web_audio_api/index.html "Folder: en-us/web/api/web_audio_api/using_web_audio_api (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FUsing_Web_Audio_API%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%2Fusing_web_audio_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FUsing_Web_Audio_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Fusing_web_audio_api%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F63c69f3c933acbea9bfb24d359a7d2ffdb3c0bea%0A*+Document+last+modified%3A+2021-02-19T19%3A51%3A22.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Using+the+Web+Audio+API%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Feb 19, 2021, [by MDN contributors](Using_Web_Audio_API/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語한국어Русский中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  Guides
    1.  [Using the Web Audio API](Using_Web_Audio_API.html)
    2.  [Basic concepts behind Web Audio API](Basic_concepts_behind_Web_Audio_API.html)
    3.  [Web Audio API best practices](Best_practices.html)
    4.  [Advanced techniques: Creating and sequencing audio](Advanced_techniques.html)
    5.  [Controlling multiple parameters with ConstantSourceNode](Controlling_multiple_parameters_with_ConstantSourceNode.html)
    6.  [Migrating from webkitAudioContext](Migrating_from_webkitAudioContext.html)
    7.  [Example and tutorial: Simple synth keyboard](Simple_synth.html)
    8.  [Tools for analyzing Web Audio usage](Tools.html)
    9.  [Using IIR filters](Using_IIR_filters.html)
    10. [Visualizations with Web Audio API](Visualizations_with_Web_Audio_API.html)
    11. [Web audio spatialization basics](Web_audio_spatialization_basics.html)
3.  Interfaces
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
    35. [`WaveShaperNode`](../WaveShaperNode.html)
    36. [`StereoPannerNode`](../StereoPannerNode.html)

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
