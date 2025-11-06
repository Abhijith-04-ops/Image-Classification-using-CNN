
# 🧠 CNN Image Classification: Pandas vs Bears 🐼🐻

This project demonstrates a **Convolutional Neural Network (CNN)** model built using Python and deep learning libraries to classify images of **Pandas** and **Bears** into their respective categories.  
It covers the complete workflow — from dataset loading and preprocessing to model training, evaluation, and prediction.

---

## 📘 Table of Contents
- [Introduction](#introduction)
- [Dataset Overview](#dataset-overview)
- [About CNN Architecture](#about-cnn-architecture)
- [Workflow and Procedure](#workflow-and-procedure)
- [Model Evaluation](#model-evaluation)
- [Results](#results)
- [Future Improvements](#future-improvements)
- [How to Run](#how-to-run)

---

## 🧩 Introduction

Convolutional Neural Networks (CNNs) are a class of deep learning models primarily used for **image recognition and computer vision tasks**.  
They automatically learn **spatial hierarchies of features** through convolutional layers, enabling them to recognize patterns like edges, textures, and shapes.

This project implements a CNN model from scratch to **classify animal images** — distinguishing between **Pandas** and **Bears**.

---

## 📊 Dataset Overview

- **Classes**: `2` → *Pandas*, *Bears*  
- **Dataset Type**: Image classification  
- **Data Format**: `.jpg` or `.png` images organized into folders per class  
  ```
  dataset/
  ├── train/
  │   ├── panda/
  │   └── bear/
  ├── test/
  │   ├── panda/
  │   └── bear/
  ```
- **Preprocessing Steps**:
  - Image resizing to uniform dimensions (e.g., 128×128 or 224×224)
  - Normalization of pixel values
  - Splitting dataset into training and testing sets
  - Data augmentation (rotation, flip, zoom) to prevent overfitting

---

## 🧠 About CNN Architecture

A **Convolutional Neural Network (CNN)** consists of the following key layers:

1. **Convolutional Layer** — extracts local features by applying learnable filters across the image.  
2. **Activation Function (ReLU)** — introduces non-linearity to enable complex pattern learning.  
3. **Pooling Layer** — reduces spatial dimensions and retains important features (typically using MaxPooling).  
4. **Fully Connected (Dense) Layers** — integrate extracted features and perform classification.  
5. **Output Layer** — uses *Softmax* activation for multi-class classification (here, 2 classes).

**Typical Model Flow:**
```
Input Image → Conv2D → ReLU → MaxPooling → Conv2D → ReLU → MaxPooling → Flatten → Dense → Output
```

---

## ⚙️ Workflow and Procedure

### 1️⃣ Importing Libraries
Essential libraries like `TensorFlow`, `Keras`, `NumPy`, `Matplotlib`, and `os` are imported for model creation and visualization.

### 2️⃣ Data Loading and Preprocessing
- The dataset is loaded using Keras’ `ImageDataGenerator`.
- Images are **resized**, **normalized**, and **split** into training and validation sets.
- Data augmentation (flip, rotation, zoom) is applied to enhance generalization.

### 3️⃣ Building the CNN Model
- The CNN is defined using `Sequential()` API.
- Several convolutional layers with `ReLU` activation and `MaxPooling2D` are stacked.
- Flatten and Dense layers are added before the final classification layer.
- The output layer uses **Softmax activation** to predict the class probabilities.

### 4️⃣ Model Compilation
- The model is compiled with:
  ```python
  optimizer = 'adam'
  loss = 'categorical_crossentropy'
  metrics = ['accuracy']
  ```

### 5️⃣ Model Training
- The model is trained using:
  ```python
  model.fit(train_data, validation_data=val_data, epochs=EPOCHS)
  ```
- Training accuracy and validation loss are tracked over epochs.

### 6️⃣ Model Evaluation
- The trained model is evaluated on the test dataset.
- Accuracy, loss, and confusion matrix are calculated.
- Visualizations show correctly and incorrectly classified images.

### 7️⃣ Model Prediction
- The model predicts the class of unseen images using:
  ```python
  model.predict(img)
  ```
- The class with the highest probability (Panda or Bear) is displayed.

---

## 📈 Model Evaluation

| Metric | Description |
|:--------|:-------------|
| **Training Accuracy** | Measures how well the model fits the training data |
| **Validation Accuracy** | Indicates the model’s ability to generalize |
| **Loss Curve** | Shows learning stability over epochs |
| **Confusion Matrix** | Displays correct vs. misclassified predictions |

Visualization plots include **accuracy and loss curves** to analyze training progress.

---

## 🏁 Results

- The CNN successfully differentiates between Pandas and Bears.  
- Achieved high accuracy on both training and validation datasets.  
- The model generalizes well after tuning hyperparameters like learning rate and epochs.

---

## 🚀 Future Improvements

- Use **transfer learning** with pretrained models (e.g., VGG16, ResNet50) for better accuracy.  
- Introduce more **data augmentation** for robustness.  
- Experiment with **dropout layers** to reduce overfitting.  
- Deploy the trained model as a **web app** using Flask or Streamlit.

---

## 💻 How to Run

```bash
# Clone this repository
git clone https://github.com/<your-username>/pandas-vs-bears-cnn.git

# Navigate into the project directory
cd pandas-vs-bears-cnn

# Install dependencies
pip install -r requirements.txt

# Run the Jupyter Notebook
jupyter notebook model.ipynb
```

---

## 📚 References
- [TensorFlow Keras Documentation](https://www.tensorflow.org/api_docs/python/tf/keras)
- [Deep Learning with Python — François Chollet](https://www.manning.com/books/deep-learning-with-python)
- [Image Classification with CNNs](https://www.tensorflow.org/tutorials/images/cnn)

---

**Author:** *Abhijith P V*  
**Field:** Deep Learning / Computer Vision  
**Tags:** `#CNN` `#ImageClassification` `#TensorFlow` `#DeepLearning` `#PandasVsBears`
