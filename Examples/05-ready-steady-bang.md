# Ready Steady Bang

### Game Description

The game has two players, one is system and the other is player controlled. Both the players are allowed to shoot as soon as the word 'BANG' pops on the screen. The objective of the game is to fire the opponent before he does by tapping anywhere on the screen immediately after the 'BANG' appears.

**Playstore Link:**  [Ready Steady Bang](https://play.google.com/store/apps/details?id=com.noodlecake.rsb&hl=en)

<!-- Some Bootstrap segments are needed for front end because of markdown limitations-->
<div class="row" style="text-align:center;">
	<img src="/Images/BangPlaystore.png" alt="Play Store Image" height="500px"> 
	<img src="/Images/BangGameplay.png" alt="Game Play Image" height="500px">
</div>
<!-- End Bootstrap segment -->

**Difficulty Level:** Moderate

You can see a demo video of the working of this game at the following link: https://youtu.be/riNjidXmOY4

<div class="row" style="text-align:center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/riNjidXmOY4" frameborder="0" allowfullscreen></iframe>
</div> 

### Overview

As soon as the word 'BANG' appears, the voltage output from the pin where the LDR is connected decreases. Whenever a drop in voltage is detected, the output pin is set to LOW and thus the Relay output is connected to ground which is equivalent to a 'Touch'.

### Requirements

- An Android Device with the 'Ready Steady Bang' game installed on it. (Turn on the  Developer options for better visualization)
- Arduino, Breadboard, 22k Resistor, LDR, Relay, Connecting wires, a conducting metal coin
- Computer to program Arduino
 
### Block Diagram

![BlockDiagram](/Images/methods-2.jpg)

### Circuit diagram using fritzing

![BlockDiagram](/Images/BangFritzing.png)

### Tutorial

Here's the step-wise tutorial to automate the game. The source code is avaiable [here](https://github.com/GameAutomators/Bang).

#### Step 1: Sensor placement

The LDR is fixed on the screen exactly where the 'BANG' appears. When the 'BANG' appears, the intensity of the light from the screen being detected by the LDR decreases.

#### Step 2: Touch simulation

The coin is placed on the screen and the output from the relay is connected to it. When the relay output is grounded, it simulates a touch on the screen and when it is open circuited, it withdraws the touch.

#### Step 3: Arduino code

Initially, set the output pin HIGH.

```C
digitalWrite(4,HIGH);
```

Read the input from the input pin, make a condition to check whether the input is less than the threshold voltage value (to be found experimentally) and check it with the condition.

```C
int a=analogRead(A0);
if (a > Threshold value)
{
	:
	:
}
```

Whenever it satisfies the condition: (Simulate the touch)

a. Delay the period of time for which the 'BANG' appears.

```C
delay(30);
```

Set the output pin to LOW- this is equivalent to a touch on the screen.

```C
digitalWrite(4,LOW);
```

Give a small delay and then un-touch the screen by setting the output pin to HIGH.

```C
delay(500);
digitalWrite(4,HIGH);
```

### Conclusions

This way, the the circuit plays the game for us. Because the reaction time of the circuit is very fast, it beats the computer easily.