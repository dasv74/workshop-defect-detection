## Defect Classification in Industrial Images

This notebook investigates supervised image classification methods for defect detection in industrial components.

#### Objectives
- Evaluate multiple feature extraction methods:
  - Classical algorithms: Discrete Cosine Transform (DCT), Histogram of Oriented Gradients (HOG), Color Moments (CM)
  - Pre-trained deep-learning models: DINOv2, DINOv3, ResNet18, ResNet50, VGG16, VGG19
- Compare classification methods: Logistic Regression, Random Forest, Support Vector Machine (SVC), K-Means
- Analyze robustness across different datasets

#### Experimental Scenarios of Classification

- **Scenario 1 — Binary classification** — Classes: *good* vs *bad*

- **Scenario 2 — Multi-class with normal class** — Classes: *good* + individual defect types

- **Scenario 3 — Defect-only classification** — Classes: defect types only (excluding *good*, less images)

#### Methodology

- Images are processed per component category independently
- Feature extraction is applied to all samples according the scenario
- A train/test split is defined per scenario
- A classifier is trained on extracted features
- Evaluation is performed using: Accuracy, Computation time, Confusion Matrix, tSNE

#### Dataset
- Source: MVTec Anomaly Detection (Kaggle)
- 5 different components: tile, carpet, cable, leather, hazelnut

```
dataset/
|-- component-defect-classes/
|  |-- bad/
|  | |-- defect1/
|  | | |-- 000.png, 001.png, ...
|  | |-- defect2/
|  |-- good/
|  | |-- 000.png, 001.png, ...
|  |-- bad-masks/ (not used)

```
