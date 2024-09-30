# Object_Detection_using_SAM2
### Steps:
1. Unzip the dataset.
2. Iterate over the first image and mask for each product.
3. Use process_img_png_mask on the first image and mask.
4. Apply track_item_boxes on the first image to track the object in all other images of the same product.
5. Use bounding boxes (predicted vs ground truth) for performance calculation.

### Explanation:
1. Unzipping: The unzip_dataset function extracts the CMU10_3D.zip file into the CMU10_3D directory.

2. File Paths: The code uses glob to list the first image of each product (*_000001.jpg) and its corresponding mask (*_000001_1_gt.png).

3. Object Tracking and Performance Calculation:
For each product, the process_img_png_mask function calculates the bounding box for the first image using the mask.
The track_item_boxes function tracks the object in all subsequent images of the same product.
The predicted bounding boxes from SAM2 are compared against the ground truth bounding boxes (from the corresponding mask).
Performance is calculated using the COCO API by formatting the predictions and ground truth into the required format.

4.Object Detection Performance: The function calculate_performance evaluates the object detection performance using COCO's evaluation metrics, specifically Average Precision (AP).
