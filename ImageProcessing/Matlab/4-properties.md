### Object detection

In this section, we will learn how we can use the function `regionprops` in MATLAB to detect various properties of objects that can be detected using steps in the previous sections. The input to the `regionprops` function is a binary image, with the object marked in white and the background marked in black.

#### regionprops
Measure properties of image regions. This command creates a ‘struct’ data-type variable in which it stores three fields for every region i.e.
	
a) Area
b) Centroid
c) Bounding Box

The image which is to be passed in ‘regionprops’ must be a binary image.

**Syntax**

*variable_name = regionprops (image)*

*variable_name = regionprops (image, field)*

**Example**

*Stats = regionprops (bi_3)*

*Stats = regionprops (bi_3, Centroid)*

It returns measurements for the set of properties specified by properties for each connected component (object) in the binary image. ‘Stats’ is a struct array containing a struct for each object in the image. We can use regionprops on contiguous regions and discontiguous regions as well.Suppose if we need to calculate only a specific field then we can give it as a parameter.
