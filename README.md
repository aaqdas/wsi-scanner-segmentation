# Whole Slide Image Segmentation
Whole Slide Image Segmentation uses FAST.AI to perform Semantic Segmentation of Keratin Pearls in Whole Slide Images using UNet Learner.
## Whole Slide Images
Whole Slide Images are ultra high resolution images captured by scanning and stitching images of pathological slides under a microscope. Such images have very high resolutions above 1000MPs. To load such resolution images in Python, I have used an open source library [OpenSlide](https://openslide.org/api/python/) to load a **.svs** file in Colab Notebook. Using the latter, I have tiled images into small segments to be used easily for semantic segmentation. Due to computation constraints of tiling, I have kept the tile size larger than usually needed for semantic segmentation.

<p align="center">
  <img src="https://user-images.githubusercontent.com/65295655/192130657-c958ce62-6afc-4b2d-a23d-c34c0d551e95.png">
</p>
<div align="center">
  <b>Compressed Whole Slide Image</b>
</div>
 

## Mask Generation
Whole Slide Images are loaded into QuPath. A medical specialist has previously provided me with an annoated image. I have exported the annotation as a GeoJSON file. Using Scikit-Image I have converted GeoJSON coordinates to binary mask using polygon function. The binary mask generated is then utilized in training a UNet Learner to perform semantic segmentation on whole slide images.

<p align="center">
  <img src="https://user-images.githubusercontent.com/65295655/192131523-0d4e9cf9-25d9-49a6-976d-51ccf2f0d378.png">
</p>
<div align="center">
  <b>Binary Mask</b>
</div>
 
## Training 
I have trained a UNet Learner in FAST.AI to develop a prototype for my supervisor to use in Whole Slide Image Scanner implementation.

<p align="center">
  <img src="https://user-images.githubusercontent.com/65295655/192131582-b4efa2e5-ffd6-4bae-87eb-f3e14fc3744a.png">
</p>
<div align="center">
  <b>Results</b>
</div
