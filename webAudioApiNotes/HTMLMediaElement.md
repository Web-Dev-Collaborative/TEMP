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
3.  <a href="HTMLMediaElement.html" class="breadcrumb-current-page"><span data-property="name">HTMLMediaElement</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Obsolete attributes](#obsolete_attributes)
-   [Methods](#methods)
-   [Obsolete methods](#obsolete_methods)
-   [Events](#events)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

HTMLMediaElement
================

<span class="seoSummary">The **`HTMLMediaElement`** interface adds to [`HTMLElement`](HTMLElement.html) the properties and methods needed to support basic media-related capabilities that are common to audio and video.</span> The [`HTMLVideoElement`](HTMLVideoElement.html) and [`HTMLAudioElement`](HTMLAudioElement.html) elements both inherit this interface.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

*This interface also inherits properties from its ancestors [`HTMLElement`](HTMLElement.html), [`Element`](Element.html), [`Node`](Node.html), and [`EventTarget`](EventTarget.html).*

[`HTMLMediaElement.audioTracks`](HTMLMediaElement/audioTracks.html)  
A [`AudioTrackList`](AudioTrackList.html) that lists the [`AudioTrack`](AudioTrack.html) objects contained in the element.

[`HTMLMediaElement.autoplay`](HTMLMediaElement/autoplay.html)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`autoplay`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-autoplay) HTML attribute, indicating whether playback should automatically begin as soon as enough media is available to do so without interruption.

**Note**: Automatically playing audio when the user doesn't expect or desire it is a poor user experience and should be avoided in most cases, though there are exceptions. See the [Autoplay guide for media and Web Audio APIs](https://developer.mozilla.org/en-US/docs/Web/Media/Autoplay_guide) for more information. Keep in mind that browsers may ignore autoplay requests, so you should ensure that your code isn't dependent on autoplay working.

[`HTMLMediaElement.buffered`](HTMLMediaElement/buffered.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`TimeRanges`](TimeRanges.html) object that indicates the ranges of the media source that the browser has buffered (if any) at the moment the `buffered` property is accessed.

[`HTMLMediaElement.controller`](HTMLMediaElement/controller.html)  
Is a <span class="page-not-created">`MediaController`</span> object that represents the media controller assigned to the element, or `null` if none is assigned.

[`HTMLMediaElement.controls`](HTMLMediaElement/controls.html)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`controls`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-controls) HTML attribute, indicating whether user interface items for controlling the resource should be displayed.

[`HTMLMediaElement.controlsList`](HTMLMediaElement/controlsList.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMTokenList`](DOMTokenList.html) that helps the user agent select what controls to show on the media element whenever the user agent shows its own set of controls. The `DOMTokenList` takes one or more of three possible values: `nodownload`, `nofullscreen`, and `noremoteplayback`.

[`HTMLMediaElement.crossOrigin`](HTMLMediaElement/crossOrigin.html)  
A [`DOMString`](DOMString.html) indicating the [CORS setting](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin) for this media element.

[`HTMLMediaElement.currentSrc`](HTMLMediaElement/currentSrc.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`DOMString`](DOMString.html) with the absolute URL of the chosen media resource.

[`HTMLMediaElement.currentTime`](HTMLMediaElement/currentTime.html)  
A double-precision floating-point value indicating the current playback time in seconds; if the media has not started to play and has not been seeked, this value is the media's initial playback time. Setting this value seeks the media to the new time. The time is specified relative to the media's timeline.

[`HTMLMediaElement.defaultMuted`](HTMLMediaElement/defaultMuted.html)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`muted`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-muted) HTML attribute, which indicates whether the media element's audio output should be muted by default.

[`HTMLMediaElement.defaultPlaybackRate`](HTMLMediaElement/defaultPlaybackRate.html)  
A `double` indicating the default playback rate for the media.

[`HTMLMediaElement.disableRemotePlayback`](HTMLMediaElement/disableRemotePlayback.html)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that sets or returns the remote playback state, indicating whether the media element is allowed to have a remote playback UI.

[`HTMLMediaElement.duration`](HTMLMediaElement/duration.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
A read-only double-precision floating-point value indicating the total duration of the media in seconds. If no media data is available, the returned value is `NaN`. If the media is of indefinite length (such as streamed live media, a WebRTC call's media, or similar), the value is `+Infinity`.

[`HTMLMediaElement.ended`](HTMLMediaElement/ended.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the media element has finished playing.

[`HTMLMediaElement.error`](HTMLMediaElement/error.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`MediaError`](MediaError.html) object for the most recent error, or `null` if there has not been an error.

[`HTMLMediaElement.loop`](HTMLMediaElement/loop.html)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`loop`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-loop) HTML attribute, which indicates whether the media element should start over when it reaches the end.

[`HTMLMediaElement.mediaGroup`](HTMLMediaElement/mediaGroup.html)  
A [`DOMString`](DOMString.html) that reflects the [`mediagroup`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-mediagroup) HTML attribute, which indicates the name of the group of elements it belongs to. A group of media elements shares a common <span class="page-not-created">`MediaController`</span>.

<span class="page-not-created">`HTMLMediaElement.mediaKeys`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`MediaKeys`](MediaKeys.html) object or `null`. MediaKeys is a set of keys that an associated HTMLMediaElement can use for decryption of media data during playback.

[`HTMLMediaElement.muted`](HTMLMediaElement/muted.html)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that determines whether audio is muted. `true` if the audio is muted and `false` otherwise.

[`HTMLMediaElement.networkState`](HTMLMediaElement/networkState.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `unsigned short` (enumeration) indicating the current state of fetching the media over the network.

[`HTMLMediaElement.paused`](HTMLMediaElement/paused.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the media element is paused.

[`HTMLMediaElement.playbackRate`](HTMLMediaElement/playbackRate.html)  
Is a `double` that indicates the rate at which the media is being played back.

<span class="page-not-created">`HTMLMediaElement.played`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`TimeRanges`](TimeRanges.html) object that contains the ranges of the media source that the browser has played, if any.

<span class="page-not-created">`HTMLMediaElement.preload`</span>  
Is a [`DOMString`](DOMString.html) that reflects the [`preload`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-preload) HTML attribute, indicating what data should be preloaded, if any. Possible values are: `none`, `metadata`, `auto`.

<span class="page-not-created">`HTMLMediaElement.preservesPitch`</span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that determines if the pitch of the sound will be preserved. If set to `false`, the pitch will adjust to the speed of the audio. This is implemented with prefixes in Firefox (`mozPreservesPitch`) and WebKit (`webkitPreservesPitch`).

[`HTMLMediaElement.readyState`](HTMLMediaElement/readyState.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a `unsigned short` (enumeration) indicating the readiness state of the media.

[`HTMLMediaElement.seekable`](HTMLMediaElement/seekable.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`TimeRanges`](TimeRanges.html) object that contains the time ranges that the user is able to seek to, if any.

<span class="page-not-created">`HTMLMediaElement.seeking`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the media is in the process of seeking to a new position.

[`HTMLMediaElement.sinkId`](HTMLMediaElement/sinkId.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`DOMString`](DOMString.html) that is the unique ID of the audio device delivering output, or an empty string if it is using the user agent default. This ID should be one of the `MediaDeviceInfo.deviceid` values returned from [`MediaDevices.enumerateDevices()`](MediaDevices/enumerateDevices.html), `id-multimedia`, or `id-communications`.

[`HTMLMediaElement.src`](HTMLMediaElement/src.html)  
Is a [`DOMString`](DOMString.html) that reflects the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-src) HTML attribute, which contains the URL of a media resource to use.

[`HTMLMediaElement.srcObject`](HTMLMediaElement/srcObject.html)  
Is a [`MediaStream`](MediaStream.html) representing the media to play or that has played in the current `HTMLMediaElement`, or `null` if not assigned.

[`HTMLMediaElement.textTracks`](HTMLMediaElement/textTracks.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the list of [`TextTrack`](TextTrack.html) objects contained in the element.

[`HTMLMediaElement.videoTracks`](HTMLMediaElement/videoTracks.html) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the list of [`VideoTrack`](VideoTrack.html) objects contained in the element.

[`HTMLMediaElement.volume`](HTMLMediaElement/volume.html)  
Is a `double` indicating the audio volume, from 0.0 (silent) to 1.0 (loudest).

### [Event handlers](#event_handlers "Permalink to Event handlers")

[`HTMLMediaElement.onencrypted`](HTMLMediaElement/onencrypted.html)  
Sets the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when the media is encrypted.

[`HTMLMediaElement.onwaitingforkey`](HTMLMediaElement/onwaitingforkey.html)  
Sets the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when playback is blocked while waiting for an encryption key.

[Obsolete attributes](#obsolete_attributes "Permalink to Obsolete attributes")
------------------------------------------------------------------------------

These attributes are obsolete and should not be used, even if a browser still supports them.

<span class="page-not-created">`HTMLMediaElement.mozAudioCaptured`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Related to audio stream capture.

<span class="page-not-created">`HTMLMediaElement.mozChannels`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a `double` representing the number of channels in the audio resource (e.g., `2` for stereo).

<span class="page-not-created">`HTMLMediaElement.mozFragmentEnd`</span>   
Is a `double` that provides access to the fragment end time if the media element has a fragment URI for `currentSrc`, otherwise it is equal to the media duration.

<span class="page-not-created">`HTMLMediaElement.mozFrameBufferLength`</span>   
Is a `unsigned long` that indicates the number of samples that will be returned in the framebuffer of each `MozAudioAvailable` event. This number is a total for all channels, and by default is set to be the number of channels \* 1024 (e.g., 2 channels \* 1024 samples = 2048 total).

The `mozFrameBufferLength` property can be set to a new value for lower latency, larger amounts of data, etc. The size given *must* be a number between 512 and 16384. Using any other size results in an exception being thrown. The best time to set a new length is after the [loadedmetadata](HTMLMediaElement/loadedmetadata_event.html) event fires, when the audio info is known, but before the audio has started or `MozAudioAvailable` events have begun firing.

<span class="page-not-created">`HTMLMediaElement.mozSampleRate`</span> <span class="badge inline readonly" title="This value may not be changed.">Read only </span>   
Returns a `double` representing the number of samples per second that will be played. For example, 44100 samples per second is the sample rate used by CD audio.

### [Obsolete event handlers](#obsolete_event_handlers "Permalink to Obsolete event handlers")

<span class="page-not-created">`HTMLMediaElement.onmozinterruptbegin`</span>   
Sets the `event handler` called when the media element is interrupted because of the Audio Channel manager. This was Firefox-specific, having been implemented for Firefox OS, and was removed in Firefox 55.

<span class="page-not-created">`HTMLMediaElement.onmozinterruptend`</span>   
Sets the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when the interruption is concluded. This was Firefox-specific, having been implemented for Firefox OS, and was removed in Firefox 55.

[Methods](#methods "Permalink to Methods")
------------------------------------------

*This interface also inherits methods from its ancestors [`HTMLElement`](HTMLElement.html), [`Element`](Element.html), [`Node`](Node.html), and [`EventTarget`](EventTarget.html).*

<span class="page-not-created">`HTMLMediaElement.addTextTrack()`</span>  
Adds a text track (such as a track for subtitles) to a media element.

[`HTMLMediaElement.captureStream()`](HTMLMediaElement/captureStream.html)   
Returns [`MediaStream`](MediaStream.html), captures a stream of the media content.

[`HTMLMediaElement.canPlayType()`](HTMLMediaElement/canPlayType.html)  
Given a string specifying a MIME media type (potentially with the [`codecs` parameter](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter) included), `canPlayType()` returns the string `probably` if the media should be playable, `maybe` if there's not enough information to determine whether the media will play or not, or an empty string if the media cannot be played.

[`HTMLMediaElement.fastSeek()`](HTMLMediaElement/fastSeek.html)   
Quickly seeks to the given time with low precision.

[`HTMLMediaElement.load()`](HTMLMediaElement/load.html)  
Resets the media to the beginning and selects the best available source from the sources provided using the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-src) attribute or the [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) element.

[`HTMLMediaElement.pause()`](HTMLMediaElement/pause.html)  
Pauses the media playback.

[`HTMLMediaElement.play()`](HTMLMediaElement/play.html)  
Begins playback of the media.

[`HTMLMediaElement.seekToNextFrame()`](HTMLMediaElement/seekToNextFrame.html)   
Seeks to the next frame in the media. This non-standard, experimental method makes it possible to manually drive reading and rendering of media at a custom speed, or to move through the media frame-by-frame to perform filtering or other operations.

[`HTMLMediaElement.setMediaKeys()`](HTMLMediaElement/setMediaKeys.html)   
Returns [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). Sets the [`MediaKeys`](MediaKeys.html) keys to use when decrypting media during playback.

[`HTMLMediaElement.setSinkId()`](HTMLMediaElement/setSinkId.html)   
Sets the ID of the audio device to use for output and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). This only works when the application is authorized to use the specified device.

[Obsolete methods](#obsolete_methods "Permalink to Obsolete methods")
---------------------------------------------------------------------

*These methods are obsolete and should not be used, even if a browser still supports them.*

<span class="page-not-created">`HTMLMediaElement.mozCaptureStream()`</span>   
\[enter description\]

<span class="page-not-created">`HTMLMediaElement.mozCaptureStreamUntilEnded()`</span>   
\[enter description\]

<span class="page-not-created">`HTMLMediaElement.mozGetMetadata()`</span>   
Returns [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object), which contains properties that represent metadata from the playing media resource as `{key: value}` pairs. A separate copy of the data is returned each time the method is called. This method must be called after the [loadedmetadata](HTMLMediaElement/loadedmetadata_event.html) event fires.

<span class="page-not-created">`HTMLMediaElement.mozLoadFrom()`</span>   
This method, available only in Mozilla's implementation, loads data from another media element. This works similarly to `load()` except that instead of running the normal resource selection algorithm, the source is set to the `other` element's `currentSrc`. This is optimized so this element gets access to all of the `other` element's cached and buffered data; in fact, the two elements share downloaded data, so data downloaded by either element is available to both.

[Events](#events "Permalink to Events")
---------------------------------------

*Inherits methods from its parent, [`HTMLElement`](HTMLElement.html)* , defined in the [`GlobalEventHandlers`](GlobalEventHandlers.html) mixin. Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`abort`](HTMLMediaElement/abort_event.html "abort")  
Fired when the resource was not fully loaded, but not as the result of an error.

[`canplay`](HTMLMediaElement/canplay_event.html "canplay")  
Fired when the user agent can play the media, but estimates that **not** enough data has been loaded to play the media up to its end without having to stop for further buffering of content

[`canplaythrough`](HTMLMediaElement/canplaythrough_event.html "canplaythrough")  
Fired when the user agent can play the media, and estimates that enough data has been loaded to play the media up to its end without having to stop for further buffering of content.

[`durationchange`](HTMLMediaElement/durationchange_event.html "durationchange")  
Fired when the duration attribute has been updated.

[`emptied`](HTMLMediaElement/emptied_event.html "emptied")  
Fired when the media has become empty; for example, when the media has already been loaded (or partially loaded), and the [`HTMLMediaElement.load()`](HTMLMediaElement/load.html) method is called to reload it.

[`ended`](HTMLMediaElement/ended_event.html "ended")  
Fired when playback stops when end of the media (&lt;audio&gt; or &lt;video&gt;) is reached or because no further data is available.

[`error`](HTMLMediaElement/error_event.html "error")  
Fired when the resource could not be loaded due to an error.

[`loadeddata`](HTMLMediaElement/loadeddata_event.html "loadeddata")  
Fired when the first frame of the media has finished loading.

[`loadedmetadata`](HTMLMediaElement/loadedmetadata_event.html "loadedmetadata")  
Fired when the metadata has been loaded

[`loadstart`](HTMLMediaElement/loadstart_event.html "loadstart")  
Fired when the browser has started to load a resource.

[`pause`](HTMLMediaElement/pause_event.html "pause")  
Fired when a request to pause play is handled and the activity has entered its paused state, most commonly occurring when the media's [`HTMLMediaElement.pause()`](HTMLMediaElement/pause.html) method is called.

[`play`](HTMLMediaElement/play_event.html "play")  
Fired when the `paused` property is changed from `true` to `false`, as a result of the [`HTMLMediaElement.play()`](HTMLMediaElement/play.html) method, or the `autoplay` attribute

[`playing`](HTMLMediaElement/playing_event.html "playing")  
Fired when playback is ready to start after having been paused or delayed due to lack of data

[`progress`](HTMLMediaElement/progress_event.html "progress")  
Fired periodically as the browser loads a resource.

[`ratechange`](HTMLMediaElement/ratechange_event.html "ratechange")  
Fired when the playback rate has changed.

[`seeked `](HTMLMediaElement/seeked_event.html "seeked ")  
Fired when a seek operation completes

[`seeking`](HTMLMediaElement/seeking_event.html "seeking")  
Fired when a seek operation begins

[`stalled`](HTMLMediaElement/stalled_event.html "stalled")  
Fired when the user agent is trying to fetch media data, but data is unexpectedly not forthcoming.

[`suspend`](HTMLMediaElement/suspend_event.html "suspend")  
Fired when the media data loading has been suspended.

[`timeupdate`](HTMLMediaElement/timeupdate_event.html "timeupdate")  
Fired when the time indicated by the [`currentTime`](HTMLMediaElement/currentTime.html "currentTime") attribute has been updated.

[`volumechange`](HTMLMediaElement/volumechange_event.html "volumechange")  
Fired when the volume has changed.

[`waiting`](HTMLMediaElement/waiting_event.html "waiting")  
Fired when playback has stopped because of a temporary lack of data.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#introduction" class="external">Encrypted Media Extensions<br />
<span class="small">The definition of 'Encrypted Media Extensions' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds <a href="MediaKeys.html"><code>MediaKeys</code></a>, <span class="page-not-created"><code>MediaEncryptedEvent</code></span>, <span class="page-not-created"><code>setMediaKeys</code></span>, <span class="page-not-created"><code>onencrypted</code></span>, and <span class="page-not-created"><code>onwaitingforkey</code></span>.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/the-video-element.html#htmlmediaelement" class="external">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/" class="external" title="The &#39;HTML5&#39; specification">HTML5</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement" class="external">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

### [References](#references "Permalink to References")

-   [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) and [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) HTML elements.
-   [`HTMLVideoElement`](HTMLVideoElement.html) and [`HTMLAudioElement`](HTMLAudioElement.html) interfaces, derived from `HTMLMediaElement`.

### [Guides](#guides "Permalink to Guides")

-   [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)
-   Learning area: [Video and audio content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
-   [Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)
-   [Handling media support issues in web content](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Support_issues)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/htmlmediaelement/index.html "Folder: en-us/web/api/htmlmediaelement (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLMediaElement%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fhtmlmediaelement%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FHTMLMediaElement%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fhtmlmediaelement%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fcb20a8045f6cbdbd224b1068e46c8644470dd8c3%0A*+Document+last+modified%3A+2021-06-01T09%3A10%3A31.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22HTMLMediaElement%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Jun 1, 2021, [by MDN contributors](HTMLMediaElement/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançais日本語한국어Русский中文 (简体)正體中文 (繁體)

Change language

#### Related Topics

1.  **[`HTMLMediaElement`](HTMLMediaElement.html)**
2.  Properties
    1.  [`audioTracks`](HTMLMediaElement/audioTracks.html)
    2.  [`autoplay`](HTMLMediaElement/autoplay.html)
    3.  [`buffered`](HTMLMediaElement/buffered.html)
    4.  [`controller`](HTMLMediaElement/controller.html)
    5.  [`controls`](HTMLMediaElement/controls.html)
    6.  [`controlsList`](HTMLMediaElement/controlsList.html)
    7.  [`crossOrigin`](HTMLMediaElement/crossOrigin.html)
    8.  [`currentSrc`](HTMLMediaElement/currentSrc.html)
    9.  [`currentTime`](HTMLMediaElement/currentTime.html)
    10. [`defaultMuted`](HTMLMediaElement/defaultMuted.html)
    11. [`defaultPlaybackRate`](HTMLMediaElement/defaultPlaybackRate.html)
    12. [`duration`](HTMLMediaElement/duration.html)
    13. [`ended`](HTMLMediaElement/ended.html)
    14. [`error`](HTMLMediaElement/error.html)
    15. [`loop`](HTMLMediaElement/loop.html)
    16. [`mediaGroup`](HTMLMediaElement/mediaGroup.html)
    17. [`muted`](HTMLMediaElement/muted.html)
    18. [`networkState`](HTMLMediaElement/networkState.html)
    19. [`onerror`](HTMLMediaElement/onerror.html)
    20. [`paused`](HTMLMediaElement/paused.html)
    21. [`playbackRate`](HTMLMediaElement/playbackRate.html)
    22. [`readyState`](HTMLMediaElement/readyState.html)
    23. [`seekable`](HTMLMediaElement/seekable.html)
    24. [`sinkId`](HTMLMediaElement/sinkId.html)
    25. [`src`](HTMLMediaElement/src.html)
    26. [`srcObject`](HTMLMediaElement/srcObject.html)
    27. [`textTracks`](HTMLMediaElement/textTracks.html)
    28. [`videoTracks`](HTMLMediaElement/videoTracks.html)
    29. [`volume`](HTMLMediaElement/volume.html)
3.  Methods
    1.  [`canPlayType()`](HTMLMediaElement/canPlayType.html)
    2.  [`captureStream()`](HTMLMediaElement/captureStream.html)
    3.  [`fastSeek()`](HTMLMediaElement/fastSeek.html)
    4.  [`load()`](HTMLMediaElement/load.html)
    5.  [`msInsertAudioEffect()`](HTMLMediaElement/msInsertAudioEffect.html)
    6.  [`pause()`](HTMLMediaElement/pause.html)
    7.  [`play()`](HTMLMediaElement/play.html)
    8.  [`seekToNextFrame()`](HTMLMediaElement/seekToNextFrame.html)
    9.  [`setMediaKeys()`](HTMLMediaElement/setMediaKeys.html)
    10. [`setSinkId()`](HTMLMediaElement/setSinkId.html)
4.  Events
    1.  [`abort`](HTMLMediaElement/abort_event.html)
    2.  [`canplay`](HTMLMediaElement/canplay_event.html)
    3.  [`canplaythrough`](HTMLMediaElement/canplaythrough_event.html)
    4.  [`durationchange`](HTMLMediaElement/durationchange_event.html)
    5.  [`emptied`](HTMLMediaElement/emptied_event.html)
    6.  [`ended`](HTMLMediaElement/ended_event.html)
    7.  [`error`](HTMLMediaElement/error_event.html)
    8.  [`loadeddata`](HTMLMediaElement/loadeddata_event.html)
    9.  [`loadedmetadata`](HTMLMediaElement/loadedmetadata_event.html)
    10. [`loadstart`](HTMLMediaElement/loadstart_event.html)
    11. [`pause`](HTMLMediaElement/pause_event.html)
    12. [`play`](HTMLMediaElement/play_event.html)
    13. [`progress`](HTMLMediaElement/progress_event.html)
    14. [`ratechange`](HTMLMediaElement/ratechange_event.html)
    15. [`seeked`](HTMLMediaElement/seeked_event.html)
    16. [`seeking`](HTMLMediaElement/seeking_event.html)
    17. [`stalled`](HTMLMediaElement/stalled_event.html)
    18. [`suspend`](HTMLMediaElement/suspend_event.html)
    19. [`timeupdate`](HTMLMediaElement/timeupdate_event.html)
    20. [`volumechange`](HTMLMediaElement/volumechange_event.html)
    21. [`waiting`](HTMLMediaElement/waiting_event.html)
5.  Inheritance:
    1.  [`HTMLElement`](HTMLElement.html)
    2.  [`Element`](Element.html)
    3.  [`Node`](Node.html)
    4.  [`EventTarget`](EventTarget.html)
6.  Related pages for HTML DOM
    1.  [`BeforeUnloadEvent`](BeforeUnloadEvent.html)
    2.  [`DOMStringMap`](DOMStringMap.html)
    3.  [`ErrorEvent`](ErrorEvent.html)
    4.  [`GlobalEventHandlers`](GlobalEventHandlers.html)
    5.  [`HTMLAnchorElement`](HTMLAnchorElement.html)
    6.  [`HTMLAreaElement`](HTMLAreaElement.html)
    7.  [`HTMLAudioElement`](HTMLAudioElement.html)
    8.  [`HTMLBRElement`](HTMLBRElement.html)
    9.  [`HTMLBaseElement`](HTMLBaseElement.html)
    10. [`HTMLBaseFontElement`](HTMLBaseFontElement.html)
    11. [`HTMLBodyElement`](HTMLBodyElement.html)
    12. [`HTMLButtonElement`](HTMLButtonElement.html)
    13. [`HTMLCanvasElement`](HTMLCanvasElement.html)
    14. [`HTMLContentElement`](HTMLContentElement.html)
    15. [`HTMLDListElement`](HTMLDListElement.html)
    16. [`HTMLDataElement`](HTMLDataElement.html)
    17. [`HTMLDataListElement`](HTMLDataListElement.html)
    18. [`HTMLDialogElement`](HTMLDialogElement.html)
    19. [`HTMLDivElement`](HTMLDivElement.html)
    20. [`HTMLDocument`](HTMLDocument.html)
    21. [`HTMLElement`](HTMLElement.html)
    22. [`HTMLEmbedElement`](HTMLEmbedElement.html)
    23. [`HTMLFieldSetElement`](HTMLFieldSetElement.html)
    24. [`HTMLFormControlsCollection`](HTMLFormControlsCollection.html)
    25. [`HTMLFormElement`](HTMLFormElement.html)
    26. [`HTMLFrameSetElement`](HTMLFrameSetElement.html)
    27. [`HTMLHRElement`](HTMLHRElement.html)
    28. [`HTMLHeadElement`](HTMLHeadElement.html)
    29. [`HTMLHeadingElement`](HTMLHeadingElement.html)
    30. [`HTMLHtmlElement`](HTMLHtmlElement.html)
    31. [`HTMLIFrameElement`](HTMLIFrameElement.html)
    32. [`HTMLImageElement`](HTMLImageElement.html)
    33. [`HTMLInputElement`](HTMLInputElement.html)
    34. [`HTMLIsIndexElement`](HTMLIsIndexElement.html)
    35. [`HTMLKeygenElement`](HTMLKeygenElement.html)
    36. [`HTMLLIElement`](HTMLLIElement.html)
    37. [`HTMLLabelElement`](HTMLLabelElement.html)
    38. [`HTMLLegendElement`](HTMLLegendElement.html)
    39. [`HTMLLinkElement`](HTMLLinkElement.html)
    40. [`HTMLMapElement`](HTMLMapElement.html)
    41. [`HTMLMetaElement`](HTMLMetaElement.html)
    42. [`HTMLMeterElement`](HTMLMeterElement.html)
    43. [`HTMLModElement`](HTMLModElement.html)
    44. [`HTMLOListElement`](HTMLOListElement.html)
    45. [`HTMLObjectElement`](HTMLObjectElement.html)
    46. [`HTMLOptGroupElement`](HTMLOptGroupElement.html)
    47. [`HTMLOptionElement`](HTMLOptionElement.html)
    48. [`HTMLOptionsCollection`](HTMLOptionsCollection.html)
    49. [`HTMLOutputElement`](HTMLOutputElement.html)
    50. [`HTMLParagraphElement`](HTMLParagraphElement.html)
    51. [`HTMLParamElement`](HTMLParamElement.html)
    52. [`HTMLPictureElement`](HTMLPictureElement.html)
    53. [`HTMLPreElement`](HTMLPreElement.html)
    54. [`HTMLProgressElement`](HTMLProgressElement.html)
    55. [`HTMLQuoteElement`](HTMLQuoteElement.html)
    56. [`HTMLScriptElement`](HTMLScriptElement.html)
    57. [`HTMLSelectElement`](HTMLSelectElement.html)
    58. [`HTMLShadowElement`](HTMLShadowElement.html)
    59. [`HTMLSourceElement`](HTMLSourceElement.html)
    60. [`HTMLSpanElement`](HTMLSpanElement.html)
    61. [`HTMLStyleElement`](HTMLStyleElement.html)
    62. [`HTMLTableCaptionElement`](HTMLTableCaptionElement.html)
    63. [`HTMLTableCellElement`](HTMLTableCellElement.html)
    64. [`HTMLTableColElement`](HTMLTableColElement.html)
    65. [`HTMLTableDataCellElement`](HTMLTableCellElement.html)
    66. [`HTMLTableElement`](HTMLTableElement.html)
    67. [`HTMLTableHeaderCellElement`](HTMLTableCellElement.html)
    68. [`HTMLTableRowElement`](HTMLTableRowElement.html)
    69. [`HTMLTableSectionElement`](HTMLTableSectionElement.html)
    70. [`HTMLTemplateElement`](HTMLTemplateElement.html)
    71. [`HTMLTextAreaElement`](HTMLTextAreaElement.html)
    72. [`HTMLTimeElement`](HTMLTimeElement.html)
    73. [`HTMLTitleElement`](HTMLTitleElement.html)
    74. [`HTMLTrackElement`](HTMLTrackElement.html)
    75. [`HTMLUListElement`](HTMLUListElement.html)
    76. [`HTMLUnknownElement`](HTMLUnknownElement.html)
    77. [`HTMLVideoElement`](HTMLVideoElement.html)
    78. [`HashChangeEvent`](HashChangeEvent.html)
    79. [`History`](History.html)
    80. [`ImageData`](ImageData.html)
    81. [`Location`](Location.html)
    82. [`MessageChannel`](MessageChannel.html)
    83. [`MessageEvent`](MessageEvent.html)
    84. [`MessagePort`](MessagePort.html)
    85. [`Navigator`](Navigator.html)
    86. [`NavigatorGeolocation`](Geolocation.html)
    87. [`NavigatorID`](NavigatorID.html)
    88. [`NavigatorLanguage`](NavigatorLanguage.html)
    89. [`NavigatorOnLine`](NavigatorOnLine.html)
    90. [`NavigatorPlugins`](NavigatorPlugins.html)
    91. [`PageTransitionEvent`](PageTransitionEvent.html)
    92. [`Plugin`](Plugin.html)
    93. [`PluginArray`](PluginArray.html)
    94. [`PopStateEvent`](PopStateEvent.html)
    95. [`PortCollection`](PortCollection.html)
    96. [`PromiseRejectionEvent`](PromiseRejectionEvent.html)
    97. [`RadioNodeList`](RadioNodeList.html)
    98. [`Transferable`](Transferable.html)
    99. [`ValidityState`](ValidityState.html)
    100. [`Window`](Window.html)
    101. [`WindowBase64`](WindowOrWorkerGlobalScope.html)
    102. [`WindowEventHandlers`](WindowEventHandlers.html)
    103. [`WindowTimers`](WindowOrWorkerGlobalScope.html)

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
