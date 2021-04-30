# Structure From Motion

## Description
The following repository contains the data, code and implementation of Structure From Motion (SFM) for Orthogonal angle estimation from multiview imaging. This method can decrease ample time and resources where imaging of object from orthogonal view requires lot of experimental setup. The following method is based on SIFT for correspondence detection and binocular SFM for 3D reconstruction. I have also used in build AliceVision Meshroom implementation for dense 3D reconstruction.

## Steps For Angle Estimation
* Image object from different angle and take atleast 10 images containing angular face of interest.
* Use SIFT to detect correspondence between consecutive pair of images and calculate the keypoints.
* Provide the Intrinsic Camera parameters, necessary to normalize the image point coordinates.
* Calculate the Essential matrix using 8 Point algorithm between the pairs of images.
* Assume P1 = \[I 0\], and calculate the second projection matrix P2 using the Essential matrix.
* Triangulate using the fact that x1 = P1X and x2 = P2X, where X is the 3D point and x1, x2 are corresponding points on the images.
* Store the projection matrix used for each image pairs into a list.
* Take input points on each of the image that corresponds to the edges, between which our interest of angle lies
* Reproject the 3D points using the projection matrix and input points chosen for each image pair.
* Use vector algebra to calculate the angle between the 3D edges projected.

## Google Colab Files
| File Name | Colab Link |
| ----------- | ---------- |
| Angle Estimation : Binocular SFM | <a target="_blank" href="https://colab.research.google.com/drive/16UIwZAQsV3AZpD5FM1Aqw-F1zWk1bthP?usp=sharing">Run in Google Colab</a> |
| Angle Estimation : Meshroom Implementation | <a target="_blank" href="https://colab.research.google.com/drive/1D9e7tz8sxbD7RtYRXN93knRAkcZ5S-6Q?usp=sharing">Run in Google Colab</a> |
| SIFT Implementation | <a target="_blank" href="https://colab.research.google.com/drive/1i2J4DidtcGEf8EYj2QmLqHmoMH8pvGvx?usp=sharing">Run in Google Colab</a> |

## References
* [AliceVision](https://alicevision.org/)
* [Meshroom](https://meshroom.com/)
* [Meshlab](https://www.meshlab.net/)
* [Structure From Motion](https://towardsdatascience.com/structure-from-motion-311c0cb50e8d)
* [3D reconstruction](https://github.com/alyssaq/3Dreconstruction)
* [Python Implementation of SFM](https://github.com/aferral/Structure-from-motion-python)
* [Meshroom Implementation](https://github.com/aj7amigo/3D-Reconstruction)
