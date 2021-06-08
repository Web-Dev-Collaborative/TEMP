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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API" class="breadcrumb-penultimate"><span data-property="name">WebRTC API</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Taking_still_photos" class="breadcrumb-current-page"><span data-property="name">Taking still photos with WebRTC</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [The HTML markup](#the_html_markup)
-   [<span style="font-size: 30px;">The JavaScript code</span>](#the_javascript_code)
-   [Fun with filters](#fun_with_filters)
-   [Using specific devices](#using_specific_devices)
-   [See also](#see_also)

Taking still photos with WebRTC
===============================

<span class="seoSummary">This article shows how to use WebRTC to access the camera on a computer or mobile phone with WebRTC support and take a photo with it.</span> <a href="https://mdn-samples.mozilla.org/s/webrtc-capturestill" class="external">Try this sample</a> then read on to learn how it works.

<img src="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Taking_still_photos/web-rtc-demo.png" alt="WebRTC-based image capture app — on the left we have a video stream taken from a webcam and a take photo button, on the right we have the still image output from taking the photo" width="677" height="252" />

You can also jump straight to the <a href="https://github.com/mdn/samples-server/tree/master/s/webrtc-capturestill" class="external">code on Github</a> if you like.

[The HTML markup](#the_html_markup "Permalink to The HTML markup")
------------------------------------------------------------------

<a href="https://github.com/mdn/samples-server/tree/master/s/webrtc-capturestill/index.html" class="external">Our HTML interface</a> has two main operational sections: the stream and capture panel and the presentation panel. Each of these is presented side-by-side in its own [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) to facilitate styling and control.

The first panel on the left contains two components: a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, which will receive the stream from WebRTC, and a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) the user clicks to capture a video frame.

      <div class="camera">
        <video id="video">Video stream not available.</video>
        <button id="startbutton">Take photo</button>
      </div>

This is straightforward, and we'll see how it ties together when we get into the JavaScript code.

Next, we have a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element into which the captured frames are stored, potentially manipulated in some way, and then converted into an output image file. This canvas is kept hidden by styling the canvas with [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)`:none`, to avoid cluttering up the screen — the user does not need to see this intermediate stage.

We also have an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element into which we will draw the image — this is the final display shown to the user.

      <canvas id="canvas">
      </canvas>
      <div class="output">
        <img id="photo" alt="The screen capture will appear in this box.">
      </div>

That's all of the relevant HTML. The rest is just some page layout fluff and a bit of text offering a link back to this page.

[<span style="font-size: 30px;">The JavaScript code</span>](#the_javascript_code "Permalink to The JavaScript code")
--------------------------------------------------------------------------------------------------------------------

Now let's take a look at the <a href="https://github.com/mdn/samples-server/tree/master/s/webrtc-capturestill/capture.js" class="external">JavaScript code</a>. We'll break it up into a few bite-sized pieces to make it easier to explain.

### [Initialization](#initialization "Permalink to Initialization")

We start by wrapping the whole script in an anonymous function to avoid global variables, then setting up various variables we'll be using.

    (function() {
      var width = 320;    // We will scale the photo width to this
      var height = 0;     // This will be computed based on the input stream

      var streaming = false;

      var video = null;
      var canvas = null;
      var photo = null;
      var startbutton = null;

Those variables are:

`width`  
Whatever size the incoming video is, we're going to scale the resulting image to be 320 pixels wide.

`height`  
The output height of the image will be computed given the `width` and the aspect ratio of the stream.

`streaming`  
Indicates whether or not there is currently an active stream of video running.

`video`  
This will be a reference to the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element after the page is done loading.

`canvas`  
This will be a reference to the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element after the page is done loading.

`photo`  
This will be a reference to the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element after the page is done loading.

`startbutton`  
This will be a reference to the [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element that's used to trigger capture. We'll get that after the page is done loading.

### [The startup() function](#the_startup_function "Permalink to The startup() function")

The `startup()` function is run when the page has finished loading, courtesy of [`EventTarget.addEventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener). This function's job is to request access to the user's webcam, initialize the output [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) to a default state, and to establish the event listeners needed to receive each frame of video from the camera and react when the button is clicked to capture an image.

#### Getting element references

First, we grab references to the major elements we need to be able to access.

      function startup() {
        video = document.getElementById('video');
        canvas = document.getElementById('canvas');
        photo = document.getElementById('photo');
        startbutton = document.getElementById('startbutton');

#### Get the media stream

The next task is to get the media stream:

        navigator.mediaDevices.getUserMedia({ video: true, audio: false })
        .then(function(stream) {
            video.srcObject = stream;
            video.play();
        })
        .catch(function(err) {
            console.log("An error occurred: " + err);
        });

Here, we're calling [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia) and requesting a video stream (without audio). It returns a promise which we attach success and failure callbacks to.

The success callback receives a `stream` object as input. It is the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element's source to our new stream.

Once the stream is linked to the `<video>` element, we start it playing by calling `HTMLMediaElement.play()`.

The error callback is called if opening the stream doesn't work. This will happen for example if there's no compatible camera connected, or the user denied access.

#### Listen for the video to start playing

After calling `HTMLMediaElement.play()` on the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video), there's a (hopefully brief) period of time that elapses before the stream of video begins to flow. To avoid blocking until that happens, we add an event listener to `video` for the `canplay` event, which is delivered when the video playback actually begins. At that point, all the properties in the `video` object have been configured based on the stream's format.

        video.addEventListener('canplay', function(ev){
          if (!streaming) {
            height = video.videoHeight / (video.videoWidth/width);

            video.setAttribute('width', width);
            video.setAttribute('height', height);
            canvas.setAttribute('width', width);
            canvas.setAttribute('height', height);
            streaming = true;
          }
        }, false);

This callback does nothing unless it's the first time it's been called; this is tested by looking at the value of our `streaming` variable, which is `false` the first time this method is run.

If this is indeed the first run, we set the video's height based on the size difference between the video's actual size, `video.videoWidth`, and the width at which we're going to render it, `width`.

Finally, the `width` and `height` of both the video and the canvas are set to match each other by calling [`Element.setAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute) on each of the two properties on each element, and setting widths and heights as appropriate. Finally, we set the `streaming` variable to `true` to prevent us from inadvertently running this setup code again.

#### Handle clicks on the button

To capture a still photo each time the user clicks the `startbutton`, we need to add an event listener to the button, to be called when the `click` event is issued:

        startbutton.addEventListener('click', function(ev){
          takepicture();
          ev.preventDefault();
        }, false);

This method is simple enough: it just calls our `takepicture()` function, defined below in the section [Capturing a frame from the stream](#capturing_a_frame_from_the_stream), then calls [`Event.preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault) on the received event to prevent the click from being handled more than once.

#### Wrapping up the startup() method

There are only two more lines of code in the `startup()` method:

        clearphoto();
      }

This is where we call the `clearphoto()` method we'll describe below in the section [Clearing the photo box](#clearing_the_photo_box).

### [Clearing the photo box](#clearing_the_photo_box "Permalink to Clearing the photo box")

Clearing the photo box involves creating an image, then converting it into a format usable by the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element that displays the most recently captured frame. That code looks like this:

      function clearphoto() {
        var context = canvas.getContext('2d');
        context.fillStyle = "#AAA";
        context.fillRect(0, 0, canvas.width, canvas.height);

        var data = canvas.toDataURL('image/png');
        photo.setAttribute('src', data);
      }

We start by getting a reference to the hidden [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element that we use for offscreen rendering.  Next we set the `fillStyle` to `#AAA` (a fairly light grey), and fill the entire canvas with that color by calling [`fillRect()`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fillRect "fillRect()").

Last in this function, we convert the canvas into a PNG image and call `photo.setAttribute()` to make our captured still box display the image.

### [Capturing a frame from the stream](#capturing_a_frame_from_the_stream "Permalink to Capturing a frame from the stream")

There's one last function to define, and it's the point to the entire exercise: the `takepicture()` function, whose job it is to capture the currently displayed video frame, convert it into a PNG file, and display it in the captured frame box. The code looks like this:

      function takepicture() {
        var context = canvas.getContext('2d');
        if (width && height) {
          canvas.width = width;
          canvas.height = height;
          context.drawImage(video, 0, 0, width, height);

          var data = canvas.toDataURL('image/png');
          photo.setAttribute('src', data);
        } else {
          clearphoto();
        }
      }

As is the case any time we need to work with the contents of a canvas, we start by getting the [`2D drawing context`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D "2D drawing context") for the hidden canvas.

Then, if the width and height are both non-zero (meaning that there's at least potentially valid image data), we set the width and height of the canvas to match that of the captured frame, then call [`drawImage()`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/drawImage "drawImage()") to draw the current frame of the video into the context, filling the entire canvas with the frame image.

**Note:** This takes advantage of the fact that the [`HTMLVideoElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement) interface looks like an [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement) to any API that accepts an `HTMLImageElement` as a parameter, with the video's current frame presented as the image's contents.

Once the canvas contains the captured image, we convert it to PNG format by calling [`HTMLCanvasElement.toDataURL()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/toDataURL) on it; finally, we call [`photo.setAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute "photo.setAttribute()") to make our captured still box display the image.

If there isn't a valid image available (that is, the `width` and `height` are both 0), we clear the contents of the captured frame box by calling `clearphoto()`.

[Fun with filters](#fun_with_filters "Permalink to Fun with filters")
---------------------------------------------------------------------

Since we're capturing images from the user's webcam by grabbing frames from a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, we can very easily apply filters and fun effects to the video. As it turns out, any CSS filters you apply to the element using the [`filter`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter) property affect the captured photo. These filters can range from the simple (making the image black and white)  to the extreme (gaussian blurs and hue rotation).

You can play with this effect using, for example, the Firefox developer tools' [style editor](https://developer.mozilla.org/en-US/docs/Tools/Style_Editor); see [Edit CSS filters](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Edit_CSS_filters) for details on how to do so.

[Using specific devices](#using_specific_devices "Permalink to Using specific devices")
---------------------------------------------------------------------------------------

You can, if needed, restrict the set of permitted video sources to a specific device or set of devices. To do so, call [`MediaDevices.enumerateDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/enumerateDevices). When the promise is fulfilled with an array of [`MediaDeviceInfo`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDeviceInfo)  objects describing the available devices, find the ones that you want to allow and specify the corresponding [`deviceId`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/deviceId "deviceId") or `deviceId`s in the [`MediaTrackConstraints`](https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints) object passed into [`getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia "getUserMedia()").

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   <a href="https://mdn-samples.mozilla.org/s/webrtc-capturestill" class="external">Try this sample</a>
-   <a href="https://github.com/mdn/samples-server/tree/master/s/webrtc-capturestill" class="external">Sample code on Github</a>
-   [`MediaDevices.getUserMedia`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
-   [Using frames from a video](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Using_images#using_frames_from_a_video) in [Using images](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Using_images)
-   [`CanvasRenderingContext2D.drawImage()`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/drawImage)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_api/taking_still_photos/index.html "Folder: en-us/web/api/webrtc_api/taking_still_photos (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FTaking_still_photos%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_api%2Ftaking_still_photos%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FTaking_still_photos%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_api%2Ftaking_still_photos%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F6c2523b8365f2bef7b26dee75ac7c74e686f3f62%0A*+Document+last+modified%3A+2021-02-24T02%3A44%3A05.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Taking+still+photos+with+WebRTC%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Feb 24, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Taking_still_photos/contributors.txt)

Change your languageSelect your preferred language English (US)EspañolFrançaisРусский中文 (简体)

Change language

#### Related Topics

1.  [**WebRTC API**](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
2.  WebRTC Guides
    1.  [WebRTC Architecture](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Architecture)
    2.  [WebRTC Basics](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/WebRTC_Basics)
    3.  [WebRTC Protocols](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Protocols)
    4.  [Dealing with connectivity](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Connectivity)
    5.  [Overview of WebRTC interfaces](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Overview)
    6.  [Lifetime of a WebRTC Session](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime)
    7.  [Using data channels](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Using_data_channels)
3.  WebRTC Tutorials
    1.  [Interoperability with adapter.js](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/adapter.js)
    2.  [Taking still photos from the camera](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Taking_still_photos)
    3.  [A simple data channel example](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Simple_RTCDataChannel_sample)
    4.  [Building an internet-connected phone with Peer.js](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Build_a_phone_with_peerjs)
4.  Interfaces
    1.  [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
    2.  [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription)
    3.  [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate)
    4.  [`RTCPeerConnectionIceEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent)
    5.  [`MessageEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent)
    6.  [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)
    7.  [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
    8.  [`RTCIdentityEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityEvent)
    9.  [`RTCIdentityErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityErrorEvent)
    10. [`MediaStreamEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamEvent)
    11. [`MediaStreamTrack`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack)
    12. [`MediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices)
5.  **[Documentation:](https://developer.mozilla.org/en-US/docs/MDN)**
6.  Contribute
    1.  [The MDN project](https://developer.mozilla.org/en-US/docs/MDN)

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
