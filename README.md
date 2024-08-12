# image_stitching_panaroma_generation
The code uploaded makes use of a simple pipeline to stitch a series of four images and displays the output.
The pipeline followed is as follows:
1. Images are passed consecutively and initially the first two appropriate images are selected to stitch together. The image_stitcher function computes the keypoints and the descriptors of the images that are passed in.
2. The descriptors are then matched through a FLANN based matcher and later the good matches are filtered out.
3. Source points and destination points are computed then appropriately and later these points are used to compute the homography through which the source image is warped according to the destination image
4. The width of the target image is kept such that it accomodates both the source as well as the destination image. The destiation image is pasted followed by the pasting of the source image to create a panaromic view.

The following four images are supposed to be stitched together.

<img width="893" alt="dataset_images" src="https://github.com/user-attachments/assets/578fd78a-afcc-46c2-8a1c-98bcf7dd502e">

The following image is the output of the pipeline.

![final_warped_image](https://github.com/user-attachments/assets/9dd4c71f-7578-475b-a006-8d4c535c1786)
