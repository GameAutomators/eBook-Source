# 5.3. Using Electronics circuits and Image Processing
In this method we will be using the concepts of electronics and image processing together to automate the game.The Basic concepts of image processing which we are going to use is described in detail in the next chapter of this book.

##### Approach
![image11](/Images/methods-3.png)
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