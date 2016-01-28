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

After taking screenshot main part of game is cropped out. Since Target block is of almost red color.
so for specially that block, red color thresholding is performed.

```
ImBW = Im(:,:,2) < 10;
S = regionprops(ImBW,'BoundingBox','Area');

```
S.BoundingBox gives the x,y,width and height of target block.

Now to detect other blocks position other color thresholding is applied.

```
ImBW = Im(:, :, 1) > 220;
ImBW = imfill(ImBW,'holes');
S = regionprops(ImBW,'BoundingBox','Area');

for in=1:numel(S)
    if S(in).Area > 5000
        % take only those block whose Area is > 5000 since regionprops may detect small on. of rectangles. 
    end
end
```

##### Step 3: Algorithm

The algorithm uses a simple Breadth first search to find a particular order of moves to free the red block.

```
	Enqueue the current board
	while Q not empty:
    	Dequeue a board and examine it
    	can block escape?
        	he can! Ok
    	he cant?
        	for each possible board that can arise out of this one
            	add board to END of Q
```

The code is written in c++ . it takes command line string input  and return string have order of moves.
using following commands in matlab we can run c++ program.

```
%  s is input string.
cmd = 'unblock.exe ';
[status,out] = system([cmd s]);
```

##### Step 4: Using ADB Tool to simulate touch
The following command swipes from the point (x1,y1) on the screen to the point (x2, y2) . 

swapping from (x1 y1) to (x2 y2)
```
 system(['adb shell input swipe ' '' num2str(x1) ' ' num2str(y1) ' ' num2str(x2) ' ' num2str(y2) ' 100']);
```               