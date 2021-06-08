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
3.  <a href="../AnalyserNode.html" class="breadcrumb-penultimate"><span data-property="name">AnalyserNode</span></a>
4.  <a href="getByteTimeDomainData.html" class="breadcrumb-current-page"><span data-property="name">AnalyserNode.getByteTimeDomainData()</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [Syntax](#syntax)
-   [Example](#example)
-   [Specifications](#specifications)
-   [Browser compatibility](#browser_compatibility)
-   [See also](#see_also)

AnalyserNode.getByteTimeDomainData()
====================================

The **`getByteTimeDomainData()`** method of the [`AnalyserNode`](../AnalyserNode.html) Interface copies the current waveform, or time-domain, data into a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) (unsigned byte array) passed into it.

If the array has fewer elements than the [`AnalyserNode.fftSize`](fftSize.html), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

[Syntax](#syntax "Permalink to Syntax")
---------------------------------------

    const audioCtx = new AudioContext();
    const analyser = audioCtx.createAnalyser();
    const dataArray = new Uint8Array(analyser.fftSize); // Uint8Array should be the same length as the fftSize
    analyser.getByteTimeDomainData(dataArray); // fill the Uint8Array with data returned from getByteTimeDomainData()

### [Parameters](#parameters "Permalink to Parameters")

`array`  
The [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) that the time domain data will be copied to.  
If the array has fewer elements than the [`AnalyserNode.fftSize`](fftSize.html), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

### [Return value](#return_value "Permalink to Return value")

**`void`** | None

[Example](#example "Permalink to Example")
------------------------------------------

The following example shows basic usage of an [`AudioContext`](../AudioContext.html) to create an `AnalyserNode`, then [`requestAnimationFrame`](../window/requestAnimationFrame.html "requestAnimationFrame") and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to collect time domain data repeatedly and draw an "oscilloscope style" output of the current audio input. For more complete applied examples/information, check out our <a href="https://mdn.github.io/voice-change-o-matic/" class="external">Voice-change-O-matic</a> demo (see <a href="../../../../../../github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.html#L128-L205" class="external">app.js lines 128–205</a> for relevant code).

    const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    const analyser = audioCtx.createAnalyser();

      ...

    analyser.fftSize = 2048;
    const bufferLength = analyser.fftSize;
    const dataArray = new Uint8Array(bufferLength);
    analyser.getByteTimeDomainData(dataArray);

    // draw an oscilloscope of the current audio source
    function draw() {
      drawVisual = requestAnimationFrame(draw);
      analyser.getByteTimeDomainData(dataArray);

      canvasCtx.fillStyle = 'rgb(200, 200, 200)';
      canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);

      canvasCtx.lineWidth = 2;
      canvasCtx.strokeStyle = 'rgb(0, 0, 0)';

      const sliceWidth = WIDTH * 1.0 / bufferLength;
      let x = 0;

      canvasCtx.beginPath();
      for(var i = 0; i < bufferLength; i++) {
        const v = dataArray[i]/128.0;
        const y = v * HEIGHT/2;

        if(i === 0)
          canvasCtx.moveTo(x, y);
        else
          canvasCtx.lineTo(x, y);

        x += sliceWidth;
      }

      canvasCtx.lineTo(WIDTH, HEIGHT/2);
      canvasCtx.stroke();
    };

    draw();

[Specifications](#specifications "Permalink to Specifications")
---------------------------------------------------------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-getbytetimedomaindata" class="external">Web Audio API<br />
<span class="small">The definition of 'getByteTimeDomainData()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

[Browser compatibility](#browser_compatibility "Permalink to Browser compatibility")
------------------------------------------------------------------------------------

BCD tables only load in the browser

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Using the Web Audio API](../Web_Audio_API/Using_Web_Audio_API.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/analysernode/getbytetimedomaindata/index.html "Folder: en-us/web/api/analysernode/getbytetimedomaindata (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAnalyserNode%2FgetByteTimeDomainData%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fanalysernode%2Fgetbytetimedomaindata%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FAnalyserNode%2FgetByteTimeDomainData%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fanalysernode%2Fgetbytetimedomaindata%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2Fc141b2c35a21ca911a3dc050de0d77695873dba5%0A*+Document+last+modified%3A+2021-05-29T02%3A55%3A10.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22AnalyserNode.getByteTimeDomainData%28%29%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** May 29, 2021, [by MDN contributors](getByteTimeDomainData/contributors.txt)

Change your language Select your preferred language English (US) Français 中文 (简体)

Change language

#### Related Topics

1.  **[`AnalyserNode`](../AnalyserNode.html)**
2.  Constructor
    1.  [`AnalyserNode()`](AnalyserNode.html)
3.  Properties
    1.  [`fftSize`](fftSize.html)
    2.  [`frequencyBinCount`](frequencyBinCount.html)
    3.  [`maxDecibels`](maxDecibels.html)
    4.  [`minDecibels`](minDecibels.html)
    5.  [`smoothingTimeConstant`](smoothingTimeConstant.html)
4.  Methods
    1.  [`getByteFrequencyData()`](getByteFrequencyData.html)
    2.  *`getByteTimeDomainData()`*
    3.  [`getFloatFrequencyData()`](getFloatFrequencyData.html)
    4.  [`getFloatTimeDomainData()`](getFloatTimeDomainData.html)
5.  Inheritance:
    1.  [`AudioNode`](../AudioNode.html)
    2.  [`EventTarget`](../EventTarget.html)

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
