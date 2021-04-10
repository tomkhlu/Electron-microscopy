Microsoft's Image Composite Editor (ICE) is sensitive to any tilt in the illumination of the tiles. This code corrects for any bias field (intensity inhomogeneity) triggered by vignetting and created by ICE in the final stitched mosaic. Briefly, what this code does is:

1)  Sum all tiles in the mosaic
2)  Low pass filter

The first two processes resulted in an average illumination measurement for the tiles. If there is any tilt in the illumination such that the maximum brightness point touches a border, there is likely to be a bias field in the final mosaic. To correct for it, the code finally does:

3) Divide each frame pixel by pixel by the normalized average intensity.  

And this will completely remove the bias field.
