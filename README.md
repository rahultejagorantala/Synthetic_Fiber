# Establishing a Baseline for Cotton Fiber Classification
 
Problem: Establishing a Baseline for Cotton Fiber Classification Amidst Ambiguities in Ground Truth Labels.

Solution: Generating synthetic fiber images that closely resemble holographic cotton fiber images, granting us precise control over fiber structure and image fiber count. Subsequently, employing pre-trained models to classify these images, thereby gauging the upper limits of achievable performance.

_Contact me at [mail](mailto:tejarahul618@gmail.com) for more information._


# Example Synthetic Fiber Images 
<table>
  <tr>
    <td align="center">Texture Image 1</td>
    <td align="center">Texture Image 1 BW</td>
    <td align="center">Texture Image 2</td>
    <td align="center">Texture Image 2 BW</td>
  </tr>
  <tr> 
    <td align="center"><img src="https://github.com/rahultejagorantala/Synthetic_Fiber/blob/main/Images/image_8.jpg" width=100 height=100 ></td>
    <td align="center"><img src="https://github.com/rahultejagorantala/Synthetic_Fiber/blob/main/Images/image_8-BW.jpg" width=100 height=100 ></td>
    <td align="center"><img src="https://github.com/rahultejagorantala/Synthetic_Fiber/blob/main/Images/image_12.jpg" width=100 height=100 ></td>
    <td align="center"><img src="https://github.com/rahultejagorantala/Synthetic_Fiber/blob/main/Images/image_12-BW.jpg" width=100 height=100 ></td>
  </tr>
 </table>

These two Images above belong to cotton fibers with different levels of maturity. But visually they cannot be distinguished.

This is a Major problem to solve in cotton fiber industry. Correct classification of cotton fibers according to their maturity can repalce the existing 
techniques which are not reliable and produce inconsistent results.

# Supervised Classification using Transfer Learning.
We have tried different pretrained models to see which one would work better on our dataset. Overall Efficient-B4 and ResNet-50 work slightly better than other models.(when used a subsampled images of size 240x240 from 1002x1002)

The models perform surprisingly well with an average accuracy on test set of around 80%.

<table>
  <tr>
    <td><img src="https://github.com/rahultejagorantala/CottonFiberHolography/blob/main/Images/Models%20Vs%20Accuracy-1.jpg" width=300 height=250 ></td>
    <td><img src="https://github.com/rahultejagorantala/CottonFiberHolography/blob/main/Images/Models%20Vs%20Accuracy.jpg" width=300 height=250 ></td>
  </tr>
 </table>
 
##  Visualisation of the predictions frame by frame.

<tr>
 <td><img src="https://github.com/rahultejagorantala/CottonFiberHolography/blob/main/Images/Barplot.png" width=300 height=250 ></td>
</tr>

The model's predictions can be visualized intuitively with the barplot above. All the videos to the left are Class 0 and to the right are Class 1. blues indicate the class 0 predictions and reds indicate class 1 predictions. for a 100% accuracy, all the left bars become blue and all the right bars becomd red.

##  Visualization of Predictions using GRAD-CAM and Guided BackPropagation (Explainability).
https://github.com/rahultejagorantala/CottonFiberHolography/assets/101026703/86ef630b-c687-4c86-88db-fe84d3a9ad54

Grad-CAM and Guided Backpropagation are used to locate the regions in the image the model is focusing to make the deciscions.

More about Grad-CAM and Guided Back propagation- https://github.com/jacobgil/pytorch-grad-cam

We observed that the model focuses on fiber while making the predictions in some cases and some times in the background. Therefore no conclusive opinion was formed.
