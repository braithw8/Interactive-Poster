# Interactive-Poster
## Introduction
This project is an interactive poster for my thesis, 2020 Sound. 2020 Sound is a virual prototype for a positional tracking microphone system.
## Making the Poster
### Code Concatenation
The current interaction is quite simple: the user surfs around the poster, finds something they're interested in, and touches it to activate narration that dives deeper into the concept. For example, if the user is intrigued by the section 'Time of Arrival narratives', tapping the title narrates what the user can expect in the the subsections.
This simple interaction was relatively simple to code. By activating a section of the poster, the JavaScript:
* stops any sound if it is currently playing
* selects a new sound, based on the svg element activated
* plays that sound
The code is as follows:
```
$("#Title_Title").click(function() {sound.pause();sound.setAttribute('src', 'aac/Title_Title.wav');sound.play();});
```
