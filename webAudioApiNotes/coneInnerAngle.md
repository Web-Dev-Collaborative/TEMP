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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneInnerAngle" class="breadcrumb-current-page"><span data-property="name">PannerNode.coneInnerAngle</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

PannerNode.coneInnerAngle
=========================

The `coneInnerAngle` property of the [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode) interface is a double value describing the angle, in degrees, of a cone inside of which there will be no volume reduction.

The `coneInnerAngle` property's default value is `360`, suitable for a non-directional source.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    var audioCtx = new AudioContext();
    var panner = audioCtx.createPanner();
    panner.coneInnerAngle = 360;

### [Value](#value "Permalink to Value")

A double.

[Example](#example "Permalink to Example")
------------------------------------------

In this example, we'll demonstrate how changing the orientation parameters of a [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode) in combination with [`coneInnerAngle`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneInnerAngle "coneInnerAngle") and [`coneOuterAngle`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneOuterAngle "coneOuterAngle") affects volume. To help us visualise how the orientation vector affects, we can use the <a href="https://en.wikipedia.org/wiki/Right-hand_rule" class="external">Right-hand rule</a>:

<img src="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationX/pannernode-orientation.png" alt="This chart visualises how the PannerNode orientation vectors affect the direction of the sound cone." width="935" height="381" />

First, let's start by writing a utility function to figure out our *orientation vector.* The X and Z components are always at a 90° to each other, so we can use the sine and cosine functions, which are offset by the same amount in radians. However, normally this would mean the [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode) points to the **left** of the listener at 0° rotation – since \`x = cos(0) = 1\` and \`z = sin(0) = 0\`. It's more useful to offset the angle by -90°, which means the [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode) will point **directly at the listener** at 0° rotation.

    // this utility converts amount of rotation around the Y axis
    // (i.e. rotation in the 'horizontal plane') to an orientation vector
    const yRotationToVector = degrees => {
      // convert degrees to radians and offset the angle so 0 points towards the listener
      const radians = (degrees - 90) * (Math.PI / 180);
      // using cosine and sine here ensures the output values are always normalized
      // i.e. they range between -1 and 1
      const x = Math.cos(radians);
      const z = Math.sin(radians);

      // we hard-code the Y component to 0, as Y is the axis of rotation
      return [x, 0, z];
    };

Now we can create our [`AudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext), an oscillator and a [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode):

    const context = new AudioContext();

    const osc = new OscillatorNode(context);
    osc.type = 'sawtooth';

    const panner = new PannerNode(context);
    panner.panningModel = 'HRTF';

Next, we set up the *cone* of our spatialised sound, determining the area in which it can be heard:

    // this value determines the size of the area in which the sound volume is constant
    // if coneInnerAngle == 30, it means that when the sound is rotated
    // by at most 15 (30/2) degrees either direction, the volume won't change
    panner.coneInnerAngle = 30;
    // this value determines the size of the area in which the sound volume decreases gradually
    // if coneOuterAngle == 45 and coneInnerAngle == 30, it means that when the sound is rotated
    // by between 15 (30/2) and 22.5 (45/2) degrees either direction,
    // the volume will decrease gradually
    panner.coneOuterAngle = 45;
    // this value determines the volume of the sound outside of both inner and outer cone
    // setting it to 0 means there is no sound, so we can clearly hear when we leave the cone
    // 0 is also the default
    panner.coneOuterGain = 0;
    // increase the Z position to ensure the cone has an effect
    // (otherwise the sound is located at the same position as the listener)
    panner.positionZ.setValueAtTime(1, context.currentTime);

Having set up the [`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode), we can now schedule some updates to its Y-axis rotation:

    // calculate the vector for no rotation
    // this means the sound will play at full volume
    const [x1, y1, z1] = yRotationToVector(0);
    // schedule the no-rotation vector immediately
    panner.orientationX.setValueAtTime(x1, context.currentTime);
    panner.orientationY.setValueAtTime(y1, context.currentTime);
    panner.orientationZ.setValueAtTime(z1, context.currentTime);

    // calculate the vector for -22.4 degrees
    // since our coneOuterAngle is 45, this will just about make the sound audible
    // if we set it to +/-22.5, the sound volume will be 0, as the threshold is exclusive
    const [x2, y2, z2] = yRotationToVector(-22.4);
    panner.orientationX.setValueAtTime(x2, context.currentTime + 2);
    panner.orientationY.setValueAtTime(y2, context.currentTime + 2);
    panner.orientationZ.setValueAtTime(z2, context.currentTime + 2);

Finally, let's connect all our nodes and start the oscillator! 

    osc.connect(panner)
       .connect(context.destination);

    osc.start(0);

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-pannernode-coneinnerangle" class="external">Web Audio API<br />
<span class="small">The definition of 'coneInnerAngle' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)
-   [Web Audio spatialisation basics](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Web_audio_spatialization_basics)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/pannernode/coneinnerangle/index.html "Folder: en-us/web/api/pannernode/coneinnerangle (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FPannerNode%2FconeInnerAngle%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fpannernode%2Fconeinnerangle%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FPannerNode%2FconeInnerAngle%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fpannernode%2Fconeinnerangle%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fa2282aa45be910a103b93ad06396ee195a10f456%0A*+Document+last+modified%3A+2021-06-01T11%3A47%3A53.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22PannerNode.coneInnerAngle%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneInnerAngle/contributors.txt)

Change your languageSelect your preferred language English (US)日本語

Change language

#### Related Topics

1.  **[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)**
2.  **[`PannerNode`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode)**
3.  Constructor
    1.  [`PannerNode()`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/PannerNode)
4.  Properties
    1.  *`coneInnerAngle`*
    2.  [`coneOuterAngle`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneOuterAngle)
    3.  [`coneOuterGain`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/coneOuterGain)
    4.  [`distanceModel`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/distanceModel)
    5.  [`maxDistance`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/maxDistance)
    6.  [`orientationX`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationX)
    7.  [`orientationY`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationY)
    8.  [`orientationZ`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/orientationZ)
    9.  [`panningModel`](https://developer.mozilla.org/en-US/docs/Web/API/PannerNode/panningModel)
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
