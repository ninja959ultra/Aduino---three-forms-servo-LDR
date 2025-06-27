# Aduino---three-forms-servo-LDR


# Code:
```cpp
#include <Servo.h>


Servo servo;


// LEDs
byte redLED = 7;
byte blueLED = 8;
byte whiteLED = 9;
byte LDR = A5;


// Globals
int LDRValue;


void setup() {
  Serial.begin(9600);
  servo.attach(2);
  servo.write(0);
  delay(1500);
  pinMode(redLED, OUTPUT);
  pinMode(blueLED, OUTPUT);
  pinMode(whiteLED, OUTPUT);
  pinMode(LDR, INPUT);
}


void loop() {
  LDRValue = analogRead(LDR);

  if (LDRValue <= 300){
    servo.write(0);
  }

  else if (LDRValue > 300){
    servo.write(90);
  }

  if (LDRValue > 700){
    servo.write(180);
  }

  Serial.print("Brightness= ");
  Serial.println(LDRValue);
  delay(1000);
}

```
