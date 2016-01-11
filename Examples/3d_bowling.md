# 3D  Bowling

##### Game Description
This is the best and most realistic 3D bowling game on the Android phones. It is the only bowling game that fully embraces the incredible 3D physics engine and effects.
Be the world's best player in 3D bowling game. How many consecutive strikes can you score?

**Playstore Link:** [3D Bowling](https://play.google.com/store/apps/details?id=com.threed.bowling&hl=en)
![playstore image](/Images/3dbowlingps.png)
![game](/Images/3dbowlingim.png)
           

##### Difficulty Level
Easy

##### Overview
The system’s perfect move is identified by using Image processing, the further move is calculated by the algorithm and is marked in the concerned box using ADB Tool. This continues as the algorithm tries to win the game in the best way possible

##### Requirements
 Computer with MATLAB, ADB Tool and required drivers set up.
An Android Device with the ‘3D Bowling’ game installed on it. (Turn on the Developer options for better visualization)
USB data transfer cable


##### Block Diagram
![image](/Images/BlockDiagram.png)


##### Tutorial

**Step 1: Using ADB Tool to capture screenshot**

The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.
```                       
system(' adb shell screencap -p /sdcard/screen.png ');
```
The following command pulls it from the SD card of the android device into the working system following the path specified
``` 
system(' adb pull /sdcard/screen.png ');
 ```
The pulled image is stored in the form of a matrix of pixel values by the MATLAB

**Step 2: Image processing**
Once the screenshot is obtained, the centre point of the ball and the centre of the lane and these are taken as an input to the command and system has to make a simple swipe.
**Step 3: Using ADB Tool to simulate swipe**
The following command . makes a swipe operation on the screen with the co-ordinates mentioned as (x1, y1) and (x2, y2)This is used to simulate swipe at the appropriate points where we want to make a swipe.
```                          	
system(' adb shell input swipe x1 y1 x2 y2 ');
```
Ideally, the algorithm should be able to win each and every time because it’s playing the best move every time. But there is a random element that has been programmed into the game because of which the ideal move doesn’t always work.