### Image Enhancement

The above image thresholding algorithm might not always work. Sometimes you will have to do some additional processing before you can detect the location of the object and that is what we will be learning now.

Below are a few of the funtions functions that you can use for post enhancement of your binary image.
* Dilation
* Erosion
* Filling holes
* Removing small objects

Let us learn about each of them now. Please understand that the definition provided here are over simplified for easier understanding. If you want to learn more in detail, take a course on Image Processing.

#### Dilation

Dilation is the process of widening the object from the edges in the image. It can be used when the size of the binary image is smaller than the actual object. Dilation can help make the object size bigger. Here's the syntax for dilation of an image one time.

```MATLAB
out2 = bwmorph(out, 'dilate'); % Dilating the image once
```

You can also dilate an image multiple times by using an additional parameter as shown below.

```MATLAB
n = 10;
out2 = bwmorph(out, 'dilate', n); % Dilating the image 'n' times
```

#### Erosion

Erosion is the process of thining the object from the edges in the image. It can be used when the size of the binary image is larger than the actual object. Erosion can help make the object size smaller and filter out small object that have been unintentionally detected. Here's the syntax for erosion of an image one time.

```MATLAB
out2 = bwmorph(out, 'erode'); % Eroding the image once
```

You can also erode an image multiple times by using an additional parameter as shown below.

```MATLAB
n = 10;
out2 = bwmorph(out, 'erode', n); % Eroding the image 'n' times
```


#### Filling holes

Holes are black pixels in the image which are completely covered in all directions by white pixels. In other words, hole is a set of pixels that cannot be reached by filling background from edge of image. The `imfill` function can be used to fill the holes. An example of how it can be used is shown below.

```MATLAB
out2 = imfill(out, 'holes'); % Filling holes
```

#### Removing small objects

Small object in an image can be removed by using the following function. The size of the object less than which have to be eliminated must be mentioned as one of the parameters for the function.

```MATLAB
size = 100;
out2 = bwareaopen(out, size); % removing object with area less than size
```

Once we have enhance the image properly, we need to have only the object (or objects) of interest left in the image. We will learn how to find the properties of these objects in the next section.