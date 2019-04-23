# Interactive-Poster


http://webspace.ocad.ca/~3164558/site3/

![alt text](https://webspace.ocad.ca/~3164558/site3/Poster.png "Interactive Poster")

## Introduction
This project is an interactive poster for my thesis, 2020 Sound. 2020 Sound is a virual prototype for a positional tracking microphone system.
## Making the Poster
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
This code is relatively straightforward, the trick becomes coordinating a rather long list of interactive elements, their Illustrator layer names, and matching recorded audio files of the narration. Spreasheets to the rescue! Since each elements code is mostly common with the only differences lying in the element ID and the audio file, a spreadsheet could be used to concatenate common and unique elements into functional code. Concatenation in a spreadsheet essentially allows you to combine strings to generate a newer, longer, combined string. Take the following example:

A | B | C | D
--- | --- | --- | ---
Hello | Marcus | Gordon | ARRAYFORMULA(CONCATENATE(A1:C1))
Hello | Marcus | Gordon | HelloMarcusGordon

This allows simple function of spreadsheets allows for mass construction of code through concatenation of alternating colums of common code and unique element identifiers as below:

A | B | C | D | E
--- | --- | --- | --- | ---
`$("#` | Title_Title | `").click(function() {sound.pause();sound.setAttribute('src', 'aac/` | Title_Title | `.aac');sound.play();});`

This concatenates into `$("#Title_Title").click(function() {sound.pause();sound.setAttribute('src', 'aac/Title_Title.aac');sound.play();});`

The spreadsheet used to create the code is available [here](https://docs.google.com/spreadsheets/d/1lC8hsgBdGXd4YCx4ujEXdwN8Nb8D9jy-Y_YoU23IvEA/edit?usp=sharing).
