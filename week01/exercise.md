# Light Theremin

The following simple circuit creates a theremin with a frequency modulated by light exposure, allowing a musician to play the instrument by adjusting the amount of light that strikes a light-dependent-resistor (LDR), or photoresistor. 

![light theremin](theremin.png)




The Arduino code is available below.


```c
int speakerPin = 12;
int sensorPin = 0;
 
void setup(){
	pinMode(speakerPin, OUTPUT);
	pinMode(sensorPin, INPUT);
}
 
void loop(){
  int rawReading = analogRead(photocellPin);
  int mappedReading = map(mappedReading, 0, 1024, 261, 440)

  tone(speakerPin, mappedReading);
}

```