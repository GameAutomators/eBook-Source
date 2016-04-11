## Rainbow Tiles

### Game Description

This is an endless runner game. You have 30 seconds to run as far as you can - the further you go the higher you score. Watch out where you step and avoid white blocks. 

![rainbowtiles1](/Images/rainbowtiles1.png)
![rainbowtiles2](/Images/rainbowtiles2.png)

**Playstore Link:** [RainbowTiles](https://play.google.com/store/apps/details?id=com.crimsonpine.dontstep&hl=en)

![Playstore](/Images/rainbowtiles_playstore.png) 

**Difficulty level:** Moderate

### Overview

The position of the tiles is identified by using Image processing, further move is calculated by the algorithm and touch is simulated on the concerned tile. 

### Requirements

- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the 'RainbowTiles' game installed on it. (Turn on the Developer options for better visualization)
- USB data transfer cable.


### Block Diagram

![BlockDiagram](/Images/BlockDiagram.png)

### Tutorial

Here's the step-wise tutorial to automate the game. The source code is avaiable [here](https://github.com/GameAutomators/rainbow-tiles).

#### Step 1: Using ADB Tool to capture screenshot

The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.
  
 ```MATLAB                    
system(' adb shell screencap -p /sdcard/screen.png ');
```       

The following command pulls it from the SD card of the android device into the working system following the path specified.

```MATLAB
system(' adb pull /sdcard/screen.png ');
  ```
  
The pulled image is stored in the form of a matrix of pixel values by the MATLAB.
                
                
#### Step 2: Image processing

The position of the tiles is identified and an algorithm is used to identify the tile to be touched. 

#### Step 4: Using ADB Tool to simulate touch

The following command taps at the point on the screen with the co-ordinates mentioned as (x, y) . This is used to simulate touch at the appropriate points.

```MATLAB
system(' adb shell input tap x y ');
```