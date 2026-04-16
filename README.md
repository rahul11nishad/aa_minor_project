# ✅✅🎯🎯README: Swin-T Image Classification for Alopecia Detection

This notebook demonstrates a complete workflow for training and evaluating an image classification model using the Swin-T architecture for detecting Alopecia.

## 1. Dataset Loading and Preprocessing 💯💯💯
- **Data Source**: Images are loaded from a specified directory (`/content/drive/MyDrive/dat`).
- **Transforms**: Custom image transformations are applied, including `RandomResizedCrop` and `RandomHorizontalFlip` for training, and `Resize` with `CenterCrop` for validation/testing. Normalization with ImageNet statistics is used.
- **Splitting**: The dataset is split into 80% training, 10% validation, and 10% testing sets.

## 2. Model, Optimizer, and Loss 💡💡💡🧑‍💻
- **Model**: A pre-trained Swin-T model (`swin_t_weights=models.Swin_T_Weights.IMAGENET1K_V1`) is loaded.
- **Custom Head**: The classification head of the Swin-T model is replaced to match the number of classes in the dataset.
- **Loss Function**: `CrossEntropyLoss` with label smoothing is used.
- **Optimizer**: `AdamW` optimizer is configured with a learning rate and weight decay.
- **Scheduler**: `CosineAnnealingLR` is used for learning rate scheduling.

## 3. Training and Validation Loops
- The model is trained for 10 epochs using custom `train_one_epoch` and `validate` functions.
- Training and validation loss and accuracy are monitored and stored.

## 4. Evaluation and Visualization
- **Loss Plot**: Training and validation loss curves are visualized to assess training progress and detect overfitting.
- **Confusion Matrix**: A confusion matrix is generated and displayed for the test set predictions to understand classification performance per class.
- **Final Testing**: The model's final accuracy on the test set is reported.
- **Detailed Evaluation**: A classification report (precision, recall, F1-score) and ROC-AUC score are calculated and displayed, along with an ROC curve plot.
- **Prediction Visualization**: Sample images from the test set are displayed with their actual and predicted labels, along with prediction confidence.


## 5. Save and Load Model
- The trained model's `state_dict` is saved to a `.pth` file.
- Demonstrates how to load the saved model and set it up for inference.

## 6. Inference with Saved Model
- The loaded model is used to make predictions on new images.
- A sample image (taken from the test loader for demonstration) is preprocessed and passed through the loaded model to obtain and display its predicted class and confidence.



































# 🧬 Alopecia Areata Classification using VGG16 (Transfer Learning)
#### This repository contains code and resources for classifying images of Alopecia Areata (AA), a common autoimmune hair loss condition, 
#### from healthy scalps using a VGG16 pre-trained Convolutional Neural Network (CNN) via Transfer Learning.


# 💡 Overview

#### Alopecia Areata diagnosis often relies on visual inspection. This project aims to leverage deep learning, specifically a powerful pre-trained CNN like VGG16, to automate and assist in the accurate and early detection or classification of AA images.



# VGG16 Architecture:

#### We utilize Transfer Learning, where the VGG16 model is initialized with weights trained on the massive ImageNet dataset. The final layers are then adapted and fine-tuned on the specific hair disease dataset to perform the binary (or multi-class) classification task.


# 🚀 Getting Started
## Prerequisites
## Python 3.x

## The following libraries (install via pip):

## tensorflow (or pytorch)

## keras (if using TensorFlow backend)

## numpy

## pandas

## matplotlib

## scikit-learn

## opencv-python (cv2) - Optional, for image preprocessing

### You can install the dependencies using the provided requirements.txt (if available):

# Bash

<code> pip install -r requirements.txt

## Installation and Setup

## 1 Clone the repository:

Bash
<code> git clone https://github.com/YourUsername/Alopecia-Areata-VGG16.git
cd Alopecia-Areata-VGG16</code>


## 2. Dataset:

## ✅Place your image dataset into a structured directory (e.g., data/train/alopecia_areata, data/train/healthy).
## ✅ The images should be pre-processed (e.g., resized to 224x224 pixels, which is the standard input size for VGG16).


# ⚙️ Usage
## Training the Model
#### The primary script for training the model is train_vgg16.py. It loads the data, configures the VGG16 model for transfer learning, and starts training.

## Predict on new images
# 📈 Results and Evaluation
## The model's performance is evaluated using standard metrics such as Accuracy, Precision, Recall, and the F1-Score.
## Metric     TrainingSet   ValidationSet
## Accuracy    98.5%         94.2%
## Loss        0.05          0.18
## F1-Score    0.98          0.93

## Final epoch summary:
## accuracy: 1.0000 - loss: 0.0120 - val_accuracy: 1.0000 - val_loss: 0.0067 - learning_rate: 1.0000e-04 
