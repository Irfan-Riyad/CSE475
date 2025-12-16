| Name                     | Student ID       |
|-------------------------|------------------|
| Md Riyad Hossain        | 2022-3-60-156    |
| Mehjarin Aklima Jerin   | 2022-3-60-325    |
| Rafid Rahman            | 2022-2-60-116    |
| Ishraque Manzur         | 2021-3-60-130    |



# Medicinal Plant Diagnosis Dataset

## Description

The **Medicinal Plant Diagnosis** dataset is a curated collection of 10,858 original images and 65,178 augmented images of medicinal plant leaves, categorized into healthy and diseased conditions. The dataset primarily focuses on four medicinal plant species—**Cinnamomum camphora**, **Terminalia Chebula**, **Moringa Oleifera**, and **Azadirachta Indica**—and covers common leaf diseases such as **Bacterial Spot**, **Shot Hole**, **Powdery Mildew**, and **Yellow Leaf Disease**.

## Categories

1. **Camphor_Healthy Leaf**: 800 images
2. **Camphor_Bacterial Spot**: 801 images
3. **Camphor_Shot Hole**: 795 images
4. **HariTaki_Bacterial Spot**: 803 images
5. **HariTaki_Healthy Leaf**: 816 images
6. **HariTaki_Shot Hole**: 802 images
7. **Sojina_Healthy Leaf**: 860 images
8. **Sojina_Bacterial Spot**: 804 images
9. **Sojina_Yellow Leaf**: 814 images
10. **Neem_Healthy Leaf**: 1021 images
11. **Neem_Shot Hole Leaf**: 834 images
12. **Neem_Powdery Mildew**: 854 images
13. **Neem_Yellow Leaf**: 854 images

**Total images**: 10,858

[AI-MedLeafX Dataset on Mendeley Data](https://data.mendeley.com/datasets/zz7r5y4dc6/1)

## 📈 Performance Overview

We evaluated several state-of-the-art pre-trained deep learning models to identify the optimal architecture for this specific task.

### Tested Architectures (with Best Results)

| Model | Best Accuracy (%) | Train : Test Split | Remark |
|------|------------------|--------------------|--------|
| DenseNet201 | 92.97 | 70 : 30 | — |
| EfficientNet (B5) | 78.91 | 90 : 10 | — |
| **InceptionV3** | **98.13** | **70 : 30** | **Winner** |
| MobileNetV2 | 75.51 | 80 : 20 | — |
| NASNet | 89.96 | 90 : 10 | — |
| VGG16 | 89.87 | 80 : 20 | — |
| ResNet50 | 89.04 | 90 : 10 | — |
| **VGG19** | **97.51** | **90 : 10** | **Strong Contender** |


To ensure robustness, each model was tested across a spectrum of data distributions. We utilized nine distinct **Train-Test splits**:
* 10:90 through 90:10 (in 10% increments)

### Key Findings
While both **Inception** and **VGG19** showed strong performance, **Inception** proved to be the most effective model for our dataset.

### Self-Supervised Learning (SSL) Experiments  
**Models:** DINOv2 · MAE · MoCo v3 · BYOL · SimCLR

To improve overall model accuracy, we experimented with multiple **self-supervised learning (SSL)** methods and backbone configurations. Our objective was to strengthen feature representations through iterative experimentation rather than relying on a single training strategy.

#### Experimental Setup and Findings

- **SimCLR with an Inception backbone** was tested first but produced very low accuracy and was not effective for this dataset.
- To further enhance representation learning, **Vision Transformer (ViT)** backbones were used for all SSL models **except SimCLR**.
- Multiple feature extraction and fine-tuning strategies were evaluated across all SSL approaches.

## Self-Supervised Model Performance

| Model | Accuracy (%) | Downstream Classifier | Evaluation Report | Diagram |
|------|-------------|----------------------|-------------------|---------|
| **MoCo v3** | 94.98% | SVM | Coming Soon | Coming Soon |
| **SimCLR** | 87.85% |  SVM | Coming Soon | Coming Soon |
| **MEW** | 82.41% | MLP  | Coming Soon | Coming Soon |
| **BYOL** | 85.48% | MLP  | Coming Soon | Coming Soon |
| **DINOv2** | 98.07% | SVM | [View Report](https://github.com/Irfan-Riyad/CSE475/blob/main/Reports/SLL_Models_Report/Dinov2_Report.pdf) | [View Diagram](https://github.com/Irfan-Riyad/CSE475/blob/main/Reports/SLL_Models_Report/Diagrams/Diagrams.pdf) |



#### Best Result

Among all SSL models, **DINOv2 with a ViT backbone** achieved the **highest accuracy of 98.07%**, making it the best-performing SSL method in our experiments.

These results demonstrate the strong effectiveness of transformer-based self-supervised representations for the Medicinal Plant Diagnosis task.

