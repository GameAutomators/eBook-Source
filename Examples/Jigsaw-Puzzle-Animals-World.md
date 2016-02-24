# Animals World Jigsaw Puzzle
### Game Description
In this game an image of animal is shown which then gets divided into number of parts depending upon the difficult level and parts are jumbled. The player then need to rearrange the jumbled parts to form the original image again.


Playstore Link: [Animals World Jigsaw Puzzle] 
(https://play.google.com/store/apps/details?id=com.violetrose.puzzle.drag.animals&hl=en)

![Playstore](/Images/jigsaw_p.png) 
![Image](/Images/jigsaw_o.png)


#### Difficulty level
Moderate

#### Overview
First we divide the image into n X n parts and store each part in matrices namely a1, a2….an .Then we crop the jumbled image and store them in other matrices namely b1,b2,…bn. Then a comparison is done between the matrices and found which two are same, and then they are swiped accordingly.
#### Requirements
- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the ‘Bowling 3D’ game installed on it. (Turn on the Developer options for better visualization)
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
 Then image is cropped into number of parts like a1,a2,a3…an, depending upon the difficulty level.
##### Step 2: Comparison of each subparts
A loop is run to take the snapshot of jumbled image and it is divided into same number of parts lke b1,b2,b3…bn. Then each ak where 1<k<=n is compared with all the bjs ge , whenever there is similarity its index is stored in the variable id.

##### Step 3:Moving each part to appropriate position
Then parts(bjs) are moved to their appropriate position.

