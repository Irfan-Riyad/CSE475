# Medicinal Plant Diagnosis using Deep Learning

## 📄 Project Overview
This project presents a comprehensive study on the diagnosis of medicinal plant diseases using advanced Deep Learning techniques. We utilize the **AI-MedLeafX** dataset to evaluate both Supervised Learning benchmarks and state-of-the-art Self-Supervised Learning (SSL) frameworks.

Our research focuses on four specific medicinal plant species—*Cinnamomum camphora*, *Terminalia Chebula*, *Moringa Oleifera*, and *Azadirachta Indica*—and identifies phytopathological conditions such as Bacterial Spot, Shot Hole, and Yellow Leaf Disease.

---

## 👥 Contributors

| Name | Student ID |
| :--- | :--- |
| **Md Riyad Hossain** | 2022-3-60-156 |
| **Mehjarin Aklima Jerin** | 2022-3-60-325 |
| **Rafid Rahman** | 2022-2-60-116 |
| **Ishraque Manzur** | 2021-3-60-130 |

---

## 📂 Repository Structure

This repository is organized as follows:

* **`Code/`**: Contains the source code for data preprocessing, model training, and evaluation scripts.
* **`Reports/`**: Detailed performance reports, and architectural diagrams (e.g., DINOv2 analysis).

---

## 🍃 Dataset: AI-MedLeafX

The dataset comprises **10,858 original images** and **65,178 augmented images**. It is curated to ensure diversity across healthy and diseased samples.

**🔗 [Access Dataset on Mendeley Data](https://data.mendeley.com/datasets/zz7r5y4dc6/1)**

### Class Distribution
| Plant Species | Condition | Image Count |
| :--- | :--- | :--- |
| **Camphor** | Healthy, Bacterial Spot, Shot Hole | 2,396 |
| **Haritaki** | Healthy, Bacterial Spot, Shot Hole | 2,421 |
| **Sojina** | Healthy, Bacterial Spot, Yellow Leaf | 2,478 |
| **Neem** | Healthy, Shot Hole, Powdery Mildew, Yellow Leaf | 3,563 |
| **Total** | | **10,858** |

---

## 📈 Supervised Learning Benchmarks

We evaluated multiple pre-trained architectures across nine distinct **Train-Test splits** (10:90 to 90:10) to determine model robustness.

| Model Architecture | Best Accuracy (%) | Optimal Split | Remark |
| :--- | :--- | :--- | :--- |
| **InceptionV3** | **98.13%** | **70 : 30** | **🏆 Best Model** |
| **VGG19** | **97.51%** | **90 : 10** | **Strong Contender** |
| DenseNet201 | 92.97% | 70 : 30 | — |
| NASNet | 89.96% | 90 : 10 | — |
| VGG16 | 89.87% | 80 : 20 | — |
| ResNet50 | 89.04% | 90 : 10 | — |
| EfficientNet (B5) | 78.91% | 90 : 10 | — |
| MobileNetV2 | 75.51% | 80 : 20 | — |

---

## 🧠 Self-Supervised Learning (SSL) Experiments

To enhance feature representation and label efficiency, we experimented with several SSL frameworks. **Vision Transformer (ViT)** backbones were utilized for most models to leverage global attention mechanisms, replacing the initial Inception backbones which showed lower convergence in SSL tasks.

### SSL Performance Metrics

| Model | Accuracy (%) | Downstream Classifier | Resources |
| :--- | :--- | :--- | :--- |
| **DINOv2** | **98.07%** | **SVM** | [📄 Report](https://github.com/Irfan-Riyad/CSE475/blob/main/Reports/SLL_Models_Report/Dinov2_Report.pdf) \| [📊 Diagram](https://github.com/Irfan-Riyad/CSE475/blob/main/Reports/SLL_Models_Report/Diagrams/Diagrams.pdf) |
| **MoCo v3** | 94.98% | SVM | *Coming Soon* |
| **SimCLR** | 87.85% | SVM | *Coming Soon* |
| **BYOL** | 85.48% | MLP | *Coming Soon* |
| **MEW** | 82.41% | MLP | *Coming Soon* |

**Finding:** DINOv2 (ViT backbone) achieved the highest accuracy (98.07%), demonstrating the effectiveness of transformer-based self-supervised learning for this domain.
