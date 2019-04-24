# Interactive-Poster


http://webspace.ocad.ca/~3164558/site5/

![alt text](https://webspace.ocad.ca/~3164558/site3/Poster.png "Interactive Poster")

## Introduction
This project is an interactive poster for my thesis, 2020 Sound. 2020 Sound is a virual prototype for a positional tracking microphone system. For its exhibition, the poster presentation made sense. A lot of details in the project show well with diagrams from the technical details of audio time of arrival to my methodological structure. While in attendance, I would naturally extol the details of the diagrams and text, but I wanted to create a presentation that could take an audience through my project in my absence. Coming from a background of radio and television audio production, I felt an interactive layer of narration would enhance the potential of the poster to connect with a wide range of audiences. The interactive poster as developed allows users to spelunk in the details of my thesis explorations at their leisure. This allows for different experiences depending on the user's comfort level with content. A pro audio user may skip the Property of Sound section, for example, wheras a novice might dive deeper to gain a foundation in the terms discussed. The poster is highly scalable, making a tablet its ideal presentation platform. On a tablet, users pinch to zoom, touch and drag to navigate, and touch to activate.

![Interactive Poster Users](http://webspace.ocad.ca/~3164558/site5/20190412_181122.png "Interactive Poster Users")
![Interactive Poster Setup](http://webspace.ocad.ca/~3164558/site5/20190414_132059.png "Interactive Poster Setup")


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
Hello | Marcus | Gordon | `ARRAYFORMULA(CONCATENATE(A1:C1))`
Hello | Marcus | Gordon | HelloMarcusGordon

This allows simple function of spreadsheets allows for mass construction of code through concatenation of alternating colums of common code and unique element identifiers as below:

A | B | C | D | E
--- | --- | --- | --- | ---
`$("#` | Title_Title | `").click(function() {sound.pause();sound.setAttribute('src', 'aac/` | Title_Title | `.aac');sound.play();});`

This concatenates into `$("#Title_Title").click(function() {sound.pause();sound.setAttribute('src', 'aac/Title_Title.aac');sound.play();});`

The spreadsheet used to create the code is available [here](https://docs.google.com/spreadsheets/d/1lC8hsgBdGXd4YCx4ujEXdwN8Nb8D9jy-Y_YoU23IvEA/edit?usp=sharing). In addition to creating the code that runs the poster, the spreadsheet is was also the developmental nexus, where elements were created and assigned Illustrator layer and audio file names. Progress on both element type completion is tracked with check boxes in the spreadsheet. This was instrumental in designing, coding, and recording seventy-four individual elements. The recordings alone have a total duration of thirty-two minutes.

## Conclusions and Future Work

The poster worked well as an exhibition of my project. The irony is that I was in attendance for all hours of the exhibition and, as a result, I presented details of my work in-person. However, the poster made for an excellent backdrop to my engagements as I could quickly surf around to illustrations that matched the conversation. The proved so effective, that I used the poster as my media support for my thesis defense rather than a traditional slide show. With this method, I was able to present my thesis while smoothly moving through diagrams that illustrate the principles at hand.

I plan to continue developing the interactive poster as a presentation platform. I would like to develop more deep-content, making more individual elements of the poster interactive rather. Currently, the interactions are largely section-based, but it would be effective to make some very small details interactive.

Moving beyond vector graphics, future iterations will include animated diagrams. This would really add an extra dimension to the presentation, enhancing the potential of many of the currently static diagrams.

Another small detail would be creating a roll-over state for interactive elements. This was part of an early iteration of the poster. However, with the scope of the current build time did not allow for this interaction. It is my plan to ressurect this for future builds once I streamline its inclusion in the build. 
