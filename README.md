---

# Multi-Cancer Image Classification

This project explores deep learning techniques to classify images across **8 types of cancer** using three model architectures:

* **Custom Convolutional Neural Network (CNN)**
* **MobileNetV2 (Transfer Learning)**
* **ResNet50 (Transfer Learning)**

Through iterative experiments, we studied how **data augmentation, class imbalance handling, and hyperparameter tuning** impact model performance.

---

## 📂 Dataset

* Total images: **130,002**
* Channels: **RGB (3 channels)**
* Classes (8 types of cancer):

  * Cervical Cancer
  * Lung and Colon Cancer
  * Brain Cancer
  * Lymphoma
  * Oral Cancer
  * Kidney Cancer
  * Breast Cancer
  * Acute Lymphoblastic Leukemia (ALL)

---

## 🔬 Exploratory Data Analysis (EDA)

* **Class imbalance** detected → some classes >25k samples, others <10k.
* **Image quality analysis**:

  * Brightness & contrast distributions
  * Blur detection using **Laplace Variance** & **Tenengrad Score**
* **Outlier detection** using the **ITR Method** with box plots.

---

## 🏗️ Methodology

* Models tested: Custom CNN, MobileNetV2, ResNet50
* Training pipeline included:

  * **Adam optimizer**
  * **ReLU activations**
  * **Batch Normalization**
  * **Dropout regularization**
  * **Early Stopping**
* Output layer: **Softmax** for multi-class classification

---

## 📊 Model Training

We trained models in **5 stages**:

1. **Small subset (\~5k images)** – baseline performance.
2. **Larger subset (\~75k images)** – improved stability.
3. **Larger subset + Data Augmentation** – better generalization.
4. **Augmentation + Class Imbalance Handling** – tested class-weighting & oversampling.
5. **Grid Search** – optimized learning rate & dropout.

---

## 📈 Results

| Model           | Best Validation Accuracy | Best Test Accuracy | Notes                                                            |
| --------------- | ------------------------ | ------------------ | ---------------------------------------------------------------- |
| **CNN**         | 97.89%                   | 99.08%             | Needs more tuning, stable with augmentation + imbalance handling |
| **MobileNetV2** | 98.80%                   | 99.30%             | Most stable, best real-world applicability                       |
| **ResNet50**    | 99.15%                   | 99.45%             | Possible data leakage – requires further investigation           |

* **Best overall model**: **MobileNetV2** (stable, low loss, robust generalization)
* **ResNet50** achieved near-perfect results but showed signs of data leakage.

---

## 🚀 Future Work

* Investigate **data leakage in ResNet50**.
* Improve **CNN calibration** and loss stability.
* Explore **other pretrained models** (EfficientNet, DenseNet, Vision Transformers).

---

## 📚 References

* [Multi-Cancer Dataset (Kaggle)](https://www.kaggle.com/datasets/obulisainaren/multi-cancer)
* Automating cancer diagnosis with deep learning (Nature, 2024)
* Skin cancer detection using deep learning – Review (Diagnostics, 2023)
* Blur image detection using Laplacian operator (IEEE)


---

✨ *This project was built as part of AML 3104 coursework (submitted August 15, 2025).*

---

Would you like me to also add a **“How to Run” section** with setup instructions (e.g., Python version, dependencies, training script), or should I keep it as a research-style README?
