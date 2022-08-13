# on-and-off-system

 Electric: Design a circuit that can be turned on and off automatically
 
 ## Circuit design :
 
 ![on   off](https://user-images.githubusercontent.com/103388162/184477939-cb312663-ba60-4596-8009-a722c30809ac.jpeg)
 
 ## Hardware Required :
 
 * Power Supply
 * Light bulb
 * NPN Transistor
 * Relay SPDT
 * Arduino UNO
 * Button
 * Resistor

## The Code :

```
int pinButton = 8; 
 
int Relay = 2; 
 
int stateRelay = LOW; 
 
int stateButton; 
 
int previous = LOW; 
 
long time = 0; 
 
long debounce = 100; 
 
int stayON = 5000; 
 
void setup() 
{ 
  pinMode(pinButton, INPUT); 
  pinMode(Relay, OUTPUT); 
} 
 
void loop() 
{ 
  stateButton = digitalRead(pinButton);   
  if(stateButton == HIGH && previous == LOW && millis() - time > debounce) {     if(stateRelay == HIGH){       digitalWrite(Relay, LOW); 
    }else{ 
 
       
       digitalWrite(Relay, HIGH);        delay(stayON); 
       digitalWrite(Relay, LOW); 
    } 
    time = millis(); 
  } 
  previous == stateButton; 
} 
mark

```

## Reference :

* https://youtu.be/58Ynhqmvzoc
* https://roboticsbackend.com/arduino-turn-led-on-and-off-with-button/
