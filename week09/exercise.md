# Reading Large Files in Batches

Let's convert an audio file to amplitude samples, and then playback those samples


![playback](playback.png)

-----

### Code

Make sure to import the `SdFat` Library for this code to compile. After set-up and opening a file, writing to an sd card is just like printing over `Serial`. Reading is similarly straighforward.

Check out the documentation for the library [here](https://github.com/greiman/SdFat-Particle). There are many code samples as well as discussions on common use cases.

This is the baseline code for reading, as well as writing.

```c
#include "SdFat.h"

SdFat sd;
const uint8_t chipSelect = SS;

File myFile;

void setup() {
  Serial.begin(9600);
  // Wait for USB Serial 
  while (!Serial) {
    SysCall::yield();
  }
  
  // Initialize SdFat or print a detailed error message and halt
  // Use half speed like the native library.
  // Change to SPI_FULL_SPEED for more performance.
  if (!sd.begin(chipSelect, SPI_HALF_SPEED)) {
    sd.initErrorHalt();
  }

//  This is code for writing
//   // this opens a file for editing, makes the file if it doesn't exist, and places our imaginary text cursor at the end.
//   if (!myFile.open("test.txt", O_RDWR | O_CREAT | O_AT_END)) {
//     //prints an error if for some reason the file couldn't be written
//     sd.errorHalt("opening test.txt for write failed");
//   }
//   // if the file opened okay, write to it:
//   Serial.print("Writing to test.txt...");
//   myFile.println("hello world!");

//   // close the file:
//   myFile.close();
//   Serial.println("done.");


  // This is code for reading
  // Open the file for reading:
  if (!myFile.open("test.txt", O_READ)) {
    sd.errorHalt("opening test.txt for read failed");
  }
  Serial.println("test.txt content:");

  // read from the file until there's nothing else in it:
  int data;
  
  //myFile.read() returns -1 when there is nothing left on the card...
  while ((data = myFile.read()) >= 0) {
    Serial.write(data);
  }
  // close the file:
  myFile.close();

}

void loop() {
  // nothing happens after setup
}

```

-----

More advanced code allows us to read a stream of data and operate on it.

```c


