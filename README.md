# Quantum-Assisted Band Selection with SVM for Hyperspectral Image Classification


---

## 📌 Objective

This project presents a hyperspectral image classification pipeline that integrates:

* **Quantum-inspired spectral band importance estimation**
* **Classical machine learning using Support Vector Machines (SVM)**

The goal is to reduce spectral dimensionality while maintaining high classification accuracy.

---

## 📊 Dataset

* **Dataset:** Pavia University
* **Spatial Dimensions:** 610 × 340 pixels
* **Spectral Bands:** 103
* **Classes:** 9 (excluding background)

Each pixel is treated as an independent sample with 103 spectral features.

---

## ⚙️ Pipeline Overview

Raw Image → Flattening → Background Removal → Scaling → Quantum Band Importance → Band Selection → Rescaling → Train-Test Split → SVM Training → Evaluation → Full Image Prediction

---

## 🚀 Methodology

### 1. Data Loading

* Dataset loaded using `scipy.io`
* Extract hyperspectral cube and ground truth labels

### 2. Visualization

* Visualize ground truth label map
* Understand spatial distribution of classes

### 3. Data Preprocessing

**Flattening**

* Convert 3D hyperspectral cube → 2D matrix (pixels × bands)

**Background Removal**

* Remove samples where label = 0

---

### 4. Standard Scaling

* Apply `StandardScaler`

  * Mean = 0
  * Variance = 1
* Improves SVM performance

---

### 5. Quantum-Based Band Importance

#### Concept

Estimate importance of each spectral band based on its influence on a quantum-encoded state.

#### Procedure

* Normalize input vector: `x → x / ||x||`
* Pad vector to nearest power of 2
* Encode into quantum state: `|ψ(x)> = Σ xᵢ |i>`
* Compute baseline output
* Perturb one band: `x[i] → x[i] + ε`
* Measure change in output
* Repeat across samples and average

#### Output

* Importance score for each spectral band

---

### 6. Band Selection

* Select top **k = 50** bands
* Dimensionality reduction: **103 → 50 (51.5%)**

---

### 7. Feature Rescaling

* Apply `StandardScaler` again after selection

---

### 8. Train-Test Split

* Stratified split to preserve class distribution

---

### 9. SVM Model

**Why SVM?**

* Effective in high-dimensional spaces
* Handles non-linear decision boundaries

**Hyperparameter Tuning (GridSearchCV)**

* `C`: Regularization parameter
* `gamma`: Kernel coefficient
* Kernel: **RBF**

---

### 10. Evaluation

**Metrics**

* Accuracy
* Confusion Matrix
* Classification Report:

  * Precision
  * Recall
  * F1-score

---

### 11. Full Image Classification

* Predict labels for all pixels
* Reconstruct classification map

---

### 12. Visualization

* Compare predicted map with ground truth

---

## 📈 Results

* **Overall Accuracy:** 91.67%
* **Weighted F1 Score:** 0.92
* **Band Reduction:** 51.5%

---

## 🔗 Reproducibility

Google Colab:
https://colab.research.google.com/drive/1pxq5X1xaqULCJInES7yQSdjf5BnoTB8q

---

## ✨ Key Highlights

* Quantum-inspired feature importance estimation
* Effective dimensionality reduction
* Optimized SVM classifier
* End-to-end classification pipeline
* High accuracy (~91%)

---

## 📌 Conclusion

This work demonstrates that quantum-inspired techniques can effectively identify informative spectral bands while classical SVM ensures robust classification. The hybrid approach achieves high performance with reduced dimensionality, making it suitable for hyperspectral image analysis.
