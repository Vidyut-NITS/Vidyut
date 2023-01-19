## Vidyut ⚡

### 👪 Team: [Aditya Kotari](https://github.com/AdityaKotari), [Ankur Upadhyay](https://github.com/ankurup3) and [Tejas Sangale](https://github.com/tejas-sangale01)
### 📑 Submission for [L&T EduTech Hackathon at SHAASTRA IITM](https://unstop.com/hackathon/lt-edutech-hackathon-at-shaastra-iitm-shaastra-2023-indian-institute-of-technology-iit-madras-579093)

### ❓ Problem Statement 2: 
#### *Train Kappa Score = 0.9375* | *Validation Kappa Score = 0.8333*

---
### 🖋️ Description


Power outages in the power distribution systems are extremely expensive. Substation issues include:
+ Equipment repair and replacement
+ Less system reliability
+ Wildlife reach in the open areas of substations

### Requirement Specification

1. Use the given dataset of images of objects of substation (dataset given from L&T)
2. Develop a suitable deep learning-based framework for detecting the objects accurately


### 🔋  Dataset Description

There are 192 images used for training and 54 images used for testing purposes. There are 3 classes namely

1. Transformer *(TR)*
2. Transformer with Surge Arrester *(TS)*
3. Surge Arrester *(SA)*

  <img src = "https://user-images.githubusercontent.com/77192368/212900483-a2d6eeb7-7f29-4ff0-9771-212b6f3e5856.jpeg" width="70%">
  <img src = "https://user-images.githubusercontent.com/77192368/212900455-44017822-1b4a-4ae3-aa6f-509329c74275.jpeg" width="70%">



<!--[](https://user-images.githubusercontent.com/77192368/212900455-44017822-1b4a-4ae3-aa6f-509329c74275.jpeg) -->



We have first rescaled the images to 224x224 and normalised them. 

For training images we have performed additional data augmentation as dataset is very small.

## 🔀 Methodology

In order to solve multi-class image classification problem, we have experimented with our own custom CNN architecture and with pre-trained CNN models such as

1. RESNET18
2. XCEPTION
3. VGG16
4. EFFICIENTNET (B0 & B4)
5. EFFICIENTNETV2

We have found that RESNET18 shows highest performance with 1 extra layer for classification and SGD for optimizer ( learning rate = 0.001, momentum = 0.9 ), batch size = 8. 

We experimented with freezing layers but were not able to get high accuracy when the majority of the layers were frozen. This may be due to the model being pretrained on Imagenet, which may not have had data with similar features as the electrical dataset used here.

+ #### Early stopping: 
We have tracked validation accuracy and saved the weights of model when performance was highest as after too many epochs model starts to overfit. 


### ⚖️ Judging Metrics
+ #### Accuracy, Loss vs Epochs

<img width="432" src="https://user-images.githubusercontent.com/39759092/213529038-53b495c7-b1cf-40ef-8496-69ac87d2f1b0.png">
<img width="432" src="https://user-images.githubusercontent.com/39759092/213528945-a027e855-d79f-4f11-b1bb-eb4fe0e597e9.png">

+ #### Confusion Matrix
<img width="432" src="https://user-images.githubusercontent.com/39759092/213531187-8f8baac4-bdea-4ccb-9747-3fb8a5e6abab.png">

+ #### Classification report
<img width="432" src="https://user-images.githubusercontent.com/39759092/213529182-7ea9ded3-fde3-4a6d-9c01-b2113addf30f.png">

+ #### Kappa score
<img width="432" src="https://user-images.githubusercontent.com/39759092/213529370-b68f9f69-1c97-4335-b036-938a5db8472c.png">


