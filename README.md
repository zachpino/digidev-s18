# digidev-s17
Documentation and Resources for the Spring 2018 IIT Institute of Design Digital Development Workshop

- [Week 01 · Microcontroller Basics, Arduino and Particle Platforms, Photoresistor Theremin](week01/readme.md) 	
	
	- Presentation: Syllabus Review, (Electonic) Instruments, Explore Variety of Arduino Components and Electronic Instruments, Particle Build Site and App
	- Make: [Theremin](https://learn.adafruit.com/adafruit-arduino-lesson-10-making-sounds/pseudo-theramin)
	- New Components: Photon, Breadboard, Jumper Cables, Buzzer, LED, Resistor, Photoresistor
	- New Code: tone(), noTone(), map(), analogRead(), int, digitalWrite(), delay()
	- Homework: Make an instrument! Handheld object that can make at least 8 distinct sounds. Translate single song into tone/hertz language
	- Homework: Purchase Kit and Sensor Pack

- [Week 02 · Sound of Electricity](week02/readme.md) 	
	> Presentation: Electric / Sonic Waveforms, Plumbing Model of Electricity, Circuit Diagramming
	> Make: Buzzer Melody, [3 Tone Keyboard](https://www.arduino.cc/en/Tutorial/toneKeyboard)
	> New Components: Button, LEDs, TrimPot
	> New Code: digitalRead(), if(){}, else{}
	> Homework: Improve keyboard! Add 4th button, change from tones to small melodies from each button
	> Homework: Watch Moog Movie

- [Week 03 · Rhythm](week03/readme.md) 	
	> Presentation: Digital Loops
	> Make: 4 beat drum machine, led indicator, pots for pitch, on/off switch, TRS jack with volume pot
	> New Components: Headphone Jack, Toggle Switch
	> New Code: while(), for(); Reading Potentiometers, Switches; Global On/Off
	> Homework: Improve Sequencer! Add trimpot for tempo control. [Sequencer](https://learn.sparkfun.com/tutorials/build-an-auduino-step-sequencer)
	> Homework: Visit Chicago Music Exchange

- [Week 04 · PWM and Polyphony](week04/readme.md) 	
	> Presentation: PWM, Color and Sonic Harmony
	> Make: Basic Harmonics Tool with 3 Buzzers
	> New Components: RGB LED, Amps, Multiple Buzzers
	> New Code: analogWrite(),[Tone Library](https://code.google.com/archive/p/rogue-code/wikis/ToneLibraryDocumentation.wiki)
	> Homework: Switch to PWM polyphony with Tone Library and 1 buzzer

 - [Week 05 · Playback and Feedback](week05/readme.md) 	
	> Presentation: PAM8302 Amplifier, Speaker, WAV Files
	> Make: [WAV Player with Navigable Screen Interface and SD Card Memory](https://circuitdigest.com/microcontroller-projects/arduino-audio-music-player)
	> New Components: [LCD Display](https://www.hackster.io/ingo-lohs/what-s-my-i2c-address-0a097e), Speaker, SD Card Reader, LiPo Battery, LiPo Charger
	> New Code: Libraries, String Processing, String() manipulation
	> Homework: Add toggle between headphones and speaker

 - [Week 06 · Recording and Capture](week06/readme.md) 	
	> Presentation: Microphones, Analog and Digital Sensors
	> Make: [Sound recorder capable of capturing and playing back a sound](http://www.instructables.com/id/Arduino-Audio-Input/)
	> New Components: Microphones, Analog Sensors (Piezo Force Sensor, Slide Pot, Flex Sensor) and Digital Sensors (Temperature Sensor, Digital Color Sensor)
	> New Code: Library Import, Particle.variable(), Particle.publish(), Serial Data Writing
	> Homework: Record/Prepare 8 Sounds, Make 8 Sound Sample/FX Board

 - [Week 07 · Desktop Input](week07/readme.md) 	
	> Presentation: MIDI, Adobe Audition
	> Make: [MIDI Controller](http://www.instructables.com/id/Arduino-MIDI-Controller/)
	> New Components: Slide Pots, Push Buttons
	> New Code: MIDI Serial Signalling
	> Homework: Record/Prepare Some Music!


- Break

- [Week 08 · Inputs from Body and Physical Space](week08/readme.md) 	
	> Presentation: Fashion and Electronic Music
	> Make: Wearable Wearable Sound Controller
	> New Components: 6DOF, Analog Range Finder
	> New Code: Sonar Echo/Trigger
	> Homework: Bodily Sound Effect Maker 

- [Week 09 · Miniaturization and Listening](week09/readme.md) 	
	> Presentation: Acoustics
	> Make: Speakers and Headphones
	> New Components: Audio Drivers, Mems Microphone
	> New Code: Acoustics Prototyping in Rhino?
	> Homework: Headphone/Speaker Shell Design

- [Week 10 · Data Plotting / Audio Visualizer](week09/readme.md) 	
	> Presentation: Data Visualization
	> Make: Online Temperature Recorder
	> New Components: 
	> New Code: Particle API calls, SVG and D3 basics
	> Homework: Begin Work on Final Briefs

- [Week 11 · Communication Protocols](week10/readme.md) 	
	> Presentation: Pirate Radio + Designed Disobedience
	> Make: [FM Radio Tuner, FM Radio Transmitter](https://create.arduino.cc/projecthub/nickthegreek82/arduino-tea5767-fm-radio-receiver-543480)
	> New Components: Radio Module, Bluetooth, XBee, IR Diodes
	> New Code: 
	> Homework: 

- [Weeks 12 — 13]
	> Catch-Up, Worktime, Review, and Odds+Ends

- [Week 14 · Finished!]
	> Presentation: Final Critique
	> Homework: Deliverables


# Final Briefs

## Wearable, Tabletop, or Spatial Synthesizers

Develop a physical object composed of a set of sensors and audio feedback that allows for wide expressability, novel interactions, and intentional musicality. Bonus points for the development of an accompanying DJ persona.

###### Deliverables	 

* Prototyped Working Object (or scale model if necessary)
* Fritzing Diagram of Circuit
* Photographic Documentation of Project
* *Edited* Video Demonstrating Functionality

* Set of MP3s of Practiced Compositions on Synthesizer
* Instruction Manual Educating an Inexperienced User

-----

## Musical Human Factors

Choose a physical object/space that currently lacks sonic feedback — and through a combination of *non-invasive* sensors — provide feedback that makes the object/space more engaging in its use, more intuitive to learn or master, and/or safer for an end-user to engage. 
	
###### Deliverables	 

* Prototyped Working Object
* Fritzing Diagram of Circuit
* Photographic Documentation of Project
* *Edited* Video Demonstrating Functionality

* Storyboard of Proposed Functionality in Context
* Instruction Manual Educating an Inexperienced User

-----

## Sound Design for Social Impact

*Read this vague, yearly-renewed grant call for proposals carefully and in its entirety*

[Help America Vote Act Grant Application](https://www.grants.gov/web/grants/view-opportunity.html?oppId=293206)

This public grant — awarding up to $220,000 per winner — tasks applicants to make the American polling places easier for users with visuo-spatial impairments. How could electronically-produced sonic feedback be used to improve the voting experience for such users? Are there other, significant, public experiences that could be similarly improved?

###### Deliverables	 

* Prototyped Working Object
* Fritzing Diagram of Circuit
* Photographic Documentation of Project
* *Edited* Video Demonstrating Functionality

* Documentation of an Interview with a Potential User
* Storyboard of Proposed Functionality in Context

-----

## Electronic Sonic Play

Create a toy for children that allows the capture, creation, manipulation, and production of sound. 

Additional design challenge: Sonic feedback is especially helpful to many children on the autistic-asbergers spectrum. How could the toy described above be made more appropriate and valuable for this underserved audience?

###### Deliverables	 

* Prototyped Working Object
* Fritzing Diagram of Circuit
* Photographic Documentation of Project
* *Edited* Video Demonstrating Functionality

* Documentation of an Interview with a Potential User
* Storyboard of Proposed Functionality in Context

-----

## Sensor Bomb for Designing with Data

Combine a set of related sensors into a composed object that both captures and produces sound in some way and is able to generate an acoustic fingerprint of its environment. This object could be proposed as an answer to any of the many [grants.gov grants](http://grants.gov) currently on offer, which require a set of sensors to be deployed in a specific environment.

###### Deliverables	 

* Prototyped Working Object
* Fritzing Diagram of Circuit
* Photographic Documentation of Project
* *Edited* Video Demonstrating Functionality

* Storyboard of Proposed Functionality in Context
* Designed Data Visualization for Logged Data