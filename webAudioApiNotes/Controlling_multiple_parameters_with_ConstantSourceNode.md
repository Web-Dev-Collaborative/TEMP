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
4.  <a href="Controlling_multiple_parameters_with_ConstantSourceNode.html" class="breadcrumb-current-page"><span data-property="name">Controlling multiple parameters with ConstantSourceNode</span></a>

Table of contents
-----------------

Table of contents

-   [The technique](#the_technique)
-   [Example](#example)
-   [See also](#see_also)

Controlling multiple parameters with ConstantSourceNode
=======================================================

<span class="seoSummary">This article demonstrates how to use a [`ConstantSourceNode`](../ConstantSourceNode.html) to link multiple parameters together so they share the same value, which can be changed by setting the value of the [`ConstantSourceNode.offset`](../ConstantSourceNode/offset.html) parameter.</span>

You may have times when you want to have multiple audio parameters be linked so they share the same value even while being changed in some way. For example, perhaps you have a set of oscillators, and two of them need to share the same, configurable volume, or you have a filter that's been applied to certain inputs but not to all of them. You could use a loop and change the value of each affected [`AudioParam`](../AudioParam.html) one at a time, but there are two drawbacks to doing it that way: first, that's extra code that, as you're about to see, you don't have to write; and second, that loop uses valuable CPU time on your thread (likely the main thread), and there's a way to offload all that work to the audio rendering thread, which is optimized for this kind of work and may run at a more appropriate priority level than your code.

The solution is simple, and it involves using an audio node type which, at first glance, doesn't look all that useful: [`ConstantSourceNode`](../ConstantSourceNode.html).

[The technique](#the_technique "Permalink to The technique")
------------------------------------------------------------

This is actually a really easy way to do something that sounds like it might be hard to do. You need to create a [`ConstantSourceNode`](../ConstantSourceNode.html) and connect it to all of the [`AudioParam`](../AudioParam.html)s whose values should be linked to always match each other. Since `ConstantSourceNode`'s [`offset`](../ConstantSourceNode/offset.html "offset") value is sent straight through to all of its outputs, it acts as a splitter for that value, sending it to each connected parameter.

The diagram below shows how this works; an input value, `N`, is set as the value of the [`ConstantSourceNode.offset`](../ConstantSourceNode/offset.html) property. The `ConstantSourceNode` can have as many outputs as necessary; in this case, we've connected it to three nodes: two [`GainNode`](../GainNode.html)s and a [`StereoPannerNode`](../StereoPannerNode.html). So `N` becomes the value of the specified parameter ([`gain`](../GainNode/gain.html "gain") for the [`GainNode`](../GainNode.html)s and pan for the [`StereoPannerNode`](../StereoPannerNode.html).

<img src="Controlling_multiple_parameters_with_ConstantSourceNode/customsourcenode-as-splitter.svg" alt="Dagram in SVG showing how ConstantSourceNode can be used to split an input parameter to share it with multiple nodes." width="773" height="461" />

As a result, every time you change `N` (the value of the input [`AudioParam`](../AudioParam.html), the values of the two `GainNode`s' `gain` properties and the value of the `StereoPannerNode`'s `pan` propertry are all set to `N` as well.

[Example](#example "Permalink to Example")
------------------------------------------

Let's take a look at this technique in action. In this simple example, we create three [`OscillatorNode`](../OscillatorNode.html)s. Two of them have adjustable gain, controlled using a shared input control. The other oscillator has a fixed volume.

### [HTML](#html "Permalink to HTML")

The HTML content for this example is primarily a button to toggle the oscillator tones on and off and an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element of type `range` to control the volume of two of the three oscillators.

    <div class="controls">
      <div class="left">
        <div id="playButton" class="button">
          ▶️
        </div>
      </div>
      <div class="right">
        <span>Volume: </span>
        <input type="range" min="0.0" max="1.0" step="0.01"
            value="0.8" name="volume" id="volumeControl">
      </div>
    </div>

    <p>Use the button above to start and stop the tones, and the volume control to
    change the volume of the notes E and G in the chord.</p>

### [JavaScript](#javascript "Permalink to JavaScript")

Now let's take a look at the JavaScript code, a piece at a time.

#### Setting up

Let's start by looking at the global variable initialization.

    let context = null;

    let playButton = null;
    let volumeControl = null;

    let oscNode1 = null;
    let oscNode2 = null;
    let oscNode3 = null;
    let constantNode = null;
    let gainNode1 = null;
    let gainNode2 = null;
    let gainNode3 = null;

    let playing = false;

These variables are:

`context`  
The [`AudioContext`](../AudioContext.html) in which all the audio nodes live.

`playButton` and `volumeControl`  
References to the play button and volume control elements.

`oscNode1`, `oscNode2`, and `oscNode3`  
The three [`OscillatorNode`](../OscillatorNode.html)s used to generate the chord.

`gainNode1`, `gainNode2`, and `gainNode3`  
The three [`GainNode`](../GainNode.html) instances which provide the volume levels for each of the three oscillators. `gainNode2` and `gainNode3` will be linked together to have the same, adjustable, value using the [`ConstantSourceNode`](../ConstantSourceNode.html).

`constantNode`  
The [`ConstantSourceNode`](../ConstantSourceNode.html) used to control the values of `gainNode2` and `gainNode3` together.

`playing`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that we'll use to keep track of whether or not we're currently playing the tones.

Now let's look at the `setup()` function, which is our handler for the window's `load` event; it handles all the initialization tasks that require the DOM to be in place.

    function setup() {
      context = new (window.AudioContext || window.webkitAudioContext)();

      playButton = document.querySelector("#playButton");
      volumeControl = document.querySelector("#volumeControl");

      playButton.addEventListener("click", togglePlay, false);
      volumeControl.addEventListener("input", changeVolume, false);

      gainNode1 = context.createGain();
      gainNode1.gain.value = 0.5;

      gainNode2 = context.createGain();
      gainNode3 = context.createGain();
      gainNode2.gain.value = gainNode1.gain.value;
      gainNode3.gain.value = gainNode1.gain.value;
      volumeControl.value = gainNode1.gain.value;

      constantNode = context.createConstantSource();
      constantNode.connect(gainNode2.gain);
      constantNode.connect(gainNode3.gain);
      constantNode.start();

      gainNode1.connect(context.destination);
      gainNode2.connect(context.destination);
      gainNode3.connect(context.destination);
    }

    window.addEventListener("load", setup, false);

First, we get access to the window's [`AudioContext`](../AudioContext.html), stashing the reference in `context`. Then we get references to the control widgets, setting `playButton` to reference the play button and `volumeControl` to reference the slider control that the user will use to adjust the gain on the linked pair of oscillators.

Then we assign a handler for the play button's `click` event (see [Toggling the oscillators on and off](#toggling_the_oscillators_on_and_off) for more on the `togglePlay()` method), and for the volume slider's `input` event (see [Controlling the linked oscillators](#controlling_the_linked_oscillators) to see the very short `changeVolume()` method).

Next, the [`GainNode`](../GainNode.html) `gainNode1` is created to handle the volume for the non-linked oscillator (`oscNode1`). We set that gain to 0.5. We also create `gainNode2` and `gainNode3`, setting their values to match `gainNode1`, then set the value of the volume slider to the same value, so it is synchronized with the gain level it controls.

Once all the gain nodes are created, we create the [`ConstantSourceNode`](../ConstantSourceNode.html), `constantNode`. We connect its output to the `gain` [`AudioParam`](../AudioParam.html) on both `gainNode2` and `gainNode3`, and we start the constant node running by calling its [`start()`](../AudioScheduledSourceNode/start.html "start()") method; now it's sending the value 0.5 to the two gain nodes' values, and any change to [`constantNode.offset`](../ConstantSourceNode/offset.html "constantNode.offset") will automatically set the gain of both `gainNode2` and `gainNode3` (affecting their audio inputs as expected).

Finally, we connect all the gain nodes to the [`AudioContext`](../AudioContext.html)'s [`destination`](../BaseAudioContext/destination.html "destination"), so that any sound delivered to the gain nodes will reach the output, whether that output be speakers, headphones, a recording stream, or any other destination type.

After setting the window's `load` event handler to be the `setup()` function, the stage is set. Let's see how the action plays out.

#### Toggling the oscillators on and off

Because [`OscillatorNode`](../OscillatorNode.html) doesn't support the notion of being in a paused state, we have to simulate it by terminating the oscillators and starting them again when the play button is clicked again to toggle them back on. Let's look at the code.

    function togglePlay(event) {
      if (playing) {
        playButton.textContent = "▶️";
        stopOscillators();
      } else {
        playButton.textContent = "⏸";
        startOscillators();
      }
    }

If the `playing` variable indicates we're already playing the oscillators, we change the `playButton`'s content to be the Unicode character "right-pointing triangle" (▶️) and call `stopOscillators()` to shut down the oscillators. See [Stopping the oscillators](#stopping_the_oscillators) below for that code.

If `playing` is false, indicating that we're currently paused, we change the play button's content to be the Unicode character "pause symbol" (⏸) and call `startOscillators()` to start the oscillators playing their tones. That code is covered under [Starting the oscillators](#starting_the_oscillators) below.

#### Controlling the linked oscillators

The `changeVolume()` function—the event handler for the slider control for the gain on the linked oscillator pair—looks like this:

    function changeVolume(event) {
      constantNode.offset.value = volumeControl.value;
    }

That simple function controls the gain on both nodes. All we have to do is set the value of the [`ConstantSourceNode`](../ConstantSourceNode.html)'s [`offset`](../ConstantSourceNode/offset.html "offset") parameter. That value becomes the node's constant output value, which is fed into all of its outputs, which are, as set above, `gainNode2` and `gainNode3`.

While this is an extremely simple example, imagine having a 32 oscillator synthesizer with multiple linked parameters in play across a number of patched nodes. Being able to shorten the number of operations to adjust them all will prove invaluable for code size and performance both.

#### Starting the oscillators

When the user clicks the play/pause toggle button while the oscillators aren't playing, the `startOscillators()` function gets called.

    function startOscillators() {
      oscNode1 = context.createOscillator();
      oscNode1.type = "sine";
      oscNode1.frequency.value = 261.625565300598634; // middle C
      oscNode1.connect(gainNode1);

      oscNode2 = context.createOscillator();
      oscNode2.type = "sine";
      oscNode2.frequency.value = 329.627556912869929; // E
      oscNode2.connect(gainNode2);

      oscNode3 = context.createOscillator();
      oscNode3.type = "sine";
      oscNode3.frequency.value = 391.995435981749294 // G
      oscNode3.connect(gainNode3);

      oscNode1.start();
      oscNode2.start();
      oscNode3.start();

      playing = true;
    }

Each of the three oscillators is set up the same way:

1.  Create the [`OscillatorNode`](../OscillatorNode.html) by calling [`BaseAudioContext.createOscillator`](../BaseAudioContext/createOscillator.html).
2.  Set the oscillator's type to `"sine"` to use a sine wave as the audio waveform.
3.  Set the oscillator's frequency to the desired value; in this case, `oscNode1` is set to a middle C, while `oscNode2` and `oscNode3` round out the chord by playing the E and G notes.
4.  Connect the new oscillator to the corresponding gain node.

Once all three oscillators have been created, they're started by calling each one's [`ConstantSourceNode.start()`](../AudioScheduledSourceNode/start.html "ConstantSourceNode.start()") method in turn, and `playing` is set to `true` to track that the tones are playing.

#### Stopping the oscillators

Stopping the oscillators when the user toggles the play state to pause the tones is as simple as stopping each node.

    function stopOscillators() {
      oscNode1.stop();
      oscNode2.stop();
      oscNode3.stop();
      playing = false;
    }

Each node is stopped by calling its [`ConstantSourceNode.stop()`](../AudioScheduledSourceNode/stop.html "ConstantSourceNode.stop()") method, then `playing` is set to `false`.

### [Result](#result "Permalink to Result")

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Web Audio API](../Web_Audio_API.html)
-   [Using the Web Audio API](Using_Web_Audio_API.html)
-   [Simple synth keyboard](Simple_synth.html) (example)
-   [`OscillatorNode`](../OscillatorNode.html)
-   [`ConstantSourceNode`](../ConstantSourceNode.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/controlling_multiple_parameters_with_constantsourcenode/index.html "Folder: en-us/web/api/web_audio_api/controlling_multiple_parameters_with_constantsourcenode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FControlling_multiple_parameters_with_ConstantSourceNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%2Fcontrolling_multiple_parameters_with_constantsourcenode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FControlling_multiple_parameters_with_ConstantSourceNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Fcontrolling_multiple_parameters_with_constantsourcenode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F085be4abf5406e6fdc164d7d1a31e18f942e582f%0A*+Document+last+modified%3A+2021-03-09T14%3A48%3A30.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Controlling+multiple+parameters+with+ConstantSourc%E2%80%A6%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Mar 9, 2021, [by MDN contributors](Controlling_multiple_parameters_with_ConstantSourceNode/contributors.txt)

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
