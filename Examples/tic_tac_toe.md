# Tic Tac Toe


### Game Description
This is a two-player game. The player and the system get alternative chances to mark their move on the 3x3 grid provided. One who marks 3 linearly oriented squares first, wins the game. If none of the players can do this, the game ends to be a draw. (The system’s move is marked with a circle and the player’s with a cross)

Playstore Link: [Tic Tac Toe](https://play.google.com/store/apps/details?id=com.pinkpointer.tictactoe&hl=en)

#### Difficulty level
Moderate.

#### Overview
The player starts at a point. The system’s move is identified using Image processing, the further move is calculated by the algorithm and is marked in the concerned box using ADB Tool. This continues as the algorithm tries to win the game in the best way possible


#### Requirements
- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the ‘Tic Tac Toe’ game installed on it. (Turn on the Developer options for better visualization)
- USB data transfer cable.

#### Block Diagram


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

Once the screenshot is obtained, nine different points in the 9 boxes are chosen and checked for the appearance of circle. The box where a circle is detected is identified to be the system’s move and is given as input to the algorithm

##### Step 3: Algorithm

The algorithm checks all the possible ways, chooses the most favourable move and returns it. Then, that box is tapped on (touched) using the ADB Tool.

##### Step 4: Using ADB Tool to simulate touch
The following command taps at the point on the screen with the co-ordinates mentioned as (x, y). This is used to simulate touch at the appropriate points where we want to make a move.

```
system(' adb shell input tap x y ');
```               
