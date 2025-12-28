### Brain Tumor Classification using MRI Scans and Deep Learning
___

<br>
This repository contains a complete data science pipeline for classifying brain tumors from MRI scans. The project ranges from statistical hypothesis testing to building a high-performance deep learning model using transfer learning.

<br>

### 📋 Project Overview
___
The goal of this project is to accurately classify brain MRI images into four distinct categories:
- Glioma
- Meningioma
- Pituitary 
- TumorHealthy (No Tumor)

### 🧠 Methodology
___
1. Data ProcessingDataset: 
- Sourced from the [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/miadul/brain-tumor-mri-dataset).
- Balancing: Performed random sampling to ensure 400 images per class, preventing model bias.
- Pre-processing: Images were resized to 224x224 and normalized.
2. Statistical Analysis & Feature EngineeringBefore training, a new feature "Average Pixel Intensity" was generated to prove the separability of the classes.
    - Shapiro-Wilk Test: Confirmed non-normal distribution of the data ($p < 0.001$).
    - Mann-Whitney U Test: Confirmed a statistically significant difference between "Healthy" and "Tumor" groups ($p \approx 0$).
3. Deep Learning ArchitectureThe project utilizes the VGG16 model with **Transfer Learning**:
- Pre-trained weights from ImageNet.
- Custom Global Average Pooling and Dense layers.
- Early Stopping to ensure optimal training and prevent overfitting.

### 📊 Results
___ 
The model achieved an overall Accuracy of **90%**.

**Classification Performance
:** 
| Klasa | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: |
| **Healthy** | 0.96 | 0.94 | 0.95 |
| **Pituitary** | 0.91 | 0.96 | 0.94 |
| **Glioma** | 0.98 | 0.82 | 0.89 |
| **Meningioma** | 0.79 | 0.88 | 0.83 |

- **Insight**: The model is exceptionally good at identifying healthy tissue (0.95 F1-score) and pituitary tumors. The slight drop in precision for meningiomas is due to visual similarities with certain glioma structures.

### 🛠️ Requirements
___
This project requires Python 3.x and the dependencies listed in `requirements.txt`. 

To install everything at once, run:
```bash
pip install -r requirements.txt
```
### 🚀 How to Use
___
1. Clone the repository:
    ```bash
    git clone https://github.com/Nidzoki/brain-tumor-classification.git```
2. Ensure the dataset is placed in the correct directory (as specified in the notebook).
3. Open and run `brain_tumor_classification.ipynb`.

### 📚 References
___

- Ismael, S. S., & Mohammed, A. (2020): Brain tumor classification using ResNet.
- Abiwinanda, N., et al. (2019): Brain tumor classification using basic CNN architectures.
___
Author: nidzoki<br>
License: MIT