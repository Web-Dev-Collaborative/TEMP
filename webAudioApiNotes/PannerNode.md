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
3.  <a href="PannerNode.html" class="breadcrumb-current-page"><span data-property="name">PannerNode</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

PannerNode
==========

The `PannerNode` interface represents the position and behavior of an audio source signal in space. It is an [`AudioNode`](AudioNode.html) audio-processing module describing its position with right-hand Cartesian coordinates, its movement using a velocity vector and its directionality using a directionality cone.

A `PannerNode` always has exactly one input and one output: the input can be *mono* or *stereo* but the output is always *stereo* (2 channels); you can't have panning effects without at least two audio channels!

<img src="PannerNode/webaudiopannernode.png" alt="The PannerNode brings a spatial position and velocity and a directionality for a given signal." width="771" height="225" />

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"clamped-max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code></td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`PannerNode.PannerNode`](PannerNode/PannerNode.html)  
Creates a new `PannerNode` object instance.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*Inherits properties from its parent, [`AudioNode`](AudioNode.html)*.

The orientation and position value are set and retrieved using different syntaxes, since they're stored as [`AudioParam`](AudioParam.html) values. Retrieval is done by accessing, for example, `PannerNode.positionX`. While setting the same property is done with `PannerNode.positionX.value`. This is why these values are not marked read only, which is how they appear in the WebIDL.

[`PannerNode.coneInnerAngle`](PannerNode/coneInnerAngle.html)  
Is a double value describing the angle, in degrees, of a cone inside of which there will be no volume reduction.

[`PannerNode.coneOuterAngle`](PannerNode/coneOuterAngle.html)  
A double value describing the angle, in degrees, of a cone outside of which the volume will be reduced by a constant value, defined by the `coneOuterGain` attribute.

[`PannerNode.coneOuterGain`](PannerNode/coneOuterGain.html)  
A double value describing the amount of volume reduction outside the cone defined by the `coneOuterAngle` attribute. Its default value is `0`, meaning that no sound can be heard.

[`PannerNode.distanceModel`](PannerNode/distanceModel.html)  
An enumerated value determining which algorithm to use to reduce the volume of the audio source as it moves away from the listener. Possible values are `"linear"`, `"inverse"` and `"exponential"`. The default value is `"inverse"`.

[`PannerNode.maxDistance`](PannerNode/maxDistance.html)  
A double value representing the maximum distance between the audio source and the listener, after which the volume is not reduced any further.

[`PannerNode.orientationX`](PannerNode/orientationX.html)  
Represents the horizontal position of the audio source's vector in a right-hand cartesian coordinate system. While this [`AudioParam`](AudioParam.html) cannot be directly changed, its value can be altered using its [`value`](AudioParam/value.html "value") property. The default is value is 1.

[`PannerNode.orientationY`](PannerNode/orientationY.html)  
Represents the vertical position of the audio source's vector in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](AudioParam.html) cannot be directly changed, its value can be altered using its [`value`](AudioParam/value.html "value") property. The default is value is 0.

[`PannerNode.orientationZ`](PannerNode/orientationZ.html)  
Represents the longitudinal (back and forth) position of the audio source's vector in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](AudioParam.html) cannot be directly changed, its value can be altered using its [`value`](AudioParam/value.html "value") property. The default is value is 0.

[`PannerNode.panningModel`](PannerNode/panningModel.html)  
An enumerated value determining which spatialisation algorithm to use to position the audio in 3D space.

[`PannerNode.positionX`](PannerNode/positionX.html)  
Represents the horizontal position of the audio in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](AudioParam.html) cannot be directly changed, its value can be altered using its [`value`](AudioParam/value.html "value") property. The default is value is 0.

[`PannerNode.positionY`](PannerNode/positionY.html)  
Represents the vertical position of the audio in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](AudioParam.html) cannot be directly changed, its value can be altered using its [`value`](AudioParam/value.html "value") property. The default is value is 0.

[`PannerNode.positionZ`](PannerNode/positionZ.html)  
Represents the longitudinal (back and forth) position of the audio in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](AudioParam.html) cannot be directly changed, its value can be altered using its [`value`](AudioParam/value.html "value") property. The default is value is 0.

[`PannerNode.refDistance`](PannerNode/refDistance.html)  
A double value representing the reference distance for reducing volume as the audio source moves further from the listener. For distances greater than this the volume will be reduced based on `rolloffFactor` and `distanceModel`.

[`PannerNode.rolloffFactor`](PannerNode/rolloffFactor.html)  
A double value describing how quickly the volume is reduced as the source moves away from the listener. This value is used by all distance models.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*Inherits methods from its parent, [`AudioNode`](AudioNode.html)*.

[`PannerNode.setPosition()`](PannerNode/setPosition.html)   
Defines the position of the audio source relative to the listener (represented by an [`AudioListener`](AudioListener.html) object stored in the [`BaseAudioContext.listener`](BaseAudioContext/listener.html) attribute.)

[`PannerNode.setOrientation()`](PannerNode/setOrientation.html)   
Defines the direction the audio source is playing in.

[`PannerNode.setVelocity()`](PannerNode/setVelocity.html)   
Defines the velocity vector of the audio source — how fast it is moving and in what direction. In a previous version of the specification, the [`PannerNode`](PannerNode.html) had a velocity that could pitch up or down [`AudioBufferSourceNode`](AudioBufferSourceNode.html)s connected downstream. This feature was not clearly specified and had a number of issues, so it was removed from the specification.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

In the following example, you can see an example of how the `createPanner()` method, [`AudioListener`](AudioListener.html)  and [`PannerNode`](PannerNode.html) would be used to control audio spatialisation. Generally you will define the position in 3D space that your audio listener and panner (source) occupy initially, and then update the position of one or both of these as the application is used. You might be moving a character around inside a game world for example, and wanting delivery of audio to change realistically as your character moves closer to or further away from a music player such as a stereo. In the example you can see this being controlled by the functions `moveRight()`, `moveLeft()`, etc., which set new values for the panner position via the `PositionPanner()` function.

To see a complete implementation, check out our <a href="https://mdn.github.io/webaudio-examples/panner-node/" class="external">panner-node example</a> (<a href="https://github.com/mdn/webaudio-examples/tree/master/panner-node" class="external">view the source code</a>) — this demo transports you to the 2.5D "Room of metal", where you can play a track on a boom box and then walk around the boom box to see how the sound changes!

Note how we have used some feature detection to either give the browser the newer property values (like [`AudioListener.forwardX`](AudioListener/forwardX.html)) for setting position, etc. if it supports those, or older methods (like [`AudioListener.setOrientation()`](AudioListener/setOrientation.html)) if it still supports those but not the new properties.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#pannernode" class="external">Web Audio API<br />
<span class="small">The definition of 'PannerNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/pannernode/index.html "Folder: en-us/web/api/pannernode (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FPannerNode%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fpannernode%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FPannerNode%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fpannernode%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fa2282aa45be910a103b93ad06396ee195a10f456%0A*+Document+last+modified%3A+2021-06-01T11%3A47%3A53.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22PannerNode%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](PannerNode/contributors.txt)

Change your languageSelect your preferred language English (US)日本語Русский

Change language

#### Related Topics

1.  **[Web Audio API](Web_Audio_API.html)**
2.  **[`PannerNode`](PannerNode.html)**
3.  Constructor
    1.  [`PannerNode()`](PannerNode/PannerNode.html)
4.  Properties
    1.  [`coneInnerAngle`](PannerNode/coneInnerAngle.html)
    2.  [`coneOuterAngle`](PannerNode/coneOuterAngle.html)
    3.  [`coneOuterGain`](PannerNode/coneOuterGain.html)
    4.  [`distanceModel`](PannerNode/distanceModel.html)
    5.  [`maxDistance`](PannerNode/maxDistance.html)
    6.  [`orientationX`](PannerNode/orientationX.html)
    7.  [`orientationY`](PannerNode/orientationY.html)
    8.  [`orientationZ`](PannerNode/orientationZ.html)
    9.  [`panningModel`](PannerNode/panningModel.html)
    10. [`positionX`](PannerNode/positionX.html)
    11. [`positionY`](PannerNode/positionY.html)
    12. [`positionZ`](PannerNode/positionZ.html)
    13. [`refDistance`](PannerNode/refDistance.html)
    14. [`rolloffFactor`](PannerNode/rolloffFactor.html)
5.  Methods
    1.  [`setOrientation()`](PannerNode/setOrientation.html)
    2.  [`setPosition()`](PannerNode/setPosition.html)
    3.  [`setVelocity()`](PannerNode/setVelocity.html)
6.  Inheritance:
    1.  [`AudioNode`](AudioNode.html)
    2.  [`EventTarget`](EventTarget.html)
7.  Related pages for Web Audio API
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
