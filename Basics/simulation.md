# Touch Simulation
Simulating touch is one of the critical parts of any game. There are multiple ways in which we can simulating the touch. 

## Mechanical
The touch can be simulated by a mechanical system consisting of a stylus connected to servo motor. The stylus must be connected to the servo in such a way that when the servo rotates, the stylus hits the screen. 

But the problem with this method is that it is relatively slow. It is constrained by the speed of servo movement. To overcome this problem, we can use one of the following two ways.


## Using Relay

This and the next method can only work on capacitive touch screens. For this we have to understand how they work. The electrodes apply a low voltage to the conductive layer creating a uniform electrostatic field. When a finger hits the screen a tiny electrical charge is transferred to the finger to complete the circuit creating a voltage drop at that point on the screen. The location of this voltage drop is recorded by the controller.

![Capacitive Touch Screen](/Images/CapactiveTouchScreen.png)

We are going to use this concept, except that in the place of a finger, we use the ground pin on the arduino to transfer the charge on the screen. To have more surface area on the display of the screen, we use a coin. Relays are directly connected to the output pin of the Arduino. As shown in the figure, it is equivalent to a touch if the voltage given is high as there is a path for the current to flow to the ground. It is equivalent to not touching, if the voltage given is low.

![Relay when no touch](/Images/RelayInternals1.png)
![Relay with touch](/Images/RelayInternals2.png)

## Using Transistors

This method can work faster than a relay too. You have to use a transistor in place of a relay for switching between open circuit and ground.
