# Ready Steady Bang

The game has two players, one is system automated and the other is player controlled. Both the players are allowed to shoot as soon as the word **'Bang'** prompted on the screen. The objective of the game is to fire the opponent before he does by tapping anywhere on the screen immediately after the ‘BANG’ appears.

**Playstore Link:**  [Ready Steady Bang](https://play.google.com/store/apps/details?id=com.noodlecake.rsb&hl=en)

![PlayStoreImage | width=200px](/Images/BangPlaystore.png) 
![Game Image | width=200px](/Images/BangGameplay.png)

##### Difficulty Level
Moderate

##### Overview

As soon as the ‘BANG’ appears, the voltage output from the pin where the LDR is connected decreases. Whenever a drop in voltage is detected, the output pin is set to LOW and thus the Relay output is connected to ground which is equivalent to a ‘Touch’.
 



##### Requirements
* An Android Device with the ‘Ready Steady Bang’ game installed on it. (Turn on the  Developer options for better visualization)
* Arduino, Breadboard, 22k Resistor, LDR, Relay, Connecting wires, a conducting metal coin
* Computer to program Arduino
 
##### Circuit diagram using fritzing:
![image](/Images/BangFritzing.png)

##### Tutorial

**Step 1: Sensor placement**

The LDR is fixed on the screen exactly where the ‘BANG’ appears. When the ‘BANG’ appears, the intensity of the light from the screen being detected by the LDR decreases.

**Step 2: Touch simulation**

The coin is placed on the screen and the output from the relay is connected to it. When the relay output is grounded, it simulates a touch on the screen and when it is open circuited, it withdraws the touch.

**Step 3: Arduino code**

1. Initially, set the output pin HIGH.
  ```                  
digitalWrite(4,HIGH);
```
2. Read the input from the input pin, make a condition to check whether the input is less than the threshold voltage value (to be found experimentally) and check it with the condition.
 ```
int a=analogRead(A0);
       	
If (a > Threshold value)
 {
	:
    :
 }
 ```

3. Whenever it satisfies the condition: (Simulate the touch)
a. Delay the period of time for which the ‘BANG’ appears.
 ```
 delay(30);
```
b. Set the output pin to LOW- this is equivalent to a touch on the screen
 ```
digitalWrite(4,LOW);
 ```
c. Give a small delay and then un-touch the screen by setting the output pin to HIGH.
 ```
delay(500);

digitalWrite(4,HIGH);
```