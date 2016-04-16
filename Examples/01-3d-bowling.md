## 3D  Bowling

### Game Description

In this game, the task of this player is to knock out as many pins as possible in a throw. You can throw the ball by swiping across the screen.

**Playstore Link:** [3D Bowling](https://play.google.com/store/apps/details?id=com.threed.bowling&hl=en)

![playstore image](/Images/3dbowlingps.png)
![game](/Images/3dbowlingim.png)

**Difficulty Level:** Easy

You can see a demo video of the working of this game at the following link: https://youtu.be/fvfRw3w-E4s

{% if output.name == "ebook" %}
<div class="row" style="text-align:center;">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/fvfRw3w-E4s" frameborder="0" allowfullscreen></iframe>
</div> 
{% endif %}

### Overview

It's observed that a swipe across the center of the screen is the best way to drop maximum pins.

### Requirements

- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the '3D bowling' game installed on it. (Turn on the Developer options for better visualization)
- USB data transfer cable

### Block Diagram

![image](/Images/BlockDiagram.png)

### Tutorial

Here's the step-wise tutorial to automate the game. The source code is avaiable [here](https://github.com/GameAutomators/3D-Bowling).

#### Step 1: Using ADB Tool to capture screenshot

The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.
  
```MATLAB
system('adb shell screencap -p /sdcard/screen.png');
```

The following command pulls it from the SD card of the android device into the working system following the path specified.

```MATLAB
system('adb pull /sdcard/screen.png');
```
  
The pulled image is stored in the form of a matrix of pixel values by the MATLAB.

#### Step 2: Processing the image

The pulled image is read and the two sets of coordinates are chosen such that they lie on the vertical axis that passes through the centre of the screen.
 
```MATLAB
a =  imread('screen.png');
imshow(a)
```

#### Step 3: Swipe across the screen

A swipe across the screen can be simulated by using the following command. 

```MATLAB
system('adb shell input swipe x1 y1 x2 y2');
```
where (x1,y1) and (x2,y2) are the cooridinates that were chosen.

Note: The swipe must be in the upward direction.

#### Step 4: Wait

We use a delay of 2 seconds for waiting for the animation of the swipe to be completed and ready for next throw. These two steps can be used in a loop to complete the whole game. 

```MATLAB
pause(2);
```

### Conclusions

Ideally, the algorithm should be able to win each and every time because it’s playing the best move every time. But there is a random element that has been programmed into the game because of which the ideal move doesn’t always work.

This is an inefficient way to solve the game. A better method would be to choose the swipe direction depending on the location of the balls present on the screen.