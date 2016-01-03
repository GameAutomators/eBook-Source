# Different Methods
# 5.1. Using Electronic Circuits
This is a way to automate the mobile game without using any internal functions of Android library by using a clever integration of electronic sensors. 

##### Approach
![image9]()
Fig. The image depicts the block diagram for a typical circuit that can solve a game

##### Touch Simulation
For this we have to understand how capacitive touch screens work. The electrodes apply a low voltage to the conductive layer creating a uniform electrostatic field. When a finger hits the screen a tiny electrical charge is transferred to the finger to complete the circuit creating a voltage drop at that point on the screen. The location of this voltage drop is recorded by the controller and this is how a capacitive touch screen works.
![image10]()
We are going to use this concept, except that in the place of a finger, we use the ground pin on the arduino to transfer the charge on the screen. To have more surface area on the display of the screen, we use a coin.
##### When should we prefer to use Electronic circuits?
Since ADB tool processing is slow as discussed earlier, so it become difficult to solve time bounded game. This problem can be overcome by using electronics circuits.
##### Are there any drawbacks ?
- External condition affects the working of the circuits.
- Setting up the touch part of the circuit takes some time.
- It becomes difficult to debug the circuit.
- It’s difficult to write complicated algorithms using Arduino.
- Not many games can be solved because we can not implement Machine Learning to Arduino.
- Circuit required to simulate swipe becomes a bit difficult.



##### Games which can be solved using this method
“PIANO TILES” and “READY STEADY BANG” are some Android game which can be solved using this method because in these we just need to detect a particular word or a small part using sensors and then simulating touch using electronic circuits.