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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode" class="breadcrumb-penultimate"><span data-property="name">MediaStreamTrackAudioSourceNode</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode/MediaStreamTrackAudioSourceNode" class="breadcrumb-current-page"><span data-property="name">MediaStreamTrackAudioSourceNode()</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)

MediaStreamTrackAudioSourceNode()
=================================

<span class="seoSummary">The [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)'s `MediaStreamTrackAudioSourceNode()` constructor creates and returns a new [`MediaStreamTrackAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode) object whose audio is taken from the [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) specified in the given options object.</span>

Another way to create a `MediaStreamTrackAudioSourceNode` is to call the[`AudioContext.createMediaStreamTrackSource()`](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaStreamTrackSource) method, specifying the [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)  from which you want to obtain audio.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    audioTrackNode = new MediaStreamTrackAudioSourceNode(context, options);

### [Parameters](#parameters "Permalink to Parameters")

`context`  
An [`AudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext) representing the audio context you want the node to be associated with.

`options`  
A [`MediaStreamTrackAudioSourceOptions`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceOptions) object defining the properties you want the `MediaStreamTrackAudioSourceNode` to have:

[`mediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceOptions/mediaStreamTrack "mediaStreamTrack")  
The [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) from which to take audio data for this node's output.

### [Return value](#return_value "Permalink to Return value")

A new [`MediaStreamTrackAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode) object representing the audio node whose media is obtained from the specified media track.

### [Exceptions](#exceptions "Permalink to Exceptions")

`NotSupportedError`  
The specified `context` is not an [`AudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext).

`InvalidStateError`  
The specified [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) isn't an audio track (that is, its [`kind`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/kind "kind") property isn't `audio`.

[Example](#example "Permalink to Example")
------------------------------------------

This example uses [`getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia "getUserMedia()") to obtain access to the user's camera, then creates a new [`MediaStreamAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode) from the first audio track provided by the device.

    let audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    if (navigator.mediaDevices.getUserMedia) {
      navigator.mediaDevices.getUserMedia (
        {
          audio: true,
          video: false
        }).then(function(stream) {
          let options = {
            mediaStreamTrack: stream.getAudioTracks()[0];
          }

          let source = new MediaStreamTrackAudioSourceNode(audioCtx, options);
          source.connect(audioCtx.destination);
        }).catch(function(err) {
          console.log('The following gUM error occurred: ' + err);
        });
    } else {
      console.log('new getUserMedia not supported on your browser!');
    }

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-mediastreamtrackaudiosourcenode-mediastreamtrackaudiosourcenode" class="external">Web Audio API<br />
<span class="small">The definition of 'MediaStreamTrackAudioSourceNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediastreamtrackaudiosourcenode/mediastreamtrackaudiosourcenode/index.html "Folder: en-us/web/api/mediastreamtrackaudiosourcenode/mediastreamtrackaudiosourcenode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrackAudioSourceNode%2FMediaStreamTrackAudioSourceNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediastreamtrackaudiosourcenode%2Fmediastreamtrackaudiosourcenode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaStreamTrackAudioSourceNode%2FMediaStreamTrackAudioSourceNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediastreamtrackaudiosourcenode%2Fmediastreamtrackaudiosourcenode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaStreamTrackAudioSourceNode%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode/MediaStreamTrackAudioSourceNode/contributors.txt)

#### Related Topics

1.  **[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)**
2.  **[`MediaStreamTrackAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackAudioSourceNode)**
3.  Related pages for Web Audio API
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
    26. [`IIRFilterNode`](https://developer.mozilla.org/en-US/docs/Web/API/IIRFilterNode)
    27. [`MediaElementAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaElementAudioSourceNode)
    28. [`MediaStreamAudioDestinationNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioDestinationNode)
    29. [`MediaStreamAudioSourceNode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioSourceNode)
    30. [`OfflineAudioCompletionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioCompletionEvent)
    31. [`OfflineAudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext)
    32. [`OscillatorNode`](https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode)
    33. [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode)
    34. [`PeriodicWave`](https://developer.mozilla.org/en-US/docs/Web/API/PeriodicWave)
    35. [`StereoPannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/StereoPannerNode)
    36. [`WaveShaperNode`](https://developer.mozilla.org/en-US/docs/Web/API/WaveShaperNode)

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
