## 3D  Bowling

### Game Description

In this game, the task of this player is to knock out as many balls as possible in a throw. You can throw the ball by swiping across the screen.

**Playstore Link:** [3D Bowling](https://play.google.com/store/apps/details?id=com.threed.bowling&hl=en)

![playstore image](/Images/3dbowlingps.png)
![game](/Images/3dbowlingim.png)

**Difficulty Level:** Easy

You can see a demo video of the working of this game at the following link: https://youtu.be/fvfRw3w-E4s

<div class="row" style="text-align:center;">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/fvfRw3w-E4s" frameborder="0" allowfullscreen></iframe>
</div> 

### Overview

The system's optimal move is identified by just trial and error. It's observed that a swipe across the center of the screen is the best way to drop many pins.

### Requirements

- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the '3D bowling' game installed on it. (Turn on the Developer options for better visualization)
- USB data transfer cable

### Block Diagram

![image](/Images/BlockDiagram.png)

Please note that only the step 3 in the block diagram is being used for solving this game.

### Tutorial

Here's the step-wise tutorial to automate the game.

#### Step 1: Swipe across the screen

A swipe across the screen can be simulated by using the following command. Notice that the numbers for swipe could change depending on the screen resolution of the phone that you are using. These numbers are for a phone with resolution 720x1280.

```MATLAB
system('adb shell input swipe 360 1008 360 550');
```

#### Step 2: Wait

We use a delay of 2 seconds for waiting for the animation of the swipe to be completed and ready for next throw. These two steps can be used in a loop to complete the whole game. 

```MATLAB
pause(2);
```

### Conclusions

Ideally, the algorithm should be able to win each and every time because it’s playing the best move every time. But there is a random element that has been programmed into the game because of which the ideal move doesn’t always work.

This is an inefficient way to solve the game. A better method would be to choose the swipe direction depending on the location of the balls present on the screen.