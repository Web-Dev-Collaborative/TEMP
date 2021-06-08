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
4.  <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Perfect_negotiation" class="breadcrumb-current-page"><span data-property="name">Establishing a connection: The WebRTC perfect negotiation pattern</span></a>

Table of contents
-----------------

Table of contents

-   [Perfect negotiation concepts](#perfect_negotiation_concepts)
-   [Implementing perfect negotiation](#implementing_perfect_negotiation)
-   [Making negotiation perfect](#making_negotiation_perfect)
-   [See also](#see_also)

Establishing a connection: The WebRTC perfect negotiation pattern
=================================================================

Because [WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API) doesn't mandate a specific transport mechanism for signaling during the negotiation of a new peer connection, it's highly flexible. However, despite that flexibility in transport and communication of signaling messages, there's still a recommended design pattern you should follow when possible, known as **perfect negotiation**. <span class="seoSummary">This article introduces WebRTC perfect negotiation, describing how it works and why it's the recommended way to negotiate a WebRTC connection between peers, and provides sample code to demonstrate the technique.</span>

After the first deployments of WebRTC-capable browsers, it was realized that parts of the negotiation process were more complicated than they needed to be for typical use cases. This was due to a small number of issues with the API and some potential race conditions that needed to be prevented. These issues have since been addressed, letting us simplify our WebRTC negotiation significantly. The perfect negotiation pattern is an example of the ways in which negotiation have improved since the early days of WebRTC.

[Perfect negotiation concepts](#perfect_negotiation_concepts "Permalink to Perfect negotiation concepts")
---------------------------------------------------------------------------------------------------------

Perfect negotiation makes it possible to seamlessly and completely separate the negotiation process from the rest of your application's logic. Negotiation is an inherently asymmetric operation: one side needs to serve as the "caller" while the other peer is the "callee." The perfect negotiation pattern smooths this difference away by separating that difference out into independent negotiation logic, so that your application doesn't need to care which end of the connection it is. As far as your application is concerned, it makes no difference whether you're calling out or receiving a call.

The best thing about perfect negotiation is that the same code is used for both the caller and the callee, so there's no repetition or otherwise added levels of negotiation code to write.

Perfect negotiation works by assigning each of the two peers a role to play in the negotiation process that's entirely separate from the WebRTC connection state:

-   A **polite** peer, which uses ICE rollback to prevent collisions with incoming offers. A polite peer, essentially, is one which may send out offers, but then responds if an offer arrives from the other peer with "Okay, never mind, drop my offer and I'll consider yours instead."
-   An **impolite** peer, which always ignores incoming offers that collide with its own offers. It never apologizes or gives up anything to the polite peer. Any time a collision occurs, the impolite peer wins.

This way, both peers know exactly what should happen if there are collisions between offers that have been sent. Responses to error conditions become far more predictable.

How you determine which peer is polite and which is impolite is generally up to you. It could be as simple as assigning the polite role to the first peer to connect to the signaling server, or you could do something more elaborate like having the peers exchange random numbers and assigning the polite role to the winner. However you make the determination, once these roles are assigned to the two peers, they can then work together to manage signaling in a way that doesn't deadlock and doesn't require a lot of extra code to manage.

An important thing to keep in mind is this: the roles of caller and callee can switch during perfect negotiation. If the polite peer is the caller and it sends an offer but there's a collision with the impolite peer, the polite peer drops its offer and instead replies to the offer it has received from the impolite peer. By doing so, the polite peer has switched from being the caller to the callee!

[Implementing perfect negotiation](#implementing_perfect_negotiation "Permalink to Implementing perfect negotiation")
---------------------------------------------------------------------------------------------------------------------

Let's take a look at an example that implements the perfect negotiation pattern. The code assumes that there's a `SignalingChannel` class defined that is used to communicate with the signaling server. Your own code, of course, can use any signaling technique you like.

Note that this code is identical for both peers involved in the connection.

### [Create the signaling and peer connections](#create_the_signaling_and_peer_connections "Permalink to Create the signaling and peer connections")

First, the signaling channel needs to be opened and the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) needs to be created. The [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server listed here is obviously not a real one; you'll need to replace `stun.myserver.tld` with the address of a real STUN server.

    const config = {
      iceServers: [{ urls: "stun:stun.mystunserver.tld" }]
    };

    const signaler = new SignalingChannel();
    const pc = new RTCPeerConnection(config);

This code also gets the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements using the classes "selfview" and "remoteview"; these will contain, respectively, the local user's self-view and the view of the incoming stream from the remote peer.

### [Connecting to a remote peer](#connecting_to_a_remote_peer "Permalink to Connecting to a remote peer")

    const constraints = { audio: true, video: true };
    const selfVideo = document.querySelector("video.selfview");
    const remoteVideo = document.querySelector("video.remoteview");


    async function start() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia(constraints);

        for (const track of stream.getTracks()) {
          pc.addTrack(track, stream);
        }
        selfVideo.srcObject = stream;
      } catch(err) {
        console.error(err);
      }
    }

The `start()` function shown above can be called by either of the two end-points that want to talk to one another. It doesn't matter who does it first; the negotiation will just work.

This isn't appreciably different from older WebRTC connection establishment code. The user's camera and microphone are obtained by calling [`getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia "getUserMedia()"). The resulting media tracks are then added to the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) by passing them into [`addTrack()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addTrack "addTrack()"). Then, finally, the media source for the self-view [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element indicated by the `selfVideo` constant is set to the camera and microphone stream, allowing the local user to see what the other peer sees.

### [Handling incoming tracks](#handling_incoming_tracks "Permalink to Handling incoming tracks")

We next need to set up a handler for [`track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/track_event "track") events to handle inbound video and audio tracks that have been negotiatied to be received by this peer connection. To do this, we implement the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)'s [`ontrack`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/ontrack "ontrack") event handler.

    pc.ontrack = ({track, streams}) => {
      track.onunmute = () => {
        if (remoteVideo.srcObject) {
          return;
        }
        remoteVideo.srcObject = streams[0];
      };
    };

When the `track` event occurs, this handler executes. Using [destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment), the [`RTCTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent)'s [`track`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/track "track") and [`streams`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent/streams "streams") properties are extracted. The former is either the video track or the audio track being received. The latter is an array of [`MediaStream`](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) objects, each representing a stream containing this track (a track may in rare cases belong to multiple streams at once). In our case, this will always contain one stream, at index 0, because we passed one stream into `addTrack()` earlier.

We add an unmute event handler to the track, because the track will become unmuted once it starts receiving packets. We put the remainder of our reception code in there.

If we already have video coming in from the remote peer (which we can see if the remote view's `<video>` element's [`srcObject`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/srcObject "srcObject") property already has a value), we do nothing. Otherwise, we set `srcObject` to the stream at index 0 in the `streams` array.

### [The perfect negotiation logic](#the_perfect_negotiation_logic "Permalink to The perfect negotiation logic")

Now we get into the true perfect negotiation logic, which functions entirely independently from the rest of the application.

#### Handling the negotiationneeded event

First, we implement the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) event handler [`onnegotiationneeded`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onnegotiationneeded "onnegotiationneeded") to get a local description and send it using the signaling channel to the remote peer.

    let makingOffer = false;

    pc.onnegotiationneeded = async () => {
      try {
        makingOffer = true;
        await pc.setLocalDescription();
        signaler.send({ description: pc.localDescription });
      } catch(err) {
        console.error(err);
      } finally {
        makingOffer = false;
      }
    };

Note that `setLocalDescription()` without arguments automatically creates and sets the appropriate description based on the current [`signalingState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState "signalingState"). The set description is either an answer to the most recent offer from the remote peer *or* a freshly-created offer if there's no negotiation underway. Here, it will always be an `offer`, because the negotiationneeded event is only fired in `stable` state.

We set a Boolean variable, `makingOffer` to `true` to mark that we're preparing an offer. To avoid races, we'll use this value later instead of the signaling state to determine whether or not an offer is being processed because the value of [`signalingState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState "signalingState") changes asynchronously, introducing a glare opportunity.

Once the offer has been created, set and sent (or an error occurs), `makingOffer` gets set back to `false`.

#### Handling incoming ICE candidates

Next, we need to handle the `RTCPeerConnection` event [`icecandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidate_event "icecandidate"), which is how the local ICE layer passes candidates to us for delivery to the remote peer over the signaling channel.

    pc.onicecandidate = ({candidate}) => signaler.send({candidate});

This takes the `candidate` member of this ICE event and passes it through to the signaling channel's `send()` method to be sent over the signaling server to the remote peer.

#### Handling incoming messages on the signaling channel

The last piece of the puzzle is code to handle incoming messages from the signaling server. That's implemented here as an `onmessage` event handler on the signaling channel object. This method is invoked each time a message arrives from the signaling server.

    let ignoreOffer = false;

    signaler.onmessage = async ({ data: { description, candidate } }) => {
      try {
        if (description) {
          const offerCollision = (description.type == "offer") &&
                                 (makingOffer || pc.signalingState != "stable");

          ignoreOffer = !polite && offerCollision;
          if (ignoreOffer) {
            return;
          }

          await pc.setRemoteDescription(description);
          if (description.type == "offer") {
            await pc.setLocalDescription();
            signaler.send({ description: pc.localDescription })
          }
        } else if (candidate) {
          try {
            await pc.addIceCandidate(candidate);
          } catch(err) {
            if (!ignoreOffer) {
              throw err;
            }
          }
        }
      } catch(err) {
        console.error(err);
      }
    }

Upon receiving an incoming message from the `SignalingChannel` through its `onmessage` event handler, the received JSON object is destructured to obtain the `description` or `candidate` found within. If the incoming message has a `description`, it's either an offer or an answer sent by the other peer.

If, on the other hand, the message has a `candidate`, it's an ICE candidate received from the remote peer as part of [trickle ICE](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/canTrickleIceCandidates). The candidate is destined to be delivered to the local ICE layer by passing it into [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate "addIceCandidate()").

##### On receiving a description

If we received a `description`, we prepare to respond to the incoming offer or answer. First, we check to make sure we're in a state in which we can accept an offer. If the connection's signaling state isn't `stable` or if our end of the connection has started the process of making its own offer, then we need to look out for offer collision.

If we're the impolite peer, and we're receiving a colliding offer, we return without setting the description, and instead set `ignoreOffer` to `true` to ensure we also ignore all candidates the other side may be sending us on the signaling channel belonging to this offer. Doing so avoids error noise since we never informed our side about this offer.

If we're the polite peer, and we're receiving a colliding offer, we don't need to do anything special, because our existing offer will automatically be rolled back in the next step.

Having ensured that we want to accept the offer, we set the remote description to the incoming offer by calling [`setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription "setRemoteDescription()"). This lets WebRTC know what the proposed configuration of the other peer is. If we're the polite peer, we will drop our offer and accept the new one.

If the newly-set remote description is an offer, we ask WebRTC to select an appropriate local configuration by calling the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) method [`setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription "setLocalDescription()") without parameters. This causes `setLocalDescription()` to automatically generate an appropriate answer in response to the received offer. Then we send the answer through the signaling channel back to the first peer.

##### On receiving an ICE candidate

On the other hand, if the received message contains an ICE candidate, we deliver it to the local [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) layer by calling the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) method [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate "addIceCandidate()"). If an error occurs and we've ignored the most recent offer, we also ignore any error that may occur when trying to add the candidate.

[Making negotiation perfect](#making_negotiation_perfect "Permalink to Making negotiation perfect")
---------------------------------------------------------------------------------------------------

If you're curious what makes perfect negotiation so... perfect... this section is for you. Here, we'll look at each change made to the WebRTC API and to best practice recommendations to make perfect negotiation possible.

### [Glare-free setLocalDescription()](#glare-free_setlocaldescription "Permalink to Glare-free setLocalDescription()")

In the past, the [`negotiationneeded`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/negotiationneeded_event "negotiationneeded") event was easily handled in a way that was susceptible to glare—that is, it was prone to collisions, where both peers could wind up attempting to make an offer at the same time, leading to one or the other peers getting an error and aborting the connection attempt.

#### The old way

Consider this [`onnegotiationneeded`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onnegotiationneeded "onnegotiationneeded") event handler:

    pc.onnegotiationneeded = async () => {
      try {
        await pc.setLocalDescription(await pc.createOffer());
        signaler.send({description: pc.localDescription});
      } catch(err) {
        console.error(err);
      }
    };

Because the [`createOffer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createOffer "createOffer()") method is asynchronous and takes some time to complete, there's time in which the remote peer might attempt to send an offer of its own, causing us to leave the `stable` state and enter the `have-remote-offer` state, which means we are now waiting for a response to the offer. But once it receives the offer we just sent, so is the remote peer. This leaves both peers in a state in which the connection attempt cannot be completed.

#### Perfect negotiation with the updated API

As shown in the section [Implementing perfect negotiation](#implementing_perfect_negotiation), we can eliminate this problem by introducing a variable (here called `makingOffer`) which we use to indicate that we are in the process of sending an offer, and making use of the updated `setLocalDescription()` method:

    let makingOffer = false;

    pc.onnegotiationneeded = async () => {
      try {
        makingOffer = true;
        await pc.setLocalDescription();
        signaler.send({ description: pc.localDescription });
      } catch(err) {
        console.error(err);
      } finally {
        makingOffer = false;
      }
    };

We set `makingOffer` immediately before calling `setLocalDescription()` in order to lock against interfering with sending this offer, and we don't clear it back to `false` until the offer has been sent to the signaling server (or an error has occurred, preventing the offer from being made). This way, we avoid the risk of offers colliding.

### [Automatic rollback in setRemoteDescription()](#automatic_rollback_in_setremotedescription "Permalink to Automatic rollback in setRemoteDescription()")

A key component to perfect negotiation is the concept of the polite peer, which always rolls itself back if it receives an offer while itself waiting for an answer to an offer. Previously, triggering rollback involved manually checking for rollback conditions and triggering the rollback manually, by setting the local description to one with the type `rollback`, like this:

    await pc.setLocalDescription({ type: "rollback" });

Doing so returns the local peer to the `stable` [`signalingState`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/signalingState "signalingState") from whichever state it had previously been in. Since a peer can only accept offers when in the `stable` state, the peer has thus rescinded its offer and is ready to receive the offer from the remote (impolite) peer. As we'll see in a moment, there are problems with this approach, however.

#### Perfect negotiation with the old API

Using the previous API to implement incoming negotiation messages during perfect negotiation would look something like this:

    signaler.onmessage = async({data: { description, candidate }}) => {
      try {
        if (description) {
          if (description.type == "offer" && pc.signalingState != "stable") {
            if (!polite) {
              return;
            }

            await Promise.all([
              pc.setLocalDescription({type: "rollback"}),
              pc.setRemoteDescription(description)
            ]);
          } else {
            await pc.setRemoteDescription(description);
          }

          if (description.type == "offer") {
            await pc.setLocalDescription(await pc.createAnswer());
            signaler.send({ description: pc.localDescription });
          }
        } else if (candidate) {
          try {
            await pc.addIceCandidate(candidate);
          } catch(err) {
            if (!ignoreOffer) {
              throw err;
            }
          }
        }
      } catch(err) {
        console.error(err);
      }
    };

Since rollback works by postponing changes until the next negotiation (which will begin immediately after the current one is finished), the polite peer needs to know when it needs to throw away a received offer if it's currently waiting for a reply to an offer it's already sent.

The code checks to see if the message is an offer, and if so, if the local signaling state isn't `stable`. If it's not stable, *and* the local peer is the polite one, we need to trigger rollback so we can replace the outgoing offer with the new incoming one. and these must both be completed before we can proceed with handling the received offer.

Since there isn't a single "roll back and use this offer instead", performing this change on the polite peer requires two steps, executed in the context of `Promise.all()`, which is used to ensure that both statements execute completely before continuing to handle the received offer. The first statement triggers rollback and the second sets the remote description to the received one, thus completing the process of replacing the previously *sent* offer with the newly *received* offer. The impolite peer has now become the callee instead of the caller.

All other descriptions received from the impolite peer are processed as normal, by passing them into [`setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription "setRemoteDescription()").

Finally, we process a received offer by calling `setLocalDescription()` to set our local description to the one returned by [`createAnswer()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createAnswer "createAnswer()"). Then that gets sent to the polite peer using the signaling channel.

If the incoming message is an ICE candidate rather than an SDP description, it's delivered to the ICE layer by passing it into the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) method [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate "addIceCandidate()"). If an error occurs here and we didn't just discard an offer due to being the impolite peer during a collision, we `throw` the error so the caller can handle it. Otherwise, we drop the error, ignoring it, since it doesn't matter in this context.

#### Perfect negotiation with the updated API

The updated code takes advantage of the fact that you can now call [`setLocalDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription "setLocalDescription()") with no parameters so it just does the right thing for you, as well as the fact that `setRemoteDescription()` automatically rolls back if necessary. This lets us get rid of the need to use a `Promise` to keep the timing in order, since the rollback becomes an essentially atomic part of the `setRemoteDescription()` call.

    let ignoreOffer = false;

    signaler.onmessage = async ({ data: { description, candidate } }) => {
      try {
        if (description) {
          const offerCollision = (description.type == "offer") &&
                                 (makingOffer || pc.signalingState != "stable");

          ignoreOffer = !polite && offerCollision;
          if (ignoreOffer) {
            return;
          }

          await pc.setRemoteDescription(description);
          if (description.type == "offer") {
            await pc.setLocalDescription();
            signaler.send({ description: pc.localDescription });
          }
        } else if (candidate) {
          try {
            await pc.addIceCandidate(candidate);
          } catch(err) {
            if (!ignoreOffer) {
              throw err;
            }
          }
        }
      } catch(err) {
        console.error(err);
      }
    }

While the difference in code size is minor, and the complexity isn't reduced much either, the code is much, much more reliable. Let's take a dive into the code to see how it works now.

##### On receiving a description

In the revised code, if the received message is an SDP `description`, we check to see if it arrived while we're attempting to transmit an offer. If the received message is an `offer` *and* the local peer is the impolite peer, *and* a collision is occurring, we ignore the offer because we want to continue to try to use the offer that's already in the process of being sent. That's the impolite peer in action.

In any other case, we'll try instead to handle the incoming message. This begins by setting the remote description to the received `description` by passing it into [`setRemoteDescription()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription "setRemoteDescription()"). This works regardless of whether we're handling an offer or an answer since rollback will be performed automaticaly as needed.

At that point, if the received message is an `offer`, we use `setLocalDescription()` to create and set an appropriate local description, then we send it to the remote peer over the signaling server.

##### On receiving an ICE candidate

On the other hand, if the received message is an ICE candidate—indicated by the JSON object containing a `candidate` member—we deliver it to the local ICE layer by calling the [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection) method [`addIceCandidate()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate "addIceCandidate()"). Errors are, as before, ignored if we have just discarded an offer.

### [Explicit restartIce() method added](#explicit_restartice_method_added "Permalink to Explicit restartIce() method added")

The techniques previously used to trigger an [ICE restart](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime#ice_restart) while handling the event[`negotiationneeded`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/negotiationneeded_event "negotiationneeded") have significant flaws. These flaws have made it difficult to safely and reliably trigger a restart during negotiation. The perfect negotiation improvements have fixed this by adding a new [`restartIce()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/restartIce "restartIce()") method to `RTCPeerConnection`.

#### The old way

In the past, if you encountered an ICE error and needed to restart negotiation, you might have done something like this:

    pc.onnegotiationneeded = async options => {
      await pc.setLocalDescription(await pc.createOffer(options));
      signaler.send({ description: pc.localDescription });
    };
    pc.oniceconnectionstatechange = () => {
      if (pc.iceConnectionState === "failed") {
        pc.onnegotiationneeded({ iceRestart: true });
      }
    };

This has a number of reliability issues and outright bugs (such as failing if the [`iceconnectionstatechange`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceconnectionstatechange_event "iceconnectionstatechange") event fires when the signaling state isn't `stable`), but there was no way you could actually request an ICE restart other than by creating and sending an offer with the [`iceRestart`](https://developer.mozilla.org/en-US/docs/Web/API/RTCOfferOptions/iceRestart "iceRestart") option set to `true`. Sending the restart request thus required directly invoking the `negotiationneeded` event's handler. Getting it right was tricky at best, and was so easy to get wrong that bugs are common.

#### Using restartIce()

Now, you can use `restartIce()` to do this much more cleanly:

    pc.onnegotiationneeded = async options => {
      await pc.setLocalDescription(await pc.createOffer(options));
      signaler.send({ description: pc.localDescription });
    };
    pc.oniceconnectionstatechange = () => {
      if (pc.iceConnectionState === "failed") {
        pc.restartIce();
      }
    };

With this improved technique, instead of directly calling `onnegotiationneeded` with options to trigger ICE restart, the `failed` [ICE connection state](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/iceConnectionState) calls [`restartIce()`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/restartIce "restartIce()"). `restartIce()` tells the ICE layer to automatically add the `iceRestart` flag to the next ICE message sent. Problem solved!

### [Rollback no longer supported in the pranswer state](#rollback_no_longer_supported_in_the_pranswer_state "Permalink to Rollback no longer supported in the pranswer state")

The last of the API changes that stand out is that you can no longer roll back when in either of the `have-remote-pranswer` or the `have-local-pranswer` states. Fortunately, when using perfect negotiation there's no need to do this anyway, since the situations that cause this are caught and prevented before rolling these back ever becomes necessary.

Thus, attempting to trigger rollback while in one of the two `pranswer` states will now throw an `InvalidStateError`.

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
-   [Lifetime of a WebRTC session](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Session_lifetime)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/webrtc_api/perfect_negotiation/index.html "Folder: en-us/web/api/webrtc_api/perfect_negotiation (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FPerfect_negotiation%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fwebrtc_api%2Fperfect_negotiation%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWebRTC_API%2FPerfect_negotiation%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fwebrtc_api%2Fperfect_negotiation%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fba4a07195d8f8f4941e7ae06118b8405f9cac9cf%0A*+Document+last+modified%3A+2021-04-10T23%3A58%3A36.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Establishing+a+connection%3A+The+WebRTC+perfect+nego%E2%80%A6%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Apr 10, 2021, [by MDN contributors](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Perfect_negotiation/contributors.txt)

#### Related Topics

1.  **[WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
2.  **[`WebRTC_API`](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)**
3.  Related pages for WebRTC
    1.  [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
    2.  [`Navigator.mediaDevices`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices)
    3.  [`RTCCertificate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCCertificate)
    4.  [`RTCDTMFSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender)
    5.  [`RTCDTMFToneChangeEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent)
    6.  [`RTCDataChannel`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel)
    7.  [`RTCDataChannelEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannelEvent)
    8.  [`RTCDtlsTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport)
    9.  [`RTCErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCErrorEvent)
    10. [`RTCIceCandidate`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate)
    11. [`RTCIceTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport)
    12. [`RTCPeerConnection`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection)
    13. [`RTCPeerConnectionIceErrorEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceErrorEvent)
    14. [`RTCPeerConnectionIceEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnectionIceEvent)
    15. [`RTCRtpReceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpReceiver)
    16. [`RTCRtpSender`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender)
    17. [`RTCRtpTransceiver`](https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver)
    18. [`RTCSctpTransport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSctpTransport)
    19. [`RTCSessionDescription`](https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription)
    20. [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
    21. [`RTCTrackEvent`](https://developer.mozilla.org/en-US/docs/Web/API/RTCTrackEvent)

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
