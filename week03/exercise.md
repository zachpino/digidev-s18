# Sequencer

This particular instrument allows a player to build a 4 beat rhythm out of dynamic pitches.

![sequencer](sequencer.png)

-----

### Code

```c
//This 4 beat sequencer has adjustable pitch!

//buzzer connection
int buzzerPin = D6;

//led connections
int led0 = D0;
int led1 = D1;
int led2 = D2;
int led3 = D3;

//button connections
int button0 = A0;
int button1 = A1;
int button2 = A2;
int button3 = A3;

//store the pitch each beat should play
int pitch0 = 200;
int pitch1 = 200;
int pitch2 = 200;
int pitch3 = 200;


void setup() {

  // choose pin orientation
  pinMode(button0, INPUT);
  pinMode(button1, INPUT);
  pinMode(button2, INPUT);
  pinMode(button3, INPUT);

  pinMode(led0, OUTPUT);
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);

}

void loop() {
  //check buttons
  int button0Reading = digitalRead(button0);
  int button1Reading = digitalRead(button1);
  int button2Reading = digitalRead(button2);
  int button3Reading = digitalRead(button3);

  //increase pitch if button is pressed
  if (button0Reading == HIGH) {
    pitch0 = pitch0 + 50;
  }

  if (button1Reading == HIGH) {
    pitch1 = pitch1 + 50;
  }

  if (button2Reading == HIGH) {
    pitch2 = pitch2 + 50;
  }

  if (button3Reading == HIGH) {
    pitch3 = pitch3 + 50;
  }

  //play beat 0
  tone(button0, pitch0);
  delay(1000);
  //pause
  noTone(button0);
  delay(500);

  //play beat 1
  tone(button1, pitch1);
  delay(1000);
  //pause
  noTone(button0);
  delay(500);

  //play beat 2
  tone(button2, pitch2);
  delay(1000);
  //pause
  noTone(button0);
  delay(500);

  //play beat 3
  tone(button3, pitch3);
  delay(1000);
  //pause
  noTone(button0);
  delay(500);

}
```
