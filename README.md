# To Interface Ultersonic Sensor with Arduino and Write a program to display the distance of an object

## Device Required

 1.Arduino Uno

 2.Data Cable

 3.Bread Board

 4.Jumper Wires

 5.Ultrasonic Sensor

 **Arduino IDE** :  [Download IDE](https://www.arduino.cc/en/software)


## Theory

An ultrasonic Sensor is a device used to measure the distance between the sensor and an object without physical contact.
This device works based on time-to-distance conversion.
Ultrasonic sensor measure distance by sending and receiving the ultrasonic wave.The ultrasonic has a sender to emit the ultrasonic wave and a receiver to receiver the ultrasonic waves.The transmitted ultrasonnic wave travels through the air and is  reflected by hitting the object.Arduino calculates the time taken by the ultrasonic pulse to reach the receiver from the sender.

## Given Data

Distance=Speed


## Connection

|Pin No| Pin Name | Pin Description |
|---|---|---|
|1|VCC|Power supply 3.3v to 5.5v|
|2|TRIG| connect to any pin of arduino|
|3|ECHO|Connect to any pin of arduino|
|4|GND|Ground|


## Program

```cpp 

#define trigpin 8
#define echopin 7
long duration;
int distance;

void setup()
{
    pinMode(trigpin,OUTPUT);
    pinMode(echopin,INPUT);
    Serial.begin(9600);
}

void loop()
{
    digitalWrite(trigpin,HIGH);
    delayMicroseconds(10);
    digitalWrite(trigpin,LOW);
    duration=pulseIn(echopin,HIGH);
    distance=duration*0.034/2;
    Serial.print("Distance of an object is : ");
    Serial.print(distance);
    Serial.println("cm");
}

```

## Sreenshot

### 1

![Screenshot](./WhatsApp%20Image%202024-03-07%20at%205.33.05%20PM.jpeg)

### 2

![Screenshot](./WhatsApp%20Image%202024-03-07%20at%205.33.23%20PM.jpeg)
