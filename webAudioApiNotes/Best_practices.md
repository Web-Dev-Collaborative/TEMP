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
4.  <a href="Best_practices.html" class="breadcrumb-current-page"><span data-property="name">Web Audio API best practices</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Loading sounds/files](#loading_soundsfiles)
-   [Cross browser & legacy support](#cross_browser_legacy_support)
-   [Autoplay policy](#autoplay_policy)
-   [User control](#user_control)
-   [Setting AudioParam values](#setting_audioparam_values)

Web Audio API best practices
============================

There's no strict right or wrong way when writing creative code. As long as you consider security, performance, and accessibility, you can adapt to your own style. In this article, we'll share a number of *best practices* — guidelines, tips, and tricks for working with the Web Audio API.

[Loading sounds/files](#loading_soundsfiles "Permalink to Loading sounds/files")
--------------------------------------------------------------------------------

There are four main ways to load sound with the Web Audio API and it can be a little confusing as to which one you should use.

When working with files, you are looking at either the grabbing the file from an [`HTMLMediaElement`](../HTMLMediaElement.html) (i.e. an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element), or you're looking to fetch the file and decode it into a buffer. Both are legitimate ways of working, however, it's more common to use the former when you are working with full-length tracks, and the latter when working with shorter, more sample-like tracks.

Media elements have streaming support out of the box. The audio will start playing when the browser determines it can load the rest of the file before playing finishes. You can see an example of how to use this with the Web Audio API in the [Using the Web Audio API tutorial](Using_Web_Audio_API.html).

You will, however, have more control if you use a buffer node. You have to request the file and wait for it to load ([this section of our advanced article](Advanced_techniques.html#dial_up_%e2%80%94_loading_a_sound_sample) shows a good way to do it), but then you have access to the data directly, which means more precision, and more precise manipulation.

If you're looking to work with audio from the user's camera or microphone you can access it via the [Media Stream API](../Media_Streams_API.html) and the [`MediaStreamAudioSourceNode`](../MediaStreamAudioSourceNode.html) interface. This is good for WebRTC and situations where you might want to record or possibly analyze audio.

The last way is to generate your own sound, which can be done with either an [`OscillatorNode`](../OscillatorNode.html) or by creating a buffer and populating it with your own data. Check out the [tutorial here for creating your own instrument](Advanced_techniques.html) for information on creating sounds with oscillators and buffers.

[Cross browser & legacy support](#cross_browser_legacy_support "Permalink to Cross browser & legacy support")
-------------------------------------------------------------------------------------------------------------

The Web Audio API specification is constantly evolving and like most things on the web, there are some issues with it working consistently across browsers. Here we'll look at options for getting around cross-browser problems.

There's the <a href="https://github.com/chrisguttandin/standardized-audio-context" class="external"><code>standardised-audio-context</code></a> npm package, which creates API functionality consistently across browsers, filling holes as they are found. It's constantly in development and endeavours to keep up with the current specification.

There is also the option of libraries, of which there are a few depending on your use case. For a good all-rounder, <a href="https://howlerjs.com/" class="external">howler.js</a> is a good choice. It has cross-browser support and, provides a useful subset of functionality. Although it doesn't harness the full gamut of filters and other effects the Web Audio API comes with, you can do most of what you'd want to do.

If you are looking for sound creation or a more instrument-based option, <a href="https://tonejs.github.io/" class="external">tone.js</a> is a great library. It provides advanced scheduling capabilities, synths, and effects, and intuitive musical abstractions built on top of the Web Audio API.

<a href="https://github.com/bbc/r-audio" class="external">R-audio</a>, from the <a href="https://medium.com/bbc-design-engineering/r-audio-declarative-reactive-and-flexible-web-audio-graphs-in-react-102c44a1c69c" class="external">BBC's Research &amp; Development department</a>, is a library of React components aiming to provide a "more intuitive, declarative interface to Web Audio". If you're used to writing JSX it might be worth looking at.

[Autoplay policy](#autoplay_policy "Permalink to Autoplay policy")
------------------------------------------------------------------

Browsers have started to implement an autoplay policy, which in general can be summed up as:

> "Create or resume context from inside a user gesture".

But what does that mean in practice? A user gesture has been interpreted to mean a user-initiated event, normally a `click` event. Browser vendors decided that Web Audio contexts should not be allowed to automatically play audio; they should instead be started by a user. This is because autoplaying audio can be really annoying and obtrusive. But how do we handle this?

When you create an audio context (either offline or online) it is created with a `state`, which can be `suspended`, `running`, or `closed`.

When working with an [`AudioContext`](../AudioContext.html), if you create the audio context from inside a `click` event the state should automatically be set to `running`. Here is a simple example of creating the context from inside a `click` event:

    const button = document.querySelector('button');
    button.addEventListener('click', function() {
        const audioCtx = new AudioContext();
    }, false);

If however, you create the context outside of a user gesture, its state will be set to `suspended` and it will need to be started after user interaction. We can use the same click event example here, test for the state of the context and start it, if it is suspended, using the [`resume()`](../AudioContext/resume.html) method.

    const audioCtx = new AudioContext();
    const button = document.querySelector('button');

    button.addEventListener('click', function() {
          // check if context is in suspended state (autoplay policy)
        if (audioCtx.state === 'suspended') {
            audioCtx.resume();
        }
    }, false);

You might instead be working with an [`OfflineAudioContext`](../OfflineAudioContext.html), in which case you can resume the suspended audio context with the [`startRendering()`](../OfflineAudioContext/startRendering.html) method.

[User control](#user_control "Permalink to User control")
---------------------------------------------------------

If your website or application contains sound, you should allow the user control over it, otherwise again, it will become annoying. This can be achieved by play/stop and volume/mute controls. The [Using the Web Audio API](Using_Web_Audio_API.html) tutorial goes over how to do this.

If you have buttons that switch audio on and off, using the ARIA [`role="switch"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Switch_role) attribute on them is a good option for signalling to assistive technology what the button's exact purpose is, and therefore making the app more accessible. There's a <a href="https://codepen.io/Wilto/pen/ZoGoQm?editors=1100" class="external">demo of how to use it here</a>.

As you work with a lot of changing values within the Web Audio API and will want to provide users with control over these, the [`range input`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range) is often a good choice of control to use. It's a good option as you can set minimum and maximum values, as well as increments with the [`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-step) attribute.

[Setting AudioParam values](#setting_audioparam_values "Permalink to Setting AudioParam values")
------------------------------------------------------------------------------------------------

There are two ways to manipulate [`AudioNode`](../AudioNode.html) values, which are themselves objects of type [`AudioParam`](../AudioParam.html) interface. The first is to set the value directly via the property. So for instance if we want to change the `gain` value of a [`GainNode`](../GainNode.html) we would do so thus:

    gainNode.gain.value = 0.5;

This will set our volume to half. However, if you're using any of the `AudioParam`'s defined methods to set these values, they will take precedence over the above property setting. If for example, you want the `gain` value to be raised to 1 in 2 seconds time, you can do this:

    gainNode.gain.setValueAtTime(1, audioCtx.currentTime + 2);

It will override the previous example (as it should), even if it were to come later in your code.

Bearing this in mind, if your website or application requires timing and scheduling, it's best to stick with the [`AudioParam`](../AudioParam.html) methods for setting values. If you're sure it doesn't, setting it with the `value` property is fine.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/best_practices/index.html "Folder: en-us/web/api/web_audio_api/best_practices (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FBest_practices%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%2Fbest_practices%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FBest_practices%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Fbest_practices%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fd94cc67816001bee0b79b9dc0ec70337bf98df95%0A*+Document+last+modified%3A+2021-03-08T02%3A31%3A46.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Web+Audio+API+best+practices%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Mar 8, 2021, [by MDN contributors](Best_practices/contributors.txt)

Change your languageSelect your preferred language English (US)中文 (简体)

Change language

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
