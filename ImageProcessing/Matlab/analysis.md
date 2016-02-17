### Image Enhancement

#### imfill
Fill image regions and holes.

**Syntax**

*variable_name = imfill (image, ‘holes’)*

**Example**

*bi_2 = imfill (bi, ‘holes’)*

It fills holes in the binary image ‘bi’. In this a hole is a set of background pixels that cannot be reached by filling in the background from the edge of the image.


#### Dilate the Image
Dilates the image according to the given parameter.

**Syntax**

*variable_name = bwmorph (image, ‘dilate’, parameter)*

**Example**

*bi_3 = bwmorph (bi_2, ‘dilate’, 7)*

It will dilate the binary image ‘bi_2’ by 7 times. Usually dilation means smoothing the edges of a region. Here we can use ‘imdilate’ command instead of ‘bwmorph’ to dilate the objects / regions.


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
