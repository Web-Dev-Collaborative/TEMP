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
3.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection" class="breadcrumb-penultimate"><span data-property="name">RTCPeerConnection</span></a>
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidate_event" class="breadcrumb-current-page"><span data-property="name">RTCPeerConnection: icecandidate event</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Description](#description)
-   [Examples](#examples)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

RTCPeerConnection: icecandidate event
=====================================

An **`icecandidate`** event is sent to an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)  when an [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate) has been identified and added to the local peer by a call to [`RTCPeerConnection.setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription). The event handler should transmit the candidate to the remote peer over the signaling channel so the remote peer can add it to its set of remote candidates.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent"><code>RTCPeerConnectionIceEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicecandidate"><code>RTCPeerConnection.onicecandidate</code></a></td></tr></tbody></table>

[Description](#description "Permalink to Description")
------------------------------------------------------

There are three reasons why the `icecandidate` event is fired on an [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection).

### [Sharing a new candidate](#sharing_a_new_candidate "Permalink to Sharing a new candidate")

The majority of `icecandidate` events are fired to indicate that a new candidate has been gathered. This candidate needs to be delivered to the remote peer over the signaling channel your code manages.

    rtcPeerConnection.onicecandidate = (event) => {
      if (event.candidate) {
        sendCandidateToRemotePeer(event.candidate)
      } else {
        /* there are no more candidates coming during this negotiation */
      }
    }

The remote peer, upon receiving the candidate, will add the candidate to its candidate pool by calling [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate "addIceCandidate()"), passing in the [`candidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent/candidate "candidate") string you have passed along using the signaling server.

### [Indicating the end of a generation of candidates](#indicating_the_end_of_a_generation_of_candidates "Permalink to Indicating the end of a generation of candidates")

When an ICE negotiation session runs out of candidates to propose for a given [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport), it has completed gathering for a **generation** of candidates. That this has occurred is indicated by an `icecandidate` event whose [`candidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent/candidate "candidate") string is empty (`""`).

You should deliver this to the remote peer just like any standard candidate, as described under [Sharing a new candidate](#sharing_a_new_candidate) above. This ensures that the remote peer is given the end-of-candidates notification as well. As you see in the code in the previous section, every candidate is sent to the other peer, including any that might have an empty candidate string. Only candidates for which the event's [`candidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent/candidate "candidate") property is `null` are not forwarded across the signaling connection.

The end-of-candidates indication is described in <a href="https://datatracker.ietf.org/doc/html/draft-ietf-mmusic-trickle-ice-02#section-9.3" class="external">section 9.3 of the Trickle ICE draft specification</a> (note that the section number is subject to change as the specification goes through repeated drafts).

### [Indicating that ICE gathering is complete](#indicating_that_ice_gathering_is_complete "Permalink to Indicating that ICE gathering is complete")

Once all ICE transports have finished gathering candidates and the value of the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) object's [`iceGatheringState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceGatheringState "iceGatheringState") has made the transition to `complete`, an `icecandidate` event is sent with the value of `complete` set to `null`.

This signal exists for backward compatibility purposes and does *not* need to be delivered onward to the remote peer (which is why the code snippet above checks to see if `event.candidate` is `null` prior to sending the candidate along.

If you need to perform any special actions when there are no further candidates expected, you're much better off watching the ICE gathering state by watching for [`icegatheringstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icegatheringstatechange_event "icegatheringstatechange") events:

    pc.addEventListener("icegatheringstatechange", ev => {
      switch(pc.iceGatheringState) {
        case "new":
          /* gathering is either just starting or has been reset */
          break;
        case "gathering":
          /* gathering has begun or is ongoing */
          break;
        case "complete":
          /* gathering has ended */
          break;
      }
    });

As you can see in this example, the `icegatheringstatechange` event lets you know when the value of the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) property [`iceGatheringState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceGatheringState "iceGatheringState") has been updated. If that value is now `complete`, you know that ICE gathering has just ended.

This is a more reliable approach than looking at the individual ICE messages for one indicating that the ICE session is finished.

[Examples](#examples "Permalink to Examples")
---------------------------------------------

This example creates a simple handler for the `icecandidate` event that uses a function called `sendMessage()` to create and send a reply to the remote peer through the signaling server.

First, an example using [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "addEventListener()"):

    pc.addEventListener("icecandidate", ev => {
      if (ev.candidate) {
        sendMessage({
          type: "new-ice-candidate",
          candidate: event.candidate
        });
      }
    }, false);

You can also set the [`onicecandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicecandidate "onicecandidate") event handler property directly:

    pc.onicecandidate = ev => {
      if (ev.candidate) {
        sendMessage({
          type: "new-ice-candidate",
          candidate: event.candidate
        });
      }
    };

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-icecandidate" class="external">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'icecandidate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
-   [Signaling and video calling](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Signaling_and_video_calling)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/rtcpeerconnection/icecandidate_event/index.html "Folder: en-us/web/api/rtcpeerconnection/icecandidate_event (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCPeerConnection%2Ficecandidate_event%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Frtcpeerconnection%2Ficecandidate_event%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FRTCPeerConnection%2Ficecandidate_event%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Frtcpeerconnection%2Ficecandidate_event%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fb38887c5d8925adbfe4c051f5e59132c7363f55a%0A*+Document+last+modified%3A+2021-05-31T16%3A07%3A26.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22RTCPeerConnection%3A+icecandidate+event%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 31, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidate_event/contributors.txt)

Change your languageSelect your preferred language English (US)Русский中文 (简体)

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
