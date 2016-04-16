## Using Electronics and Image Processing

In this method we will be using the concepts of electronics and image processing together to automate the game. This helps us get over the problem we had which Approach 1 that it's slow. The concepts of image processing and electronics which we are going to use here is discussed in the following chapters.

### Approach

![image11](/Images/methods-3.png)

*Fig.The image depicts the connection between the computer, microcontroller and the phone for game automation*

We use a webcam which streams the video of the mobile screen into the computer that performs image processing to extract relevant features, generates the duration of touch and sends it to the microcontroller which is used to simulate the touch on the phone screen using electronic circuitry. Recognize that we are not using adb tool here which makes this faster.

For example, in the game 'Stick Hero', our webcam will capture the image of the screen and send it to the laptop where we can detect the pillars and the distace between them using image processing. Depending on the distance, we can send the information to the Arduino to simulate a touch for a specified time.


### Advantages of this approach

- This method can be used to solve real time games like 'Flappy Bird'.
- This is faster than adb tool, even though not as fast as just using electornic circuits.
- Debugging is relatively easier.

### Disadvantages of this approach

- Complicated.
- Since external lighting influences the image captured by the webcam, we may have to change the algorithm accordingly each time.
- Setting the touch part of circuit becomes difficult.

We can increase the speed of image processing in this method by using libraries such as OpenCV or PIL instead of MATLAB's image processing toolbox. But let's stick to MATLAB in this book.