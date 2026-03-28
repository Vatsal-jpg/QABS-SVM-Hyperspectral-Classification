## Quantum-Assisted Band Selection with SVM for Hyperspectral Image Classification

This repository presents a novel Quantum-Assisted Band Selection (QABS) framework for hyperspectral image classification. The approach leverages quantum state encoding and perturbation-based importance scoring to identify the most informative spectral bands, which are then used to train an optimized Support Vector Machine (SVM) classifier.

The proposed method reduces the spectral dimensionality from 103 to 50 bands while achieving an overall classification accuracy of 91.67% on a standard hyperspectral benchmark dataset.

### Key Features
- Quantum-inspired band importance scoring using amplitude perturbation
- Dimensionality reduction with preservation of spectral interpretability
- Optimized SVM with RBF kernel (C=300, gamma=0.01)
- Achieves high classification performance with reduced features

### Results
- Overall Accuracy: 91.67%
- Weighted F1 Score: 0.92
- Band Reduction: 51.5%

### Reproducibility
The full implementation is available via:
- Google Colab: https://colab.research.google.com/drive/1pxq5X1xaqULCJInES7yQSdjf5BnoTB8q

### Future Work
- Deployment on real quantum hardware
- Extension to additional hyperspectral datasets
- Integration with quantum kernel methods
