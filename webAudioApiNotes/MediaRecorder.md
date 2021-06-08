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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder" class="breadcrumb-current-page"><span data-property="name">MediaRecorder</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Constructor](#constructor)
-   [Properties](#properties)
-   [Methods](#methods)
-   [Static methods](#static_methods)
-   [Event handlers](#event_handlers)
-   [Events](#events)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

MediaRecorder
=============

The **`MediaRecorder`** interface of the [MediaStream Recording API](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API) provides functionality to easily record media. It is created using the [`MediaRecorder()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/MediaRecorder "MediaRecorder()") constructor.

[Constructor](#constructor "Permalink to Constructor")
------------------------------------------------------

[`MediaRecorder()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/MediaRecorder "MediaRecorder()")  
Creates a new `MediaRecorder` object, given a [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) to record. Options are available to do things like set the container's MIME type (such as `"video/webm"` or `"video/mp4"`) and the bit rates of the audio and video tracks or a single overall bit rate.

[Properties](#properties "Permalink to Properties")
---------------------------------------------------

[`MediaRecorder.mimeType`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/mimeType) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the MIME type that was selected as the recording container for the `MediaRecorder` object when it was created.

[`MediaRecorder.state`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/state) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the current state of the `MediaRecorder` object (`inactive`, `recording`, or `paused`.)

[`MediaRecorder.stream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/stream) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the stream that was passed into the constructor when the `MediaRecorder` was created.

[`MediaRecorder.ignoreMutedMedia`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/ignoreMutedMedia)  
Indicates whether the `MediaRecorder` instance will record input when the input [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack) is muted. If this attribute is `false`, `MediaRecorder` will record silence for audio and black frames for video. The default is `false`.

[`MediaRecorder.videoBitsPerSecond`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/videoBitsPerSecond) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the video encoding bit rate in use. This may differ from the bit rate specified in the constructor (if it was provided).

[`MediaRecorder.audioBitsPerSecond`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/audioBitsPerSecond) <span class="badge inline readonly" title="This value may not be changed.">Read only </span>  
Returns the audio encoding bit rate in use. This may differ from the bit rate specified in the constructor (if it was provided).

[Methods](#methods "Permalink to Methods")
------------------------------------------

[`MediaRecorder.pause()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/pause)  
Pauses the recording of media.

[`MediaRecorder.requestData()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/requestData)  
Requests a [`Blob`](https://developer.mozilla.org/en-US/docs/Web/API/Blob) containing the saved data received thus far (or since the last time `requestData()` was called. After calling this method, recording continues, but in a new `Blob`.

[`MediaRecorder.resume()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/resume)  
Resumes recording of media after having been paused.

[`MediaRecorder.start()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/start)  
Begins recording media; this method can optionally be passed a `timeslice` argument with a value in milliseconds. If this is specified, the media will be captured in separate chunks of that duration, rather than the default behavior of recording the media in a single large chunk.

[`MediaRecorder.stop()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/stop)  
Stops recording, at which point a `dataavailable` event containing the final `Blob` of saved data is fired. No more recording occurs.

[Static methods](#static_methods "Permalink to Static methods")
---------------------------------------------------------------

[`MediaRecorder.isTypeSupported()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/isTypeSupported)  
A static method which returns a `true` or `false` value indicating if the given MIME media type is supported by the current user agent. 

[Event handlers](#event_handlers "Permalink to Event handlers")
---------------------------------------------------------------

[`MediaRecorder.ondataavailable`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/ondataavailable)  
Called to handle the `dataavailable` event, which is periodically triggered each time `timeslice` milliseconds of media have been recorded (or when the entire media has been recorded, if `timeslice` wasn't specified). The event, of type [`BlobEvent`](https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent), contains the recorded media in its [`data`](https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent/data "data") property. You can then collect and act upon that recorded media data using this event handler.

[`MediaRecorder.onerror`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onerror)  
An `Event handler` called to handle the `error` event, including reporting errors that arise with media recording. These are fatal errors that stop recording. The received event is based on the [`MediaRecorderErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorderErrorEvent) interface, whose [`error`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorderErrorEvent/error "error") property contains a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) that describes the actual error that occurred.

[`MediaRecorder.onpause`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onpause)  
An `Event handler` called to handle the `pause` event, which occurs when media recording is paused.

[`MediaRecorder.onresume`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onresume)  
An `Event handler` called to handle the `resume` event, which occurs when media recording resumes after being paused.

[`MediaRecorder.onstart`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onstart)  
An `Event handler` called to handle the `start` event, which occurs when media recording starts.

[`MediaRecorder.onstop`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onstop)  
An `Event handler` called to handle the `stop` event, which occurs when media recording ends, either when the [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) ends — or after the [`MediaRecorder.stop()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/stop) method is called.

[`MediaRecorder.onwarning`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onwarning)   
An `Event handler` called to handle the `warning` event, which occurs when media recording has a non-fatal error, or after the [`MediaRecorder.onwarning()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onwarning) method is called.

[Events](#events "Permalink to Events")
---------------------------------------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

`error`  
Fired when an error occurs: for example because recording wasn't allowed or was attempted using an unsupported codec.  
Also available via the `onerror` property.

`warning`   
Fired when a problem occurs that does not halt recording.  
Also available via the `onwarning` property.

[Example](#example "Permalink to Example")
------------------------------------------

    if (navigator.mediaDevices) {
      console.log('getUserMedia supported.');

      var constraints = { audio: true };
      var chunks = [];

      navigator.mediaDevices.getUserMedia(constraints)
      .then(function(stream) {

        var mediaRecorder = new MediaRecorder(stream);

        visualize(stream);

        record.onclick = function() {
          mediaRecorder.start();
          console.log(mediaRecorder.state);
          console.log("recorder started");
          record.style.background = "red";
          record.style.color = "black";
        }

        stop.onclick = function() {
          mediaRecorder.stop();
          console.log(mediaRecorder.state);
          console.log("recorder stopped");
          record.style.background = "";
          record.style.color = "";
        }

        mediaRecorder.onstop = function(e) {
          console.log("data available after MediaRecorder.stop() called.");

          var clipName = prompt('Enter a name for your sound clip');

          var clipContainer = document.createElement('article');
          var clipLabel = document.createElement('p');
          var audio = document.createElement('audio');
          var deleteButton = document.createElement('button');

          clipContainer.classList.add('clip');
          audio.setAttribute('controls', '');
          deleteButton.innerHTML = "Delete";
          clipLabel.innerHTML = clipName;

          clipContainer.appendChild(audio);
          clipContainer.appendChild(clipLabel);
          clipContainer.appendChild(deleteButton);
          soundClips.appendChild(clipContainer);

          audio.controls = true;
          var blob = new Blob(chunks, { 'type' : 'audio/ogg; codecs=opus' });
          chunks = [];
          var audioURL = URL.createObjectURL(blob);
          audio.src = audioURL;
          console.log("recorder stopped");

          deleteButton.onclick = function(e) {
            evtTgt = e.target;
            evtTgt.parentNode.parentNode.removeChild(evtTgt.parentNode);
          }
        }

        mediaRecorder.ondataavailable = function(e) {
          chunks.push(e.data);
        }
      })
      .catch(function(err) {
        console.log('The following error occurred: ' + err);
      })
    }

This code sample is inspired by the Web Dictaphone demo. Some lines have been omitted for brevity; <a href="https://github.com/mdn/web-dictaphone/" class="external">refer to the source</a> for the complete code.

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#mediarecorder-api" class="external" title="The &#39;MediaStream Recording&#39; specification">MediaStream Recording</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the MediaRecorder API](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API/Using_the_MediaStream_Recording_API)
-   <a href="https://mdn.github.io/web-dictaphone/" class="external">Web Dictaphone</a>: MediaRecorder + getUserMedia + Web Audio API visualization demo, by <a href="https://twitter.com/chrisdavidmills" class="external">Chris Mills</a> (<a href="https://github.com/mdn/web-dictaphone/" class="external">source on Github</a>.)
-   [Recording a media element](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API/Recording_a_media_element)
-   <a href="https://simpl.info/mediarecorder/" class="external">simpl.info MediaStream Recording demo</a>, by <a href="https://twitter.com/sw12" class="external">Sam Dutton</a>.
-   [`MediaDevices.getUserMedia`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
-   <a href="https://github.com/chrisjohndigital/OpenLang" class="external">OpenLang</a>: HTML5 video language lab web application using MediaDevices and the MediaStream Recording API for video recording (<a href="https://github.com/chrisjohndigital/OpenLang" class="external">source on GitHub</a>)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/mediarecorder/index.html "Folder: en-us/web/api/mediarecorder (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaRecorder%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fmediarecorder%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FMediaRecorder%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fmediarecorder%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F5737ba49f3f0c3fc7587d329f1362a7a66afdd80%0A*+Document+last+modified%3A+2021-05-31T16%3A58%3A42.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22MediaRecorder%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/contributors.txt)

Change your languageSelect your preferred language English (US)日本語Русский中文 (简体)

Change language

#### Related Topics

1.  **[`MediaRecorder`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder)**
2.  Constructor
    1.  [`MediaRecorder()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/MediaRecorder)
3.  Properties
    1.  [`audioBitsPerSecond`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/audioBitsPerSecond)
    2.  [`ignoreMutedMedia`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/ignoreMutedMedia)
    3.  [`mimeType`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/mimeType)
    4.  [`ondataavailable`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/ondataavailable)
    5.  [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onerror)
    6.  [`onpause`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onpause)
    7.  [`onresume`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onresume)
    8.  [`onstart`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onstart)
    9.  [`onstop`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onstop)
    10. [`onwarning`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/onwarning)
    11. [`state`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/state)
    12. [`stream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/stream)
4.  Methods
    1.  [`isTypeSupported`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/isTypeSupported)
    2.  [`pause()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/pause)
    3.  [`requestData()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/requestData)
    4.  [`resume()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/resume)
    5.  [`start()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/start)
    6.  [`stop()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/stop)
5.  Events
    1.  [`error`](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder/error_event)
6.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)

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
