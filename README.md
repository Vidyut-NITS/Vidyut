## Vidyut ⚡

### 👪 Team: [Aditya Kotari](https://github.com/AdityaKotari), [Ankur Upadhyay](https://github.com/ankurup3) and [Tejas Sangale](https://github.com/tejas-sangale01)
### 📑 Submission for [L&T EduTech Hackathon at SHAASTRA IITM](https://unstop.com/hackathon/lt-edutech-hackathon-at-shaastra-iitm-shaastra-2023-indian-institute-of-technology-iit-madras-579093)

### Problem Statement 2: *(Kappa Score = 0.833)*
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



We have performed Data Augmentation by first rescaling image to 224x224 and normalising the images.
For training images we have performed additional data augmentation as dataset is too small.

## 🔀 Methodology

In order to solve multi-class image classification problem, we have experimented with our own custom CNN architecture and with pre-trained CNN models such as

1. RESNET18
2. XCEPTION
3. VGG16
4. EFFICIENTNET (B0 & B4)
5. EFFICIENTNETV2

We have found that RESNET18 shows highest performance with 1 extra layer for classification and SGD for optimizer ( learning rate = 0.001, momentum = 0.9 ), batch size = 8

##### Early stopping: 
We have tracked validation accuracy and saved the weights of model when performance was highest as after too many epochs model starts to overfit. 





### ⚖️ Judging Metrics
+ #### Accuracy, Loss vs Epochs

<p float="left">
<img width="432" alt="Screenshot 2023-01-17 at 6 24 32 PM" src="https://user-images.githubusercontent.com/77192368/212904309-7859ac8a-0070-4146-b5d6-f9f8439f4145.png">
<img width="432" alt="Screenshot 2023-01-17 at 6 27 30 PM" src="https://user-images.githubusercontent.com/77192368/212904998-b42a132e-cfc6-4c9f-aa11-6dad0435df58.png">
</p>

+ #### Confusion Matrix

<img width="432" alt="Screenshot 2023-01-17 at 6 24 32 PM" src="https://user-images.githubusercontent.com/77192368/212905401-4aae8d1a-723c-4101-9a58-92e73f834e17.jpeg">

+ #### Classification report
<img width="432" alt="Screenshot 2023-01-17 at 6 24 32 PM" src="https://user-images.githubusercontent.com/77192368/212906419-91ee72cd-e642-4248-8a64-07ca37430dfe.jpeg">

+ #### Kappa score
<img width="432" alt="Screenshot 2023-01-17 at 6 24 32 PM" src="https://user-images.githubusercontent.com/77192368/212906794-fa621468-ede8-42f9-8720-b2a051a4c926.jpeg">


