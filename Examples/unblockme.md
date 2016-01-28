# Unblockme


### Game Description
This is a single player game. The goal is to unblock the red block out of the board by sliding the other blocks out of the way, unblock it with the minimal moves.


Playstore Link: [Unblockme](https://play.google.com/store/apps/details?id=com.kiragames.unblockmefree)

![Playstore](/Images/playstore_unblockme.png) 

![Image](/Images/unblock.png)

#### Difficulty level
Moderate

#### Overview
First , using Image Processing all the blocks allignment and position is detected using image processing in MATLAB .  Using algorithm  game is solved and blocks are moved to free  the red block.


#### Requirements
- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the ‘Sudoku’ game installed on it. (Turn on the Developer options for better visualization)
- USB data transfer cable.

#### Block Diagram

![BlockDiagram](/Images/BlockDiagram.png)

#### Tutorial
##### Step 1: Using ADB Tool to capture screenshot
The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.
  
  ```                     
system(' adb shell screencap -p /sdcard/screen.png ');
```       

The following command pulls it from the SD card of the android device into the working system following the path specified

```
system(' adb pull /sdcard/screen.png ');
  ```
  
The pulled image is stored in the form of a matrix of pixel values by the MATLAB.
                
                
##### Step 2: Image processing

Once the screenshot is obtained, allignment and position of blocks are detected and are numbered differnetly.
after this step a 6x6 matrix is been returned in which position of all the blocks is stored.

##### Step 3: Algorithm

The algorithm uses a simple Breadth first search to find a particular order of moves to free the red block
The code is written in c++ . it takes command line string input  and return string have order of moves.
 using following commands in matlab we can run c++ program.
```
%  s is input string.
cmd = 'sudoku.exe ';
[status,out] = system([cmd s]);
```

##### Step 4: Using ADB Tool to simulate touch
The following command swipes from the point (x1,y1) on the screen to the point (x2, y2) . 

swapping from (x1 y1) to (x2 y2)
```
 system(['adb shell input swipe ' '' num2str(x1) ' ' num2str(y1) ' ' num2str(x2) ' ' num2str(y2) ' 100']);
```               