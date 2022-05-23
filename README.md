# Chest-X-Ray-Image_Segmentation_ResUNet-
Lung segmentation for chest X-Ray images with ResUNet and UNet. In addition, feature extraction and tuberculosis cases diagnosis has developed

# Data description
The dataset contains x-rays and corresponding masks. Some masks are missing so it is advised to cross-reference the images and masks.
The OP had the following request:
It is requested that publications resulting from the use of this data attribute the source (National Library of Medicine, National Institutes of Health, Bethesda, MD, USA and Shenzhen No.3 People’s Hospital, Guangdong Medical College, Shenzhen, China) and cite the following publications:
> [1] Jaeger S, Karargyris A, Candemir S, Folio L, Siegelman J, Callaghan F, Xue Z, Palaniappan K, Singh RK, Antani S, Thoma G, Wang YX, Lu PX, McDonald CJ. Automatic tuberculosis screening using chest radiographs. IEEE Trans Med Imaging. 2014 Feb;33(2):233-45. doi: 10.1109/TMI.2013.2284099. PMID: 24108713
[2] Candemir S, Jaeger S, Palaniappan K, Musco JP, Singh RK, Xue Z, Karargyris A, Antani S, Thoma G, McDonald CJ. Lung segmentation in chest radiographs using anatomical atlases with nonrigid registration. IEEE Trans Med Imaging. 2014 Feb;33(2):577-90. doi: 10.1109/TMI.2013.2290491. PMID: 24239990
X-ray images in this data set have been acquired from the tuberculosis control program of the Department of Health and Human Services of Montgomery County, MD, USA. This set contains 138 posterior-anterior x-rays, of which 80 x-rays are normal and 58 x-rays are abnormal with manifestations of tuberculosis. All images are de-identified and available in DICOM format. The set covers a wide range of abnormalities, including effusions and miliary patterns. The data set includes radiology readings available as a text file.
## About Data
* The dataset is made up of images and segmentated mask from two diffrent sources.
* There is a slight abnormality in naming convention of masks.
* Some images don't have their corresponding masks.
* Images from the Shenzhen dataset has apparently smaller lungs as compared to the Montgomery dataset.
