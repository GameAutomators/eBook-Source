Since, all the image processing used in the further articles is done by the software **MATLAB**, we will discuss the relevant concepts here.

#### imread
Reads image from the graphics file and stores it in a variable in the matrix form.

**Syntax** 

*varible_name = imread (‘file_location’)*

**Example**

*a = imread (‘object.png’)*

The above command will store an image named ‘object.png’ into matrix form in variable ‘a’. The size of matrix ‘a’ is decided by the dimensions of the image. Let us assume the size of ‘object.png’ be 757 x 1080, then the matrix ‘a’ will have 757 rows and 1080 columns.


#### imshow
Display the image.

**Syntax**

*imshow (image)*

**Example**

*imshow (a)*

It will display the image stored in variable ‘a’ i.e. ‘object.png’


#### imcrop
Crops the image according to the given dimensions.

**Syntax**

*varible_name = imcrop (image, [x1 y1 x2 y2])*

**Example**

*b = imcrop (a, [100 100 500 500])*

It will crop the image ‘a’ into a 400 x 400 image and store it in another variable ‘b’.


#### imresize
Resize the image according to the given scale

**Syntax**

*variable_name = imresize (image, scale)*

*variable_name = imresize (image, output_size)*

**Example**

*c = imresize (a, 0.5)*

Image ‘a’ will be shrinked to it’s half size and will be stored into another variable ‘c’.

*c = imresize (a, [200 300])*

Image ‘a’ will be resized to a matrix of 200 rows x 300 columns and will be stored in variable ‘c’.


#### imrotate
Rotates the image by given angle (in degrees) in a counterclockwise direction around its center point. To rotate the image clockwise, specify a negative value for angle. ‘imrotate’ makes the output image large enough to contain the entire rotated image.

**Syntax**

*variable_name = imrotate (image, degrees)*

**Example**

*d = imrotate (a, 75)*

Rotate the image ‘a’ in counterclockwise direction by 75 degrees and store it in variable ‘d’.

**NOTE** :- imrotate uses nearest neighbor interpolation, setting the values of pixels in output_image that are outside the rotated image to 0 (zero).


#### subplot
Creates axis in tiled positions. Whenever we need to display two or more images in one window, we use subplot.

**Syntax**

*subplot (m, n, p)*

It divides the current figure into an ‘m x n’ grid and creates an axes for a subplot in the position specified by ‘p’. **MATLAB** numbers its subplots by row, such that the first subplot is the first column of the first row, the second subplot is the second column of the first row, and so on. If the axes already exists, then the ‘subplot(m,n,p)’ makes the subplot in position p the current axes.

**Example**

*subplot (2, 2, 1)*

*imshow (a)*

‘subplot (2, 2, 1)’ will divide the figure into a 2 x 2 matrix. ‘1’ is representing the position where the image ‘a’ is going to be displayed since there are 4 positions.