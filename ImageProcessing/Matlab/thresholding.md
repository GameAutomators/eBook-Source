### Image Thresholding Technique

Image thresholding is a simple way of detecting specific objects in the image. This technique converts RGB or grayscale images into binary image that has the object of interest seperated out. The binary image has the object of interest marked in white and rest of the image in black (or vice-versa) depending on how you threshold.

In this technique, we seperate the object of interest based on the pixel values. We specify that all the pixels which have their values in a specific range must be give the value of 1 and rest as 0. For example, in the following image, you can see that the foreground and background are of different colors. Here's the command that you can use for thresholding.

Image thresholding is most effective in images when the color of the object of interest is in good contrast with the background. Basically, thresholding is used to separate one color from the image. We can write this as a 'vector-valued' function :

*f(x, y) = [r (x, y), g(x, y), b(x, y)]*

In an image, each pixel is a combination of red, green and blue color, where the value of each function can be defined between 0 to 255.

**Example :**

*For White color :			f(x, y) = [255, 255, 255]*

*For Red color :			f(x, y) = [255, 0, 0]*

*For Green color :		f(x, y) = [0, 255, 0]*

*For Blue color :			f(x, y) = [0, 0, 255]*

*For Black color :			f(x, y) = [0, 0, 0]*


#### Split a Color image to its RGB Channels

As we have already discussed, every image is a three layered matrix. Each layer represents the intensities of red, green and blue color valued from 0 to 255. Generally to process an image we need to split these three layers into three different matrices.
**Example**

*Red = a (: , : , 1)*

*Green = a (: , : , 2)*

*Blue = a (: , : , 3)*

This snippet of code will split the image ‘a’ into its RGB channels. ‘Red’ will contain the grayscale image of red color varying intensity from 0 to 255 (i.e., Unit-8). In the similar fashion, ‘Green’ & ‘Blue’ will contain the respective layers of colors.


### impixel
Returns pixel color values of a binary, grayscale as well as RGB image.

**Syntax**

*variable_name = impixel (image)*

**Example**

*matrix = impixel (a)*

It displays the image ‘a’ and waits for you to select the pixels in the image using the mouse. If you omit the input arguments, impixel operates on the image in the current axes.
	Use normal button clicks to select pixels. Press Backspace or Delete to remove the previously selected pixel. To finish selecting pixels, adding a final pixel, press shift-click, right-click, or double-click. To finish selecting pixels without adding a final pixel, press Return.
	When you finish selecting pixels, impixel returns a ‘m x 3’ matrix of RGB values in the supplied output argument. impixel always returns pixel values as RGB triplets, regardless of the image type.


#### Picking Up a Specific Color
After impixel, we need to pick up that particular color from the image. For this we need to convert a RGB image into a binary image. To make an RGB image to a binary image generally we use a conditional statement.
	Since, in variable ‘matrix’ we stored a particular set of pixels in which the values of R G and B varies over a definite region, so we bound this range by giving a conditional statement.

**Syntax**

*variable_name = condition (f (Red, Green, Blue))*

**Example**

Let us say we need to pick up the red color from the image so we can give the following line segment of code :-

*bi = Red > 150 & Green < 10 & Blue < 10*

Here, ‘bi’ is a binary image since it contains only 0’s and 1’s. When in a pixel the intensity of Red becomes greater than 150 (i.e. very high) and less than 10 in case of Green and Blue (i.e. very less) the condition results true and returns 1 else 0.
	In this case we’ll get a binary image ‘bi’ which contains ‘1’ wherever the intensity of red will be high.
