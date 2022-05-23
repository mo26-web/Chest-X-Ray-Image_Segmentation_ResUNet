# Chest-X-Ray-Image_Segmentation_ResUNet-
Lung segmentation for chest X-Ray images with ResUNet and UNet. In addition, feature extraction and tuberculosis cases diagnosis has developed

# Data description
The dataset contains x-rays and corresponding masks. Some masks are missing so it is advised to cross-reference the images and masks.
The OP had the following request:
It is requested that publications resulting from the use of this data attribute the source (National Library of Medicine, National Institutes of Health, Bethesda, MD, USA and Shenzhen No.3 People’s Hospital, Guangdong Medical College, Shenzhen, China) and cite the following publications:
> [1] Jaeger S, Karargyris A, Candemir S, Folio L, Siegelman J, Callaghan F, Xue Z, Palaniappan K, Singh RK, Antani S, Thoma G, Wang YX, Lu PX, McDonald CJ. Automatic tuberculosis screening using chest radiographs. IEEE Trans Med Imaging. 2014 Feb;33(2):233-45. doi: 10.1109/TMI.2013.2284099. PMID: 24108713
> 
> [2] Candemir S, Jaeger S, Palaniappan K, Musco JP, Singh RK, Xue Z, Karargyris A, Antani S, Thoma G, McDonald CJ. Lung segmentation in chest radiographs using anatomical atlases with nonrigid registration. IEEE Trans Med Imaging. 2014 Feb;33(2):577-90. doi: 10.1109/TMI.2013.2290491. PMID: 24239990

X-ray images in this data set have been acquired from the tuberculosis control program of the Department of Health and Human Services of Montgomery County, MD, USA. This set contains 138 posterior-anterior x-rays, of which 80 x-rays are normal and 58 x-rays are abnormal with manifestations of tuberculosis. All images are de-identified and available in DICOM format. The set covers a wide range of abnormalities, including effusions and miliary patterns. The data set includes radiology readings available as a text file.
## About Data
* The dataset is made up of images and segmentated mask from two diffrent sources.
* There is a slight abnormality in naming convention of masks.
* Some images don't have their corresponding masks.
* Images from the Shenzhen dataset has apparently smaller lungs as compared to the Montgomery dataset.

## Visualizing images and masks
<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/1.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/1.png" align="center"></a>
</p>

## Data Augmetation
Data augmentation in data analysis are techniques used to increase the amount of data by adding slightly modified copies of already existing data or newly created synthetic data from existing data. It acts as a regularizer and helps reduce overfitting when training a machine learning model. It is closely related to oversampling in data analysis.
* create contrast images(v1)
* create contrast images(v2)
* create noise images

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/2.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/2.png" align="center"></a>
</p>

# Approach for segmentation
## U-Net
U-Net is a convolutional neural network that was developed for biomedical image segmentation at the Computer Science Department of the University of Freiburg. The network is based on the fully convolutional network and its architecture was modified and extended to work with fewer training images and to yield more precise segmentations.

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/u-net-architecture.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/u-net-architecture.png" align="center"></a>
</p>

## Deep-Residual-Unet
ResUNet, a semantic segmentation model inspired by the deep residual learning and UNet. An architecture that take advantages from both(Residual and UNet) models.
Paper: https://arxiv.org/pdf/1711.10684.pdf

Video Explaination: https://youtu.be/BOoBWRTpaKk

<p align="center">
<a href="https://github.com/nikhilroxtomar/Deep-Residual-Unet/raw/master/images/arch.png"><img src="https://github.com/nikhilroxtomar/Deep-Residual-Unet/raw/master/images/arch.png" align="center"></a>
</p>

# Results for segmentation
## U-Net

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/results4.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/results4.png" align="center"></a>
</p>

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/results3.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/results3.png" align="center"></a>
</p>

## Residual-Unet

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/results2.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/results2.png" align="center"></a>
</p>

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/results1.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/results1.png" align="center"></a>
</p>

## Comparison

|               | Number of parameters |validation loss|
| ------------- |:-------------:| -----:   |
|  U-Net     | 7,759,521         |   0.03169 |
| Residual-Unet     | 4,722,737         |     0.02861   |

# Tuberculosis cases diagnosis

* Exploratory data analysis
* Feature extraction
* Feed extracted features into MLP Neural Network for classification

## Number of samples
<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/TB1.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/TB1.png" align="center"></a>
</p>

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/TB2.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/TB2.png" align="center"></a>
</p>

## Visualizing Samples
### negative case

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/negative1.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/negative1.png" align="center" width="200" height="200"></a>
</p>

### positive case

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/positive1.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/positive1.png" align="center" width="200" height="200"></a>
</p>

## Deep MLP Architecture (Classifier)

<p align="center">
<a href="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/mlp1.png"><img src="https://github.com/mo26-web/Chest-X-Ray-Image_Segmentation_ResUNet-/blob/main/images/mlp1.png" align="center"></a>
</p>

## Results for Feature extraction (InceptionResNetV2) and Classification
Use pretrained InceptionResNetV2 for feature extraction.

|               | precision     |recall    |f1-score |support|
| ------------- |:-------------:| :-----: |:-----:   |-----:   |
| Tuberculosis negative cases   | 0.80         | 0.88  |  0.84  |  77 |
| Tuberculosis positive cases   |0.88          |  0.80  |  0.84   |    83  |
| accuracy                      | 0.84         |  0.84  |  0.84      |    160   |

## Results for Feature extraction (ResNet50) and Classification
Use pretrained ResNet50 for feature extraction.

|               | precision     |recall    |f1-score |support|
| ------------- |:-------------:| :-----: |:-----:   |-----:   |
| Tuberculosis negative cases   | 0.95         | 0.85  |  0.89  |  85 |
| Tuberculosis positive cases   |0.85          |  0.95  |  0.89   |    75  |
| accuracy                      | 0.89         |  0.89  |  0.89      |    160   |

## Results for Feature extraction (VGG16) and Classification
Use pretrained VGG16 for feature extraction.

|               | precision     |recall    |f1-score |support|
| ------------- |:-------------:| :-----: |:-----:   |-----:   |
| Tuberculosis negative cases   | 0.90         | 0.90  |  0.90  |  84 |
| Tuberculosis positive cases   |0.89          |  0.89  |  0.89   |    76  |
| accuracy                      | 0.90         |  0.90  |  0.90      |    160   |
