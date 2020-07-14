---
description: Telling amap which way round your images are
---

# Image orientation

**If the supplied data does not match the NifTI standard orientation \(origin is the most ventral, posterior, left voxel\), then the atlas can be reoriented to match:**

* `--flip-x` Flip the sample brain along the first dimension
* `--flip-y` Flip the sample brain along the second dimension
* `--flip-z` Flip the sample brain along the third dimension
* `--orientation` The orientation of the sample brain `coronal`, `saggital`or `horizontal`

\`\`

**If your data isn't in a standard \(i.e. anatomical orientation\), and needs to be rotated, you can use the `--rotation` flag**  
 What follows the `--rotation` flag, must be a string in the format `xIyJzK`, where x, y & z are the axes to rotate around, and I, J & K are the number of 90 degree rotations for the respective axes.  The direction of the rotation is: 

* For a rotation around X, the rotation is from the Y axis to Z
* For a rotation around Y, the rotation is from the X axis to Z
* For a rotation around Z, the rotation is from the X axis to Y

For example:

* `x0y0z3` would rotate around the Z axis 90 degrees clockwise \(i.e. 270 degrees anticlockwise\)
* `x0y0z0` would not rotate the image \(default\)



