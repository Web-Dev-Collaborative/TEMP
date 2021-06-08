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
4.  <a href="Visualizations_with_Web_Audio_API.html" class="breadcrumb-current-page"><span data-property="name">Visualizations with Web Audio API</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Basic concepts](#basic_concepts)
-   [Creating a waveform/oscilloscope](#creating_a_waveformoscilloscope)
-   [Creating a frequency bar graph](#creating_a_frequency_bar_graph)

Visualizations with Web Audio API
=================================

One of the most interesting features of the Web Audio API is the ability to extract frequency, waveform, and other data from your audio source, which can then be used to create visualizations. This article explains how, and provides a couple of basic use cases.

**Note**: You can find working examples of all the code snippets in our <a href="https://mdn.github.io/voice-change-o-matic/" class="external">Voice-change-O-matic</a> demo.

[Basic concepts](#basic_concepts "Permalink to Basic concepts")
---------------------------------------------------------------

To extract data from your audio source, you need an [`AnalyserNode`](../AnalyserNode.html), which is created using the [`BaseAudioContext.createAnalyser`](../BaseAudioContext/createAnalyser.html) method, for example:

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var analyser = audioCtx.createAnalyser();

This node is then connected to your audio source at some point between your source and your destination, for example:

    source = audioCtx.createMediaStreamSource(stream);
    source.connect(analyser);
    analyser.connect(distortion);
    distortion.connect(audioCtx.destination);

**Note**: you don't need to connect the analyser's output to another node for it to work, as long as the input is connected to the source, either directly or via another node.

The analyser node will then capture audio data using a Fast Fourier Transform (fft) in a certain frequency domain, depending on what you specify as the [`AnalyserNode.fftSize`](../AnalyserNode/fftSize.html) property value (if no value is specified, the default is 2048.)

**Note**: You can also specify a minimum and maximum power value for the fft data scaling range, using [`AnalyserNode.minDecibels`](../AnalyserNode/minDecibels.html) and [`AnalyserNode.maxDecibels`](../AnalyserNode/maxDecibels.html), and different data averaging constants using [`AnalyserNode.smoothingTimeConstant`](../AnalyserNode/smoothingTimeConstant.html). Read those pages to get more information on how to use them.

To capture data, you need to use the methods [`AnalyserNode.getFloatFrequencyData()`](../AnalyserNode/getFloatFrequencyData.html) and [`AnalyserNode.getByteFrequencyData()`](../AnalyserNode/getByteFrequencyData.html) to capture frequency data, and [`AnalyserNode.getByteTimeDomainData()`](../AnalyserNode/getByteTimeDomainData.html) and [`AnalyserNode.getFloatTimeDomainData()`](../AnalyserNode/getFloatTimeDomainData.html) to capture waveform data.

These methods copy data into a specified array, so you need to create a new array to receive the data before invoking one. The first one produces 32-bit floating point numbers, and the second and third ones produce 8-bit unsigned integers, therefore a standard JavaScript array won't do — you need to use a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) or [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) array, depending on what data you are handling.

So for example, say we are dealing with an fft size of 2048. We return the [`AnalyserNode.frequencyBinCount`](../AnalyserNode/frequencyBinCount.html) value, which is half the fft, then call Uint8Array() with the frequencyBinCount as its length argument — this is how many data points we will be collecting, for that fft size.

    analyser.fftSize = 2048;
    var bufferLength = analyser.frequencyBinCount;
    var dataArray = new Uint8Array(bufferLength);

To actually retrieve the data and copy it into our array, we then call the data collection method we want, with the array passed as it's argument. For example:

    analyser.getByteTimeDomainData(dataArray);

We now have the audio data for that moment in time captured in our array, and can proceed to visualize it however we like, for example by plotting it onto an HTML5 [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas).

Let's go on to look at some specific examples.

[Creating a waveform/oscilloscope](#creating_a_waveformoscilloscope "Permalink to Creating a waveform/oscilloscope")
--------------------------------------------------------------------------------------------------------------------

To create the oscilloscope visualisation (hat tip to <a href="https://soledadpenades.com/" class="external">Soledad Penadés</a> for the original code in <a href="../../../../../../github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.html#L123-L167" class="external">Voice-change-O-matic</a>), we first follow the standard pattern described in the previous section to set up the buffer:

    analyser.fftSize = 2048;
    var bufferLength = analyser.frequencyBinCount;
    var dataArray = new Uint8Array(bufferLength);

Next, we clear the canvas of what had been drawn on it before to get ready for the new visualization display:

    canvasCtx.clearRect(0, 0, WIDTH, HEIGHT);

We now define the `draw()` function:

    function draw() {

In here, we use `requestAnimationFrame()` to keep looping the drawing function once it has been started:

    var drawVisual = requestAnimationFrame(draw);

Next, we grab the time domain data and copy it into our array

    analyser.getByteTimeDomainData(dataArray);

Next, fill the canvas with a solid color to start

    canvasCtx.fillStyle = 'rgb(200, 200, 200)';
    canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);

Set a line width and stroke color for the wave we will draw, then begin drawing a path

    canvasCtx.lineWidth = 2;
    canvasCtx.strokeStyle = 'rgb(0, 0, 0)';
    canvasCtx.beginPath();

Determine the width of each segment of the line to be drawn by dividing the canvas width by the array length (equal to the FrequencyBinCount, as defined earlier on), then define an x variable to define the position to move to for drawing each segment of the line.

    var sliceWidth = WIDTH * 1.0 / bufferLength;
    var x = 0;

Now we run through a loop, defining the position of a small segment of the wave for each point in the buffer at a certain height based on the data point value form the array, then moving the line across to the place where the next wave segment should be drawn:

          for(var i = 0; i < bufferLength; i++) {

            var v = dataArray[i] / 128.0;
            var y = v * HEIGHT/2;

            if(i === 0) {
              canvasCtx.moveTo(x, y);
            } else {
              canvasCtx.lineTo(x, y);
            }

            x += sliceWidth;
          }

Finally, we finish the line in the middle of the right hand side of the canvas, then draw the stroke we've defined:

          canvasCtx.lineTo(canvas.width, canvas.height/2);
          canvasCtx.stroke();
        };

At the end of this section of code, we invoke the `draw()` function to start off the whole process:

        draw();

This gives us a nice waveform display that updates several times a second:

<img src="Visualizations_with_Web_Audio_API/wave.png" alt="a black oscilloscope line, showing the waveform of an audio signal" width="640" height="96" />

[Creating a frequency bar graph](#creating_a_frequency_bar_graph "Permalink to Creating a frequency bar graph")
---------------------------------------------------------------------------------------------------------------

Another nice little sound visualization to create is one of those Winamp-style frequency bar graphs. We have one available in Voice-change-O-matic; let's look at how it's done.

First, we again set up our analyser and data array, then clear the current canvas display with `clearRect()`. The only difference from before is that we have set the fft size to be much smaller; this is so that each bar in the graph is big enough to actually look like a bar rather than a thin strand.

    analyser.fftSize = 256;
    var bufferLength = analyser.frequencyBinCount;
    console.log(bufferLength);
    var dataArray = new Uint8Array(bufferLength);

    canvasCtx.clearRect(0, 0, WIDTH, HEIGHT);

Next, we start our `draw()` function off, again setting up a loop with `requestAnimationFrame()` so that the displayed data keeps updating, and clearing the display with each animation frame.

        function draw() {
          drawVisual = requestAnimationFrame(draw);

          analyser.getByteFrequencyData(dataArray);

          canvasCtx.fillStyle = 'rgb(0, 0, 0)';
          canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);

Now we set our `barWidth` to be equal to the canvas width divided by the number of bars (the buffer length). However, we are also multiplying that width by 2.5, because most of the frequencies will come back as having no audio in them, as most of the sounds we hear every day are in a certain lower frequency range. We don't want to display loads of empty bars, therefore we shift the ones that will display regularly at a noticeable height across so they fill the canvas display.

We also set a `barHeight` variable, and an `x` variable to record how far across the screen to draw the current bar.

    var barWidth = (WIDTH / bufferLength) * 2.5;
    var barHeight;
    var x = 0;

As before, we now start a for loop and cycle through each value in the `dataArray`. For each one, we make the `barHeight` equal to the array value, set a fill color based on the `barHeight` (taller bars are brighter), and draw a bar at `x` pixels across the canvas, which is `barWidth` wide and `barHeight/2` tall (we eventually decided to cut each bar in half so they would all fit on the canvas better.)

The one value that needs explaining is the vertical offset position we are drawing each bar at: `HEIGHT-barHeight/2`. I am doing this because I want each bar to stick up from the bottom of the canvas, not down from the top, as it would if we set the vertical position to 0. Therefore, we instead set the vertical position each time to the height of the canvas minus `barHeight/2`, so therefore each bar will be drawn from partway down the canvas, down to the bottom.

          for(var i = 0; i < bufferLength; i++) {
            barHeight = dataArray[i]/2;

            canvasCtx.fillStyle = 'rgb(' + (barHeight+100) + ',50,50)';
            canvasCtx.fillRect(x,HEIGHT-barHeight/2,barWidth,barHeight);

            x += barWidth + 1;
          }
        };

Again, at the end of the code we invoke the draw() function to set the whole process in motion.

    draw();

This code gives us a result like the following:

<img src="Visualizations_with_Web_Audio_API/bar-graph.png" alt="a series of red bars in a bar graph, showing intensity of different frequencies in an audio signal" width="1260" height="157" />

**Note**: The examples listed in this article have shown usage of [`AnalyserNode.getByteFrequencyData()`](../AnalyserNode/getByteFrequencyData.html) and [`AnalyserNode.getByteTimeDomainData()`](../AnalyserNode/getByteTimeDomainData.html). For working examples showing [`AnalyserNode.getFloatFrequencyData()`](../AnalyserNode/getFloatFrequencyData.html) and [`AnalyserNode.getFloatTimeDomainData()`](../AnalyserNode/getFloatTimeDomainData.html), refer to our <a href="https://mdn.github.io/voice-change-o-matic-float-data/" class="external">Voice-change-O-matic-float-data</a> demo (see the <a href="https://github.com/mdn/voice-change-o-matic-float-data" class="external">source code</a> too) — this is exactly the same as the original <a href="https://mdn.github.io/voice-change-o-matic/" class="external">Voice-change-O-matic</a>, except that it uses Float data, not unsigned byte data.

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/visualizations_with_web_audio_api/index.html "Folder: en-us/web/api/web_audio_api/visualizations_with_web_audio_api (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FVisualizations_with_Web_Audio_API%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%2Fvisualizations_with_web_audio_api%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FVisualizations_with_Web_Audio_API%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Fvisualizations_with_web_audio_api%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F6c2523b8365f2bef7b26dee75ac7c74e686f3f62%0A*+Document+last+modified%3A+2021-02-24T02%3A44%3A05.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Visualizations+with+Web+Audio+API%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Feb 24, 2021, [by MDN contributors](Visualizations_with_Web_Audio_API/contributors.txt)

Change your languageSelect your preferred language English (US)Français日本語Русский中文 (简体)

Change language

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
