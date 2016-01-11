# Find the differences

### Game Description
###### The game has two images with ten minute differences separated horizontally. The aim of the player is to find the ten differences and tap on all of them to reach the next level. 

**Playstore link**:[ Find the  Differences](https://play.google.com/store/apps/details?id=com.ivanovandapps.ftdiaa3&hl=en)

![playstoreFTD](/Images/ftdps.png) 

![game](/Images/ftdim.png)

### Difficulty Level
###### Difficult

### Overview
###### Initially, the image is divided into two parts and are checked for differences by using the Image processing technique. The differences are made significant using an algorithm and the final ten differences are obtained. The ADB Tool is used to tap (touch) on the found differences.

### Requirements
 * Computer with MATLAB, ADB Tool and required drivers set up.
* An Android Device with the ‘My Piano’ installed on it. (Turn on the Developer options for better visualization)
* USB data transfer cable

### Block diagram

![blockdiagram](/Images/BlockDiagram.png)

### Tutorial
##### Step 1: Using ADB Tool to capture screenshot
 The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.   

 ```
system(' adb shell screencap -p /sdcard/screen.png ');
 ```

 The following command pulls it from the SD card of the android device into the working system following the path specified

```
system(' adb pull /sdcard/screen.png ');
 ```
 The pulled image is stored in the form of a matrix of pixel values by the MATLAB
##### Step 2: Image processing
Both the images are separated and stored in two different matrices. The matrices are subtracted to get the difference matrix.


##### Step 3: Algorithm
The difference matrix is converted into a binary image and the differences are made more significant by increasing the size of the differences. The centroids of the ten differences are found.


##### Step 4: Using ADB Tool to simulate touch
The following command taps at the point on the screen with the co-ordinates mentioned as (x, y). This is used to simulate touch at the centroid of the differences.

```
system(' adb shell input tap x y ');
```
