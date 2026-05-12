# Project 2: Advanced OCR & CNNs (Week 6)

This project focuses on enhancing the accuracy of Optical Character Recognition (OCR) systems by applying advanced image preprocessing and implementing deep learning architectures. The goal is to handle real-world document challenges—such as camera angles and noise—and build a Convolutional Neural Network (CNN) from scratch for handwritten digit recognition.

---

## 🎯 Project Goals

* 
**Perspective Correction**: Straighten skewed documents and fix photos taken at an angle.


* 
**Automatic Deskewing**: Implement algorithms to automatically detect and correct document rotation.


* 
**Noise Removal**: Use morphological operations (erosion, dilation, opening, closing) to clean low-quality scans.


* 
**Deep Learning**: Build, train, and evaluate a CNN on the MNIST dataset to achieve over **98% accuracy**.



---

## 🛠️ Setup Requirements

### 1. Library Installation

You will need several image processing and machine learning libraries:

```bash
pip install tensorflow keras opencv-python scikit-image imutils

```



### 2. Dataset

The project utilizes the **MNIST dataset**, which contains 60,000 training samples and 10,000 test samples of handwritten digits.

---

## 📂 Pipeline Components

### Part 1: Advanced Preprocessing

* 
**Perspective Transform**: Uses a four-point transform to map an angled document back into a top-down, bird's-eye view.


* 
**Deskewing**: Calculates the rotation angle of a document based on its pixel coordinates and corrects it using an affine transformation.


* 
**Morphological Ops**: Cleans text by removing small noise (Opening) or filling small holes in characters (Closing).



### Part 2: CNN Architecture

The digit recognition model is built using a sequential architecture with the following layers:

* 
**Convolutional Layers**: Two blocks (32 and 64 filters) to extract visual features using "relu" activation.


* 
**Pooling Layers**: `MaxPooling2D` to reduce spatial dimensions and focus on key features.


* 
**Regularization**: A **Dropout layer (0.5)** is used to prevent overfitting.


* 
**Output**: A Dense layer with **softmax** activation to classify the image into 10 categories (digits 0-9).



---

## 📊 Training & Performance

The model is trained using the **Adam optimizer** and **categorical crossentropy loss**.

* 
**Batch Size**: 128 


* 
**Epochs**: 10 


* 
**Target Accuracy**: 98%+ on the test set.



---

## 📄 Deliverables Checklist

* [ ] Perspective correction and deskewing functions.


* [ ] Demonstration of all 4 morphological operations.


* [ ] CNN model summary and training history plots.


* [ ] 98%+ accuracy on test predictions.


* [ ] Code hosted in `week6_advanced_ocr.ipynb`.
