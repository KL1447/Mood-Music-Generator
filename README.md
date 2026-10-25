# Mood Music Generator
> Type a feeling (happy, calm or nervous, angry or sad) and the code makes a short piece of music that fits it. The music is a little different every time.
> Live demo [_here_](https://tunepad.com/project/135156#code). <!-- If you have the project hosted somewhere, include the link here. -->

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

* Week 7: TunePad basics and a simple tune that plays one note at a time (`week7_melody`).
* Week 8: `if / elif / else` to choose the music from an emotion word (`week8_emotion`).
* Week 9: the `random` module and three emotion templates (`week9_random templates`).
* Week 10: a smoother tune, a fitting ending note, and a drum pattern (`week10_smooth_drums`).
* Week 11: two more feelings (angry and sad), a bass cell and an arpeggio cell (`week11_final`).

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- TunePad, a free website for making music with code. No installation is needed. It runs in the browser.
- Python, as built into TunePad (TunePad's Python is a smaller version of normal Python).
- Python's random module (comes with TunePad, nothing to install).



## Features
List the ready features here:
- Five emotions: happy, calm, nervous, angry and sad. Each one has its own notes, note lengths, loudness and speed.
- Different music every time, because notes, rhythm, rests and loudness are chosen at random inside the limits of each emotion.
- A drum pattern (kick and hi-hat) in a second cell, using the same file. The pattern is random too, so it changes every time.
- A bass line in a third cell, using the same file. It plays low notes that fit the feeling and changes every time.
- An arpeggio ("arp") line in a fourth cell, using the same file. It plays the notes of a chord one after another, in the middle range between the bass and the melody.


## Screenshots
TunePad Keyboard cell with the code:
<img width="1440" height="777" alt="Screenshot 2026-10-22 at 2 06 40 pm" src="https://github.com/user-attachments/assets/bb4d917e-2921-4cdb-b120-baeabd092e81" />
TunePad Drums cell with the same code, set to drums:
<img width="1440" height="777" alt="Screenshot 2026-10-25 at 5 59 02 am" src="https://github.com/user-attachments/assets/a205a21c-483e-45cb-b439-bf567e731f83" />
TunePad Bass cell with the same code, set to bass:
<img width="1440" height="777" alt="Screenshot 2026-10-26 at 7 58 05 am" src="https://github.com/user-attachments/assets/a2a12062-ae00-4988-9920-2fbb41cd535a" />
TunePad Arp cell with the same code, set to arp:
<img width="1440" height="777" alt="Screenshot 2026-10-26 at 8 00 19 am" src="https://github.com/user-attachments/assets/7e6aee6b-7873-401b-b160-e4efdfb5c263" />



## Setup
The code must run inside TunePad, because it uses TunePad's playNote() and rest() functions. It will not run in a normal Python window.

1. Go to tunepad.com and sign in (a free account is needed to save a project).
2. Open the project link, or make a new project.
3. Click ADD CELL and choose a Keyboard (Piano) cell.
4. Click in the code box, select everything and delete it.
5. Open final/week11 final, copy the whole file, and paste it into the cell.
6. Press the play triangle next to the cell name.
7. Read the line printed in the console: Set the TunePad project tempo to ... BPM. Type that number into the bpm box at the top of the page (see the table in Usage).
8. Press play again to hear the music at the right speed.

To add drums: click ADD CELL again and choose Drums. Paste the same file. In this cell only, change CELL = "melody" to CELL = "drums".

To add a bass line: click ADD CELL again and choose Bass. Paste the same file. In this cell only, change CELL = "melody" to CELL = "bass".

To add an arpeggio line: click ADD CELL again and choose Keyboard (or any other instrument you like). Paste the same file. In this cell only, change CELL = "melody" to CELL = "arp".

Use the same EMOTION in all cells, then press the big play button at the top right to hear them together.


## Usage
Only two lines near the top of week11 final need to be changed:


`EMOTION = "happy"
CELL = "melody"`

- EMOTION can be "happy", "calm", "nervous", "angry" or "sad". It picks the music style.
- CELL can be "melody", "drums", "bass" or "arp". Use "melody" in a Keyboard cell, "drums" in a Drums cell, "bass" in a Bass cell and "arp" in a second Keyboard cell (or any instrument you like).

Set the tempo by hand in the bpm box at the top of TunePad, because TunePad cannot set the speed from code:

- happy: 124 BPM. Listen for bright, short, lively notes.
- calm: 68 BPM. Listen for slow, soft, long notes.
- nervous: 150 BPM. Listen for fast, jumpy notes and a tense ending.
- angry: 140 BPM. Listen for loud, hard, short notes and a heavy beat.
- sad: 60 BPM. Listen for very slow, quiet, long notes with gaps between them.

Run it a few times with the same emotion. The tune should change each time but keep the same mood. Each clip is 8 beats (2 bars) long.

If the drum sounds are wrong, change the numbers 0 (kick) and 5 (hi-hat) in the play_drums() function to match your drum kit. If the bass line sounds too high or too low, change the numbers in bass_notes (36 is a low C). The same works for arp_notes in the arp cell.

## How the Code Works
- Choosing the emotion. EMOTION.strip().lower() cleans the word. An if / elif / else block then sets the notes, note lengths, loudness, rest chance and BPM for that emotion.
- Making it random. A while loop keeps adding notes until 8 beats are filled. random.randint() picks the note length, whether to rest, and the loudness.
- Making it smooth. Each new note moves 0 to 2 steps up or down the list of allowed notes instead of jumping anywhere.
- Ending. The last note comes from the template. It is the home note for happy and calm, and a tense note for nervous.
- Drums. play_drums() goes through the steps one by one. Even steps can play a kick and odd steps can play a hi-hat. Each hit has a random chance to play, and its loudness is random too, so the drum pattern is different every time. The first kick always plays so the beat has a clear start.
- Bass. play_bass() plays one low note for each step. The first note is always the home note. The other notes are picked at random from bass_notes, and the last note comes from end_index (a tense note for nervous). The loudness is random too.
- Arpeggio. play_arp() plays one chord note for each step. The first and last notes are always the first note of the chord. The notes in between are picked at random from arp_notes, with a random loudness. Each feeling has its own chord: bright for happy, soft for calm, tense for nervous, hard for angry and dark for sad.
- New feelings. Angry and sad are two more templates in the if / elif / else block. Angry uses a blues-style scale, loud notes and a fast beat. Sad uses a minor scale, quiet long notes and a slow beat.

## Project Status
Finished as a prototype for the assessment (Weeks 7 to 11). The drum and bass numbers may need small changes for a different TunePad instrument.
## Room for Improvement

Room for improvement:
- Check the drum numbers (kick 0, hi-hat 5) and the bass notes on more TunePad instruments
- Let the user type the emotion while the program runs, instead of changing a line in the code

To do:
- Add more emotions, such as excited or lonely
- Make longer pieces, and add chords that match the melody


## Acknowledgements
- This project was inspired by the TunePad tutorials, especially [Chicago house beat](https://learn.tunepad.com/tutorials/chicago-house/) (drum sound numbers: kick 0, hi-hat 5) and [Loopy hip-hop beat](https://learn.tunepad.com/curriculum/activities/livecode-hiphop/) (playing drum sounds in a loop).
- This project was based on [TunePad documentation](https://tunepad.com/docs) for `playNote()`, `rest()` and the idea that notes are numbers (60 is middle C), and on [Notes and melody](https://learn.tunepad.com/curriculum/activities/livecode-notes/) for playing a melody from note numbers.
- `random.randint()` comes from the [Python random module](https://docs.python.org/3/library/random.html).
- This README was written with the help of the [README cheatsheet](https://github.com/ritaly/README-cheatsheet) and [How to write a good README for your GitHub project](https://bulldogjob.com/readme/how-to-write-a-good-readme-for-your-github-project).
- The emotion templates, the if / elif / else logic, the random note picker, the smooth "random walk", the endings, the drum pattern, the bass line, the arpeggio line and the angry and sad templates were written for this project.
- Many thanks to my tutor and classmates in tutorial Sem1.

## Contact
Created by [Kaiduan.Liu@student.uts.edu.au](https://www.flynerd.pl/) - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
