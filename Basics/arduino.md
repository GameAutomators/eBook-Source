# Introduction to Arduino

Arduino is an open-source platform used for building electronics projects. Arduino consists of both a physical programmable circuit board (often referred to as a microcontroller) and a piece of software, or IDE (Integrated Development Environment) that runs on your computer, used to write and upload computer code to the physical board.

Jeremy Blum's Arduino tutorials on the YouTube are one of the best out there, watch the first three videos to get the basic understanding of Arduino.

**Link:** https://www.youtube.com/watch?v=fCxzA9_kg6s&list=PLV009FNOX7Tf-XSyghg2vrSYXw1QcCHaX

![image]()

##### What’s on the board?
It is an open-source circuit board with a microprocessor and input/output (I/O) pins for communication and controlling physical objects (LED, servos, buttons, etc.). The board will typically be powered via USB or an external power supply which in turn allows it to power other hardware and sensors.

##### Power (USB / Barrel Jack)
It needs a way to be connected to a power source. It can be powered from a USB cable coming from computer or a wall power supply that is terminated in a barrel jack.

![image1]()

##### Pins (5V, 3.3V, GND, Analog, Digital, PWM, AREF)
The pins on  Arduino are the places where you connect wires to construct a circuit (probably in connection with a breadboard and some wire. They usually have black plastic ‘headers’ that allow you to just plug a wire right into the board. The Arduino has several different kinds of pins, each of which is labeled on the board and used for different functions.

**GND (3)**: Short for ‘Ground’. There are several GND pins on the Arduino, any of which can be used to ground your circuit.

**5V (4) & 3.3V (5)**: As you might guess, the 5V pin supplies 5 volts of power, and the 3.3V pin supplies 3.3 volts of power. Most of the simple components used with the Arduino run happily off of 5 or 3.3 volts.

**Analog (6)**: The area of pins under the ‘Analog In’ label (A0 through A5 on the UNO) are Analog In pins. These pins can read the signal from an analog sensor (like a temperature sensor) and convert it into a digital value that we can read.

**Digital (7)**: Across from the analog pins are the digital pins (0 through 13 on the UNO). These pins can be used for both digital input (like telling if a button is pushed) and digital output (like powering an LED).

**PWM (8)**: You may have noticed the tilde (~) next to some of the digital pins (3, 5, 6, 9, 10, and 11 on the UNO). These pins act as normal digital pins, but can also be used for something called Pulse-Width Modulation (PWM). 

**AREF (9)**: Stands for Analog Reference. Most of the time you can leave this pin alone. It is sometimes used to set an external reference voltage (between 0 and 5 Volts) as the upper limit for the analog input pins.
##### Reset Button
It has a reset button (10). Pushing it will temporarily connect the reset pin to ground and restart any code that is loaded on the Arduino. This can be very useful if your code doesn’t repeat, but you want to test it multiple times.
##### Power LED Indicator
Just beneath and to the right of the word “UNO” on your circuit board, there’s a tiny LED next to the word ‘ON’ (11). This LED should light up whenever you plug your Arduino into a power source. If this light doesn’t turn on, there’s a good chance something is wrong. Time to re-check your circuit!
##### TX RX LEDs
TX is short for transmit, RX is short for receive. These markings appear quite a bit in electronics to indicate the pins responsible for serial communication. In this case, there are two places on the Arduino UNO where TX and RX appear – once by digital pins 0 and 1, and a second time next to the TX and RX indicator LEDs (12). These LEDs will give some nice visual indications whenever Arduino is receiving or transmitting data.

##### Main IC

The black thing with all the metal legs is an IC, or Integrated Circuit (13). Think of it as the brains of our Arduino. The main IC on the Arduino is slightly different from board type to board type, but is usually from the ATmega line of IC’s from the ATMEL company. 

##### Voltage Regulator
The voltage regulator (14) does exactly what it says – it controls the amount of voltage that is let into the Arduino board. Think of it as a kind of gatekeeper; it will turn away an extra voltage that might harm the circuit. Of course, it has its limits, so don’t hook up Arduino to anything greater than 20 volts.

##### Software
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