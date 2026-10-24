# Mood Music Generator
> Type a feeling (happy, calm or nervous) and the code makes a short piece of music that fits it. The music is a little different every time.
> Live demo [_here_](https://tunepad.com/project/134311#code). <!-- If you have the project hosted somewhere, include the link here. -->

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Features](#features)
* [Screenshots](#screenshots)
* [Setup](#setup)
* [Usage](#usage)
* [Project Status](#project-status)
* [Room for Improvement](#room-for-improvement)
* [Acknowledgements](#acknowledgements)
* [Contact](#contact)
<!-- * [License](#license) -->


## General Information
- Many people find it hard to put their feelings into words, and music therapy is hard to start because it needs training and tools. This project lets anyone "hear" a feeling by turning an emotion word into music with a few lines of Python.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- TunePad, a free website for making music with code. No installation is needed. It runs in the browser.
- Python, as built into TunePad (TunePad's Python is a smaller version of normal Python).
- Python's random module (comes with TunePad, nothing to install).



## Features
List the ready features here:
- Three emotions: happy, calm and nervous. Each one has its own notes, note lengths, loudness and speed.
- Different music every time, because notes, rhythm, rests and loudness are chosen at random inside the limits of each emotion.
- A drum pattern (kick and hi-hat) in a second cell, using the same file.


## Screenshots
TunePad Keyboard cell with the code:
<img width="1440" height="777" alt="Screenshot 2026-10-22 at 2 06 40 pm" src="https://github.com/user-attachments/assets/bb4d917e-2921-4cdb-b120-baeabd092e81" />
TunePad Drums cell with the same code, set to drums:
<![Uploading Screenshot 2026-10-24 at 7.09.45 am.png…](![Uploading Screenshot 2026-10-24 at 7.09.45 am.png…])>


## Setup
The code must run inside TunePad, because it uses TunePad's playNote() and rest() functions. It will not run in a normal Python window.

1. Go to tunepad.com and sign in (a free account is needed to save a project).
2. Open the project link, or make a new project.
3. Click ADD CELL and choose a Keyboard (Piano) cell.
4. Click in the code box, select everything (Cmd+A or Ctrl+A) and delete it.
5. Open final/week10_final., copy the whole file, and paste it into the cell.
6. Press the play triangle next to the cell name.
7. Read the line printed in the console: Set the TunePad project tempo to ... BPM. Type that number into the bpm box at the top of the page (see the table in Usage).
8. Press play again to hear the music at the right speed.

To add drums: click ADD CELL again and choose Drums. Paste the same file. In this cell only, change CELL = "melody" to CELL = "drums". Use the same EMOTION in both cells, then press the big play button at the top right to hear both cells together.

## Usage
How does one go about using it?
Provide various use cases and code examples here.

`write-your-code-here`


## Project Status
Project is: _in progress_ / _complete_ / _no longer being worked on_. If you are no longer working on it, provide reasons why.


## Room for Improvement
Include areas you believe need improvement / could be improved. Also add TODOs for future development.

Room for improvement:
- Improvement to be done 1
- Improvement to be done 2

To do:
- Feature to be added 1
- Feature to be added 2


## Acknowledgements
Give credit here.
- This project was inspired by...
- This project was based on [this tutorial](https://www.example.com).
- Many thanks to...


## Contact
Created by [Kaiduan.Liu@student.uts.edu.au](https://www.flynerd.pl/) - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
