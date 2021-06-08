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
4.  <a href="Web_audio_spatialization_basics.html" class="breadcrumb-current-page"><span data-property="name">Web audio spatialization basics</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Basics of spatialization](#basics_of_spatialization)
-   [3D boombox demo](#3d_boombox_demo)
-   [Creating an audio listener](#creating_an_audio_listener)
-   [Creating a panner node](#creating_a_panner_node)
-   [Moving the boombox](#moving_the_boombox)
-   [Wiring up our controls](#wiring_up_our_controls)
-   [Connecting Our Graph](#connecting_our_graph)
-   [Summary](#summary)

Web audio spatialization basics
===============================

<span class="seoSummary">As if its extensive variety of sound processing (and other) options wasn't enough, the Web Audio API also includes facilities to allow you to emulate the difference in sound as a listener moves around a sound source, for example panning as you move around a sound source inside a 3D game. The official term for this is **spatialization**, and this article will cover the basics of how to implement such a system.</span>

[Basics of spatialization](#basics_of_spatialization "Permalink to Basics of spatialization")
---------------------------------------------------------------------------------------------

In Web Audio, complex 3D spatializations are created using the [`PannerNode`](../PannerNode.html), which in layman's terms is basically a whole lotta cool maths to make audio appear in 3D space. Think sounds flying over you, creeping up behind you, moving across in front of you. That sort of thing.

It's really useful for WebXR and gaming. In 3D spaces, it's the only way to achieve realistic audio. Libraries like <a href="https://threejs.org/" class="external">three.js</a> and <a href="https://aframe.io/" class="external">A-frame</a> harness its potential when dealing with sound. It's worth noting that you don't *have* to move sound within a full 3D space either — you could stick with just a 2D plane, so if you were planning a 2D game, this would still be the node you were looking for.

**Note**: There's also a [`StereoPannerNode`](../StereoPannerNode.html) designed to deal with the common use case of creating simple left and right stereo panning effects. This is much simpler to use, but obviously nowhere near as versatile. If you just want a simple stereo panning effect, our <a href="https://mdn.github.io/webaudio-examples/stereo-panner-node/" class="external">StereoPannerNode example</a> (<a href="https://github.com/mdn/webaudio-examples/tree/master/stereo-panner-node" class="external">see source code</a>) should give you everything you need.

[3D boombox demo](#3d_boombox_demo "Permalink to 3D boombox demo")
------------------------------------------------------------------

To demonstrate 3D spatialization we've created a modified version of the boombox demo we created in our basic [Using the Web Audio API](Using_Web_Audio_API.html) guide. see the <a href="https://mdn.github.io/webaudio-examples/spacialization/" class="external">3D spatialization demo live</a> (and see the <a href="https://github.com/mdn/webaudio-examples/tree/master/spacialization" class="external">source code</a> also).

<img src="Web_audio_spatialization_basics/web-audio-spatialization.png" alt="A simple UI with a rotated boombox and controls to move it left and right and in and out, and rotate it." width="949" height="724" />

The boombox sits inside a room (defined by the edges of the browser viewport), and in this demo, we can move and rotate it with the provided controls. When we move the boombox, the sound it produces changes accordingly, panning as it moves to the left or right of the room, or becoming quieter as it is moved away from the user or is rotated so the speakers are facing away from them, etc. This is done by setting the different properties of the `PannerNode` object instance in relation to that movement, to emulate spacialization.

**Note**: The experience is much better if you use headphones, or have some kind of surround sound system to plug your computer into.

[Creating an audio listener](#creating_an_audio_listener "Permalink to Creating an audio listener")
---------------------------------------------------------------------------------------------------

So let's begin! The [`BaseAudioContext`](../BaseAudioContext.html) (the interface the [`AudioContext`](../AudioContext.html) is extended from) has a `listener` property that returns an [`AudioListener`](../AudioListener.html) object. This represents the listener of the scene, usually your user. You can define where they are in space and in which direction they are facing. They remain static. The `pannerNode` can then calculate its sound position relative to the position of the listener.

Let's create our context and listener and set the listener's position to emulate a person looking into our room:

    const AudioContext = window.AudioContext || window.webkitAudioContext;
    const audioCtx = new AudioContext();
    const listener = audioCtx.listener;

    const posX = window.innerWidth/2;
    const posY = window.innerHeight/2;
    const posZ = 300;

    listener.positionX.value = posX;
    listener.positionY.value = posY;
    listener.positionZ.value = posZ-5;

We could move the listener left or right using `positionX`, up or down using `positionY`, or in or out of the room using `positionZ`. Here we are setting the listener to be in the middle of the viewport and slightly in front of our boombox. We can also set the direction the listener is facing. The default values for these work well:

    listener.forwardX.value = 0;
    listener.forwardY.value = 0;
    listener.forwardZ.value = -1;
    listener.upX.value = 0;
    listener.upY.value = 1;
    listener.upZ.value = 0;

The forward properties represent the 3D coordinate position of the listener's forward direction (e.g. the direction they are facing in), while the up properties represent the 3D coordinate position of the top of the listener's head. These two together can nicely set the direction.

[Creating a panner node](#creating_a_panner_node "Permalink to Creating a panner node")
---------------------------------------------------------------------------------------

Let's create our [`PannerNode`](../PannerNode.html). This has a whole bunch of properties associated with it. Let's take a look at each of them:

To start we can set the [`panningModel`](../PannerNode/panningModel.html). This is the spacialization algorithm that's used to position the audio in 3D space. We can set this to:

`equalpower` — The default and the general way panning is figured out

`HRTF` — This stands for 'Head-related transfer function' and looks to take into account the human head when figuring out where the sound is.

Pretty clever stuff. Let's use the `HRTF` model!

    const pannerModel = 'HRTF';

The [`coneInnerAngle`](../PannerNode/coneInnerAngle.html) and [`coneOuterAngle`](../PannerNode/coneOuterAngle.html) properties specify where the volume emanates from. By default, both are 360 degrees. Our boombox speakers will have smaller cones, which we can define. The inner cone is where gain (volume) is always emulated at a maximum and the outer cone is where the gain starts to drop away. The gain is reduced by the value of the [`coneOuterGain`](../PannerNode/coneOuterGain.html) value. Let's create constants that store the values we'll use for these parameters later on:

    const innerCone = 60;
    const outerCone = 90;
    const outerGain = 0.3;

The next parameter is [`distanceModel`](../PannerNode/distanceModel.html) — this can only be set to `linear`, `inverse`, or `exponential`. These are different algorithms, which are used to reduce the volume of the audio source as it moves away from the listener. We'll use `linear`, as it is simple:

    const distanceModel = 'linear';

We can set a maximum distance ([`maxDistance`](../PannerNode/maxDistance.html)) between the source and the listener — the volume will not be reduced anymore if the source moves further away from this point. This can be useful, as you may find you want to emulate distance, but volume can drop out and that's actually not what you want. By default, it's 10,000 (a unitless relative value). We can keep it as this:

    const maxDistance = 10000;

There's also a reference distance (`refDistance`), which is used by the distance models. We can keep that at the default value of `1` as well:

    const refDistance = 1;

Then there's the roll-off factor ([`rolloffFactor`](../PannerNode/rolloffFactor.html)) — how quickly does the volume reduce as the panner moves away from the listener. The default value is 1; let's make that a bit bigger to exaggerate our movements.

    const rollOff = 10;

Now we can start setting our position and orientation of our boombox. This is a lot like how we did it with our listener. These are also the parameters we're going to change when the controls on our interface are used.

    const positionX = posX;
    const positionY = posY;
    const positionZ = posZ;

    const orientationX = 0.0;
    const orientationY = 0.0;
    const orientationZ = -1.0;

Note the minus value on our z orientation — this sets the boombox to face us. A positive value would set the sound source facing away from us.

Let's use the relevant constructor for creating our panner node and pass in all those parameters we set above:

    const panner = new PannerNode(audioCtx, {
        panningModel: pannerModel,
        distanceModel: distanceModel,
        positionX: positionX,
        positionY: positionY,
        positionZ: positionZ,
        orientationX: orientationX,
        orientationY: orientationY,
        orientationZ: orientationZ,
        refDistance: refDistance,
        maxDistance: maxDistance,
        rolloffFactor: rollOff,
        coneInnerAngle: innerCone,
        coneOuterAngle: outerCone,
        coneOuterGain: outerGain
    })

[Moving the boombox](#moving_the_boombox "Permalink to Moving the boombox")
---------------------------------------------------------------------------

Now we're going to move our boombox around our 'room'. We've got some controls set up to do this. We can move it left and right, up and down, and back and forth; we can also rotate it. The sound direction is coming from the boombox speaker at the front, so when we rotate it, we can alter the sound's direction — i.e. make it project to the back when the boombox is rotated 180 degrees and facing away from us.

We need to set up a few things for the interface. First, we'll get references to the elements we want to move, then we'll store references to the values we'll change when we set up [CSS transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transforms) to actually do the movement. Finally, we'll set some bounds so our boombox doesn't move too far in any direction:

    const moveControls = document.querySelector('#move-controls').querySelectorAll('button');
    const boombox = document.querySelector('.boombox-body');

    // the values for our css transforms
    let transform = {
        xAxis: 0,
        yAxis: 0,
        zAxis: 0.8,
        rotateX: 0,
        rotateY: 0
    }

    // set our bounds
    const topBound = -posY;
    const bottomBound = posY;
    const rightBound = posX;
    const leftBound = -posX;
    const innerBound = 0.1;
    const outerBound = 1.5;

Let's create a function that takes the direction we want to move as a parameter, and both modifies the CSS transform and updates the position and orientation values of our panner node properties to change the sound as appropriate.

To start with let's take a look at our left, right, up and down values as these are pretty straightforward. We'll move the boombox along these axis and update the appropriate position.

    function moveBoombox(direction) {
        switch (direction) {
            case 'left':
                if (transform.xAxis > leftBound) {
                    transform.xAxis -= 5;
                    panner.positionX.value -= 0.1;
                }
            break;
            case 'up':
                if (transform.yAxis > topBound) {
                    transform.yAxis -= 5;
                    panner.positionY.value -= 0.3;
                }
            break;
            case 'right':
                if (transform.xAxis < rightBound) {
                    transform.xAxis += 5;
                    panner.positionX.value += 0.1;
                }
            break;
            case 'down':
                if (transform.yAxis < bottomBound) {
                    transform.yAxis += 5;
                    panner.positionY.value += 0.3;
                }
            break;
        }
    }

It's a similar story for our move in and out values too:

    case 'back':
        if (transform.zAxis > innerBound) {
            transform.zAxis -= 0.01;
            panner.positionZ.value += 40;
        }
    break;
    case 'forward':
        if (transform.zAxis < outerBound) {
            transform.zAxis += 0.01;
            panner.positionZ.value -= 40;
        }
    break;

Our rotation values are a little more involved, however, as we need to move the sound *around*. Not only do we have to update two axis values (e.g. if you rotate an object around the x-axis, you update the y and z coordinates for that object), but we also need to do some more maths for this. The rotation is a circle and we need `Math.sin` and `Math.cos` to help us draw that circle.

Let's set up a rotation rate, which we'll convert into a radian range value for use in `Math.sin` and `Math.cos` later, when we want to figure out the new coordinates when we're rotating our boombox:

    // set up rotation constants
    const rotationRate = 60; // bigger number equals slower sound rotation

    const q = Math.PI/rotationRate; //rotation increment in radians

We can also use this to work out degrees rotated, which will help with the CSS transforms we will have to create (note we need both an x and y-axis for the CSS transforms):

    // get degrees for css
    const degreesX = (q * 180)/Math.PI;
    const degreesY = (q * 180)/Math.PI;

Let's take a look at our left rotation as an example. We need to change the x orientation and the z orientation of the panner coordinates, to move around the y-axis for our left rotation:

    case 'rotate-left':
      transform.rotateY -= degreesY;

      // 'left' is rotation about y-axis with negative angle increment
      z = panner.orientationZ.value*Math.cos(q) - panner.orientationX.value*Math.sin(q);
      x = panner.orientationZ.value*Math.sin(q) + panner.orientationX.value*Math.cos(q);
      y = panner.orientationY.value;

      panner.orientationX.value = x;
      panner.orientationY.value = y;
      panner.orientationZ.value = z;
    break;

This *is* a little confusing, but what we're doing is using sin and cos to help us work out the circular motion the coordinates need for the rotation of the boombox.

We can do this for all the axes. We just need to choose the right orientations to update and whether we want a positive or negative increment.

    case 'rotate-right':
      transform.rotateY += degreesY;
      // 'right' is rotation about y-axis with positive angle increment
      z = panner.orientationZ.value*Math.cos(-q) - panner.orientationX.value*Math.sin(-q);
      x = panner.orientationZ.value*Math.sin(-q) + panner.orientationX.value*Math.cos(-q);
      y = panner.orientationY.value;
      panner.orientationX.value = x;
      panner.orientationY.value = y;
      panner.orientationZ.value = z;
    break;
    case 'rotate-up':
      transform.rotateX += degreesX;
      // 'up' is rotation about x-axis with negative angle increment
      z = panner.orientationZ.value*Math.cos(-q) - panner.orientationY.value*Math.sin(-q);
      y = panner.orientationZ.value*Math.sin(-q) + panner.orientationY.value*Math.cos(-q);
      x = panner.orientationX.value;
      panner.orientationX.value = x;
      panner.orientationY.value = y;
      panner.orientationZ.value = z;
    break;
    case 'rotate-down':
      transform.rotateX -= degreesX;
      // 'down' is rotation about x-axis with positive angle increment
      z = panner.orientationZ.value*Math.cos(q) - panner.orientationY.value*Math.sin(q);
      y = panner.orientationZ.value*Math.sin(q) + panner.orientationY.value*Math.cos(q);
      x = panner.orientationX.value;
      panner.orientationX.value = x;
      panner.orientationY.value = y;
      panner.orientationZ.value = z;
    break;

One last thing — we need to update the CSS and keep a reference of the last move for the mouse event. Here's the final `moveBoombox` function.

    function moveBoombox(direction, prevMove) {
        switch (direction) {
            case 'left':
                if (transform.xAxis > leftBound) {
                    transform.xAxis -= 5;
                    panner.positionX.value -= 0.1;
                }
            break;
            case 'up':
                if (transform.yAxis > topBound) {
                    transform.yAxis -= 5;
                    panner.positionY.value -= 0.3;
                }
            break;
            case 'right':
                if (transform.xAxis < rightBound) {
                    transform.xAxis += 5;
                    panner.positionX.value += 0.1;
                }
            break;
            case 'down':
                if (transform.yAxis < bottomBound) {
                    transform.yAxis += 5;
                    panner.positionY.value += 0.3;
                }
            break;
            case 'back':
                if (transform.zAxis > innerBound) {
                    transform.zAxis -= 0.01;
                    panner.positionZ.value += 40;
                }
            break;
            case 'forward':
                if (transform.zAxis < outerBound) {
                    transform.zAxis += 0.01;
                    panner.positionZ.value -= 40;
                }
            break;
            case 'rotate-left':
                transform.rotateY -= degreesY;

                // 'left' is rotation about y-axis with negative angle increment
                z = panner.orientationZ.value*Math.cos(q) - panner.orientationX.value*Math.sin(q);
                x = panner.orientationZ.value*Math.sin(q) + panner.orientationX.value*Math.cos(q);
                y = panner.orientationY.value;

                panner.orientationX.value = x;
                panner.orientationY.value = y;
                panner.orientationZ.value = z;
            break;
            case 'rotate-right':
                transform.rotateY += degreesY;
                // 'right' is rotation about y-axis with positive angle increment
                z = panner.orientationZ.value*Math.cos(-q) - panner.orientationX.value*Math.sin(-q);
                x = panner.orientationZ.value*Math.sin(-q) + panner.orientationX.value*Math.cos(-q);
                y = panner.orientationY.value;
                panner.orientationX.value = x;
                panner.orientationY.value = y;
                panner.orientationZ.value = z;
            break;
            case 'rotate-up':
                transform.rotateX += degreesX;
                // 'up' is rotation about x-axis with negative angle increment
                z = panner.orientationZ.value*Math.cos(-q) - panner.orientationY.value*Math.sin(-q);
                y = panner.orientationZ.value*Math.sin(-q) + panner.orientationY.value*Math.cos(-q);
                x = panner.orientationX.value;
                panner.orientationX.value = x;
                panner.orientationY.value = y;
                panner.orientationZ.value = z;
            break;
            case 'rotate-down':
                transform.rotateX -= degreesX;
                // 'down' is rotation about x-axis with positive angle increment
                z = panner.orientationZ.value*Math.cos(q) - panner.orientationY.value*Math.sin(q);
                y = panner.orientationZ.value*Math.sin(q) + panner.orientationY.value*Math.cos(q);
                x = panner.orientationX.value;
                panner.orientationX.value = x;
                panner.orientationY.value = y;
                panner.orientationZ.value = z;
            break;
        }

      boombox.style.transform = 'translateX('+transform.xAxis+'px) translateY('+transform.yAxis+'px) scale('+transform.zAxis+') rotateY('+transform.rotateY+'deg) rotateX('+transform.rotateX+'deg)';

      const move = prevMove || {};
      move.frameId = requestAnimationFrame(() => moveBoombox(direction, move));
        return move;
    }

[Wiring up our controls](#wiring_up_our_controls "Permalink to Wiring up our controls")
---------------------------------------------------------------------------------------

Wiring up out control buttons is comparatively simple — now we can listen for a mouse event on our controls and run this function, as well as stop it when the mouse is released:

    // for each of our controls, move the boombox and change the position values
    moveControls.forEach(function(el) {

        let moving;
        el.addEventListener('mousedown', function() {

            let direction = this.dataset.control;
            if (moving && moving.frameId) {
                window.cancelAnimationFrame(moving.frameId);
            }
            moving = moveBoombox(direction);

        }, false);

        window.addEventListener('mouseup', function() {
            if (moving && moving.frameId) {
                window.cancelAnimationFrame(moving.frameId);
            }
        }, false)

    })

[Connecting Our Graph](#connecting_our_graph "Permalink to Connecting Our Graph")
---------------------------------------------------------------------------------

Our HTML contains the audio element we want to be affected by the panner node.

    <audio src="myCoolTrack.mp3"></audio>

We need to grab the source from that element and pipe it into the Web Audio API using the [`AudioContext.createMediaElementSource`](../AudioContext/createMediaElementSource.html).

    // get the audio element
    const audioElement = document.querySelector('audio');

    // pass it into the audio context
    const track = audioContext.createMediaElementSource(audioElement);

Next we have to connect our audio graph. We connect our input (the track) to our modification node (the panner) to our destination (in this case the speakers).

    track.connect(panner).connect(audioCtx.destination);

Let's create a play button, that when clicked will play or pause the audio depending on the current state.

    <button data-playing="false" role="switch">Play/Pause</button>

    // select our play button
    const playButton = document.querySelector('button');

    playButton.addEventListener('click', function() {

    // check if context is in suspended state (autoplay policy)
    if (audioContext.state === 'suspended') {
    audioContext.resume();
    }

    // play or pause track depending on state
    if (this.dataset.playing === 'false') {
    audioElement.play();
    this.dataset.playing = 'true';
    } else if (this.dataset.playing === 'true') {
    audioElement.pause();
    this.dataset.playing = 'false';
    }

    }, false);

For a more in depth look at playing/controlling audio and audio graphs check out [Using The Web Audio API.](Using_Web_Audio_API.html)

[Summary](#summary "Permalink to Summary")
------------------------------------------

Hopefully, this article has given you an insight into how Web Audio spatialization works, and what each of the [`PannerNode`](../PannerNode.html) properties do (there are quite a few of them). The values can be hard to manipulate sometimes and depending on your use case it can take some time to get them right.

**Note**: There are slight differences in the way the audio spatialization sounds across different browsers. The panner node does some very involved maths under the hood; there are a <a href="https://wpt.fyi/results/webaudio/the-audio-api/the-pannernode-interface?label=stable&amp;aligned=true" class="external">number of tests here</a> so you can keep track of the status of the inner workings of this node across different platforms.

Again, you can <a href="https://mdn.github.io/webaudio-examples/spacialization/" class="external">check out the final demo here</a>, and the <a href="https://github.com/mdn/webaudio-examples/tree/master/spacialization" class="external">final source code is here</a>. There is also a <a href="https://codepen.io/Rumyra/pen/MqayoK?editors=0100" class="external">Codepen demo too</a>.

If you are working with 3D games and/or WebXR it's a good idea to harness a 3D library to create such functionality, rather than trying to do this all yourself from first principles. We rolled our own in this article to give you an idea of how it works, but you'll save a lot of time by taking advantage of work others have done before you.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/web_audio_spatialization_basics/index.html "Folder: en-us/web/api/web_audio_api/web_audio_spatialization_basics (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FWeb_audio_spatialization_basics%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%2Fweb_audio_spatialization_basics%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FWeb_audio_spatialization_basics%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Fweb_audio_spatialization_basics%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fec48c5bda627f8a6c9ac18b8038f3f16bd884359%0A*+Document+last+modified%3A+2021-03-09T14%3A47%3A39.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Web+audio+spatialization+basics%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Mar 9, 2021, [by MDN contributors](Web_audio_spatialization_basics/contributors.txt)

Change your languageSelect your preferred language English (US)Français中文 (简体)

Change language

#### Related Topics

1.  **[Web Audio API](../Web_Audio_API.html)**
2.  Guides
    1.  [Using the Web Audio API](Using_Web_Audio_API.html)
    2.  [Basic concepts behind Web Audio API](Basic_concepts_behind_Web_Audio_API.html)
    3.  [Web Audio API best practices](Best_practices.html)
    4.  [Advanced techniques: Creating and sequencing audio](Advanced_techniques.html)
    5.  [Controlling multiple parameters with ConstantSourceNode](Controlling_multiple_parameters_with_ConstantSourceNode.html)
    6.  [Migrating from webkitAudioContext](Migrating_from_webkitAudioContext.html)
    7.  [Example and tutorial: Simple synth keyboard](Simple_synth.html)
    8.  [Tools for analyzing Web Audio usage](Tools.html)
    9.  [Using IIR filters](Using_IIR_filters.html)
    10. [Visualizations with Web Audio API](Visualizations_with_Web_Audio_API.html)
    11. [Web audio spatialization basics](Web_audio_spatialization_basics.html)
3.  Interfaces
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
    35. [`WaveShaperNode`](../WaveShaperNode.html)
    36. [`StereoPannerNode`](../StereoPannerNode.html)

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
