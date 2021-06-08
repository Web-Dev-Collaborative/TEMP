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
3.  <a href="MediaStreamAudioDestinationNode.html" class="breadcrumb-current-page"><span data-property="name">MediaStreamAudioDestinationNode</span></a>

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

MediaStreamAudioDestinationNode
===============================

The `MediaStreamAudioDestinationNode` interface represents an audio destination consisting of a [WebRTC](WebRTC_API.html) [`MediaStream`](MediaStream.html) with a single `AudioMediaStreamTrack`, which can be used in a similar way to a `MediaStream` obtained from [`Navigator.getUserMedia()`](Navigator/getUserMedia.html).

It is an [`AudioNode`](AudioNode.html) that acts as an audio destination, created using the [`AudioContext.createMediaStreamDestination()`](AudioContext/createMediaStreamDestination.html) method.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>0</code></td></tr><tr class="odd"><td>Channel count</td><td><code>2</code></td></tr><tr class="even"><td>Channel count mode</td><td><code>"explicit"</code></td></tr><tr class="odd"><td>Channel count interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`MediaStreamAudioDestinationNode.MediaStreamAudioDestinationNode()`](MediaStreamAudioDestinationNode/MediaStreamAudioDestinationNode.html)  
Creates a new `MediaStreamAudioDestinationNode` object instance.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`AudioNode`](AudioNode.html)*.

[`MediaStreamAudioDestinationNode.stream`](MediaStreamAudioDestinationNode/stream.html)  
A [`MediaStream`](MediaStream.html) containing a single [`MediaStreamTrack`](MediaStreamTrack.html) whose [`kind`](MediaStreamTrack/kind.html "kind") is `audio` and with the same number of channels as the node. You can use this property to get a stream out of the audio graph and feed it into another construct, such as a [Media Recorder](MediaStream_Recording_API.html).

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent, [`AudioNode`](AudioNode.html)*.

[Example](#example "Permalink to Example")
------------------------------------------

In the following simple example, we create a [`MediaStreamAudioDestinationNode`](MediaStreamAudioDestinationNode.html), an [`OscillatorNode`](OscillatorNode.html) and a [`MediaRecorder`](MediaRecorder.html) (the example will therefore only work in Firefox and Chrome at this time.) The `MediaRecorder` is set up to record information from the `MediaStreamDestinationNode`.

When the button is clicked, the oscillator starts, and the `MediaRecorder` is started. When the button is stopped, the oscillator and` MediaRecorder` both stop. Stopping the `MediaRecorder` causes the `dataavailable` event to fire, and the event data is pushed into the `chunks` array. After that, the `stop` event fires, a new `blob` is made of type opus — which contains the data in the `chunks` array, and a new window (tab) is then opened that points to a URL created from the blob.

From here, you can play and save the opus file.

    <!DOCTYPE html>
    <html>
      <head>
        <title>createMediaStreamDestination() demo</title>
      </head>
      <body>
        <h1>createMediaStreamDestination() demo</h1>

        <p>Encoding a pure sine wave to an Opus file </p>
        <button>Make sine wave</button>
        <audio controls></audio>
        <script>
         var b = document.querySelector("button");
         var clicked = false;
         var chunks = [];
         var ac = new AudioContext();
         var osc = ac.createOscillator();
         var dest = ac.createMediaStreamDestination();
         var mediaRecorder = new MediaRecorder(dest.stream);
         osc.connect(dest);

         b.addEventListener("click", function(e) {
           if (!clicked) {
               mediaRecorder.start();
               osc.start(0);
               e.target.textContent = "Stop recording";
               clicked = true;
             } else {
               mediaRecorder.stop();
               osc.stop(0);
               e.target.disabled = true;
             }
         });

         mediaRecorder.ondataavailable = function(evt) {
           // push each chunk (blobs) in an array
           chunks.push(evt.data);
         };

         mediaRecorder.onstop = function(evt) {
           // Make blob out of our blobs, and open it.
           var blob = new Blob(chunks, { 'type' : 'audio/ogg; codecs=opus' });
           document.querySelector("audio").src = URL.createObjectURL(blob);
         };
        </script>
      </body>
    </html>

**Note**: You can <a href="https://mdn.github.io/webaudio-examples/create-media-stream-destination/index.html" class="external">view this example live</a>, or <a href="https://github.com/mdn/webaudio-examples/blob/master/create-media-stream-destination/index.html" class="external">study the source code</a>, on Github.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#mediastreamaudiodestinationnode" class="external">Web Audio API<br />
<span class="small">The definition of 'MediaStreamAudioDestinationNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediastreamaudiodestinationnode/index.html "Folder: en-us/web/api/mediastreamaudiodestinationnode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamAudioDestinationNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediastreamaudiodestinationnode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamAudioDestinationNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediastreamaudiodestinationnode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaStreamAudioDestinationNode%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](MediaStreamAudioDestinationNode/contributors.txt)

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`MediaStreamAudioDestinationNode`](MediaStreamAudioDestinationNode.html)**
3.  Constructor
    1.  [`MediaStreamAudioDestinationNode()`](MediaStreamAudioDestinationNode/MediaStreamAudioDestinationNode.html)
4.  Properties
    1.  [`stream`](MediaStreamAudioDestinationNode/stream.html)
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
-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
