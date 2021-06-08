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
4.  <a href="Using_IIR_filters.html" class="breadcrumb-current-page"><span data-property="name">Using IIR filters</span></a>

Table of contents
-----------------

Table of contents

-   [Demo](#demo)
-   [Browser support](#browser_support)
-   [The IIRFilterNode](#the_iirfilternode)
-   [Setting our IIRFilter co-efficients](#setting_our_iirfilter_co-efficients)
-   [Using an IIRFilter in an audio graph](#using_an_iirfilter_in_an_audio_graph)
-   [Summary](#summary)

Using IIR filters
=================

The **`IIRFilterNode`** interface of the [Web Audio API](../Web_Audio_API.html) is an [`AudioNode`](../AudioNode.html) processor that implements a general <a href="https://en.wikipedia.org/wiki/infinite%20impulse%20response" class="external">infinite impulse response</a> (IIR) filter; this type of filter can be used to implement tone control devices and graphic equalizers, and the filter response parameters can be specified, so that it can be tuned as needed. This article looks at how to implement one, and use it in a simple example.

[Demo](#demo "Permalink to Demo")
---------------------------------

Our simple example for this guide provides a play/pause button that starts and pauses audio play, and a toggle that turns an IIR filter on and off, altering the tone of the sound. It also provides a canvas on which is drawn the frequency response of the audio, so you can see what effect the IIR filter has.

<img src="Using_IIR_filters/iir-filter-demo.png" alt="A demo featuring a play button, and toggle to turn a filter on and off, and a line graph showing the filter frequencies returned after the filter has been applied." width="620" height="621" />

You can check out the <a href="https://codepen.io/Rumyra/pen/oPxvYB/" class="external">full demo here on Codepen</a>. Also see the <a href="https://github.com/mdn/webaudio-examples/tree/master/iirfilter-node" class="external">source code on GitHub</a>. It includes some different coefficient values for different lowpass frequencies — you can change the value of the `filterNumber` constant to a value between 0 and 3 to check out the different available effects.

[Browser support](#browser_support "Permalink to Browser support")
------------------------------------------------------------------

[IIR filters](../IIRFilterNode.html) are supported well across modern browsers, although they have been implemented more recently than some of the more longstanding Web Audio API features, like [Biquad filters](../BiquadFilterNode.html).

[The IIRFilterNode](#the_iirfilternode "Permalink to The IIRFilterNode")
------------------------------------------------------------------------

The Web Audio API now comes with an [`IIRFilterNode`](../IIRFilterNode.html) interface. But what is this and how does it differ from the [`BiquadFilterNode`](../BiquadFilterNode.html) we have already?

An IIR filter is a **infinite impulse response filter**. It's one of two primary types of filters used in audio and digital signal processing. The other type is FIR — **finite impulse response filter**. There's a really good overview to <a href="https://dspguru.com/dsp/faqs/iir/basics/" class="external">IIF filters and FIR filters here</a>.

A biquad filter is actually a *specific type* of infinite impulse response filter. It's a commonly-used type and we already have it as a node in the Web Audio API. If you choose this node the hard work is done for you. For instance, if you want to filter lower frequencies from your sound, you can set the [type](../BiquadFilterNode/type.html) to `highpass` and then set which frequency to filter from (or cut off). <a href="https://www.earlevel.com/main/2003/02/28/biquads/" class="external">There's more information on how biquad filters work here</a>.

When you are using an [`IIRFilterNode`](../IIRFilterNode.html) instead of a [`BiquadFilterNode`](../BiquadFilterNode.html) you are creating the filter yourself, rather than just choosing a pre-programmed type. So you can create a highpass filter, or a lowpass filter, or a more bespoke one. And this is where the IIR filter node is useful — you can create your own if none of the alaready available settings is right for what you want. As well as this, if your audio graph needed a highpass and a bandpass filter within it, you could just use one IIR filter node in place of the two biquad filter nodes you would otherwise need for this.

With the IIRFIlter node it's up to you to set what `feedforward` and `feedback` values the filter needs — this determines the characteristics of the filter. The downside is that this involves some complex maths.

If you are looking to learn more there's some <a href="http://ece.uccs.edu/~mwickert/ece2610/lecture_notes/ece2610_chap8.pdf" class="external">information about the maths behind IIR filters here</a>. This enters the realms of signal processing theory — don't worry if you look at it and feel like it's not for you.

If you want to play with the IIR filter node and need some values to help along the way, there's <a href="https://www.dspguide.com/CH20.PDF" class="external">a table of already calculated values here</a>; on pages 4 & 5 of the linked PDF the a*n* values refer to the `feedForward` values and the b*n* values refer to the `feedback`. <a href="http://musicdsp.org/" class="external">musicdsp.org</a> is also a great resource if you want to read more about different filters and how they are implemented digitally.

With that all in mind, let's take a look at the code to create an IIR filter with the Web Audio API.

[Setting our IIRFilter co-efficients](#setting_our_iirfilter_co-efficients "Permalink to Setting our IIRFilter co-efficients")
------------------------------------------------------------------------------------------------------------------------------

When creating an IIR filter, we pass in the `feedforward` and `feedback` coefficients as options (coefficients is how we describe the values). Both of these parameters are arrays, neither of which can be larger than 20 items.

When setting our coefficients, the `feedforward` values can't all be set to zero, otherwise nothing would be sent to the filter. Something like this is acceptable:

    let feedForward = [0.00020298, 0.0004059599, 0.00020298];

Our `feedback` values cannot start with zero, otherwise on the first pass nothing would be sent back:

    let feedBackward = [1.0126964558, -1.9991880801, 0.9873035442];

**Note**: These values are calculated based on the lowpass filter specified in the <a href="https://webaudio.github.io/web-audio-api/#filters-characteristics" class="external">filter characteristics of the Web Audio API specification</a>. As this filter node gains more popularity we should be able to collate more coefficient values.

[Using an IIRFilter in an audio graph](#using_an_iirfilter_in_an_audio_graph "Permalink to Using an IIRFilter in an audio graph")
---------------------------------------------------------------------------------------------------------------------------------

Let's create our context and our filter node:

    const AudioContext = window.AudioContext || window.webkitAudioContext;
    const audioCtx = new AudioContext();

    const iirFilter = audioCtx.createIIRFilter(feedForward, feedBack);

We need a sound source to play. We set this up using a custom function, `playSoundNode()`, which [creates a buffer source](../BaseAudioContext/createBufferSource.html) from an existing [`AudioBuffer`](../AudioBuffer.html), attaches it to the default destination, starts it playing, and returns it:

    function playSourceNode(audioContext, audioBuffer) {
      const soundSource = audioContext.createBufferSource();
      soundSource.buffer = audioBuffer;
      soundSource.connect(audioContext.destination);
      soundSource.start();
      return soundSource;
    }

This function is called when the play button is pressed. The play button HTML looks like this:

    <button class="button-play" role="switch" data-playing="false" aria-pressed="false">Play</button>

And the `click` event listener starts like so:

    playButton.addEventListener('click', function() {
        if (this.dataset.playing === 'false') {
            srcNode = playSourceNode(audioCtx, sample);
            ...
    }, false);

The toggle that turns the IIR filter on and off is set up in the similar way. First, the HTML:

    <button class="button-filter" role="switch" data-filteron="false" aria-pressed="false" aria-describedby="label" disabled></button>

The filter button's `click` handler then connects the `IIRFilter` up to the graph, between the source and the detination:

    filterButton.addEventListener('click', function() {
        if (this.dataset.filteron === 'false') {
            srcNode.disconnect(audioCtx.destination);
            srcNode.connect(iirfilter).connect(audioCtx.destination);
            ...
    }, false);

### [Frequency response](#frequency_response "Permalink to Frequency response")

We only have one method available on [`IIRFilterNode`](../IIRFilterNode.html) instances, `getFrequencyResponse()`, this allows us to see what is happening to the frequencies of the audio being passed into the filter.

Let's draw a frequency plot of the filter we've created with the data we get back from this method.

We need to create three arrays. One of frequency values for which we want to receive the magnitude response and phase response for, and two empty arrays to receive the data. All three of these have to be of type [`float32array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) and all be of the same size.

    // arrays for our frequency response
    const totalArrayItems = 30;
    let myFrequencyArray = new Float32Array(totalArrayItems);
    let magResponseOutput = new Float32Array(totalArrayItems);
    let phaseResponseOutput = new Float32Array(totalArrayItems);

Let's fill our first array with frequency values we want data to be returned on:

    myFrequencyArray = myFrequencyArray.map(function(item, index) {
        return Math.pow(1.4, index);
    });

We could go for a linear approach, but it's far better when working with frequencies to take a log approach, so let's fill our array with frequency values that get larger further on in the array items.

Now let's get our response data:

    iirFilter.getFrequencyResponse(myFrequencyArray, magResponseOutput, phaseResponseOutput);

We can use this data to draw a filter frequency plot. We'll do so on a 2d canvas context.

    // create a canvas element and append it to our dom
    const canvasContainer = document.querySelector('.filter-graph');
    const canvasEl = document.createElement('canvas');
    canvasContainer.appendChild(canvasEl);

    // set 2d context and set dimesions
    const canvasCtx = canvasEl.getContext('2d');
    const width = canvasContainer.offsetWidth;
    const height = canvasContainer.offsetHeight;
    canvasEl.width = width;
    canvasEl.height = height;

    // set background fill
    canvasCtx.fillStyle = 'white';
    canvasCtx.fillRect(0, 0, width, height);

    // set up some spacing based on size
    const spacing = width/16;
    const fontSize = Math.floor(spacing/1.5);

    // draw our axis
    canvasCtx.lineWidth = 2;
    canvasCtx.strokeStyle = 'grey';

    canvasCtx.beginPath();
    canvasCtx.moveTo(spacing, spacing);
    canvasCtx.lineTo(spacing, height-spacing);
    canvasCtx.lineTo(width-spacing, height-spacing);
    canvasCtx.stroke();

    // axis is gain by frequency -> make labels
    canvasCtx.font = fontSize+'px sans-serif';
    canvasCtx.fillStyle = 'grey';
    canvasCtx.fillText('1', spacing-fontSize, spacing+fontSize);
    canvasCtx.fillText('g', spacing-fontSize, (height-spacing+fontSize)/2);
    canvasCtx.fillText('0', spacing-fontSize, height-spacing+fontSize);
    canvasCtx.fillText('Hz', width/2, height-spacing+fontSize);
    canvasCtx.fillText('20k', width-spacing, height-spacing+fontSize);

    // loop over our magnitude response data and plot our filter

    canvasCtx.beginPath();

    for(let i = 0; i < magResponseOutput.length; i++) {

        if (i === 0) {
            canvasCtx.moveTo(spacing, height-(magResponseOutput[i]*100)-spacing );
        } else {
            canvasCtx.lineTo((width/totalArrayItems)*i, height-(magResponseOutput[i]*100)-spacing );
        }

    }

    canvasCtx.stroke();

[Summary](#summary "Permalink to Summary")
------------------------------------------

That's it for our IIRFilter demo. This should have shown you how to use the basics, and helped you to understand what it's useful for and how it works.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/using_iir_filters/index.html "Folder: en-us/web/api/web_audio_api/using_iir_filters (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FUsing_IIR_filters%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%2Fusing_iir_filters%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FUsing_IIR_filters%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Fusing_iir_filters%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F085be4abf5406e6fdc164d7d1a31e18f942e582f%0A*+Document+last+modified%3A+2021-03-09T14%3A48%3A30.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Using+IIR+filters%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Mar 9, 2021, [by MDN contributors](Using_IIR_filters/contributors.txt)

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
