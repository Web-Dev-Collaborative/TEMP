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
4.  <a href="Simple_synth.html" class="breadcrumb-current-page"><span data-property="name">Example and tutorial: Simple synth keyboard</span></a>

-   <a href="#select-language" class="language-icon"><span class="show-desktop">Change language</span></a>

Table of contents
-----------------

Table of contents

-   [The video keyboard](#the_video_keyboard)
-   [See also](#see_also)

Example and tutorial: Simple synth keyboard
===========================================

This article presents the code and working demo of a video keyboard you can play using the mouse. The keyboard allows you to switch among the standard waveforms as well as one custom waveform, and you can control the main gain using a volume slider beneath the keyboard. This example makes use of the following Web API interfaces: [`AudioContext`](../AudioContext.html), [`OscillatorNode`](../OscillatorNode.html), [`PeriodicWave`](../PeriodicWave.html), and [`GainNode`](../GainNode.html).

Because [`OscillatorNode`](../OscillatorNode.html) is based on [`AudioScheduledSourceNode`](../AudioScheduledSourceNode.html), this is to some extent an example for that as well.

[The video keyboard](#the_video_keyboard "Permalink to The video keyboard")
---------------------------------------------------------------------------

### [HTML](#html "Permalink to HTML")

There are three primary components to the display for our virtual keyboard. The first is the musical keyboard itself. We draw this in a pair of nested [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements so that we can make the keyboard horizontally scrollable if all the keys don't fit on the screen, without having them wrap around.

#### The keyboard

First, we create space to build the keyboard into. We will be programmatically constructing the keyboard, because doing so gives us the flexibility to configure each key as we determine the appropriate data for the corresponding note. In our case, we get each key's frequency from a table, but it could be calculated algorithmically as well.

    <div class="container">
      <div class="keyboard"></div>
    </div>

The [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) named `"container"` is the scrollable box that lets the keyboard be scrolled horiontally if it's too wide for the available space. The keys themselves will be inserted into the block of class `"keyboard"`.

#### The settings bar

Beneath the keyboard, we'll put some controls for configuring the layer. For now, we will have two controls: one to set the main volume and another to select what periodic waveform to use when generating notes.

##### The volume control

First we create the `<div>` to contain the settings bar, so it can be styled as needed. Then we establish a box that will be presented on the left side of the bar and place a label and an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element of type `"range"`. The range element will typically be presented as a slider control; we configure it to allow any value between 0.0 and 1.0, stepping by 0.01 each position.

    <div class="settingsBar">
      <div class="left">
        <span>Volume: </span>
        <input type="range" min="0.0" max="1.0" step="0.01"
            value="0.5" list="volumes" name="volume">
        <datalist id="volumes">
          <option value="0.0" label="Mute">
          <option value="1.0" label="100%">
        </datalist>
      </div>

We specify a default value of 0.5, and we provide a [`<datalist>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist) element which is connected to the range using the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-name) attribute to find an option list whose ID matches; in this case, the data set is named `"volume"`. This lets us provide a set of common values and special strings which the browser may optionally choose to display in some fashion; we provide names for the values 0.0 ("Mute") and 1.0 ("100%").

##### The waveform picker

On the right side of the settings bar, we place a label and a [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element named `"waveform"` whose options correspond to the available waveforms.

      <div class="right">
        <span>Current waveform: </span>
        <select name="waveform">
          <option value="sine">Sine</option>
          <option value="square" selected>Square</option>
          <option value="sawtooth">Sawtooth</option>
          <option value="triangle">Triangle</option>
          <option value="custom">Custom</option>
        </select>
      </div>
    </div>

### [JavaScript](#javascript "Permalink to JavaScript")

The JavaScript code begins by initializing a number of variables.

    let audioContext = new (window.AudioContext || window.webkitAudioContext)();
    let oscList = [];
    let mainGainNode = null;

1.  `audioContext` is set to reference the global [`AudioContext`](../AudioContext.html) object (or `webkitAudioContext` if necessary).
2.  `oscillators` is set up to be ready to contain a list of all currently-playing oscillators. It starts off empty, since there are none playing yet.
3.  `mainGainNode` is set to null; during the setup process, it will be configured to contain a [`GainNode`](../GainNode.html) which all playing oscillators will connect to and play through to allow the overall volume to be controlled using a single slider control.

<!-- -->

    let keyboard = document.querySelector(".keyboard");
    let wavePicker = document.querySelector("select[name='waveform']");
    let volumeControl = document.querySelector("input[name='volume']");

References to elements we'll need access to are obtained:

-   `keyboard` is the container element into which the keys will be placed.
-   `wavePicker` is the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element used to choose the waveform to use for the notes.
-   `volumeControl` is the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element (of type `"range"`) used to control the main audio volume.

<!-- -->

    let noteFreq = null;
    let customWaveform = null;
    let sineTerms = null;
    let cosineTerms = null;

Finally, global variables that will be used when constructing waveforms are created:

-   `noteFreq` will be an array of arrays; each array represents one octave, each of which contains one entry for each note in that octave. The value for each is the frequency, in Hertz, of the note's tone.
-   `customWaveform` will be set up as a [`PeriodicWave`](../PeriodicWave.html) describing the waveform to use when the user selects "Custom" from the waveform picker.
-   `sineTerms` and `cosineTerms` will be used to store the data for generating the waveform; each will contain an array that's generated when the user chooses "Custom".

### [Creating the note table](#creating_the_note_table "Permalink to Creating the note table")

The `createNoteTable()` function builds the array `noteFreq` to contain an array of objects representing each octave. Each octave, in turn, has one named property for each note in that octave; the property's name is the note's name (such as "C\#" to represent C-sharp), and the value is the frequency, in Hertz, of that note.

    function createNoteTable() {
      let noteFreq = [];
      for (let i=0; i< 9; i++) {
        noteFreq[i] = [];
      }

      noteFreq[0]["A"] = 27.500000000000000;
      noteFreq[0]["A#"] = 29.135235094880619;
      noteFreq[0]["B"] = 30.867706328507756;

      noteFreq[1]["C"] = 32.703195662574829;
      noteFreq[1]["C#"] = 34.647828872109012;
      noteFreq[1]["D"] = 36.708095989675945;
      noteFreq[1]["D#"] = 38.890872965260113;
      noteFreq[1]["E"] = 41.203444614108741;
      noteFreq[1]["F"] = 43.653528929125485;
      noteFreq[1]["F#"] = 46.249302838954299;
      noteFreq[1]["G"] = 48.999429497718661;
      noteFreq[1]["G#"] = 51.913087197493142;
      noteFreq[1]["A"] = 55.000000000000000;
      noteFreq[1]["A#"] = 58.270470189761239;
      noteFreq[1]["B"] = 61.735412657015513;

... several octaves not shown for brevity ...

      noteFreq[7]["C"] = 2093.004522404789077;
      noteFreq[7]["C#"] = 2217.461047814976769;
      noteFreq[7]["D"] = 2349.318143339260482;
      noteFreq[7]["D#"] = 2489.015869776647285;
      noteFreq[7]["E"] = 2637.020455302959437;
      noteFreq[7]["F"] = 2793.825851464031075;
      noteFreq[7]["F#"] = 2959.955381693075191;
      noteFreq[7]["G"] = 3135.963487853994352;
      noteFreq[7]["G#"] = 3322.437580639561108;
      noteFreq[7]["A"] = 3520.000000000000000;
      noteFreq[7]["A#"] = 3729.310092144719331;
      noteFreq[7]["B"] = 3951.066410048992894;

      noteFreq[8]["C"] = 4186.009044809578154;
      return noteFreq;
    }

The result is an array, `noteFreq`, with an object for each octave. Each octave object has named properties in it where the property name is the name of the note (such as "C\#" to represent C-sharp) and the property's value is the note's frequency in Hertz. In part, the resulting object looks like this:

Octave

Notes

0

"A" ⇒ 27.5

"A\#" ⇒ 29.14

"B" ⇒ 30.87

1

"C" ⇒ 32.70

"C\#" ⇒ 34.65

"D" ⇒ 36.71

"D\#" ⇒ 38.89

"E" ⇒ 41.20

"F" ⇒ 43.65

"F\#" ⇒ 46.25

"G" ⇒ 49

"G\#" ⇒ 51.9

"A" ⇒ 55

"A\#" ⇒ 58.27

"B" ⇒ 61.74

2

. . .

With this table in place, we can find out the frequency for a given note in a particular octave quite easily. If we want the frequency for the note G\# in octave 1, we use `noteFreq[1]["G#"]` and get the value 51.9 as a result.

The values in the example table above have been rounded to two decimal places.

### [Building the keyboard](#building_the_keyboard "Permalink to Building the keyboard")

The `setup()` function is responsible for building the keyboard and preparing the app to play music.

    function setup() {
      noteFreq = createNoteTable();

      volumeControl.addEventListener("change", changeVolume, false);

      mainGainNode = audioContext.createGain();
      mainGainNode.connect(audioContext.destination);
      mainGainNode.gain.value = volumeControl.value;

      // Create the keys; skip any that are sharp or flat; for
      // our purposes we don't need them. Each octave is inserted
      // into a <div> of class "octave".

      noteFreq.forEach(function(keys, idx) {
        let keyList = Object.entries(keys);
        let octaveElem = document.createElement("div");
        octaveElem.className = "octave";

        keyList.forEach(function(key) {
          if (key[0].length == 1) {
            octaveElem.appendChild(createKey(key[0], idx, key[1]));
          }
        });

        keyboard.appendChild(octaveElem);
      });

      document.querySelector("div[data-note='B'][data-octave='5']").scrollIntoView(false);

      sineTerms = new Float32Array([0, 0, 1, 0, 1]);
      cosineTerms = new Float32Array(sineTerms.length);
      customWaveform = audioContext.createPeriodicWave(cosineTerms, sineTerms);

      for (i=0; i<9; i++) {
          oscList[i] = {};
      }
    }

    setup();

1.  The table which maps note names and octaves to their frequenies is created by calling `createNoteTable()`.
2.  An event handler is established (by calling our old friend [`addEventListener()`](../EventTarget/addEventListener.html "addEventListener()") to handle `change` events on the main gain control. This will update the main gain node's volume to the new value of the control.
3.  Next, we iterate over each octave in the note frequencies table. For each octave, we use [`Object.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) to get a list of the notes in that octave.
4.  Create a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) to contain that octave's notes (so we can have a small bit of space drawn between octaves), and set its class name to "octave"
5.  For each key in the octave, we check to see if the note's name has more than one character. We skip these, because we're leaving out the sharp notes in this example. If the note's name is only one character, then we call `createKey()`, specifying the note string, octave, and frequency. The returned element is appended to the octave element created  in step 4.
6.  When each octave element has been built, it's appended to the keyboard.
7.  Once the keyboard has been constructed, we scroll the note "B" in octave 5 into view; this has the effect of ensuring that middle-C is visible along with its surrounding keys.
8.  Then a new custom waveform is built using [`AudioContext.createPeriodicWave()`](../BaseAudioContext/createPeriodicWave.html). This waveform will be used any time the user selects "Custom" from the waveform picker control.
9.  Finally, the oscillator list is initialized to ensure that it's ready to receive information identifiying which oscillators are associated with which keys.

#### Creating a key

The `createKey()` function is called once for each key that we want to present in the virtual keyboard. It creates the elements that comprise the key and its label, adds some data attributes to the element for later use, and assigns event handlers for the events we care about.

    function createKey(note, octave, freq) {
      let keyElement = document.createElement("div");
      let labelElement = document.createElement("div");

      keyElement.className = "key";
      keyElement.dataset["octave"] = octave;
      keyElement.dataset["note"] = note;
      keyElement.dataset["frequency"] = freq;

      labelElement.innerHTML = note + "<sub>" + octave + "</sub>";
      keyElement.appendChild(labelElement);

      keyElement.addEventListener("mousedown", notePressed, false);
      keyElement.addEventListener("mouseup", noteReleased, false);
      keyElement.addEventListener("mouseover", notePressed, false);
      keyElement.addEventListener("mouseleave", noteReleased, false);

      return keyElement;
    }

After creating the elements that will represent the key and its label, we configure the key's element by setting its class to "key" (which establishes its appearance). Then we add [`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-data-*) attributes which contain the key's octave (attribute `data-octave`), string representing the note to play (attribute `data-note`), and frequency (attribute `data-frequency`) in Hertz. This will let us easily fetch that information as needed when handling events.

### [Making music](#making_music "Permalink to Making music")

#### Playing a tone

The `playTone()` function's job is to play a tone at the given frequency. This will be used by the handler for events triggering keys on the keyboard to start playing the appropriate notes.

    function playTone(freq) {
      let osc = audioContext.createOscillator();
      osc.connect(mainGainNode);

      let type = wavePicker.options[wavePicker.selectedIndex].value;

      if (type == "custom") {
        osc.setPeriodicWave(customWaveform);
      } else {
        osc.type = type;
      }

      osc.frequency.value = freq;
      osc.start();

      return osc;
    }

`playTone()` begins by creating a new [`OscillatorNode`](../OscillatorNode.html) by calling the [`AudioContext.createOscillator()`](../BaseAudioContext/createOscillator.html) method. We then connect it to the main gain node by calling the new oscillator's <span class="page-not-created">`OscillatorNode.connect()`</span> method;, which tells the oscillator where to send its output to. By doing this, changing the gain of the main gain node will affect the volume of all tones being generated.

Then we get the type of waveform to use by checking the value of the waveform picker control in the settings bar. If the user has it set to `"custom"`, we call [`OscillatorNode.setPeriodicWave()`](../OscillatorNode/setPeriodicWave.html) to configure the oscillator to use our custom waveform. Doing this automatically sets the oscillator's [`type`](../OscillatorNode/type.html "type") to `custom`. If any other waveform type is selected in the wave picker, we set the oscillator's type to the value of the picker; that value will be one of `sine`, `square`, `triangle`, and `sawtooth`.

The oscillator's frequency is set to the value specified in the `freq` parameter by setting the value of the <span class="page-not-created">`Oscillator.frequency`</span> [`AudioParam`](../AudioParam.html) object. Then, at last, the oscillator is started up so that it begins to produce sound by calling the oscillator's inherited [`AudioScheduledSourceNode.start()`](../AudioScheduledSourceNode/start.html) method.

#### Playing a tone

When the `mousedown` or <span class="page-not-created">`mouseover`</span> event occurs on a key, we want to start playing the corresponding note. The `notePressed()` function is used as the event handler for these events.

    function notePressed(event) {
      if (event.buttons & 1) {
        let dataset = event.target.dataset;

        if (!dataset["pressed"]) {
          let octave = +dataset["octave"];
          oscList[octave][dataset["note"]] = playTone(dataset["frequency"]);
          dataset["pressed"] = "yes";
        }
      }
    }

We start by checking whether the primary mouse button is pressed, for two reasons. First, we want to only allow the primary mouse button to trigger notes playing. Second, and more importantly, we are using this to handle `mouseover` for cases where the user is dragging from note to note, and we only want to start playing the note if the mouse is pressed when it enters the element.

If the mouse button is in fact down, we get the pressed key's [`dataset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-dataset) attribute; this makes it easy to access the custom data attributes on the element. We look for a `data-pressed` attribute; if there isn't one (which indicates that the note isn't already playing), we call `playTone()` to start playing the note, passing in the value of the element's `data-frequency` attribute. The returned oscillator is stored into `oscList` for future reference, and `data-pressed` is set to `yes` to indicate that the note is playing so we don't start it again next time this is called.

#### Stopping a tone

The `noteReleased()` function is the event handler called when the user releases the mouse button or moves the mouse out of the key that's currently playing.

    function noteReleased(event) {
      let dataset = event.target.dataset;

      if (dataset && dataset["pressed"]) {
        let octave = +dataset["octave"];
        oscList[octave][dataset["note"]].stop();
        delete oscList[octave][dataset["note"]];
        delete dataset["pressed"];
      }
    }

`noteReleased()` uses the `data-octave` and `data-note` custom attributes to look up the key's oscillator, then calls the oscillator's inherited [`stop()`](../AudioScheduledSourceNode/stop.html "stop()") method to stop playing the note. Finally, the `oscList` entry for the note is cleared and the `data-pressed` attribute is removed from the key element (as identified by [`event.target`](../Event/target.html)), to indicate that the note is not currently playing.

#### Changing the main volume

The volume slider in the settings bar provides a simple interface to change the gain value on the main gain node, thereby changing the loudness of all playing notes. The `changeVolume()` method is the handler for the `change` event on the slider.

    function changeVolume(event) {
      mainGainNode.gain.value = volumeControl.value
    }

This sets the value of the main gain node's `gain` [`AudioParam`](../AudioParam.html) to the slider's new value.

### [Result](#result "Permalink to Result")

Put all together, the result is a simple but working point-and-click musical keyboard:

[See also](#see_also "Permalink to See also")
---------------------------------------------

-   [Web Audio API](../Web_Audio_API.html)
-   [`OscillatorNode`](../OscillatorNode.html)
-   [`GainNode`](../GainNode.html)
-   [`AudioContext`](../AudioContext.html)

#### Found a problem with this page?

-   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/web/api/web_audio_api/simple_synth/index.html "Folder: en-us/web/api/web_audio_api/simple_synth (Opens in a new tab)")
-   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?body=MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FSimple_synth%0A%0A%23%23%23%23+What+information+was+incorrect%2C+unhelpful%2C+or+incomplete%3F%0A%0A%0A%23%23%23%23+Specific+section+or+headline%3F%0A%0A%0A%23%23%23%23+What+did+you+expect+to+see%3F%0A%0A%0A%23%23%23%23+Did+you+test+this%3F+If+so%2C+how%3F%0A%0A%0A%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+Content+page+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Fweb%2Fapi%2Fweb_audio_api%2Fsimple_synth%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FAPI%2FWeb_Audio_API%2FSimple_synth%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Fweb%2Fapi%2Fweb_audio_api%2Fsimple_synth%2Findex.html%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F8e8d4164f1add73f39aaaa347531af0419bc4c0e%0A*+Document+last+modified%3A+2021-03-24T09%3A07%3A11.000Z%0A%0A%3C%2Fdetails%3E&title=Issue+with+%22Example+and+tutorial%3A+Simple+synth+keyboard%22%3A+%28short+summary+here+please%29&labels=Content%3AWebAPI%2Cneeds-triage "This will take you to https://github.com/mdn/content to file a new issue")
-   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Mar 24, 2021, [by MDN contributors](Simple_synth/contributors.txt)

Change your languageSelect your preferred language English (US)Português (do Brasil)

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
