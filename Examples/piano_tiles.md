# Piano Tiles

The game consists of tapping on the black tiles only.One need to see where are the black tiles moving and tapping on it as per the requirements.

##### Playstore Link: [Piano Tiles](https://play.google.com/store/apps/details?id=com.umonistudio.tile&hl=en)

 [Image] 
 
#### Difficulty Level:
Moderate
#### Overview
- Sensing color of the tile (Black or White)
- Processing the color information and generating timing  for the touch (Arduino)
- Simulating capacitive touch (Relays)


#### Requirements
- An Android Device with the ‘Piano Tiles’ game
- Arduino, Breadboard, 22k Resistor, LDR, Relay, Connecting wires, a conducting metal coin
- Computer to program Arduino

#### Circuit Diagram:


#### Tutorial:
##### Sensing:
We use light dependent resistors (LDRs) to sense if the tiles are white or black.  Four LDRs are positioned over the screen each facing one tile. The LDRs have been connected to the back of the cardboard like this.

The LDR resistance changes with the intensity of Light. Higher the intensity of light, lesser the resistance. LDR is placed in a Voltage divider circuit to produce a voltage proportional to its resistance.The LDRs are connected to the analog input pins of the Arduino as shown.

Practically, this is how you would connect the circuit. You can check the [test_ldr code](https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/test_ldr/test_ldr.ino) to see if the LDRs are working fine. When you run the code, you will get a high value from the LDR if it’s sensing black, else you get a low value.



##### Processing:
Arduino reads the voltage drop across the LDR. Observe the voltage voltages for Black and White tiles, choose a suitable threshold voltage say Vt.  If  (V<Vt) larger the drop across LDR, larger the resistance, which implies a Black tile and vice versa. If found 
Run the [test_relay code](https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/test_touch/test_touch.ino) at this link to see if the electronic touch is simulated properly.
tile is a Black one simulate touch corresponding to that tile. 

##### Touching:
For this we have to understand how capacitive touch screens work. The electrodes apply a low voltage to the conductive layer creating a uniform electrostatic field. When a finger hits the screen a tiny electrical charge is transferred to the finger to complete the circuit creating a voltage drop at that point on the screen. The location of this voltage drop is recorded by the controller and this is how a capacitive touch screen works.

We are going to use this concept, except that in the place of a finger, we use the ground pin on the arduino to transfer the charge on the screen. To have more surface area on the display of the screen, we use a coin.

Relays are directly connected to the output pin of the Arduino. It is equivalent to a touch if the voltage given is high as there is a path for the current to flow to the ground. It is equivalent to not touching if the voltage given is low.

##### Finishing Touch:
Once you the connect the circuit and dump the code [main.ino](https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/main/main.ino) at this link, your circuit should start working. If not, it is because the delays are not adjusted perfectly. Tweak the delay values in the code and it should work.

And you built a circuit that can play Piano Tiles better than any human in the world.


On Tue, Jan 5, 2016 at 10:57 PM, Barai Aarti Deepnarayan <abarai@student.nitw.ac.in> wrote:
# Piano Tiles

Ever wondered if your phone can play games by itself. Yes, it is possible. You can build a circuit to play Piano tiles on your smartphone

And the circuit can be built with simple components like Light sensors, Relays and Arduino

#### Three main functions of the circuit are :
- Sensing color of the tile (Black or White)
-  Processing the color information and generating timing  for the touch (Arduino)
- Simulating capacitive touch (Relays)

#### Building the circuit:
##### Sensing:
We use light dependent resistors (LDRs) to sense if the tiles are white or black.  Four LDRs are positioned over the screen each facing one tile. The LDRs have been connected to the back of the cardboard like this.

The LDR resistance changes with the intensity of Light. Higher the intensity of light, lesser the resistance. LDR is placed in a Voltage divider circuit to produce a voltage proportional to its resistance.The LDRs are connected to the analog input pins of the Arduino as shown.

Practically, this is how you would connect the circuit. You can check the [test_ldr code](https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/test_ldr/test_ldr.ino) to see if the LDRs are working fine. When you run the code, you will get a high value from the LDR if it’s sensing black, else you get a low value.



##### Processing:
Arduino reads the voltage drop across the LDR. Observe the voltage voltages for Black and White tiles, choose a suitable threshold voltage say Vt.  If  (V<Vt) larger the drop across LDR, larger the resistance, which implies a Black tile and vice versa. If found
tile is a Black one simulate touch corresponding to that tile. 

##### Touching:
For this we have to understand how capacitive touch screens work. The electrodes apply a low voltage to the conductive layer creating a uniform electrostatic field. When a finger hits the screen a tiny electrical charge is transferred to the finger to complete the circuit creating a voltage drop at that point on the screen. The location of this voltage drop is recorded by the controller and this is how a capacitive touch screen works.

We are going to use this concept, except that in the place of a finger, we use the ground pin on the arduino to transfer the charge on the screen. To have more surface area on the display of the screen, we use a coin.

Relays are directly connected to the output pin of the Arduino. It is equivalent to a touch if the voltage given is high as there is a path for the current to flow to the ground. It is equivalent to not touching if the voltage given is low.

Relays are directly connected to the output pin of the Arduino. It is equivalent to a touch if the voltage given is high as there is a path for the current to flow to the ground. It is equivalent to not touching if the voltage given is low.

##### Finishing Touch:
Once you the connect the circuit and dump the code [main.ino](https://github.com/psurya1994/arduino-plays-piano-tiles/blob/master/Code/main/main.ino) at this link, your circuit should start working. If not, it is because the delays are not adjusted perfectly. Tweak the delay values in the code and it should work.

And you built a circuit that can play Piano Tiles better than any human in the world!!

##### [Source code and Schematics](https://github.com/psurya1994/arduino-plays-piano-tiles)
