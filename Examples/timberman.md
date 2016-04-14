# Timberman

**Playstore Link:**  [Timberman](https://play.google.com/store/apps/details?id=com.dm.timber&hl=en)

##### About the game:
Timberman is an oldschool arcade style casual game. You have to put on your checkered shirt, pull up your sleeves, pick up the sharpened ax and ... grow a beard. In a moment there will be splinters flying and knocks off ax will bear echoed through the forest. Show how quick and how efficiently you can cut down a hundred-meter tall pine tree. But be careful, work of a lumberjack is tough and it's not hard for the accident at work. In addition, time is chasing you in every step not giving even a moment to rest. 

##### Difficulty Level : 
Easy

##### Overview
As soon as the timber branch appears above the timberman, the voltage output from the pin where the LDR is connected decreases. Whenever a drop in voltage is detected, the output pin is set to LOW and thus the Relay output is connected to ground which is equivalent to a 'Touch' on the other side of the side bearing lumberjack. In the absence of branch overhead, repeated touch is simulated on the same side of lumberjack.

##### Requirements
* An Android Device with the 'Timberman’' game installed on it. (Turn on the Developer options for better visualization)
* Arduino, Breadboard, 22k Resistor X 2, LDR, Relay X 2, Connecting wires, two conducting metal coin
* Computer to program Arduino

##### Block Diagram

##### Circuit Diagram


##### Tutorial
Here's the step-wise tutorial to automate the game.

**Step 1: Sensor placement**

The LDR is fixed on the screen exactly above the head of the wood-cutter on the left side. When the branch appears, the intensity of the light from the screen being detected by the LDR decreases.

**Step 2: Touch simulation**

The coin is placed on the screen and the output from the relay is connected to it. When the relay output is grounded, it simulates a touch on the screen and when it is open circuited, it withdraws the touch.

**Step 3: Arduino code**

Initially, set the output pins
```
int left=4,right=5;  
```
```
void loop() {
   int sv = analogRead(A0);  //read the input on analog pin A0
   Serial.println(sv);  //print out the value you read:
  //When a branch is encountered, right tap two times (until then, the branch      disappears)   
   if(sv<750)  //threshold value=750
   {
       digitalWrite(right, HIGH);  //simulate no touch
       delay(700); 
       digitalWrite(right, LOW);   //simulate touch
       delay(700);
       digitalWrite(right, HIGH);   //simulate no touch
       delay(700); 
       digitalWrite(right, LOW);   //simulate touch
       delay(700);
   }
   else   //otherwise keep tapping left
   {
       digitalWrite(left, HIGH); // simulate no touch
       delay(300); 
       digitalWrite(left, LOW); // simulate touch
       delay(300);
   }
   // delay(100);        // delay in between reads for stability
}

##### Conclusions

This way, the the circuit plays the game for us. Because the reaction time of the circuit is very fast, it can make highscores!



