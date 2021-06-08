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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel" class="breadcrumb-penultimate"><span data-property="name">RTCDataChannel</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/open_event" class="breadcrumb-current-page"><span data-property="name">RTCDataChannel: open event</span></a>

Table of contents
-----------------

Table of contents

-   [Examples](#examples)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

RTCDataChannel: open event
==========================

The WebRTC `open` event is sent to an [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) object's [`onopen`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onopen "onopen") event handler when the underlying transport used to send and receive the data channel's messages is opened or re-opened.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent"><code>RTCDataChannelEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onopen" title="onopen"><code>onopen</code></a></td></tr></tbody></table>

[Examples](#examples "Permalink to Examples")
---------------------------------------------

This example adds to the [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel) `dc` a handler for the `open` event that adjusts the user interface to indicate that a chat window is ready to be used after a connection has been established. It enables the message input box and send button as well as enabling the disconnect button and disabling the connect button. Finally, the message input box is focused so the user can immediately begin to type.

    dc.addEventListener("open", ev => {
      messageInputBox.disabled = false;
      sendMessageButton.disabled = false;
      disconnectButton.disabled = false;
      connectButton.disabled = true;

      messageInputBox.focus();

    }, false);

This can also be done by directly setting the value of the channel's [`onopen`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onopen "onopen") event handler property.

    dc.onopen = ev => {
      messageInputBox.disabled = false;
      sendMessageButton.disabled = false;
      disconnectButton.disabled = false;
      connectButton.disabled = true;

      messageInputBox.focus();
    }

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
-   [A simple RTCDataChannel example](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Simple_RTCDataChannel_sample)
-   Related events: [`message`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/message_event "message"), [`close`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close_event "close"), and [`error`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/error_event "error")

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcdatachannel/open_event/index.html "Folder: en-us/web/api/rtcdatachannel/open_event (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCDataChannel%2Fopen_event%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcdatachannel%2Fopen_event%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCDataChannel%2Fopen_event%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcdatachannel%2Fopen_event%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCDataChannel%3A+open+event%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/open_event/contributors.txt)

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel)**
3.  Properties
    1.  [`binaryType`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/binaryType)
    2.  [`bufferedAmount`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmount)
    3.  [`bufferedAmountLowThreshold`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/bufferedAmountLowThreshold)
    4.  [`id`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/id)
    5.  [`label`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/label)
    6.  [`maxPacketLifeTime`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxPacketLifeTime)
    7.  [`maxRetransmits`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/maxRetransmits)
    8.  [`negotiated`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/negotiated)
    9.  [`onbufferedamountlow`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onbufferedamountlow)
    10. [`onclose`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onclose)
    11. [`onclosing`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onclosing)
    12. [`onerror`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onerror)
    13. [`onmessage`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onmessage)
    14. [`onopen`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onopen)
    15. [`ordered`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/ordered)
    16. [`protocol`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/protocol)
    17. [`readyState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/readyState)
    18. [`reliable`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/reliable)
    19. [`stream`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/stream)
4.  Methods
    1.  [`close()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/close)
    2.  [`send()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/send)
5.  Inheritance:
    1.  [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)
6.  Related pages for WebRTC
    1.  [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
    2.  [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
    3.  [`RTCCertificate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCCertificate)
    4.  [`RTCDTMFSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender)
    5.  [`RTCDTMFToneChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent)
    6.  [`RTCDataChannelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent)
    7.  [`RTCDtlsTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport)
    8.  [`RTCErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent)
    9.  [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate)
    10. [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport)
    11. [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
    12. [`RTCPeerConnectionIceErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent)
    13. [`RTCPeerConnectionIceEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent)
    14. [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver)
    15. [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender)
    16. [`RTCRtpTransceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver)
    17. [`RTCSctpTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport)
    18. [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription)
    19. [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
    20. [`RTCTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent)

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
