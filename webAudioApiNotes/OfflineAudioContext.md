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
3.  <a href="OfflineAudioContext.html" class="breadcrumb-current-page"><span data-property="name">OfflineAudioContext</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Events](#events)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

OfflineAudioContext
===================

The `OfflineAudioContext` interface is an [`AudioContext`](AudioContext.html) interface representing an audio-processing graph built from linked together [`AudioNode`](AudioNode.html)s. In contrast with a standard [`AudioContext`](AudioContext.html), an `OfflineAudioContext` doesn't render the audio to the device hardware; instead, it generates it, as fast as it can, and outputs the result to an [`AudioBuffer`](AudioBuffer.html).

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`OfflineAudioContext.OfflineAudioContext()`](OfflineAudioContext/OfflineAudioContext.html)  
Creates a new `OfflineAudioContext` instance.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Also inherits properties from its parent interface, [`BaseAudioContext`](BaseAudioContext.html).*

[`OfflineAudioContext.length`](OfflineAudioContext/length.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
An integer representing the size of the buffer in sample-frames.

### [Event handlers](#event_handlers "Permalink to Event handlers")

[`OfflineAudioContext.oncomplete`](OfflineAudioContext/oncomplete.html)  
Is an `event handler` called when processing is terminated, that is when the `complete` event (of type [`OfflineAudioCompletionEvent`](OfflineAudioCompletionEvent.html)) is raised, after the event-based version of [`OfflineAudioContext.startRendering()`](OfflineAudioContext/startRendering.html) is used.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Also inherits methods from its parent interface, [`BaseAudioContext`](BaseAudioContext.html).*

[`OfflineAudioContext.suspend()`](OfflineAudioContext/suspend.html)  
Schedules a suspension of the time progression in the audio context at the specified time and returns a promise.

[`OfflineAudioContext.startRendering()`](OfflineAudioContext/startRendering.html)  
Starts rendering the audio, taking into account the current connections and the current scheduled changes. This page covers both the event-based version and the promise-based version.

### [Deprecated methods](#deprecated_methods "Permalink to Deprecated methods")

[`OfflineAudioContext.resume()`](OfflineAudioContext/resume.html)  
Resumes the progression of time in an audio context that has previously been suspended.

**Note**: The `resume()` method is still available — it is now defined on the [`BaseAudioContext`](BaseAudioContext.html) interface (see [`AudioContext.resume`](AudioContext/resume.html)) and thus can be accessed by both the [`AudioContext`](AudioContext.html) and [`OfflineAudioContext`](OfflineAudioContext.html) interfaces.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface:

`complete`  
Fired when the rendering of an offline audio context is complete.  
Also available using the `oncomplete` event handler property.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In this simple example, we declare both an [`AudioContext`](AudioContext.html) and an `OfflineAudioContext` object. We use the `AudioContext` to load an audio track via XHR ([`BaseAudioContext.decodeAudioData`](BaseAudioContext/decodeAudioData.html)), then the `OfflineAudioContext` to render the audio into an [`AudioBufferSourceNode`](AudioBufferSourceNode.html) and play the track through. After the offline audio graph is set up, you need to render it to an [`AudioBuffer`](AudioBuffer.html) using [`OfflineAudioContext.startRendering`](OfflineAudioContext/startRendering.html).

When the `startRendering()` promise resolves, rendering has completed and the output `AudioBuffer` is returned out of the promise.

At this point we create another audio context, create an [`AudioBufferSourceNode`](AudioBufferSourceNode.html) inside it, and set its buffer to be equal to the promise `AudioBuffer`. This is then played as part of a simple standard audio graph.

**Note**: For a working example, see our <a href="https://mdn.github.io/webaudio-examples/offline-audio-context-promise/" class="external">offline-audio-context-promise</a> Github repo (see the <a href="https://github.com/mdn/webaudio-examples/tree/master/offline-audio-context-promise" class="external">source code</a> too.)

    // define online and offline audio context

    var audioCtx = new AudioContext();
    var offlineCtx = new OfflineAudioContext(2,44100*40,44100);

    source = offlineCtx.createBufferSource();

    // use XHR to load an audio track, and
    // decodeAudioData to decode it and OfflineAudioContext to render it

    function getData() {
      request = new XMLHttpRequest();

      request.open('GET', 'viper.ogg', true);

      request.responseType = 'arraybuffer';

      request.onload = function() {
        var audioData = request.response;

        audioCtx.decodeAudioData(audioData, function(buffer) {
          myBuffer = buffer;
          source.buffer = myBuffer;
          source.connect(offlineCtx.destination);
          source.start();
          //source.loop = true;
          offlineCtx.startRendering().then(function(renderedBuffer) {
            console.log('Rendering completed successfully');
            var song = audioCtx.createBufferSource();
            song.buffer = renderedBuffer;

            song.connect(audioCtx.destination);

            play.onclick = function() {
              song.start();
            }
          }).catch(function(err) {
              console.log('Rendering failed: ' + err);
              // Note: The promise should reject when startRendering is called a second time on an OfflineAudioContext
          });
        });
      }

      request.send();
    }

    // Run getData to start the process off

    getData();

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#OfflineAudioContext" class="external">Web Audio API<br />
<span class="small">The definition of 'OfflineAudioContext' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/offlineaudiocontext/index.html "Folder: en-us/web/api/offlineaudiocontext (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FOfflineAudioContext%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fofflineaudiocontext%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FOfflineAudioContext%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fofflineaudiocontext%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fa2282aa45be910a103b93ad06396ee195a10f456%0A*+Document+last+modified%3A+2021-06-01T11%3A47%3A53.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22OfflineAudioContext%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](OfflineAudioContext/contributors.txt)

Change your languageSelect your preferred language English (US)日本語Português (do Brasil)中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`OfflineAudioContext`](OfflineAudioContext.html)**
3.  Constructor
    1.  [`OfflineAudioContext()`](OfflineAudioContext/OfflineAudioContext.html)
4.  Properties
    1.  [`length`](OfflineAudioContext/length.html)
    2.  [`oncomplete`](OfflineAudioContext/oncomplete.html)
5.  Methods
    1.  [`resume()`](OfflineAudioContext/resume.html)
    2.  [`startRendering()`](OfflineAudioContext/startRendering.html)
    3.  [`suspend()`](OfflineAudioContext/suspend.html)
6.  Events
    1.  [`complete`](OfflineAudioContext/complete_event.html)
7.  Inheritance:
    1.  [`BaseAudioContext`](BaseAudioContext.html)
    2.  [`EventTarget`](EventTarget.html)
8.  Related pages for Web Audio API
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

#### Mozilla

-   <a href="https://twitter.com/mozilla" class="social-icon twitter"><span class="visually-hidden">Mozilla on Twitter</span></a>
-   <a href="https://www.instagram.com/mozillagram/" class="social-icon instagram"><span class="visually-hidden">Mozilla on Instagram</span></a>

© 2005-2021 Mozilla and individual contributors. Content is available under [these licenses](https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
