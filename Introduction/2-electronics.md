## Using Electronics

This is a way to automate the mobile game without using any internal functions of Android library by using clever electronic circuitry placed on top of your phone. 

### Approach

![image9](/Images/methods-2.jpg)

*Fig. The image depicts the block diagram for a typical electronic circuit that can solve a game on the mobile*

The microcontroller senses the inputs from a sensor that is used to detect what's on the screen, analyses the data using a logic that has been programmed into it and sends appropriate commands to the touch circuitry. 

Refer to the electronics chapter in the book to learn in detail about who the sensing and touching circuits work.

### Advantages
- Since ADB tool processing is slow as discussed earlier, so it become difficult to solve time bounded game. This problem can be overcome by using electronics circuits.

### Disadvantages
- External condition affects the working of the circuits.
- Setting up the touch part of the circuit takes some time.
- It becomes difficult to debug the circuit.
- It's difficult to write complicated algorithms using Arduino.
- Not many games can be solved because we can not implement Machine Learning to Arduino.
- Circuit required to simulate swipe becomes a bit difficult.

### Games which can be solved using this method
Piano Tiles and Ready Steady Bang are some Android game which can be solved using this method because in these we just need to detect a particular word or a small part using sensors and then simulating touch using electronic circuits.