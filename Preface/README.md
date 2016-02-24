# Preface

Making learning fun is extremely important. Many of us would have played video games when we were young, and what kept us glued and excited was the desire to make a high score. How awesome would it be to build your own robots and algorithms that play these games? How exciting would it be to watch how your algorithm will make it through the level that you found very hard?

This book is an attempt in that direction. It will introduce you on how to build systems and robots that can play mobile games. This approach will help you learn concepts of algorithms, electronics, image processing and machine learning; and have a lot of fun at the same time. 

### Background 

I’m Surya Penmetsa, an ECE graduate from NIT Warangal class of 2015. I started working on such robots and algorithms during my final year at college. They could solve mobile games using concepts of electronics, image processing and machine learning. We used electronic sensors or image processing to sense what's on the screen; and then simulated touch physically or virtually at the appropriate locations. 

I uploaded the video of one of the robots that could play the game 'Piano Tiles' on YouTube and it went viral. More than 200,000 people watched it. Video link: https://youtu.be/2TJ7itil1cc

<div class="row" style="text-align:center;">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/2TJ7itil1cc" frameborder="0" allowfullscreen></iframe>
</div>

On popular demand, I also uploaded a tutorial video for the same, and it again got over 200,000 views. This shows the excitement and interest of people to solve games in an innovative manner. Video link: https://youtu.be/8hlQ0MiowN8

<div class="row" style="text-align:center;">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/8hlQ0MiowN8" frameborder="0" allowfullscreen></iframe>
</div>

I decided it was time for me to take the work to the next level. With the help of The Lakshya Foundation and Innovation Garage, I teamed up with students from NIT Warangal during the winter vacation in December 2015, and Hackathon 5.0 in January 2016 to solve more games.

Here's a video of overview of the winter internship at NIT Warangal: https://youtu.be/iDJW98c7uhg

<div class="row" style="text-align:center;">
	<iframe width="560" height="315" src="https://www.youtube.com/embed/iDJW98c7uhg" frameborder="0" allowfullscreen></iframe>
</div>

Most students had prior experience with electronic circuits, but very few knew image processing. I guided them through short lectures and provided them with online resources where they could learn further. They worked very hard, and grasped all required concepts very quickly. Together, we wrote algorithms for various games which beat human-level-performance. 

We open-sourced all of the projects so that people around the world can replicate and build upon it. We also made video demonstrations for all projects and uploaded them on YouTube. 

This book **Building Mobile Game Solvers** is a result of our work. I hope you learn a lot while reading the book and have a lot of fun. 

We are open sourcing this book so that it can get better in quality by contributors across the world. We invite you, the reader, to be a contributor to the book to have more projects. The details on how to contribute are at the end of the book.

### Scope

Artificial Intelligence has been one of the fastest growing fields in the recent past. This book could also bolster the interest of the readers towards the field of Artificial Intelligence. 

Once people learn building machines for game playing, they can expand into other areas in AI such as- natural language processing, robotics, computer vision, stock trading, medical diagnosis, etc.

### Prerequisites

So what should you know in order to get started? This book has been carefully designed to help readers with or without experience in electronics and image processing.

We tried to cover the concepts that are relevant to solving mobile games in this book. In case you want to learn more, we have provided links at relevant places. 

### What this book covers

*Chapter 1, Introduction,* covers the basic idea of the approach that we are going to use to solve the games in this book.

*Chapter 2, Electronics,* introduces the sensors that can be used to sense what's on the screen and the various ways to simulate touch. It also talks about how a microcontroller can be used in to program the sensors and the touch simulation part in an efficient way.

*Chapter 3, Image Processing,* explains what an image is actually made up of and how it can be analysed using different methods. It also teaches MATLAB commands that can be used for image processing.

*Chapter 4, Different Methods of Automating,* covers three different ways of automating the mobile game- each of them has it's own advantages disadvantages. The method needs to be chosen based on the game that we intend to solve.

*Chapter 5, Specific Examples,* demonstrates how the concepts and methods of solving that we have learnt earlier can be used to solve specific games.

### Conventions

In this book, you will find different formats of text that specify different types of information. For example, the paragraph text you are reading right now depicts normal text in the book. The bold in a bigger font size depicts the chapter names, headings or subheadings.

Codes are represented in blocks as follows-

Arduino code is represented this way.
```C
void setup()
{
    // initialize serial communications at 9600 bps:
    Serial.begin(9600);
}
```

MATLAB code is represented this way.
```MATLAB
% Reading an image
a = imread('input.jpg');
% Displaying the image
imshow(a);
```

### Downloading the codes used in the book

All the codes that have been used in the book can be found at this link: https://github.com/GameAutomators

### Downloading color images in the book

You can find the color images that have been used in the book at the following links: https://github.com/GameAutomators/eBook-Source/tree/master/Images

### Reader feeback

We are always looking to improve the quality of the book. The feedback from the readers of our book is extremely important for us. Let us know what you think about the book by shooting an email to p.surya1994@gmail.com with the subject **Reader Feedback: Game Automators**. We promise to read each and every one of your emails.

### Questions

If you find any mistake in the book text or the code- we would be grateful if you could report this. You can contact us at p.surya1994@gmail.com if you are facing any issues with the book, and we will try our best to address it. 