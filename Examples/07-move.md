# Move: A Brain Shifting Puzzle

### Game Description

![image1](/Images/move1.jpg) 
![Image2](move2)
![Image3](move3)

**Playstore link:** [Move: A Brain Shifting Puzzle](https://play.google.com/store/apps/details?id=com.nitako.move)

***Difficulty Level** Medium

### Overview

Using image processing the position of the dots,blocks and the squares is identified. The algorithm finds a solution for each level and moves are simulated using adb tool.

### Requirements

* Computer with MATLAB, ADB Tool and required drivers set up.
* An Android Device with the ‘Move’ installed on it. (Turn on the Developer options for better visualization)
* USB data transfer cable.

### blockdiagram

![BlockDiagram](/Images/BlockDiagram.png)

### Tutorial

#### Step 1: Using ADB Tool to capture screenshot

The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.

```MATLAB
system(' adb shell screencap -p /sdcard/screen.png ');
```

The following command pulls it from the SD card of the android device into the working system following the path specified.

```MATLAB
system(' adb pull /sdcard/screen.png ');
```

The pulled image is stored in the form of a matrix of pixel values by the MATLAB using this command.

```MATLAB
imread('screen.png')
```

#### Step 2: Image processing
Once the screenshot is obtained, the position of the dots, blocks and the squares is identifies and also the minimum number of moves required to solve the level is extracted. For conenience each color is assigned an integer. This information is then fed to the algorithm with finds the solution.

#### Step 3: Algorithm
The algorithm tries out all permutations and combination of moves possible to get to the right one.

#### Step 4: Using ADB Tool to simulate touch

The following command swipes on the screen from the co-ordinates mentioned as (x1, y1) to (x2,y2)
, to make a move. This can also be used to simulate touch at the appropriate points.

```MATLAB
system(' adb shell input swipe x1 y1 x2 y2');
```