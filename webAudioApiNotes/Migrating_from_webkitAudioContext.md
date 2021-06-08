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
4.  <a href="Migrating_from_webkitAudioContext.html" class="breadcrumb-current-page"><span data-property="name">Migrating from webkitAudioContext</span></a>

Table of contents
-----------------

Table of contents

-   [Changes to the creator methods](#changes_to_the_creator_methods)
-   [Changes to starting and stopping nodes](#changes_to_starting_and_stopping_nodes)
-   [Remove synchronous buffer creation](#remove_synchronous_buffer_creation)
-   [Renaming of AudioParam.setTargetValueAtTime](#renaming_of_audioparam.settargetvalueattime)
-   [Enumerated values that changed](#enumerated_values_that_changed)
-   [Gain control moved to its own node type](#gain_control_moved_to_its_own_node_type)
-   [Removal of AudioBufferSourceNode.looping](#removal_of_audiobuffersourcenode.looping)
-   [Changes to determining playback state](#changes_to_determining_playback_state)
-   [Removal of AudioContext.activeSourceCount](#removal_of_audiocontext.activesourcecount)
-   [Renaming of WaveTable](#renaming_of_wavetable)
-   [Removal of some of the AudioParam read-only attributes](#removal_of_some_of_the_audioparam_read-only_attributes)
-   [Removal of MediaElementAudioSourceNode.mediaElement](#removal_of_mediaelementaudiosourcenode.mediaelement)
-   [Removal of MediaStreamAudioSourceNode.mediaStream](#removal_of_mediastreamaudiosourcenode.mediastream)

Migrating from webkitAudioContext
=================================

The Web Audio API went through many iterations before reaching its current state. It was first implemented in WebKit, and some of its older parts were not immediately removed as they were replaced in the specification, leading to many sites using non-compatible code. <span class="seoSummary">In this article, we cover the differences in Web Audio API since it was first implemented in WebKit and how to update your code to use the modern Web Audio API.</span>

The Web Audio standard was first implemented in <a href="https://webkit.org/" class="external">WebKit</a>, and the implementation was built in parallel with the work on the <a href="https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html" class="external">specification</a> of the API. As the specification evolved and changes were made to the spec, some of the old implementation pieces were not removed from the WebKit (and Blink) implementations due to backwards compatibility reasons.

New engines implementing the Web Audio spec (such as Gecko) will only implement the official, final version of the specification, which means that code using `webkitAudioContext` or old naming conventions in the Web Audio specification may not immediately work out of the box in a compliant Web Audio implementation.  This article attempts to summarize the areas where developers are likely to encounter these problems and provide examples on how to port such code to standards based [`AudioContext`](../AudioContext.html), which will work across different browser engines.

**Note**: There is a library called <a href="https://github.com/cwilso/webkitAudioContext-MonkeyPatch" class="external">webkitAudioContext monkeypatch</a>, which automatically fixes some of these changes to make most code targeting `webkitAudioContext` to work on the standards based `AudioContext` out of the box, but it currently doesn't handle all of the cases below.  Please consult the <a href="https://github.com/cwilso/webkitAudioContext-MonkeyPatch/blob/gh-pages/README.md" class="external">README file</a> for that library to see a list of APIs that are automatically handled by it.

[Changes to the creator methods](#changes_to_the_creator_methods "Permalink to Changes to the creator methods")
---------------------------------------------------------------------------------------------------------------

Three of the creator methods on `webkitAudioContext` have been renamed in [`AudioContext`](../AudioContext.html).

-   `createGainNode()` has been renamed to <span class="page-not-created">`createGain`</span>.
-   `createDelayNode()` has been renamed to <span class="page-not-created">`createDelay`</span>.
-   `createJavaScriptNode()` has been renamed to <span class="page-not-created">`createScriptProcessor`</span>.

These are simple renames that were made in order to improve the consistency of these method names on [`AudioContext`](../AudioContext.html).  If your code uses either of these names, like in the example below :

    // Old method names
    var gain = context.createGainNode();
    var delay = context.createDelayNode();
    var js = context.createJavascriptNode(1024);

you can rename the methods to look like this:

    // New method names
    var gain = context.createGain();
    var delay = context.createDelay();
    var js = context.createScriptProcessor(1024);

The semantics of these methods remain the same in the renamed versions.

[Changes to starting and stopping nodes](#changes_to_starting_and_stopping_nodes "Permalink to Changes to starting and stopping nodes")
---------------------------------------------------------------------------------------------------------------------------------------

In `webkitAudioContext`, there are two ways to start and stop [`AudioBufferSourceNode`](../AudioBufferSourceNode.html) and [`OscillatorNode`](../OscillatorNode.html): the `noteOn()` and `noteOff()` methods, and the `start()` and `stop()` methods.  (<span class="page-not-created">`AudioBufferSourceNode `</span>has yet another way of starting output: the `noteGrainOn()` method.)  The `noteOn()`/`noteGrainOn()`/`noteOff()` methods were the original way to start/stop output in these nodes, and in the newer versions of the specification, the `noteOn()` and `noteGrainOn()` methods were consolidated into a single `start()` method, and the `noteOff()` method was renamed to the `stop()` method.

In order to port your code, you can just rename the method that you're using.  For example, if you have code like the below:

    var osc = context.createOscillator();
    osc.noteOn(1);
    osc.noteOff(1.5);

    var src = context.createBufferSource();
    src.noteGrainOn(1, 0.25);
    src.noteOff(2);

you can change it like this in order to port it to the standard AudioContext API:

    var osc = context.createOscillator();
    osc.start(1);
    osc.stop(1.5);

    var src = context.createBufferSource();
    src.start(1, 0.25);
    src.stop(2);

[Remove synchronous buffer creation](#remove_synchronous_buffer_creation "Permalink to Remove synchronous buffer creation")
---------------------------------------------------------------------------------------------------------------------------

In the old WebKit implementation of Web Audio, there were two versions of `createBuffer()`, one which created an initially empty buffer, and one which took an existing [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing encoded audio, decoded it and returned the result in the form of an [`AudioBuffer`](../AudioBuffer.html).  The latter version of `createBuffer()` was potentially expensive, because it had to decode the audio buffer synchronously, and with the buffer being arbitrarily large, it could take a lot of time for this method to complete its work, and no other part of your web page's code could execute in the mean time.

Because of these problems, this version of the `createBuffer()` method has been removed, and you should use the asynchronous `decodeAudioData()` method instead.

The example below shows old code which downloads an audio file over the network, and then decoded it using `createBuffer()`:

    var xhr = new XMLHttpRequest();
    xhr.open("GET", "/path/to/audio.ogg", true);
    xhr.responseType = "arraybuffer";
    xhr.send();
    xhr.onload = function() {
      var decodedBuffer = context.createBuffer(xhr.response, false);
      if (decodedBuffer) {
        // Decoding was successful, do something useful with the audio buffer
      } else {
        alert("Decoding the audio buffer failed");
      }
    };

Converting this code to use `decodeAudioData()` is relatively simple, as can be seen below:

    var xhr = new XMLHttpRequest();
    xhr.open("GET", "/path/to/audio.ogg", true);
    xhr.responseType = "arraybuffer";
    xhr.send();
    xhr.onload = function() {
      context.decodeAudioData(xhr.response, function onSuccess(decodedBuffer) {
        // Decoding was successful, do something useful with the audio buffer
      }, function onFailure() {
        alert("Decoding the audio buffer failed");
      });
    };

Note that the `decodeAudioData()` method is asynchronous, which means that it will return immediately, and then when the decoding finishes, one of the success or failure callback functions will get called depending on whether the audio decoding was successful.  This means that you may need to restructure your code to run the part which happened after the `createBuffer()` call in the success callback, as you can see in the example above.

[Renaming of AudioParam.setTargetValueAtTime](#renaming_of_audioparam.settargetvalueattime "Permalink to Renaming of AudioParam.setTargetValueAtTime")
------------------------------------------------------------------------------------------------------------------------------------------------------

The `setTargetValueAtTime()` method on the [`AudioParam`](../AudioParam.html) interface has been renamed to `setTargetAtTime()`.  This is also a simple rename to improve the understandability of the API, and the semantics of the method are the same.  If your code is using `setTargetValueAtTime()`, you can rename it to use `setTargetAtTime()`. For example, if we have code that looks like this:

      var gainNode = context.createGain();
      gainNode.gain.setTargetValueAtTime(0.0, 10.0, 1.0);

you can rename the method, and be compliant with the standard, like so:

      var gainNode = context.createGain();
      gainNode.gain.setTargetAtTime(0.0, 10.0, 1.0);

[Enumerated values that changed](#enumerated_values_that_changed "Permalink to Enumerated values that changed")
---------------------------------------------------------------------------------------------------------------

The original `webkitAudioContext` API used C-style number based enumerated values in the API.  Those values have since been changed to use the Web IDL based enumerated values, which should be familiar because they are similar to things like the [`HTMLInputElement`](../HTMLInputElement.html) property <span class="page-not-created">`type`</span>.

### [OscillatorNode.type](#oscillatornode.type "Permalink to OscillatorNode.type")

[`OscillatorNode`](../OscillatorNode.html)'s type property has been changed to use Web IDL enums.  Old code using `webkitAudioContext` can be ported to standards based [`AudioContext`](../AudioContext.html) like below:

    // Old webkitAudioContext code:
    var osc = context.createOscillator();
    osc.type = osc.SINE;     // sine waveform
    osc.type = osc.SQUARE;   // square waveform
    osc.type = osc.SAWTOOTH; // sawtooth waveform
    osc.type = osc.TRIANGLE; // triangle waveform
    osc.setWaveTable(table);
    var isCustom = (osc.type == osc.CUSTOM); // isCustom will be true

    // New standard AudioContext code:
    var osc = context.createOscillator();
    osc.type = "sine";       // sine waveform
    osc.type = "square";     // square waveform
    osc.type = "sawtooth";   // sawtooth waveform
    osc.type = "triangle";   // triangle waveform
    osc.setPeriodicWave(table);  // Note: setWaveTable has been renamed to setPeriodicWave!
    var isCustom = (osc.type == "custom"); // isCustom will be true

### [BiquadFilterNode.type](#biquadfilternode.type "Permalink to BiquadFilterNode.type")

[`BiquadFilterNode`](../BiquadFilterNode.html)'s type property has been changed to use Web IDL enums.  Old code using `webkitAudioContext` can be ported to standards based [`AudioContext`](../AudioContext.html) like below:

    // Old webkitAudioContext code:
    var filter = context.createBiquadFilter();
    filter.type = filter.LOWPASS;   // lowpass filter
    filter.type = filter.HIGHPASS;  // highpass filter
    filter.type = filter.BANDPASS;  // bandpass filter
    filter.type = filter.LOWSHELF;  // lowshelf filter
    filter.type = filter.HIGHSHELF; // highshelf filter
    filter.type = filter.PEAKING;   // peaking filter
    filter.type = filter.NOTCH;     // notch filter
    filter.type = filter.ALLPASS;   // allpass filter

    // New standard AudioContext code:
    var filter = context.createBiquadFilter();
    filter.type = "lowpass";        // lowpass filter
    filter.type = "highpass";       // highpass filter
    filter.type = "bandpass";       // bandpass filter
    filter.type = "lowshelf";       // lowshelf filter
    filter.type = "highshelf";      // highshelf filter
    filter.type = "peaking";        // peaking filter
    filter.type = "notch";          // notch filter
    filter.type = "allpass";        // allpass filter

### [PannerNode.panningModel](#pannernode.panningmodel "Permalink to PannerNode.panningModel")

[`PannerNode`](../PannerNode.html)'s panningModel property has been changed to use Web IDL enums.  Old code using `webkitAudioContext` can be ported to standards based [`AudioContext`](../AudioContext.html) like below:

    // Old webkitAudioContext code:
    var panner = context.createPanner();
    panner.panningModel = panner.EQUALPOWER;  // equalpower panning
    panner.panningModel = panner.HRTF;        // HRTF panning

    // New standard AudioContext code:
    var panner = context.createPanner();
    panner.panningModel = "equalpower";       // equalpower panning
    panner.panningModel = "HRTF";             // HRTF panning

### [PannerNode.distanceModel](#pannernode.distancemodel "Permalink to PannerNode.distanceModel")

[`PannerNode`](../PannerNode.html)'s `distanceModel` property has been changed to use Web IDL enums.  Old code using `webkitAudioContext` can be ported to standards based [`AudioContext`](../AudioContext.html) like below:

    // Old webkitAudioContext code:
    var panner = context.createPanner();
    panner.distanceModel = panner.LINEAR_DISTANCE;      // linear distance model
    panner.distanceModel = panner.INVERSE_DISTANCE;     // inverse distance model
    panner.distanceModel = panner.EXPONENTIAL_DISTANCE; // exponential distance model

    // Mew standard AudioContext code:
    var panner = context.createPanner();
    panner.distanceModel = "linear";                    // linear distance model
    panner.distanceModel = "inverse";                   // inverse distance model
    panner.distanceModel = "exponential";               // exponential distance model

[Gain control moved to its own node type](#gain_control_moved_to_its_own_node_type "Permalink to Gain control moved to its own node type")
------------------------------------------------------------------------------------------------------------------------------------------

The Web Audio standard now controls all gain using the [`GainNode`](../GainNode.html). Instead of setting a `gain` property directly on an audio source, you connect the source to a gain node and then control the gain using that node's `gain` parameter.

### [AudioBufferSourceNode](#audiobuffersourcenode "Permalink to AudioBufferSourceNode")

The `gain` attribute of [`AudioBufferSourceNode`](../AudioBufferSourceNode.html) has been removed.  The same functionality can be achieved by connecting the [`AudioBufferSourceNode`](../AudioBufferSourceNode.html) to a gain node.  See the following example:

    // Old webkitAudioContext code:
    var src = context.createBufferSource();
    src.buffer = someBuffer;
    src.gain.value = 0.5;
    src.connect(context.destination);
    src.noteOn(0);

    // New standard AudioContext code:
    var src = context.createBufferSource();
    src.buffer = someBuffer;
    var gain = context.createGain();
    src.connect(gain);
    gain.gain.value = 0.5;
    gain.connect(context.destination);
    src.start(0);

### [AudioBuffer](#audiobuffer "Permalink to AudioBuffer")

The `gain` attribute of [`AudioBuffer`](../AudioBuffer.html) has been removed.  The same functionality can be achieved by connecting the [`AudioBufferSourceNode`](../AudioBufferSourceNode.html) that owns the buffer to a gain node.  See the following example:

    // Old webkitAudioContext code:
    var src = context.createBufferSource();
    src.buffer = someBuffer;
    src.buffer.gain = 0.5;
    src.connect(context.destination);
    src.noteOn(0);

    // New standard AudioContext code:
    var src = context.createBufferSource();
    src.buffer = someBuffer;
    var gain = context.createGain();
    src.connect(gain);
    gain.gain.value = 0.5;
    gain.connect(context.destination);
    src.start(0);

[Removal of AudioBufferSourceNode.looping](#removal_of_audiobuffersourcenode.looping "Permalink to Removal of AudioBufferSourceNode.looping")
---------------------------------------------------------------------------------------------------------------------------------------------

The `looping` attribute of [`AudioBufferSourceNode`](../AudioBufferSourceNode.html) has been removed.  This attribute was an alias of the `loop` attribute, so you can just use the `loop` attribute instead. Instead of having code like this:

    var source = context.createBufferSource();
    source.looping = true;

you can change it to respect the last version of the specification:

    var source = context.createBufferSource();
    source.loop = true;

Note, the `loopStart` and `loopEnd` attributes are not supported in `webkitAudioContext`.

[Changes to determining playback state](#changes_to_determining_playback_state "Permalink to Changes to determining playback state")
------------------------------------------------------------------------------------------------------------------------------------

The `playbackState` attribute of [`AudioBufferSourceNode`](../AudioBufferSourceNode.html) and [`OscillatorNode`](../OscillatorNode.html) has been removed.  Depending on why you used this attribute, you can use the following techniques to get the same information:

-   If you need to compare this attribute to `UNSCHEDULED_STATE`, you can basically remember whether you've called `start()` on the node or not.
-   If you need to compare this attribute to `SCHEDULED_STATE`, you can basically remember whether you've called `start()` on the node or not.  You can compare the value of [`AudioContext.currentTime`](../BaseAudioContext/currentTime.html) to the first argument passed to `start()` to know whether playback has started or not.
-   If you need to compare this attribute to `PLAYING_STATE`, you can compare the value of [`AudioContext.currentTime`](../BaseAudioContext/currentTime.html) to the first argument passed to `start()` to know whether playback has started or not.
-   If you need to know when playback of the node is finished (which is the most significant use case of `playbackState`), there is a new ended event which you can use to know when playback is finished.  Please see this code example:

<!-- -->

    // Old webkitAudioContext code:
    var src = context.createBufferSource();
    // Some time later...
    var isFinished = (src.playbackState == src.FINISHED_STATE);

    // New AudioContext code:
    var src = context.createBufferSource();
    function endedHandler(event) {
      isFinished = true;
    }
    var isFinished = false;
    src.onended = endedHandler;

The exact same changes have been applied to both [`AudioBufferSourceNode`](../AudioBufferSourceNode.html) and [`OscillatorNode`](../OscillatorNode.html), so you can apply the same techniques to both kinds of nodes.

[Removal of AudioContext.activeSourceCount](#removal_of_audiocontext.activesourcecount "Permalink to Removal of AudioContext.activeSourceCount")
------------------------------------------------------------------------------------------------------------------------------------------------

The `activeSourceCount` attribute has been removed from [`AudioContext`](../AudioContext.html).  If you need to count the number of playing source nodes, you can maintain the count by handling the ended event on the source nodes, as shown above.

Code using the `activeSourceCount` attribute of the [`AudioContext`](../AudioContext.html), like this snippet:

      var src0 = context.createBufferSource();
      var src1 = context.createBufferSource();
      // Set buffers and other parameters...
      src0.start(0);
      src1.start(0);
      // Some time later...
      console.log(context.activeSourceCount);

could be rewritten like that:

      // Array to track the playing source nodes:
      var sources = [];
      // When starting the source, put it at the end of the array,
      // and set a handler to make sure it gets removed when the
      // AudioBufferSourceNode reaches its end.
      // First argument is the AudioBufferSourceNode to start, other arguments are
      // the argument to the |start()| method of the AudioBufferSourceNode.
      function startSource() {
        var src = arguments[0];
        var startArgs = Array.prototype.slice.call(arguments, 1);
        src.onended = function() {
          sources.splice(sources.indexOf(src), 1);
        }
        sources.push(src);
        src.start.apply(src, startArgs);
      }
      function activeSources() {
        return sources.length;
      }
      var src0 = context.createBufferSource();
      var src0 = context.createBufferSource();
      // Set buffers and other parameters...
      startSource(src0, 0);
      startSource(src1, 0);
      // Some time later, query the number of sources...
      console.log(activeSources());

[Renaming of WaveTable](#renaming_of_wavetable "Permalink to Renaming of WaveTable")
------------------------------------------------------------------------------------

The <span class="page-not-created">`WaveTable`</span> interface has been renamed to [`PeriodicWave`](../PeriodicWave.html).  Here is how you can port old code using `WaveTable` to the standard AudioContext API:

    // Old webkitAudioContext code:
    var osc = context.createOscillator();
    var table = context.createWaveTable(realArray, imaginaryArray);
    osc.setWaveTable(table);

    // New standard AudioContext code:
    var osc = context.createOscillator();
    var table = context.createPeriodicWave(realArray, imaginaryArray);
    osc.setPeriodicWave(table);

[Removal of some of the AudioParam read-only attributes](#removal_of_some_of_the_audioparam_read-only_attributes "Permalink to Removal of some of the AudioParam read-only attributes")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The following read-only attributes have been removed from AudioParam: `name`, `units`, `minValue`, and `maxValue`.  These used to be informational attributes.  Here is some information on how you can get these values if you need them:

-   The `name` attribute is a string representing the name of the [`AudioParam`](../AudioParam.html) object.  For example, the name of [`GainNode.gain`](../GainNode/gain.html) is `"gain"`.  You can track where the [`AudioParam`](../AudioParam.html) object is coming from in your code if you need this information.
-   The `minValue` and `maxValue` attributes are read-only values representing the nominal range for the [`AudioParam`](../AudioParam.html).  For example, for [`GainNode`](../GainNode.html), these values are 0 and 1, respectively.  Note that these bounds are not enforced by the engine, and are merely used for informational purposes.  As an example, it's perfectly valid to set a gain value to 2, or even -1.  In order to find out these nominal values, you can consult the <a href="https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html" class="external">specification</a>.
-   The `units` attribute as implemented in `webkitAudioContext` implementations is unused, and always returns 0.  There is no reason why you should need this attribute.

[Removal of MediaElementAudioSourceNode.mediaElement](#removal_of_mediaelementaudiosourcenode.mediaelement "Permalink to Removal of MediaElementAudioSourceNode.mediaElement")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The `mediaElement` attribute of [`MediaElementAudioSourceNode`](../MediaElementAudioSourceNode.html) has been removed.  You can keep a reference to the media element used to create this node if you need to access it later.

[Removal of MediaStreamAudioSourceNode.mediaStream](#removal_of_mediastreamaudiosourcenode.mediastream "Permalink to Removal of MediaStreamAudioSourceNode.mediaStream")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The `mediaStream` attribute of [`MediaStreamAudioSourceNode`](../MediaStreamAudioSourceNode.html) has been removed.  You can keep a reference to the media stream used to create this node if you need to access it later.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/migrating_from_webkitaudiocontext/index.html "Folder: en-us/web/api/web_audio_api/migrating_from_webkitaudiocontext (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FMigrating_from_webkitAudioContext%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%2Fmigrating_from_webkitaudiocontext%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FMigrating_from_webkitAudioContext%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Fmigrating_from_webkitaudiocontext%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F91e8e5bb8f8326b87cfad571691b2173a6fc37ad%0A*+Document+last+modified%3A+2020-12-28T11%3A27%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Migrating+from+webkitAudioContext%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Dec 28, 2020, [by MDN contributors](Migrating_from_webkitAudioContext/contributors.txt)

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
