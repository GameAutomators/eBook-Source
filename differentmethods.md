# Different Methods
##### 1. Using ADB tool
Android Debug Bridge (adb) is a tool that allows the computer to communicate with   attached devices, capturing screenshots of the mobile screen, simulating virtual touches and swipes, etc., The latter two are the things that we will be using over and over again in the following tutorials that we use to solve various games.
##### Approach

![image1]()
Fig: the image depicts the workflow of algorithm for solving the games

We use adb tool to take a screenshot of the phone, and then use the next command to send over the image to the computer. Next, we use a set of image processing techniques to extract relevant features in the image that are required to solve the games. 
##### Installing ADB Tool
We need to install Java JDK or Android SDK in order to be able to use the ADB tool. Before installing either, you’ll have to install Oracle’s Java development kit. If you see a Java-related error during installation, ensure you downloaded and installed the x86 version of the JDK, not the x64 one.

##### Android SDK Setup
Once the Android SDK is downloaded and installed, launch the SDK Manager application from your Start menu.
Enable the Android SDK Platform-tools checkbox and click the Install button. This downloads and installs the platform-tools package, which contains ADB and other utilities.
![image2]()
##### Enable USB Debugging
To use ADB with your Android device, you must enable USB debugging on it. You’ll find this option under Developer Options on your device’s Settings screen.
![image3]()
While installing, specify the location where it needs to be saved.

##### Test ADB and Install Device Drivers
Locate the android-sdk’s folder. Note the SDK path displayed at the top of the SDK Manager window.
![image4]()
If you used the default install location, you’ll find ADB in the following directory:
C:\Users\NAME\AppData\Local\Android\android-sdk\platform-tools
If you used a different install location, you’ll find ADB in the platform-tools directory inside your android-sdk directory.
Browse to this directory, hold Shift and right-click inside it, and select Open command window here.
![image5]()
To test whether ADB is working properly, connect your Android device to your computer using a USB cable and run the following command:
adb devices
![image6]()
You should see a device in the list. If your device is connected but nothing appears in the list, you’ll need to install the appropriate drivers.
Your manufacturer may provide a downloadable driver package for your device. You can also try installing the Google USB Driver from the Extras folder in the SDK Manager window.
![image7]()
You may have to force Windows to use the installed drivers for your device. Open the Device Manager (click Start, type Device Manager, and press Enter), locate your device, right-click it and select Properties. You may see a yellow exclamation mark next to the device if its driver isn’t installed properly.
![image8]()
##### Basic ADB commands
Here are the commands that can be implemented using adb driver.
adb pull // used to pull the image into the working directory.
adb shell screencap //takes a screenshot of the device connected.
adb shell input tap x y // taps at the point on the screen with the co-ordinates mentioned as (x, y).
adb shell input swipe x1 y1 x2 y2 w //makes a swipe operation on the screen with the co-ordinates mentioned as (x1, y1) and (x2, y2) within w seconds.
adb shell rm //used to remove the screenshot in order to save the memory of the device connected.


##### When and why to use ADB tool?
Advantages of using ADB tool are listed below:
- We can get direct screenshots of our android phone because of which we get the accurate pixels values of the images.
- Since we access the locations on the screen through their coordinates, we get accurate touch and swipe.
- Circuits are not required.
- Complex algorithms can be implemented efficiently in MATLAB.
- Everything happening on the screen is visible to us unlike as in the case of electronic circuit which covers the screen.


##### Are there any disadvantages of ADB tool?

- Since ADB is taking the screenshots and sending it to laptop ,it requires some amount of time to perform that operation.Thus, its processing is slow of about some seconds.
- ADB tool takes time to set up.
- ADB tool cannot perform curved swipe.
 
##### Games which can be solved using ADB tool
 An Android game “STICK HERO” and “FIND THE DIFFERENCE” can be solved      using this ADB tool because the game is not time bounded and we just need to simulate virtual touch to play these game.

#2. Using Electronic Circuits
This is a way to automate the mobile game without using any internal functions of Android library by using a clever integration of electronic sensors. 

##### Approach
![image9]()
Fig. The image depicts the block diagram for a typical circuit that can solve a game

##### Touch Simulation
For this we have to understand how capacitive touch screens work. The electrodes apply a low voltage to the conductive layer creating a uniform electrostatic field. When a finger hits the screen a tiny electrical charge is transferred to the finger to complete the circuit creating a voltage drop at that point on the screen. The location of this voltage drop is recorded by the controller and this is how a capacitive touch screen works.
![image10]()
We are going to use this concept, except that in the place of a finger, we use the ground pin on the arduino to transfer the charge on the screen. To have more surface area on the display of the screen, we use a coin.
##### When should we prefer to use Electronic circuits?
Since ADB tool processing is slow as discussed earlier, so it become difficult to solve time bounded game. This problem can be overcome by using electronics circuits.
##### Are there any drawbacks ?
- External condition affects the working of the circuits.
- Setting up the touch part of the circuit takes some time.
- It becomes difficult to debug the circuit.
- It’s difficult to write complicated algorithms using Arduino.
- Not many games can be solved because we can not implement Machine Learning to Arduino.
- Circuit required to simulate swipe becomes a bit difficult.



##### Games which can be solved using this method
“PIANO TILES” and “READY STEADY BANG” are some Android game which can be solved using this method because in these we just need to detect a particular word or a small part using sensors and then simulating touch using electronic circuits. # 3. Using Electronics circuits and Image Processing
In this method we will be using the concepts of electronics and image processing together to automate the game.The Basic concepts of image processing which we are going to use is described in detail in the next chapter of this book.

##### Approach
![image11]()
Fig.The image depicts the connection between the computer,microcontroller and the phone

We use a webcam which takes the pictures of the mobile screen and sends it to MATLAB so that it can be used for the next processing step.The MATLAB algorithm processes the image according to our need and generates the duration of touch and sends it to the microcontroller(Arduino here),which in turn is used to simulate the touch on the phone screen using certain circuits.
For Example, In the game named ‘piano tiles’,our webcam will capture the image of the screen and send it to the laptop where we can separate the white and black tiles and accordingly we can send the information to the Arduino to simulate a touch on the particular area of the screen where the black tiles are present.

##### When should we prefer to use this method?
- This method is mostly used to solve more complex games for example- an  Android game “FLAPPY BIRD” .
- Faster than ADB tool .
- Debugging becomes easier.
    

##### What are the difficulties faced in this method?
- In some Android games we notice that background changes after completion of a level, so image processing for such games becomes difficult.
- Complex circuits are required.
- Since the amount of light affect the image taken by webcam, thus external conditions affects the working of the circuits.
- Setting the touch part of circuit becomes difficult.

We can enhance the efficiency of this method by using OpenCV instead of MATLAB.