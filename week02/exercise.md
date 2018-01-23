# 3 Tone Keyboard

This particular instrument allows a player to construct pitch-based melodies with 3 different notes.

![keyboard](keyboard.png)

There are 2 new components in play: a button and a trimpot, both of which allow user interaction. Another take on the same instrument, using force-sensitive resistors rather than buttons, is [available here](https://www.arduino.cc/en/Tutorial/toneKeyboard).

### Pushbutton

![Pushbutton](https://cdn.sparkfun.com//assets/parts/9/0/00097-03-L.jpg)

Buttons are simple components in complex packagings. They are effectively broken wires, that are fully reconnected when the button is pressed down. This allows a user to control the flow of electrons.

Buttons come in [many different form factors and sizes](https://www.sparkfun.com/search/results?term=button) for different applications, with slightly different behaviors.

Similar to the photoresistor, to get accurate readings and remove noise, a pulldown resistor is necessary.

### Trimpot (Potentiometer)

![Trimpot](https://cdn.sparkfun.com//assets/parts/3/8/2/3/09806-01.jpg)

Trimpots, a diminuitive member of a family of components called potentiometers, are resistors - though their resistance is not statics and instead changes depending on the position of a knob. As the knob is rotated clockwise, a condutive wiper inside moves along a resistive strips, forcing the electrons to travel through more or less resistive material. This attenuates the electrical signal, weakening its amplitude but leaving its pulse characteristics intact.

Here, we are using the trimpot as it is commonly used, a volume knob. No code is necessary for this, it is all handled with the electronics themselves.

![conductive wiper](https://i.stack.imgur.com/XXQEm.gif)

-----

### Code
The Arduino code to drive this circuit is a bit more complex, and uses conditionals.

```c
//This code enables a keyboard with 3 buttons that plays 3 different notes.

//Pin Definitions : Piezo Buzzer on D0 and Pushbuttons on D1, D2, D3
int buzzerPin = D0;
int button1 = D1;
int button2 = D2;
int button3 = D3;

//placeholder for what note the buzzer should play
int buzzerPitch = 0;

//how long each note holds
int buzzerDuration = 500;

 
//In setup, code runs once
void setup(){
    //setup Serial communication so we can read from the Paricle over USB
    Serial.begin(9600);
	
	//Set the 'one-way-streets' so that the right pins are speaking and listening
	pinMode(buzzerPin, OUTPUT);
	pinMode(button1, INPUT);
	pinMode(button2, INPUT);
	pinMode(button3, INPUT);
}

//After setup, loop runs over and over again 
void loop(){
 	//read from the buttons and store the values
	int button1Reading = digitalRead(button1);
	int button2Reading = digitalRead(button2);
	int button3Reading = digitalRead(button3);
 
 	//view the readings from the sensor
 	Serial.println(button1Reading);
 	Serial.println(button2Reading);
 	Serial.println(button3Reading);

		
	if(button1Reading == HIGH) {
		buzzerPitch = 261;
		
		//tell the buzzer to make noise
 		tone(buzzerPin, buzzerPitch);
 	
 		//wait a small amount of time to allow buzzer to make noise
 		delay(buzzerDuration);
 	}

 	else if(button2Reading == HIGH) {
		buzzerPitch = 659;
		
		//tell the buzzer to make noise
 		tone(buzzerPin, buzzerPitch);
 	
 		//wait a small amount of time to allow buzzer to make noise
 		delay(buzzerDuration);
 	}

 	else if(button3Reading == HIGH) {
		buzzerPitch = 1567;
		
		//tell the buzzer to make noise
 		tone(buzzerPin, buzzerPitch);
 	
 		//wait a small amount of time to allow buzzer to make noise
 		delay(buzzerDuration);
 	}

 	else{
 		noTone(buzzerPin);
 		delay(50);
 	}
}
```
