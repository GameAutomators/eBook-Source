# Preface

We think that making learning fun is an extremely important issue and this book is an attempt to do just that. The purpose of the book is to teach you concepts of algorithms, electronics, image processing and machine learning. 

A survey suggests that about a half of the general public play video games, and a tenth of them consider themselves as serious gamers. The main motivation that drives most of these people is to make a high score in the game. 

But what if we can apply the concepts that, we as engineers know, to build robots and automated algorithms to solve these mobile games? It will motivate more students to work on innovative ways to solve the games rather than spend hours trying to make high scores. We find this idea very fascinating and that's what the book covers.

### Background 

I’m Surya, an alumni of NIT Warangal (ECE 2015). I started working on such robots and algorithms during my final year at college. They could solve mobile games using concepts of electronics, image processing and machine learning. We use electronics to sense what's on the screen and simulate touch at the appropriate locations.

I decided it was time for me to take the work to the next level. With the help of The Lakshya Foundation and Innovation Garage, I teamed up with fifteen students from NIT Warangal during the winter vacation in December 2015.

Most students had prior experience with electronic circuits, but very few knew image processing. I guided them through short lectures and provided them with online resources where they could learn further. They worked very hard, and grasped all required concepts very quickly. Together, we wrote algorithms for five different games which beat human-level-performance. 

We open-sourced all of the projects so that people around the world can replicate and build upon it. We also made video demonstrations for all projects and uploaded them on YouTube. Apart from giving students and enthusiasts a new dimension to learn, this also contributes in building the brand of NIT Warangal.

This book **Building Mobile Game Solvers** is a result of our work during the internship. I hope you learn a lot while reading the book and at the same have a lot of fun. The book has been extended further with more projects during the hackathon 5.0 organised by The Lakshya Foundation at NIT Warangal.

Here's a video of overview of the winter internship at NIT Warangal: https://youtu.be/iDJW98c7uhg

<iframe width="560" height="315" src="https://www.youtube.com/embed/iDJW98c7uhg" frameborder="0" allowfullscreen></iframe>

We are open sourcing this book so that it can get better in quality by contributors across the world. We invite you, the reader, to be a contributor to the book to have more projects. The details on how to contribute are at the end of the book.

### What this book covers

*Chapter 1, Introdction,* covers the basic idea of the approach that we are going to use to solve the games in this book.

*Chapter 2, Electronics,* introduces the sensors that can be used sense what's on the screen and the various ways to simulate touch. It also talks about how a microcontroller can be used in to program the sensors and the touch simulation part in the efficient way.

*Chapter 3, Image Processing,* explains what an image is actually made up of and how it can be analysed using different methods. It also teaches various commands in MATLAB that can be used to these concepts of image processing on images and see the results.

*Chapter 4, Different Methods of Automating,* covers three different ways of automating the mobile game- each of them has it's own advantage and it's own disadvantage. The method needs to be choosen based on the game that we intend to solve.

*Chapter 5, Specific Examples,* demonstrates how the concepts and methods of solving that we have learnt earlier can be used to solve specific games.

### Conventions

In this book, you will find different formats of text that specify different types of information. For example, the paragraph text you are reading right now depicts normal text in the book. The bold in a bigger font size depicts the chapter names, headings or sub headings.

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

We are always looking to improve the quality of the book. The feedback from the readers of our book is extremely important for you. Let us know what you think about the book by shooting an email to p.surya1994@gmail.com with the subject **Reader Feedback: Game Automators**. We promise to read each and every one of your emails.

### Questions

If you find any mistake in the book text or the code- we would be grateful if you could report this. You can contact us at p.surya194@gmail.com if you are facing any issues with the book, and we will try our best to address it. 