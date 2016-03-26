# Playing the song

### Game Description

This is a virtual piano. It consists of an interface with piano keys that resemble a normal one. One can play notes by touching the respective keys on the interface. The aim is to play a tune/song on the virtual piano as on a live one.

**Playstore Link:** [Piano](https://play.google.com/store/apps/details?id=com.bti.myPiano)

![Playstore](/Images/pianops.png)

![Image](/Images/pianoim.png)

**Difficulty level** Moderate

### Overview

This is a virtual piano. For people who’ve got no or little experience with a live piano can play the same with ease. The notes taken from either a musical site or from a book are stored. Corresponding to these notes touches are simulated on the respective note keys. This thus results in a tune being played virtually.


### Requirements

- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the *My Piano* installed on it. (Turn on the Developer options for better visualization)
- USB data transfer cable.

### Block diagram

![Image](/Images/BlockDiagram.png)

### Tutorial
 [source code](https://github.com/GameAutomators/Piano-Player)
 
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

Once the screenshot is obtained, the points on the screen or interface will be identified corresponding to the particular note. For simplicity, generally the points taken are in the center of the piano key.

#### Step 3: Algorithm

The notes are fed to the code which will be stored and is editable. A switch statement is invoked and the algorithm loops through the stored note array or in this case matrix. The corresponding notes are thus played by simulating a touch till the loop is running.

#### Step 4: Using ADB Tool to simulate touch

The following command taps at the point on the screen with the co-ordinates mentioned as (x, y). This is used to simulate touch at the appropriate points where we want to make a move.

```MATLAB
system(' adb shell input tap x y ');
```