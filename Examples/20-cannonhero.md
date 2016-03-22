## Cannon Hero
### Game Description
The objective  of this game is to knock the evil trooper out by precise shooting. Tap and hold to target the evil trooper, then release to shoot. Aim at the evil trooper's head to score more.One wrong aim and you die.

![CannonHero](/Images/CannonHero.png)
![CannonHero-1](/Images/CannonHero-1.png)

##### Playstore Link: [Cannon Hero](https://play.google.com/store/apps/details?id=com.orangenose.cannonhero&hl=en)
![Playstore](/Images/CannonHero_playstore.png) 


#### Difficulty level
Moderate

#### Overview
The position of the evil trooper is identified by using Image processing. The algorithm calculates the required time duration to produce the angle to hit the trooper.  

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

Once the screenshot is obtained, the coordinates of the evil trooper and hero are found out by processing the image.

##### Step 3: Algorithm

Based on the coordinates calculated in the above step, the angle of the trooper with respect to the canon hero is obtained. The corresponding duration of the touch required is calculated by multiplying the angle of troper with a constant. 

##### Step 4: Using ADB Tool to simulate touch

The long press event is simulated for the appropriate time calculated by the algorithm to achieve the required angle by using following command.
```
system(' adb shell input swipe <x1> <y1> <x2> <y2> [duration(ms)] ');
```               



