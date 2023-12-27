# Servo-Motor-Control-
Control a servo motor using a potentiometer to vary its position.
#include <Servo.h>

Servo myservo;
int potPin = A0;
int potValue = 0;

void setup() {
  myservo.attach(9);
}

void loop() {
  potValue = analogRead(potPin);
  int angle = map(potValue, 0, 1023, 0, 180);
  myservo.write(angle);
  delay(15);
}
