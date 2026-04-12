[![UNIE Universidad](https://www.fsie.es/documentos/imagenes/Ventajas_afiliados/2024/UNIE/Brand_Unie_Vertical_Positive.png)](https://www.universidadunie.com/programas/master-formacion-permanente-virtual-inteligencia-artificial-deep-learning)

# Máster en Inteligencia Artificial y Deep Learning

## Machine Learning — Neural Networks: Perceptron & CNN

Asignatura Machine Learning del Máster en IA y Deep Learning de UNIE. Practical Lab: Introduction to Neural Networks with PyTorch.

---

## Summary

Two end-to-end notebooks covering the fundamentals of neural networks using PyTorch — from the single perceptron to convolutional networks applied to medical image classification.

### Lab 1 — Perceptron & MLP (`introduction_perceptron.ipynb`)

Introduction to PyTorch tensors and the perceptron model, applied to binary classification on the synthetic `make_moons` dataset.

- PyTorch tensor fundamentals: creation, operations, autograd, NumPy interop
- Perceptron theory: weights, biases, activation functions (Sigmoid, ReLU, Tanh, Step)
- Single-layer perceptron (`nn.Module`) with SGD
- Multi-layer perceptron (MLP) with ReLU hidden layers and Adam optimizer
- Decision boundary visualisation showing linear vs non-linear separation

### Lab 2 — Convolutional Neural Networks (`introduction_cnn.ipynb`)

CNN theory and practice applied to the [Chest X-Ray Pneumonia dataset](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia) (5,863 images, binary classification).

- CNN theory: convolution, pooling, feature maps, BatchNorm, Dropout
- Exploratory data analysis and pixel intensity distributions
- Data augmentation and `WeightedRandomSampler` for class imbalance
- Custom 3-block CNN trained from scratch
- Transfer learning with fine-tuned ResNet-18
- Evaluation: accuracy, classification report, confusion matrix, ROC-AUC
- Interpretability: misclassified images, first-layer filters, feature map hooks

---

## Project Structure

```
datasets/
└── chest_xray/          # Chest X-Ray dataset (CC BY 4.0) — download from Kaggle
    ├── train/
    │   ├── NORMAL/
    │   └── PNEUMONIA/
    ├── val/
    │   ├── NORMAL/
    │   └── PNEUMONIA/
    └── test/
        ├── NORMAL/
        └── PNEUMONIA/
src/
├── introduction_perceptron.ipynb
└── introduction_cnn.ipynb
```

## Quick Start

```bash
# Create and activate environment
python3 -m venv venv
source venv/bin/activate      # macOS/Linux
venv\Scripts\activate         # Windows

# Install dependencies
pip install -r requirements.txt

# Download dataset (requires Kaggle API)
kaggle datasets download -d paultimothymooney/chest-xray-pneumonia -p datasets/
unzip datasets/chest-xray-pneumonia.zip -d datasets/chest_xray/

# Run notebooks
jupyter notebook src/
```

---

## Disclaimer

Provided as is, for academic use only.

## Copyright and License

- Notebooks: [MIT License](LICENSE)
- Chest X-Ray data: [CC BY 4.0](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia) — Kermany et al., Cell 2018
- make_moons data: BSD 3-Clause (scikit-learn)

Developed and tested on Python ≥ 3.10. Dependencies: see `requirements.txt`.
