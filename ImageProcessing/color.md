### How any Color can be Represented as a Combination of RGB?
For image processing, we need to understand the formation of a digital image on its pixel level. A color image is a three-layered matrix. More precisely, it's just three functions to be pasted together. These three functions are Red, Green and Blue. In other words, we can say that each color can be represented by the combination of these three colors.

  *f(x, y) = [r (x, y), g(x, y), b(x, y) ]*

The following image is a pop-up box in paint window. Here you can see in the right bottom corner, there is a color representation in terms of Red, Green and Blue. We call this as RGB value of the color.

![ColorImage]()

In a similar fashion every pixel has its RGB value.

### Types of Images
On the basis of image processing, Images can be classified into three categories :-
- Binary Image
- Grayscale Image
- RGB Image

##### Binary Image
The term ‘bi’ represents two i.e. an image in which all pixels have either 0’s or 1’s is a binary image. Those pixels having pixel value as 0 are black in display while the white ones are represented as 1.


##### Grayscale Image
Grayscale image also represents a 2-D matrix. The only difference between grayscale and binary image is that it’s pixels can have value from 0 to 255. Here 0 will represent ‘pure black’ and 255 will represent ‘pure white’ color.     
The pixels having pixel value in between 0 and 255 will look like ‘gray’ in color i.e. a mixture of black and white.

##### RGB Image
RGB image is used to display a 3-D image. A colored image consists of three layers i.e. the Red, Blue and Green color component of every pixel.

![TypesofImages]()