## Using Electronics

This is a way to automate the mobile games by using clever electronic circuitry placed on top of your phone. 

### Approach

![image9](/Images/methods-2.jpg)

*Fig. The image depicts the block diagram for a typical electronic circuit that can solve a game on the mobile*

The microcontroller senses the inputs from a sensor that is used to detect what's on the screen, analyses the data using a logic that has been programmed into it and sends appropriate commands to the touch circuitry. 

Refer to the *Electronics* chapter in the book to learn in detail about how the sensing and touching circuits work.

### Advantages of this approach

- Since ADB tool processing is slow as discussed earlier, it becomes difficult to solve time bounded game. This problem can be overcome by using electronic circuits.

### Disadvantages of this approach

- External conditions such an ambient light might affect the working of the circuits.
- Setting up the touch part of the circuit takes some time.
- It's difficult to implement complex algorithms on Arduino.
- Circuit required to simulate swipe is complicated and involves mechanical parts.

### Games which can be solved using this method

'Piano Tiles' and 'Ready Steady Bang' can be solved using this method because in these we just need to detect a intensity change on a small part of the screen using sensors and then simulate touch using electronic circuits.