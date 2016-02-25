## Using Electronics and Image Processing

In this method we will be using the concepts of electronics and image processing together to automate the game. The basic concepts of image processing which we are going to use is described in detail in the next chapter of this book.

### Approach

![image11](/Images/methods-3.png)

*Fig.The image depicts the connection between the computer, microcontroller and the phone for game automation*

We use a webcam which streams the video of the mobile screen into MATLAB which performs image processing according to our need and generates the duration of touch and sends it to the microcontroller (Arduino here), which is used to simulate the touch on the phone screen using certain circuits.

For example, in the game 'Stick Hero', our webcam will capture the image of the screen and send it to the laptop where we can detect the pillars and the distace between them using image processing. Depending on the distance, we can send the information to the Arduino to simulate a touch for a specified time.


### Advantages of this approach

- This method can be used to solve more complex games like 'Flappy Bird'.
- Faster than ADB tool.
- Debugging becomes easier.

### Disadvantages of this approach

- Complex circuits are required.
- Since external lighting influences the image captured by the webcam, we may have to change the algorithm accordingly each time.
- Setting the touch part of circuit becomes difficult.

We can enhance the efficiency of this method by using OpenCV instead of MATLAB.