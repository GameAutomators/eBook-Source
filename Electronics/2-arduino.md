## Introduction to Arduino

Arduino is an open-source, easy to use platform used for various electronics projects. It has a physical programmable circuit board. The capabilities of Arduino depends on the capabilities of the the microcontroller it's holding. 

There are various types of Arduino's available in the market and the most popular one is called Arduino UNO. Each of the Arduino's capabilities depend on the core microcontroller on it's circuit board. For instance, Arduino UNO using ATMega328P and hence various specs depend on it.

All the Arduino is doing is- it reads the inputs from the sensors, and takes action depending on the logic that has been programmed into it.

Jeremy Blum's Arduino tutorials on the YouTube are one of the best out there, watch the first three videos to get the basic understanding of Arduino.

Link: https://www.youtube.com/playlist?list=PLV009FNOX7Tf-XSyghg2vrSYXw1QcCHaX

<div class="row" style="text-align:center;">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLV009FNOX7Tf-XSyghg2vrSYXw1QcCHaX" frameborder="0" allowfullscreen></iframe>
</div>

### Hardware

(write about pins here)

### Software

Arduino comes with a easy-to-use software that is available on their website ([arduino.cc](arduino.cc)). It can be used to write code, compile it and then upload it onto the Arduino that can be used in your projects.



Arduino also has an open-source software component which is similar to C++. The Arduino integrated development environment (IDE) allows you to write code, compile it, and then upload it to your Arduino for stand alone use in prototyping and projects.
 A typical Arduino C/C++ sketch consist of two functions that are compiled and linked with a program stub main() into an executable cyclic executive program:

***setup()***: a function that runs once at the start of a program and that can initialize settings.

***loop()***: a function called repeatedly until the board powers off.

Sample program: (for blinking an LED)
```C
#define LED_PIN 13

void setup() {
    pinMode(LED_PIN, OUTPUT);       // Enable pin 13 for digital output
}

void loop() {
    digitalWrite(LED_PIN, HIGH);    // Turn on the LED
    delay(1000);                    // Wait one second (1000 milliseconds)
    digitalWrite(LED_PIN, LOW);     // Turn off the LED
    delay(1000);                    // Wait one second
}
```