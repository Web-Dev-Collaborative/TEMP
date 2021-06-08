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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode" class="breadcrumb-penultimate"><span data-property="name">PannerNode</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/panningModel" class="breadcrumb-current-page"><span data-property="name">PannerNode.panningModel</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

PannerNode.panningModel
=======================

The `panningModel` property of the [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode) interface is an enumerated value determining which spatialisation algorithm to use to position the audio in 3D space.

The possible values are:

-   `equalpower`: Represents the equal-power panning algorithm, generally regarded as simple and efficient. `equalpower` is the default value.
-   `HRTF`: Renders a stereo output of higher quality than `equalpower` — it uses a convolution with measured impulse responses from human subjects.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var audioCtx = new AudioContext();
    var panner = audioCtx.createPanner();
    panner.panningModel = 'HRTF';

### [Value](#value "Permalink to Value")

A enum — see <a href="https://webaudio.github.io/web-audio-api/#idl-def-PanningModelType" class="external"><code>PanningModelType</code></a>.

[Example](#example "Permalink to Example")
------------------------------------------

In the following example, you can see an example of how the `createPanner()` method, [`AudioListener`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener)  and [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode) would be used to control audio spatialisation. Generally you will define the position in 3D space that your audio listener and panner (source) occupy initially, and then update the position of one or both of these as the application is used. You might be moving a character around inside a game world for example, and wanting delivery of audio to change realistically as your character moves closer to or further away from a music player such as a stereo. In the example you can see this being controlled by the functions `moveRight()`, `moveLeft()`, etc., which set new values for the panner position via the `PositionPanner()` function.

To see a complete implementation, check out our <a href="https://mdn.github.io/webaudio-examples/panner-node/" class="external">panner-node example</a> (<a href="https://github.com/mdn/webaudio-examples/tree/master/panner-node" class="external">view the source code</a>) — this demo transports you to the 2.5D "Room of metal", where you can play a track on a boom box and then walk around the boom box to see how the sound changes!

Note how we have used some feature detection to either give the browser the newer property values (like [`AudioListener.forwardX`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/forwardX)) for setting position, etc. if it supports those, or older methods (like [`AudioListener.setOrientation()`](https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/setOrientation)) if it still supports those but not the new properties.

    // set up listener and panner position information
    var WIDTH = window.innerWidth;
    var HEIGHT = window.innerHeight;

    var xPos = Math.floor(WIDTH/2);
    var yPos = Math.floor(HEIGHT/2);
    var zPos = 295;

    // define other variables

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    var panner = audioCtx.createPanner();
    panner.panningModel = 'HRTF';
    panner.distanceModel = 'inverse';
    panner.refDistance = 1;
    panner.maxDistance = 10000;
    panner.rolloffFactor = 1;
    panner.coneInnerAngle = 360;
    panner.coneOuterAngle = 0;
    panner.coneOuterGain = 0;

    if(panner.orientationX) {
      panner.orientationX.setValueAtTime(1, audioCtx.currentTime);
      panner.orientationY.setValueAtTime(0, audioCtx.currentTime);
      panner.orientationZ.setValueAtTime(0, audioCtx.currentTime);
    } else {
      panner.setOrientation(1,0,0);
    }

    var listener = audioCtx.listener;

    if(listener.forwardX) {
      listener.forwardX.setValueAtTime(0, audioCtx.currentTime);
      listener.forwardY.setValueAtTime(0, audioCtx.currentTime);
      listener.forwardZ.setValueAtTime(-1, audioCtx.currentTime);
      listener.upX.setValueAtTime(0, audioCtx.currentTime);
      listener.upY.setValueAtTime(1, audioCtx.currentTime);
      listener.upZ.setValueAtTime(0, audioCtx.currentTime);
    } else {
      listener.setOrientation(0,0,-1,0,1,0);
    }

    var source;

    var play = document.querySelector('.play');
    var stop = document.querySelector('.stop');

    var boomBox = document.querySelector('.boom-box');

    var listenerData = document.querySelector('.listener-data');
    var pannerData = document.querySelector('.panner-data');

    leftBound = (-xPos) + 50;
    rightBound = xPos - 50;

    xIterator = WIDTH/150;

    // listener will always be in the same place for this demo

    if(listener.positionX) {
      listener.positionX.setValueAtTime(xPos, audioCtx.currentTime);
      listener.positionY.setValueAtTime(yPos, audioCtx.currentTime);
      listener.positionZ.setValueAtTime(300, audioCtx.currentTime);
    } else {
      listener.setPosition(xPos,yPos,300);
    }

    listenerData.textContent = `Listener data: X ${xPos} Y ${yPos} Z 300`;

    // panner will move as the boombox graphic moves around on the screen
    function positionPanner() {
      if(panner.positionX) {
        panner.positionX.setValueAtTime(xPos, audioCtx.currentTime);
        panner.positionY.setValueAtTime(yPos, audioCtx.currentTime);
        panner.positionZ.setValueAtTime(zPos, audioCtx.currentTime);
      } else {
        panner.setPosition(xPos,yPos,zPos);
      }
      pannerData.textContent = `Panner data: X ${xPos} Y ${yPos} Z ${zPos}`;
    }

#### Note

In terms of working out what position values to apply to the listener and panner, to make the sound appropriate to what the visuals are doing on screen, there is quite a bit of math involved, but you will soon get used to it with a bit of experimentation.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-pannernode-panningmodel" class="external">Web Audio API<br />
<span class="small">The definition of 'panningModel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/pannernode/panningmodel/index.html "Folder: en-us/web/api/pannernode/panningmodel (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FPannerNode%2FpanningModel%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fpannernode%2Fpanningmodel%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FPannerNode%2FpanningModel%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fpannernode%2Fpanningmodel%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fa2282aa45be910a103b93ad06396ee195a10f456%0A*+Document+last+modified%3A+2021-06-01T11%3A47%3A53.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22PannerNode.panningModel%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/panningModel/contributors.txt)

#### Related Topics

1.  **[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)**
2.  **[`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode)**
3.  Constructor
    1.  [`PannerNode()`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/PannerNode)
4.  Properties
    1.  [`coneInnerAngle`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneInnerAngle)
    2.  [`coneOuterAngle`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneOuterAngle)
    3.  [`coneOuterGain`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneOuterGain)
    4.  [`distanceModel`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/distanceModel)
    5.  [`maxDistance`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/maxDistance)
    6.  [`orientationX`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationX)
    7.  [`orientationY`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationY)
    8.  [`orientationZ`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationZ)
    9.  *`panningModel`*
    10. [`positionX`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionX)
    11. [`positionY`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionY)
    12. [`positionZ`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/positionZ)
    13. [`refDistance`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/refDistance)
    14. [`rolloffFactor`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/rolloffFactor)
5.  Methods
    1.  [`setOrientation()`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/setOrientation)
    2.  [`setPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/setPosition)
    3.  [`setVelocity()`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/setVelocity)
6.  Inheritance:
    1.  [`AudioNode`](https://developer.mozilla.org/en-US/docs/Web/API/AudioNode)
    2.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
7.  Related pages for Web Audio API
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

#### Mozilla

-   <a href="https://twitter.com/mozilla" class="social-icon twitter"><span class="visually-hidden">Mozilla on Twitter</span></a>
-   <a href="https://www.instagram.com/mozillagram/" class="social-icon instagram"><span class="visually-hidden">Mozilla on Instagram</span></a>

© 2005-2021 Mozilla and individual contributors. Content is available under [these licenses](https://developer.mozilla.org/docs/MDN/About#Copyrights_and_licenses).

-   [Terms](https://www.mozilla.org/about/legal/terms/mozilla)
-   [Privacy](https://www.mozilla.org/privacy/websites/)
-   [Cookies](https://www.mozilla.org/privacy/websites/#cookies)
