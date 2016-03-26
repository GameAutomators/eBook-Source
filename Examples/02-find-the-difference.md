# Find the differences

### Game Description

The game has two images with ten minute differences separated horizontally. The aim of the player is to find the ten differences and tap on all of them to reach the next level. 

**Playstore link**: [Find the  Differences](https://play.google.com/store/apps/details?id=com.ivanovandapps.ftdiaa3&hl=en)

![playstoreFTD](/Images/ftdps.png) 
![game](/Images/ftdim.png)

**Difficulty Level:** Moderate

You can see a demo video of the working of this game at the following link: https://youtu.be/vOTyJVKrqfk

<div class="row" style="text-align:center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/vOTyJVKrqfk" frameborder="0" allowfullscreen></iframe>
</div> 

### Overview

The image is divided into two parts and the differences are detected by using the image processing. The differences are made significant using an image enhancement and the final ten differences are obtained. Then ADB Tool library is used to simulate the touch on the found differences.

### Requirements

- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the 'Find the Differences' game installed on it. (Turn on the Developer options for better visualization)
- USB data transfer cable

### Block diagram

![blockdiagram](/Images/BlockDiagram.png)

### Tutorial

Here's the step-wise tutorial to automate the game.

#### Step 1: Using ADB Tool to capture screenshot

The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.
  
```MATLAB
system('adb shell screencap -p /sdcard/screen.png');
```

The following command pulls it from the SD card of the android device into the working system following the path specified.

```MATLAB
system('adb pull /sdcard/screen.png');
```
  
The pulled image is stored in the form of a matrix of pixel values by the MATLAB.

#### Step 2: Image processing and enhancement

Both the images are separated and stored in two different matrices. The matrices are subtracted to get the difference matrix.

The difference matrix is converted into a binary image and the differences are made more significant by increasing the size of the differences by dilation. The centroids of the ten differences are found.


#### Step 3: Using ADB Tool to simulate touch

The following command taps at the point on the screen with the co-ordinates mentioned as (x, y). This is used to simulate touch at the centroid of the differences.

```MATLAB
system('adb shell input tap x y');
```

### Conclusions

This way, the computer solves the game very quickly, the speed at which humans can only dream off. This algorithm is robust and work for a few other find the difference games on the play store.