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
3.  <a href="StereoPannerNode.html" class="breadcrumb-current-page"><span data-property="name">StereoPannerNode</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

StereoPannerNode
================

The `StereoPannerNode` interface of the [Web Audio API](Web_Audio_API.html) represents a simple stereo panner node that can be used to pan an audio stream left or right. It is an [`AudioNode`](AudioNode.html) audio-processing module that positions an incoming audio stream in a stereo image using a low-cost equal-power <a href="https://webaudio.github.io/web-audio-api/#panning-algorithm" class="external">panning algorithm</a>.

The [`pan`](StereoPannerNode/pan.html "pan") property takes a unitless value between `-1` (full left pan) and `1` (full right pan). This interface was introduced as a much simpler way to apply a simple panning effect than having to use a full [`PannerNode`](PannerNode.html).

<img src="StereoPannerNode/stereopannernode.png" width="687" height="89" />

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"clamped-max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code></td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`StereoPannerNode()`](StereoPannerNode/StereoPannerNode.html "StereoPannerNode()")  
Creates a new instance of a `StereoPannerNode` object.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`AudioNode`](AudioNode.html)*.

[`StereoPannerNode.pan`](StereoPannerNode/pan.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Is an [a-rate](AudioParam.html#a-rate) [`AudioParam`](AudioParam.html) representing the amount of panning to apply.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*No specific method; inherits methods from its parent, [`AudioNode`](AudioNode.html)*.

[Example](#example "Permalink to Example")
------------------------------------------

In our <a href="https://mdn.github.io/webaudio-examples/stereo-panner-node/" class="external">StereoPannerNode example</a> (<a href="https://github.com/mdn/webaudio-examples/tree/master/stereo-panner-node" class="external">see source code</a>) HTML we have a simple [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element along with a slider [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) to increase and decrease pan value. In the JavaScript we create a [`MediaElementAudioSourceNode`](MediaElementAudioSourceNode.html) and a [`StereoPannerNode`](StereoPannerNode.html), and connect the two together using the `connect() `method. We then use an `oninput` event handler to change the value of the [`StereoPannerNode.pan`](StereoPannerNode/pan.html) parameter and update the pan value display when the slider is moved.

Moving the slider left and right while the music is playing pans the music across to the left and right speakers of the output, respectively.

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var myAudio = document.querySelector('audio');

    var panControl = document.querySelector('.panning-control');
    var panValue = document.querySelector('.panning-value');

    pre.innerHTML = myScript.innerHTML;

    // Create a MediaElementAudioSourceNode
    // Feed the HTMLMediaElement into it
    var source = audioCtx.createMediaElementSource(myAudio);

    // Create a stereo panner
    var panNode = audioCtx.createStereoPanner();

    // Event handler function to increase panning to the right and left
    // when the slider is moved

    panControl.oninput = function() {
      panNode.pan.setValueAtTime(panControl.value, audioCtx.currentTime);
      panValue.innerHTML = panControl.value;
    }

    // connect the MediaElementAudioSourceNode to the panNode
    // and the panNode to the destination, so we can play the
    // music and adjust the panning using the controls
    source.connect(panNode);
    panNode.connect(audioCtx.destination);

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#stereopannernode" class="external">Web Audio API<br />
<span class="small">The definition of 'StereoPannerNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/stereopannernode/index.html "Folder: en-us/web/api/stereopannernode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FStereoPannerNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fstereopannernode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FStereoPannerNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fstereopannernode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F0d5312d317fb301c56441905dc84e1f902cb7046%0A*+Document+last+modified%3A+2021-06-01T06%3A05%3A06.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22StereoPannerNode%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](StereoPannerNode/contributors.txt)

Change your languageSelect your preferred language English (US)日本語

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`StereoPannerNode`](StereoPannerNode.html)**
3.  Constructor
    1.  [`StereoPannerNode()`](StereoPannerNode/StereoPannerNode.html)
4.  Properties
    1.  [`pan`](StereoPannerNode/pan.html)
5.  Inheritance:
    1.  [`AudioNode`](AudioNode.html)
    2.  [`EventTarget`](EventTarget.html)
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
