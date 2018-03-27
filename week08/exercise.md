# Real Waveforms and SPI Interfaces

So far, we've used a simplifying tool to create audio waveforms -- the `tone()` function, which generates simple square waves with a frequency measured in hertz. This has been fine so far, but has largely prevented us from playing with an entire dimension of sound: volume!

In addition to generating some tones, let's also add in a new component interface: SPI.

![SPI](spi.png)

-----

### SD Card Reader

![SD Card Breakout](https://cdn-shop.adafruit.com/970x728/254-05.jpg)

This SPI protocol board, short for [Serial Peripheral Interface](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface_Bus), allows the Photon to have access to more memory and write non-volatile data. SPI sensors and actuators are very common, far more common than its younger competitor, I2C.

SPI uses four wires, in addition to power and ground, to communicate between a master and slave. SPI is very verbose and precise, and requires a separate channel for each component in the system. The pins that drive SPI communication are named Master-In-Slave-Out (MISO), Master-Out-Slave-In (MOSI), Standard/Serial Clock (SCK), and Slave Select (SS). The SS pin is only used when multiple slave devices are attached to the same master.

The Photon has several SPI-compatible blocks of pins, though normally A2-A5 are used. Consult the Particle Photon pinout for other options.

- SPI Name -> Breakout Label -> Photon Pin
- SS -> CS -> A2
- SCK -> CLK -> A3
- MISO -> DO -> A4
- MOSI -> D1 -> A5

If it's not obvious, use an I2C component when you can! SPI steals more pins, and is generally more complicated to get working and debug.

-----

### Code

Make sure to import the `SdFat` Library for this code to compile. After set-up and opening a file, writing to an sd card is just like printing over `Serial`.

Check out the documentation for the library [here](https://github.com/greiman/SdFat-Particle). There are many code samples as well as discussions on common use cases.

```c
//import the library
#include "SdFat.h"

//create a variable to hold our SD access methods
SdFat sd;

//the library allows for multiple pins to be used to speak to many different SPI devices
//here, we are saying that the SS pin is connected to our SPI device
const uint8_t chipSelect = SS;

//the library also requires us to use mthods at the file level
File myFile;

void setup() {

  Serial.begin(9600);
  // Wait for USB Serial to turn on, it's not instantaneous
  while (!Serial) {
    //this is like 'delay', but much lower level
    SysCall::yield();
  }
  
  // Initialize SdFat or print a detailed error message and stop. We work here at half speed, in case our Photon tries to access the SD card before the breakout board is ready
  if (!sd.begin(chipSelect, SPI_HALF_SPEED)) {
    sd.initErrorHalt();
  }

  // this opens a file for editing, makes the file if it doesn't exist, and places our imaginary text cursor at the end.
  if (!myFile.open("test.txt", O_RDWR | O_CREAT | O_AT_END)) {
    //prints an error if for some reason the file couldn't be written
    sd.errorHalt("opening test.txt for write failed");
  }

  // if the file opened okay, write to it:
  Serial.print("Writing to test.txt...");
  myFile.println("testing zach zach baby");

  // close the file:
  myFile.close();
  Serial.println("done.");

}

void loop() {
  // nothing happens after setup
}
```

-----

We can also use the Digital to Analog Converter on our Photon to make more interesting waveforms.

```c
//simple DAC sawtooth wave demo

int pin = DAC1;

void setup() {
    pinMode(pin, OUTPUT);
}

void loop() {
  sawtooth(pin,100,200);
}

void sawtooth(int pin, int volume, int hertz) {
  for(int i = 0; i < volume; i++){
      analogWrite(pin, i);
      delay(1000 / (hertz * volume));
  }
}

```
