# Interactive-Poster
## Introduction
This project is an interactive poster for my thesis, 2020 Sound. 2020 Sound is a virual prototype for a positional tracking microphone system.
## Making the Poster
### Code Concatenation
The current interaction is quite simple: the user surfs around the poster, finds something they're interested in, and touches it to activate narration that dives deeper into the concept. For example, if the user is intrigued by the section 'Time of Arrival narratives', tapping the title narrates what the user can expect in the the subsections.
This simple interaction was relatively simple to code. JQuery allows SVG element IDs to be activated on click. In Adobe Illustrator, the names of layers translate into SVG element IDs, thus creating a pipeline to make the interactive poster. Through coding a section of the poster, the JavaScript:
* stops any sound if it is currently playing
* selects a new sound, based on the svg element activated
* plays that sound

The code is as follows:
```
$("#Title_Title").click(function() {
  sound.pause();
  sound.setAttribute('src', 'aac/Title_Title.wav');
  sound.play();
  });
```
This code is relatively straightforward, the trick becomes coordinating a rather long list of interactive elements, their Illustrator layer names, and matching recorded audio files of the narration. Spreasheets to the rescue! Since each elements code is mostly common with the only differences lying in the element ID and the audio file, a spreadsheet could be used to concatenate common and unique elements into functional code. Concatenation in a spreadsheet essentially allows you to combine strings to generate a newer, longer, combined string. Take the following example.

No. | A | B | C | D
--- | --- | --- | --- | ---
1 | Hello | Marcus | Gordon | ARRAYFORMULA(CONCATENATE(A1:C1))
2 | Hello | Marcus | Gordon | HelloMarcusGordon
