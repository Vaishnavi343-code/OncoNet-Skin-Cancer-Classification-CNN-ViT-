# OncoNet-Skin-Cancer-Classification-CNN-ViT-
# OncoNET: Skin Lesion Classification
**Mid-Term Project | WIDS 5.0**

## Poject Overview
This project focuses on building and evaluating deep learning models to classify skin lesions into diagnostic categories using the **ISIC/HAM10000 dataset**. The project compares a custom-built CNN architecture against a state-of-the-art pre-trained ResNet-50 model, while exploring conceptual differences between Convolutional and Transformer-based vision architectures.

---

##  Tasks & Implementation

### Task 1: Baseline CNN (From Scratch)
* **Architecture:** A 3-layer Sequential CNN with ReLU activations and Max-Pooling.
* **Goal:** Establish a baseline for performance without pre-existing visual knowledge.

### Task 2: Transfer Learning (ResNet-50)
* **Architecture:** Pre-trained ResNet-50 with a modified fully connected head for 7-class classification.
* **Goal:** Leverage feature hierarchies learned from ImageNet to improve diagnostic accuracy.



### Task 3: Transformer Insight (Exploratory)
* **Method:** Patch-based image representation.
* **Insight:** Visualized how images are divided into fixed-size patches (visual tokens), contrasting the **global** receptive field of Transformers with the **local** spatial bias of traditional CNNs.



---

##  Results & Performance

| Metric | Baseline CNN (Task 1) | ResNet-50 (Task 2) |
| :--- | :--- | :--- |
| **Validation Accuracy** | **74%** | **86%** |
| **Training Speed** | Slower Convergence | Rapid Convergence |
| **Feature Extraction** | Learned from scratch | Fine-tuned from ImageNet |

### Analysis
The **12% jump in accuracy** with ResNet-50 demonstrates the efficiency of **Transfer Learning** in medical imaging. While the baseline CNN successfully identified basic edges and colors, ResNet-50 was significantly more robust in identifying complex, high-level features necessary to distinguish malignant Melanoma from benign Nevi.



---

##  Key Insights
* **Local vs. Global:** CNNs excel at capturing local textures (skin grain/irregular borders), whereas the Transformer-inspired patch analysis illustrates a path toward capturing global symmetry and structural relationships across the entire lesion.
* **Clinical Impact:** High **Recall** (Sensitivity) is prioritized in this model to ensure that malignant cases are not missed, which is life-critical in dermatological AI applications.

---

##  Technical Stack
* **Framework:** PyTorch
* **Hardware:** Google Colab T4 GPU
* **Dataset:** HAM10000 (Skin Cancer MNIST)
* **Libraries:** `torch`, `torchvision`, `pandas`, `scikit-learn`, `matplotlib`
