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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings" class="breadcrumb-current-page"><span data-property="name">MediaTrackSettings</span></a>

Table of contents
-----------------

Table of contents

-   [Properties](#properties)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaTrackSettings
==================

The **`MediaTrackSettings`** dictionary is used to return the current values configured for each of a [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)'s settings. These values will adhere as closely as possible to any constraints previously described using a [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints) object and set using [`applyConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/applyConstraints "applyConstraints()"), and will adhere to the default constraints for any properties whose constraints haven't been changed, or whose customized constraints couldn't be matched.

To learn more about how constraints and settings work, see [Capabilities, constraints, and settings](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API/Constraints).

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

Some or all of the following will be included in the object, either because it's not supported by the browser or because it's not available due to context. For example, because [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) doesn't provide some of these values during negotiation of a WebRTC connection, a track associated with a [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) will not include certain values, such as [`facingMode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/facingMode "facingMode") or [`groupId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/groupId "groupId").

### [Properties of all media tracks](#properties_of_all_media_tracks "Permalink to Properties of all media tracks")

[`deviceId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/deviceId "deviceId")  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating the current value of the `deviceId` property. The device ID is a origin-unique string identifying the source of the track; this is usually a <span class="page-not-created">GUID</span>. This value is specific to the source of the track's data and is not usable for setting constraints; it can, however, be used for initially selecting media when calling [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia).

[`groupId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/groupId "groupId")  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating the current value of the `groupId` property. The group ID is a browsing session-unique string identifying the source group of the track. Two devices (as identified by the [`deviceId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/deviceId "deviceId")) are considered part of the same group if they are from the same physical device. For instance, the audio input and output devices for the speaker and microphone built into a phone would share the same group ID, since they're part of the same physical device. The microphone on a headset would have a different ID, though. This value is specific to the source of the track's data and is not usable for setting constraints; it can, however, be used for initially selecting media when calling [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia).

### [Properties of audio tracks](#properties_of_audio_tracks "Permalink to Properties of audio tracks")

[`autoGainControl`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/autoGainControl "autoGainControl")  
A Boolean which indicates the current value of the [`autoGainControl`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/autoGainControl "autoGainControl") property, which is `true` if automatic gain control is enabled and is `false` otherwise.

[`channelCount`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/channelCount "channelCount")  
A long integer value indicating the current value of the `channelCount` property, specifying the number of audio channels present on the track (therefore indicating how many audio samples exist in each audio frame). This is 1 for mono, 2 for stereo, and so forth.

[`echoCancellation`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/echoCancellation "echoCancellation")  
A Boolean indicating the current value of the `echoCancellation` property, specifying `true` if echo cancellation is enabled, otherwise `false`.

[`latency`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/latency "latency")  
A double-precision floating point value indicating the current value of the `latency` property, specifying the audio latency, in seconds. Latency is the amount of time which elapses between the start of processing the audio and the data being available to the next stop in the audio utilization process. This value is a target value; actual latency may vary to some extent for various reasons.

[`noiseSuppression`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/noiseSuppression "noiseSuppression")  
A Boolean which indicates the current value of the [`noiseSuppression`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/noiseSuppression "noiseSuppression") property, which is `true` if noise suppression is enabled and is `false` otherwise.

[`sampleRate`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/sampleRate "sampleRate")  
A long integer value indicating the current value of the `sampleRate` property, specifying the sample rate in samples per second of the audio data. Standard CD-quality audio, for example, has a sample rate of 41,000 samples per second.

[`sampleSize`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/sampleSize "sampleSize")  
A long integer value indicating the current value of the `sampleSize` property, specifying the linear size, in bits, of each audio sample. CD-quality audio, for example, is 16-bit, so this value would be 16 in that case.

[`volume`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/volume "volume")  
A double-precision floating point value indicating the current value of the `volume` property, specifying the volume level of the track. This value will be between 0.0 (silent) to 1.0 (maximum supported volume).

### [Properties of video tracks](#properties_of_video_tracks "Permalink to Properties of video tracks")

[`aspectRatio`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/aspectRatio "aspectRatio")  
A double-precision floating point value indicating the current value of the `aspectRatio` property, specified precisely to 10 decimal places. This is the width of the image in pixels divided by its height in pixels. Common values include 1.3333333333 (for the classic television 4:3 "standard" aspect ratio, also used on tablets such as Apple's iPad), 1.7777777778 (for the 16:9 high-definition widescreen aspect ratio), and 1.6 (for the 16:10 aspect ratio common among widescreen computers and tablets).

[`facingMode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/facingMode "facingMode")  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating the current value of the `facingMode` property, specifying the direction the camera is facing. The value will be one of:

`"user"`  
A camera facing the user (commonly known as a "selfie cam"), used for self-portraiture and video calling.

`"environment"`  
A camera facing away from the user (when the user is looking at the screen). This is typically the highest quality camera on the device, used for general photography.

`"left"`  
A camera facing toward the environment to the user's left.

`"right"`  
A camera facing toward the environment to the user's right.

[`frameRate`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/frameRate "frameRate")  
A double-precision floating point value indicating the current value of the `frameRate` property, specifying how many frames of video per second the track includes. If the value can't be determined for any reason, the value will match the vertical sync rate of the device the user agent is running on.

[`height`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/height "height")  
A long integer value indicating the current value of the `height` property, specifying the height of the track's video data in pixels.

[`width`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/width "width")  
A long integer value indicating the current value of the [`width`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/width "width") property, specifying the width of the track's video data in pixels.

<span class="page-not-created">`resizeMode`</span>  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) indicating the current value of the `resizeMode` property, specifying the mode used by the user agent to derive the resolution of the track. The value will be one of:

`"none"`  
The track has the resolution offered by the camera, its driver or the OS.

`"crop-and-scale"`  
The track's resolution might be the result of the user agent using cropping or downscaling from a higher camera resolution.

### [Properties of shared screen tracks](#properties_of_shared_screen_tracks "Permalink to Properties of shared screen tracks")

Tracks containing video shared from a user's screen (regardless of whether the screen data comes from the entire screen or a portion of a screen, like a window or tab) are generally treated like video tracks, with the exception that they also support the following added settings:

[`cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/cursor "cursor")  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which indicates whether or not the mouse cursor is being included in the generated stream and under what conditions. Possible values are:

`always`  
The mouse is always visible in the video content of the {domxref("MediaStream"), unless the mouse has moved outside the area of the content.

`motion`  
The mouse cursor is always included in the video if it's moving, and for a short time after it stops moving.

`never`  
The mouse cursor is never included in the shared video.

[`displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/displaySurface "displaySurface")  
A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which specifies the type of source the track contains; one of:

`application`  
The stream contains all of the windows of the application chosen by the user rendered into the one video track.

`browser`  
The stream contains the contents of a single browser tab selected by the user.

`monitor`  
The stream's video track contains the entire contents of one or more of the user's screens.

`window`  
The stream contains a single window selected by the user for sharing.

[`logicalSurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/logicalSurface "logicalSurface")  
A Boolean value which, if `true`, indicates that the video contained in the stream's video track contains a background rendering context, rather than a user-visible one. This is `false` if the video being captured is coming from a foreground (user-visible) source.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#media-track-settings" class="external">Media Capture and Streams<br />
<span class="small">The definition of 'MediaTrackSettings' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://w3c.github.io/mediacapture-screen-share/#extensions-to-mediatracksettings" class="external">Screen Capture<br />
<span class="small">The definition of 'MediaTrackSettings extensions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines the <code>displaySurface</code>, <code>logicalSurface</code>, and <code>cursor</code> members</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
-   [`MediaDevices.getDisplayMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia)
-   [`MediaStreamTrack.getConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getConstraints)
-   [`MediaStreamTrack.applyConstraints()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/applyConstraints)
-   [`MediaStreamTrack.getSettings()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getSettings)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediatracksettings/index.html "Folder: en-us/web/api/mediatracksettings (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaTrackSettings%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediatracksettings%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaTrackSettings%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediatracksettings%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaTrackSettings%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/contributors.txt)

#### Related Topics

1.  **[Media Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)**
2.  **[`MediaTrackSettings`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings)**
3.  Properties
    1.  [`aspectRatio`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/aspectRatio)
    2.  [`autoGainControl`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/autoGainControl)
    3.  [`channelCount`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/channelCount)
    4.  [`cursor`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/cursor)
    5.  [`deviceId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/deviceId)
    6.  [`displaySurface`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/displaySurface)
    7.  [`echoCancellation`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/echoCancellation)
    8.  [`facingMode`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/facingMode)
    9.  [`frameRate`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/frameRate)
    10. [`groupId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/groupId)
    11. [`height`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/height)
    12. [`latency`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/latency)
    13. [`noiseSuppression`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/noiseSuppression)
    14. [`sampleRate`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/sampleRate)
    15. [`sampleSize`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/sampleSize)
    16. [`volume`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/volume)
    17. [`width`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSettings/width)
4.  Related pages for Media Capture and Streams
    1.  [`AudioStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/AudioStreamTrack)
    2.  [`BlobEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent)
    3.  [`CanvasCaptureMediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasCaptureMediaStream)
    4.  [`ConstrainBoolean`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainBoolean)
    5.  [`ConstrainDOMString`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDOMString)
    6.  [`ConstrainDouble`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDouble)
    7.  [`ConstrainLong`](https://developer.mozilla.org/en-US/docs/Web/API/ConstrainLong)
    8.  [`DoubleRange`](https://developer.mozilla.org/en-US/docs/Web/API/DoubleRange)
    9.  [`HTMLCanvasElement.captureStream()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/captureStream)
    10. [`LongRange`](https://developer.mozilla.org/en-US/docs/Web/API/LongRange)
    11. [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices)
    12. [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)
    13. [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)
    14. [`MediaStreamTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrackEvent)
    15. [`MediaTrackCapabilities`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackCapabilities)
    16. [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints)
    17. [`MediaTrackSupportedConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints)
    18. [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
    19. [`NavigatorUserMedia`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorUserMedia)
    20. [`NavigatorUserMediaError`](https://developer.mozilla.org/en-US/docs/Web/API/NavigatorUserMediaError)
    21. [`VideoStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/VideoStreamTrack)
    22. [`navigator.mediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/navigator/mediaDevices.getUserMedia)

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
