# Week 1 · Microprocessor Basics, Arduino and Particle Platforms, Photodiode Theremin
Documentation and Resources for the Spring 2018 IIT Institute of Design Digital Development Workshop

Welcome to Digital Development Workshop, Spring 2018. In this course, the fundamentals of microcontrollers, electronics, and functional programming will be covered through explorations into digital and experimental musicianship.

The course will rely upon the exciting opportunities offered by the Particle Photon prototyping platform, though the code and components should run on any Arduino compatible board after necessary pin number alternations.

· [Introductory Presentation](DigiDev_S18_Intro.pdf)
· [Syllabus](DigiDev_S18_Syllabus.pdf)
· [Theremins](theremin.md)
· [Exercise](exercise.md)


### The Particle Platform

The Particle platform provides a set of hardware components based on the open source [Arduino](https://www.arduino.cc) specification. Particle distinguishes their products from traditional Arduinos by providing an integrated WiFi chip, online development environment, and private and public API support. All of these combine to create, with the Particle Photon, an Arduino that can easily prototype Internet of Things and other remote data collection and actuation devices. Additionally, Particle offers whitelabel manufacturing with preloaded firmware, in order to servce hardware startups and narrow the gap between prototype and finished product.

We need to begin by installing several pieces of necessary software dependencies. These steps work are designed for Mac OS X, and should also work for most Linux distros. The equivalent steps for Windows, with Linux specifics as well, are [available here](https://docs.particle.io/guide/tools-and-features/cli/photon/).

### Install Homebrew
Install the commonly required [Homebrew Package Manager](), which is used to maintain versions and dependencies for many open source softwares on the Mac OS X platform. 

Open the *Terminal* application from your Applications/Utilities folder, paste in the following, and press 'Enter'.

> /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

### Make a Particle Build Account
Visit the Particle development website to make a free account. Please bookmark this page for frequent future use.

[https://build.particle.io](https://build.particle.io)

### Install Particle CLI Tools
The Particle platform is easier to work with after some additional utilities are installed. Paste this line into a new terminal window and press 'Enter'.

> bash <( curl -sL https://particle.io/install-cli )

Quit Terminal, and relaunch it. Type into this new windows:

> particle login

Provide your credentials there to associate your account with your computer.

### Download the Particle Mobile Application

Search your respective App Store for the 'Particle' App and login.

### Connect Photon to Internet

Please follow [these steps](https://docs.particle.io/guide/getting-started/start/photon/) to connect your Particle Photon to the internet, beginning at `Step 2B` through the Mobile App.







	> Presentation: Syllabus Review, (Electonic) Instruments, Explore Variety of Arduino Components and Electronic Instruments, Particle Build Site and App
	> Make: [Theremin](https://learn.adafruit.com/adafruit-arduino-lesson-10-making-sounds/pseudo-theramin)
	> New Components: Photon, Breadboard, Jumper Cables, Buzzer, LED, Resistor, Photoresistor
	> New Code: tone(), noTone(), map(), analogRead(), int, digitalWrite(), delay()
	> Homework: Make an instrument! Handheld object that can make at least 8 distinct sounds. Translate single song into tone/hertz language
	> Homework: Purchase Kit and Sensor Pack
