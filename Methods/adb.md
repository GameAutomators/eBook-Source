 
# Using ADB tool
Android Debug Bridge (adb) is a tool that allows the computer to communicate with   attached devices, capturing screenshots of the mobile screen, simulating virtual touches and swipes, etc., The latter two are the things that we will be using over and over again in the following tutorials that we use to solve various games.

### Approach

![image1](/Images/methods-2.jpg)

*Fig: the image depicts the workflow of algorithm for solving the games*

We use adb tool to take a screenshot of the phone, and then use the next command to send over the image to the computer. Next, we use a set of image processing techniques to extract relevant features in the image that are required to solve the games. 

### Installing ADB Tool
We need to install Java JDK or Android SDK in order to be able to use the ADB tool. Before installing either, you'll have to install Oracle's Java development kit. If you see a Java-related error during installation, ensure you downloaded and installed the x86 version of the JDK, not the x64 one.

##### Android SDK Setup
Once the Android SDK is downloaded and installed, launch the SDK Manager application from your Start menu.
Enable the Android SDK Platform-tools checkbox and click the Install button. This downloads and installs the platform-tools package, which contains ADB and other utilities.


##### Enable USB Debugging
To use ADB with your Android device, you must enable USB debugging on it. You'll find this option under Developer Options on your device's Settings screen.

While installing, specify the location where it needs to be saved.

##### Test ADB and Install Device Drivers
Locate the android-sdk's folder. Note the SDK path displayed at the top of the SDK Manager window.

If you used the default install location, you'll find ADB in the following directory:
C:\Users\NAME\AppData\Local\Android\android-sdk\platform-tools
If you used a different install location, you'll find ADB in the platform-tools directory inside your android-sdk directory. Browse to this directory, hold Shift and right-click inside it, and select Open command window here.

To test whether ADB is working properly, connect your Android device to your computer using a USB cable and run the following command:
```MATLAB
adb devices
```

You should see a device in the list. If your device is connected but nothing appears in the list, you'll need to install the appropriate drivers.
Your manufacturer may provide a downloadable driver package for your device. You can also try installing the Google USB Driver from the Extras folder in the SDK Manager window.

You may have to force Windows to use the installed drivers for your device. Open the Device Manager (click Start, type Device Manager, and press Enter), locate your device, right-click it and select Properties. You may see a yellow exclamation mark next to the device if its driver isn't installed properly.

##### Basic ADB commands
Here are the commands that can be implemented using adb driver.
```MATLAB
// used to pull the image into the working directory
adb pull 

//takes a screenshot of the device connected
adb shell screencap 

// taps at the point on the screen with the co-ordinates mentioned as (x, y).
adb shell input tap x y

//makes a swipe operation on the screen with the co-ordinates mentioned as (x1, y1) and (x2, y2) within w seconds
adb shell input swipe x1 y1 x2 y2 w

//used to remove the screenshot in order to save the memory of the device connected
adb shell rm 
```


### When and why to use ADB tool?
#####Advantages of using ADB tool
- We can get direct screenshots of our android phone because of which we get the accurate pixels values of the images.
- Since we access the locations on the screen through their coordinates, we get accurate touch and swipe.
- Circuits are not required.
- Complex algorithms can be implemented efficiently in MATLAB.
- Everything happening on the screen is visible to us unlike as in the case of electronic circuit which covers the screen.


##### Disadvantages of ADB tool?

- Since ADB is taking the screenshots and sending it to laptop ,it requires some amount of time to perform that operation.Thus, its processing is slow of about some seconds.
- ADB tool takes time to set up.
- ADB tool cannot perform curved swipe.
 
### Games which can be solved using ADB tool

 An Android game Stick Hero and Find the difference can be solved using this ADB tool because the game is not time bounded and we just need to simulate virtual touch to play these game.
