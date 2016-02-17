### Object detection

In this section, we will learn how we can use the function `regionprops` in MATLAB to detect various properties of objects that can be detected using steps in the previous sections. The input to the `regionprops` function is a binary image, with the object marked in white and the background marked in black.

This command creates a 'struct' variable in which it stores various properties for every region. The default properties are `Area`, `Centroid`, `BoundingBox`. The function also allows extracting a wide range of other properties that can be found in the MATLAB help or by typing in `doc regionprops` in the MATLAB command window.

Here's the syntax for using the function `regionprops`.

```MATLAB
% Code to extract default properties of objects
Stats = regionprops(out2);

% Code to extract only centroids of objects
Stats = regionprops(out2, 'Centroid');
```
