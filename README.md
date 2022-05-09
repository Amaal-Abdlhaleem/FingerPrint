# FingerPrint
A biometrics system uses computer technology to identify people based on physical characteristics such as fingerprint.

Biometrics in general is a science that applied statistical and mathematical methods to data analysis problems in the biological sciences.

##### In this project, I worked on fingerprint dataset and apply some operations to do feature extraction and matching.

#### Firstly, Here is the biometrics system architecture:

![Architecture-of-Biometric-system](https://user-images.githubusercontent.com/65326291/167334901-aa6c9671-9f45-4a03-ac5a-6447319ca069.png)

##### 1) We need to collect the biometrics fingerprint dataset through the biometrics sensor.
Instead of this phase I used fingerprint dataset [Sokoto Coventry Fingerprint Dataset (SOCOFing)](https://www.kaggle.com/datasets/ruizgara/socofing) from kaggle. 
It is a biometric fingerprint database designed for academic research purposes. SOCOFing is made up of 6,000 fingerprint images from 600 African subjects and contains unique attributes such as labels for gender, hand and finger name as well as synthetically altered versions with three different levels of alteration for obliteration, central rotation, and z-cut.


##### 2) To apply feature extraction, We need to do some steps before applying it:
###### - Exploring the dataset:
After that, I found two folders Real and Altered. I worked on real dataset and choose sample to working on it.

###### - Image Processing:
Perform some operations on an image (Left_index_finger) to extract some useful information from it.
Like converting images to grayscale and appling some filters to remove noise and image enhancement such as gaussian filter and median filter.

###### - Feature Detection and Extraction:
Feature is an interesting part of an image, and are used as a starting point for many computer vision algorithms.
So, we need feature detection befor extraction to know these interesting points which distinguish the image like:

          1- Edges: Used Canny Detector
              Local changes of intensity which occur on the boundary between two different regions in an image.
              Helps in extracting information and recognizing objects.
              
          2- Corners:
              Regions in images which have maximum variation when moved in all regions around it.

After appling ORB Corner Descriptor and SHI-Tomasi Corner Detection:

![orb descriptor](https://user-images.githubusercontent.com/65326291/167345338-62e447f8-9c55-47a6-805c-15679b4e6c1e.png)      ![shi-tomasi corner detection](https://user-images.githubusercontent.com/65326291/167345347-6d01434f-8a8d-45f6-873b-5fb8c0063cf3.png)
              
After extract some features through edge detection and corner detection and description, then match between the real image and an altered image!
Altered image was synthetically altered version with central rotation.

I applied a brute-force to match between these two images.
