# Stick Hero
In this game,the player need to hold on the screen such that the stick that the man is holding increase its lenght such that the stick can be used to across the gap between two black pillars.



##### Playstore Link: [Stick Hero](https://play.google.com/store/apps/details?id=com.ketchapp.stickhero&hl=en)

 [Image] 
 
#### Difficulty Level:
Moderate
#### Overview
- Detect the black pillars
- Determine the amount of time the screen is to be touched
- Simulate touch on the tablet/phone

#### Requirements
- An Android Device with the ‘Stick Hero’ game installed in it.
- Single Strand Wires, Coins, Relays are used to simulate the touch on the capacitive touch screen of phones and tablets.
- Arduino is used to control the duration of the touch.
- Matlab: Used for Image Processing
- Arduino IDE: For programming the Arduino.
- IP Cam: It is an android app which enables us to use our smartphones cam as a web cam

#### Circuit Diagram:


#### Tutorial:
#####  Step 1:Detecting the black pillars:
This is done by using Matlab. The image that is captured from the IP Cam is  processed and the locations of the black pillars are determined. The distance between the black pillars is calculated and the corresponding data is sent to the Arduino through serial communication.

The source code for the above processing can be found [here](https://github.com/psurya1994/arduino-plays-stick-hero/tree/master/Code/MATLAB)



##### Step 2:Determining the duration of the touch:
Based on the data arrived from Matlab, the duration of the touch is adjusted such that the stick exactly falls on the adjacent pillar.

The source code for the arduino can be found [here](https://github.com/psurya1994/arduino-plays-stick-hero/tree/master/Code/Arduino).
##### Step 3:Simulating Touch:

For this we have to understand how capacitive touch screens work. The electrodes apply a low voltage to the conductive layer creating a uniform electrostatic field. When a finger hits the screen a tiny electrical charge is transferred to the finger to complete the circuit creating a voltage drop at that point on the screen. The location of this voltage drop is recorded by the controller and this is how a capacitive touch screen works.

We are going to use this concept, except that in the place of a finger, we use the ground pin on the arduino to transfer the charge on the screen. To have more surface area on the display of the screen, we use a coin.

Relays are directly connected to the output pin of the Arduino. It is equivalent to a touch if the voltage given is high as there is a path for the current to flow to the ground. It is equivalent to not touching if the voltage given is low.

Run the [test_relay code](https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/test_touch/test_touch.ino) at this link to see if the electronic touch is simulated properly.