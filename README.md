# Early Detection of Alzheimer's Disease  
Using Deep Learning on MRI Scans

This project focuses on building an automated system capable of early detection of Alzheimer's disease using brain MRI images. The solution leverages deep learning models, extensive preprocessing pipelines, and a deployment-ready Streamlit application.

This work was developed as the final project for the Samsung Innovation Campus program.

---

## Table of Contents
1. Project Overview  
2. Problem Statement  
3. Dataset  
4. Data Preparation  
5. Data Preprocessing  
6. Modeling Approach  
7. Model Evaluation and Comparison  
8. Deployment  
9. How to Run the Application  
10. Project Structure  
11. Future Work  
12. Team Members  

---

## 1. Project Overview
Early detection of Alzheimer's disease can significantly improve treatment outcomes and patient quality of life. This project builds a deep learning system capable of classifying MRI brain scans into three categories:

- Non-Demented  
- Very Mild Dementia  
- Mild Dementia  

The final selected model is based on ResNet-50 due to its reliable generalization and stable performance.

---

## 2. Problem Statement
Alzheimer’s disease is one of the most widespread and devastating neurodegenerative disorders worldwide. It impacts millions of individuals annually and places a heavy emotional, financial, and social burden on families and healthcare systems.

Detecting the disease at an early stage is essential, as it allows physicians to take timely measures that slow down cognitive decline and improve long-term outcomes.

---

## 3. Dataset
The dataset consists of 85,949 MRI images, distributed across three classes:

- Non-Demented: 67,222 images  
- Very Mild Dementia: 13,725 images  
- Mild Dementia: 5,002 images  

The images are grayscale MRI scans containing structural information about different brain regions which help in identifying dementia-related abnormalities.

---

## 4. Data Preparation
Multiple preprocessing steps were applied to ensure high-quality input for the model:

- Image resizing and normalization  
- Handling class imbalance  
- Splitting into training, validation, and testing sets  
- Efficient data loading using data generators  

---

## 5. Data Preprocessing
The preprocessing pipeline includes:

- Contrast adjustments  
- Controlled noise injection  
- ImageNet mean subtraction for ResNet preprocessing  
- Ensuring consistency between training and inference inputs  

---

## 6. Modeling Approach

Two deep learning architectures were explored:

### DenseNet-121  
- ImageNet-pretrained backbone  
- Head-only training (freezing the backbone initially)  
- Dense connectivity and feature reuse  
- Weighted cross-entropy loss to address class imbalance  
- Custom callback to monitor weighted F1-score  

### ResNet-50  
- End-to-end training  
- Skip connections to mitigate vanishing gradients  
- More stable and consistent generalization  
- Class-weighted training for balanced learning  

---

## 7. Model Evaluation and Comparison

### DenseNet-121  
The model achieved extremely high recall on the Mild Dementia class, which indicates possible data leakage or overfitting. This makes it unreliable for real medical usage.

### ResNet-50  
The ResNet model demonstrated:

- Reliable generalization  
- Good balance across all classes  
- Weighted F1-score of 0.91  
- Strong recall for Mild Dementia  

This made ResNet-50 the final chosen model for deployment.

---

## 8. Deployment
The final system is deployed using a Streamlit application, which handles:

- Model loading  
- MRI image upload  
- Preprocessing  
- Real-time classification  
- Displaying predictions and confidence scores  

---

## 9. How to Run the Application

### Install dependencies
```bash
pip install -r requirements.txt
