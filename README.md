**Introduction**

While the Transformer architecture has become the de-facto standard for natural
language processing tasks, its applications to computer vision remain limited. In
vision, attention is either applied in conjunction with convolutional networks, or
used to replace certain components of convolutional networks while keeping their
overall structure in place. We show that this reliance on CNNs is not necessary
and a pure transformer applied directly to sequences of image patches can perform
very well on image classification tasks. When pre-trained on large amounts of
data and transferred to multiple mid-sized or small image recognition benchmarks
(ImageNet, CIFAR-100, VTAB, etc.), Vision Transformer (ViT) attains excellent
results compared to state-of-the-art convolutional networks while requiring substantially
fewer computational resources to train.

The idea is to build the vision transformer from scratch based on the original paper and then applying transfer learning from existing ViT models and retrain the last layer for classifying whether an image of Lung or Colon cancer is malignant or benign.

**Architecture of Vision Transformer** (**Figure.1)**


![image](https://github.com/vdinni/ProjectCapstone/assets/21176541/969418df-482e-4d9c-833c-041a70f8693d)


Figure 1: Model overview. We split an image into fixed-size patches, linearly embed each of them, add position embeddings, and feed the resulting sequence of vectors to a standard Transformer encoder. In order to perform classification, we use the standard approach of adding an extra learnable “classification token” to the sequence

An overview of the model is depicted in Figure 1. The standard Transformer receives as input a 1D sequence of token embeddings. To handle 2D images, we reshape the image x into R(HxWxC) into a sequence of flattened 2D patches xp to R(N x (P^2 x C), where (H,W) is the resolution of the original image, C is the number of channels, (P, P) is the resolution of each image patch, and N = HW/P**2 is the resulting number of patches, which also serves as the effective input sequence length for the Transformer.


**Steps to run the notebook:**
1. Please make sure the repository is cloned or downloaded. The dataset is already split into train and test (80/20).
2. The folder going_modular contains multiple files for training the data, saving the model and to evaluate the models. The file helper_functions.py which has functions for prediction and plotting the curves.
3. Open the notebook and setup the environment to GPU as this rquires time and memory. 
4. Run all the cells of notebook

**Metrics**

**ViT Accuracy: 99.1**

![image](https://github.com/vdinni/ProjectCapstone/assets/21176541/145df729-3873-4d94-9c7a-abbfef0ca2c3)


**EfficientNet B7 Accuracy: 99.14**

![image](https://github.com/vdinni/ProjectCapstone/assets/21176541/a3df557f-aa0d-4b04-ac55-4fafd8683cf7)




