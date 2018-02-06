# Resistor Sensor Array

This particular project allows us to better understand [variable] resistor behavior, as well as explore possible user interactions.

![resistor array](resistor_bb.png)

-----

### Soft Potentiometer

![SoftPot](https://cdn.sparkfun.com/r/500-500/assets/parts/1/8/4/1/08680-03-L.jpg)

Often called 'softpots' these variable resistors use the same logic as regular potentiometers. Softpots, though, don't use a spinning dial but instead use finger pressure to make a connection between two conductive surfaces. This allows a user to control the flow of electrons by sliding their finger across the softpot surface. More information on how softpots work can be found on [Sparkfun's reference](https://learn.sparkfun.com/tutorials/softpot-hookup-guide).

Softpots come in [many different form factors, like rings, and different sizes](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Daps&field-keywords=softpot).

Similar to a photoresistor, to get more accurate readings and remove noise, you'll see an optional pullup resistor used within the circuit. However, slide potentiometers are often better fabricated, and so their noise is not as problematic. If you find the sensor data noisy, [add a resistor](https://learn.sparkfun.com/tutorials/softpot-hookup-guide).

### Thermistor

![Thermistor](https://cdn.sparkfun.com//assets/parts/1/9/2/thermistor.jpg)

Thermistors are analog temperature sensors. They are another kind of variable resistor (we've talked about several already like the photoresistor and potentiometer!), except their resistance changes through thermal expansion rather than light or human intervention.

Like all *analog sensors* they do not return accurate, unit-based values like celsius or fahrenheit, but rather simply give us a sense of relative thermal conditions and temperature changes — by modulating the flow of electricity. They can be slow to respond and drift in their readings as well, as the waste heat of the microprocessor begins to be influential in the temperature readings. However, given a bit of calibration, their values can be mapped to unit-based temperatures in a specific space. 

Note that temperature readings are always tied to ambient humidity levels, and so a hygrometer is usually included with [more accurate temperature sensors](https://www.sparkfun.com/products/10167).

-----

### Code

```c
//This sensor array will help us understand resistor behavior.

//connections
int nakedPin = A0;
int resistorPin = A1;
int thermistorPin = A2;
int photoresistorPin = A3;
int trimpotPin = A4;
int slidepotPin = A5;

int rPin = D0;
int gPin = D1;
int bPin = D2;


void setup() {

  // choose pin orientation
  pinMode(nakedPin, INPUT);
  pinMode(resistorPin, INPUT);
  pinMode(thermistorPin, INPUT);
  pinMode(photoresistorPin, INPUT);
  pinMode(trimpotPin, INPUT);
  pinMode(slidepotPin, INPUT);

  pinMode(rPin, OUTPUT);
  pinMode(gPin, OUTPUT);
  pinMode(bPin, OUTPUT);

  //usb communication
  Serial.begin(9600);

}

void loop() {
  //check sensors
  int nakedReading = analogRead(nakedPin);
  int resistorReading = analogRead(resistorPin);
  int thermistorReading = analogRead(thermistorPin);
  int photoresistorReading = analogRead(photoresistorPin);
  int trimpotReading = analogRead(trimpotPin);
  int slidepotReading = analogRead(slidepotPin);

  //print sensor results over USB
  Serial.print("naked: ");
  Serial.println(nakedReading);
  Serial.print("resistor: ");
  Serial.println(resistorReading);
  Serial.print("thermistor: ");
  Serial.println(thermistorReading);
  Serial.print("photoresistor: ");
  Serial.println(photoresistorReading);
  Serial.print("trimpot: ");
  Serial.println(trimpotReading);
  Serial.print("slidepot: ");
  Serial.println(slidepotReading);
}
```
