## 3D  Bowling

### Game Description

In this game, the task of this player is to knock out as many balls as possible in a throw. You can throw the ball by swiping across the screen.

**Playstore Link:** [3D Bowling](https://play.google.com/store/apps/details?id=com.threed.bowling&hl=en)

![playstore image](/Images/3dbowlingps.png)
![game](/Images/3dbowlingim.png)

**Difficulty Level:** Easy

### Overview

The system's optimal move is identified by just trial and error. It's observed that a swipe across the center of the screen is the best way to drop many pins.

### Requirements

Computer with MATLAB, ADB Tool and required drivers set up.
An Android Device with the '3D Bowling' game installed on it. (Turn on the Developer options for better visualization)
USB data transfer cable

### Block Diagram
![image](/Images/BlockDiagram.png)


### Tutorial

**Step 1: Swipe across the screen**

**Step 2: Wait**

The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.

```MATLAB                      
system(' adb shell screencap -p /sdcard/screen.png ');
```

The following command pulls it from the SD card of the android device into the working system following the path specified
```MATLAB
system(' adb pull /sdcard/screen.png ');
 ```

The pulled image is stored in the form of a matrix of pixel values by the MATLAB

**Step 2: Image processing**
Once the screenshot is obtained, the centre point of the ball and the centre of the lane and these are taken as an input to the command and system has to make a simple swipe.

**Step 3: Using ADB Tool to simulate swipe**
The following command . makes a swipe operation on the screen with the co-ordinates mentioned as (x1, y1) and (x2, y2)This is used to simulate swipe at the appropriate points where we want to make a swipe.
```MATLAB
system(' adb shell input swipe x1 y1 x2 y2 ');
```

Ideally, the algorithm should be able to win each and every time because it’s playing the best move every time. But there is a random element that has been programmed into the game because of which the ideal move doesn’t always work.