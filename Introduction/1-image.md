## Using Image Processing

In this approach, we use a combination of image processing and adb tool library to automate the games. 

### Approach

![image1](/Images/methods-1.jpg)

*Fig: The image depicts the block diagram of the approach using adb tool and image processing works for solving the games*

We use adb tool library to take a screenshot of the phone screen and save it on the sdcard, and then use the next command to send over the image to the computer. Next, we use a set of image processing techniques to extract relevant features in the image that are required. Depending on the features, we can simuate the toch or swipe virtually again using adb tool. 

We can run the above steps in a loop to automate a game that needs repition or has multiple levels.

##### Advantages of this approach
- We can get direct screenshots of our android phone because of which we get the accurate pixels values of the images.
- Since we access the locations on the screen through their coordinates, we get accurate touch and swipe.
- Circuits are not required.
- Complex algorithms can be implemented efficiently in MATLAB.
- Everything happening on the screen is visible to us unlike as in the case of electronic circuit which covers the screen.


##### Disadvantages of this approach

- Since ADB is taking the screenshots and sending it to laptop ,it requires some amount of time to perform that operation.Thus, its processing is slow of about some seconds.
- ADB tool takes time to set up.
- ADB tool cannot perform curved swipe.
 
### Games which can be solved using ADB tool

 An Android game Stick Hero and Find the difference can be solved using this ADB tool because the game is not time bounded and we just need to simulate virtual touch to play these game.
