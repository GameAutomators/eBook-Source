## Using Image Processing

In this approach, we use image processing and adb tool to automate the games. 

### Approach

![image1](/Images/methods-1.png)

*Fig: The image depicts the block diagram of the approach using adb tool and image processing for solving the games*

We use adb tool to take a screenshot of the phone screen and send over the image to the computer. Next, we use a set of image processing techniques to extract relevant features in the image. Depending on the features, we can simuate the touch or swipe virtually on the phone using adb tool. 

We can run the above steps in a loop to automate a game that needs repetition or has multiple levels.

### Advantages of this approach

- We can get direct screenshots of the phone screen; hence the pixel values are reflected perfectly. So no preprocessing is required for the image.
- Since we can simulate precise touches and swipes.
- Complex algorithms can be implemented easily in case you are using MATLAB.
- Everything happening on the screen is visible to us unlike in the case of electronic circuits where the screen could be covered with the sensors or touch simulation circuitry.

### Disadvantages of this approach

- The transfer of the screenshots to laptop, and simulating the touch takes about half a second. This is very slow if we are working on real time games that need quick response.
 
### Games which can be solved

The Android games 'Stick Hero' and 'Find the Difference' can be solved using this approach because the games are not time bounded and tap on the screen is good enough to play these games.
