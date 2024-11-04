# 🧠 Alzheimer's Disease Classification Using VGG16 🧠

This project focuses on classifying MRI images to determine the severity of Alzheimer's disease using a fine-tuned VGG16 model. The model categorizes images into four stages: **Non-Demented**, **Very Mild Demented**, **Mild Demented**, and **Moderate Demented**.

## 📂 Dataset

The dataset consists of augmented MRI images of Alzheimer's patients. The images are organized into four classes:
- **Non-Demented**
- **Very Mild Demented**
- **Mild Demented**
- **Moderate Demented**

🔗 **Dataset Link:** [Augmented Alzheimer's MRI Dataset on Kaggle](https://www.kaggle.com/datasets/uraninjo/augmented-alzheimer-mri-dataset)  
📁 **Dataset Path:** `/kaggle/input/augmented-alzheimer-mri-dataset/`

All images are resized to 224x224 pixels to match the input size required by the VGG16 model.

## 🧱 Model Architecture

The model leverages the VGG16 architecture, pre-trained on the ImageNet dataset, and fine-tunes it for our classification task. The architecture includes:
- **Base Model:** VGG16 (without the top layer)
- **Pooling and Dense Layers:** 
  - Global Average Pooling layer
  - Dense layer with ReLU activation
  - Dropout layer for regularization
  - Output layer with softmax activation for multi-class classification

## 🖼️ Data Augmentation

Data augmentation techniques are applied to improve model generalization:
- 🔄 **Random Rotation**
- 🔍 **Random Zoom**
- 🌞 **Random Brightness and Contrast Adjustments**

These augmentations are implemented using TensorFlow's image preprocessing functions.

## 📦 Requirements

The project requires the following libraries:
- `numpy`
- `tensorflow`
- `matplotlib`

You can install these dependencies with:
```bash
pip install numpy tensorflow matplotlib
```

## 🚀 Training and Evaluation

The training script involves:
* **Data Loading:** Images are loaded using `image_dataset_from_directory`
* **Data Preprocessing:** Images are resized and normalized
* **Training:** The VGG16 model is fine-tuned on the training dataset
* **Validation:** The model is evaluated on a validation dataset

## 📊 Training Results

The model achieved impressive results during training:
* **Final Training Accuracy:** **99.24%** 🎉
* **Final Validation Accuracy:** **98.85%** 🌟
* **Final Training Loss:** **0.0230** 📉
* **Final Validation Loss:** **0.0380** 📈

## 📝 Manual Early Stopping

Manual early stopping is implemented to prevent overfitting. During training, if the validation accuracy does not improve for a specified number of epochs, the training is halted. This approach ensures that the model retains its ability to generalize on unseen data, rather than merely memorizing the training dataset.

## 📊 Conclusion

The VGG16 model effectively classifies the severity of Alzheimer's disease based on MRI images. Future improvements could involve exploring additional models or fine-tuning strategies to enhance accuracy.

## 🎉 Acknowledgments

Thank you for reviewing this project! Your feedback and contributions are welcome!