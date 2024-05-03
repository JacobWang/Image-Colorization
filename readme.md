#  Image Colorization and Enhancement Project

#### 05/03/2024

#### Zhengqi (Jacob) Wang - Shigeng La - Lan (Andy) Wang 

Project Overview This project explores various deep-learning models for image colorization and enhancement, leveraging architectures such as GANs, ResNet, and VGG. The aim is to compare different models and loss functions in terms of accuracy, perceptual quality, and other metrics like PSNR, MSE, and SSIM.



Requirement:

- Make sure all the needed dependency is downloaded in the environment, if not simply doying it by "pip install __" or if it is virtual environment set up by conda install it by "conda install _". GPU is highly recommend by not mandatory.

Dataset:

- **Colorized traning**: and validation set: inclue files type jpg, png, jpeg. with folders of drawings, engraving, iconography, painting, sculpture
- **Greycolored set**: image direcory of the colorized set with grey image version 

Preprocessing:

- **preprocessing.ipynb**: This notebook transforms images from the dataset folder into grayscale versions stored in a mirrored directory structure, preparing them for the colorization process. 

Model Notebooks: 

In all the models, the pooling layer had been removed to maintain a higher resolution output image, and the final activation layer had been changed to tanh.

- **GANS.ipynb**: Implements a Generative Adversarial Network for image colorization with unet architectures
- **RESNET.ipynb**: Modified version of reset-50, with bottleneck expansion from 4 to 2.
-  **VGG-16.ipynb**: Modified version of vgg-16.  

Models:

- Stored trained weights for each model architecture to facilitate quick deployment and testing in organized name and folders.

Evaluation:

- **VGG_xxx**: Applies high-resolution enhancement using the VGG model and generates performance metrics that are summarized in the evaluation table. 
- **RESNET_xxx and GANS_xxx**: Performs evaluation.



## Performance Evaluation
The following table summarizes the performance of each model based on various metrics. 'p' in the metrics stands for 'perceptual', indicating the use of perceptual loss functions.

|               | VGG (mse) | VGG (smooth) | VGG (p+mse) | VGG (p+smooth+mse) | Resnet (mse) | Resnet (smooth) | GAN (l1) |
| ------------- | --------- | ------------ | ----------- | ------------------ | ------------ | --------------- | -------- |
| **Accuracy**  | 0.2757    | 0.2675       | 0.5736      | 0.59               | 0.4019       | 0.4393          | 0.4357   |
| **AUC**       | 89.27     | 89.29        | 89.85       | 89.78              | 89.23        | 89.23           | 88.61    |
| **Mean PSNR** | 24.19     | 24.19        | 25.6        | 26.39              | 25.38        | 25.89           | 26.4     |
| **Mean MSE**  | 0.0062    | 0.0062       | 0.0051      | 0.0047             | 0.0052       | 0.0049          | 0.0044   |
| **Mean SSIM** | 0.7247    | 0.724        | 0.8096      | 0.8325             | 0.8117       | 0.8325          | 0.9242   |



![gan-image](/Users/wangzhengqi/Downloads/gan-image.png)

License: 

This project is licensed under the MIT License - see the LICENSE file for details.

