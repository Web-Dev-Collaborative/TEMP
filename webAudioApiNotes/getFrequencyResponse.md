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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode" class="breadcrumb-penultimate"><span data-property="name">IIRFilterNode</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode/getFrequencyResponse" class="breadcrumb-current-page"><span data-property="name">IIRFilterNode.getFrequencyResponse()</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Examples](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

IIRFilterNode.getFrequencyResponse()
====================================

The `getFrequencyResponse()` method of the [`IIRFilterNode`](https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode) interface takes the current filtering algorithm's settings and calculates the frequency response for frequencies specified in a specified array of frequencies.

The two output arrays, `magResponseOutput` and `phaseResponseOutput`, must be created before calling this method; they must be the same size as the array of input frequency values (`frequencyArray`).

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    IIRFilterNode.getFrequencyResponse(frequencyArray, magResponseOutput, phaseResponseOutput);

### [Parameters](#parameters "Permalink to Parameters")

`frequencyArray`  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing an array of frequencies, specified in Hertz, which you want to filter.

`magResponseOutput`  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) to receive the computed magnitudes of the frequency response for each frequency value in the `frequencyArray`.

`phaseResponseOutput`  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) to receive the computed phase response values in radians for each frequency value in the input `frequencyArray`.

### [Return value](#return_value "Permalink to Return value")

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### [Exceptions](#exceptions "Permalink to Exceptions")

`NotSupportedError`  
The three arrays provided are not all of the same length.

[Examples](#example "Permalink to Examples")
--------------------------------------------

In the following example we are using an IIR filter on a media stream (for a complete full demo, see our <a href="https://mdn.github.io/stream-source-buffer/" class="external">stream-source-buffer demo</a> live, or <a href="https://github.com/mdn/stream-source-buffer/blob/gh-pages/index.html" class="external">read its source</a>.) As part of this demo, we get the frequency responses for this IIR filter, for five sample frequencies. We first create the [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) objects we need, one containing the input frequencies, and two to receive the output magnitude and phase values:

    var myFrequencyArray = new Float32Array(5);
    myFrequencyArray[0] = 1000;
    myFrequencyArray[1] = 2000;
    myFrequencyArray[2] = 3000;
    myFrequencyArray[3] = 4000;
    myFrequencyArray[4] = 5000;

    var magResponseOutput = new Float32Array(5);
    var phaseResponseOutput = new Float32Array(5);

Next we create a [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) element in our HTML to contain our results, and grab a reference to it in our JavaScript:

    <p>IIR filter frequency response for: </p>
    <ul class="freq-response-output">
    </ul>

    var freqResponseOutput = document.querySelector('.freq-response-output');

Finally, after creating our filter, we use `getFrequencyResponse()` to generate the response data and put it in our arrays, then loop through each data set and output them in a human-readable list at the bottom of the page:

    var feedforwardCoefficients = [0.1, 0.2, 0.3, 0.4, 0.5];
    var feedbackCoefficients = [0.5, 0.4, 0.3, 0.2, 0.1];

    var iirFilter = audioCtx.createIIRFilter(feedforwardCoefficients, feedbackCoefficients);

      ...

    function calcFrequencyResponse() {
      iirFilter.getFrequencyResponse(myFrequencyArray, magResponseOutput, phaseResponseOutput);

      for(i = 0; i <= myFrequencyArray.length-1;i++){
        var listItem = document.createElement('li');
        listItem.innerHTML = '<strong>' + myFrequencyArray[i] + 'Hz</strong>: Magnitude ' + magResponseOutput[i] + ', Phase ' + phaseResponseOutput[i] + ' radians.';
        freqResponseOutput.appendChild(listItem);
      }
    }

    calcFrequencyResponse();

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-iirfilternode-getfrequencyresponse" class="external">Web Audio API<br />
<span class="small">The definition of 'getFrequencyResponse()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)
-   [`IIRFilterNode`](https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode)
-   [`AudioNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioNode)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/iirfilternode/getfrequencyresponse/index.html "Folder: en-us/web/api/iirfilternode/getfrequencyresponse (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FIIRFilterNode%2FgetFrequencyResponse%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fiirfilternode%2Fgetfrequencyresponse%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FIIRFilterNode%2FgetFrequencyResponse%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fiirfilternode%2Fgetfrequencyresponse%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fafb900789aa9c9f3fb0192a9ea1ae6e5ffb0d231%0A*+Document+last+modified%3A+2021-05-31T00%3A59%3A40.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22IIRFilterNode.getFrequencyResponse%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode/getFrequencyResponse/contributors.txt)

#### Related Topics

1.  **[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)**
2.  **[`IIRFilterNode`](https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode)**
3.  Constructor
    1.  [`IIRFilterNode()`](https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode/IIRFilterNode)
4.  Methods
    1.  *`getFrequencyResponse()`*
5.  Related pages for Web Audio API
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
    16. [`AudioWorkletProcessor`](https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor)
    17. [`BaseAudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext)
    18. [`BiquadFilterNode`](https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode)
    19. [`ChannelMergerNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChannelMergerNode)
    20. [`ChannelSplitterNode`](https://developer.mozilla.org/en-US/docs/Web/API/ChannelSplitterNode)
    21. [`ConstantSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/ConstantSourceNode)
    22. [`ConvolverNode`](https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode)
    23. [`DelayNode`](https://developer.mozilla.org/en-US/docs/Web/API/DelayNode)
    24. [`DynamicsCompressorNode`](https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode)
    25. [`GainNode`](https://developer.mozilla.org/en-US/docs/Web/API/GainNode)
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
