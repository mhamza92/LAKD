# LA-KD: Lesion-Aware Knowledge Distillation for Plant Disease Classification

## Overview

LA-KD is a novel lesion-aware knowledge distillation framework designed for accurate and efficient plant disease classification under complex real-world conditions. The framework leverages a powerful ensemble teacher network to transfer disease-relevant knowledge to a lightweight student network through lesion-aware supervision, enabling high recognition accuracy while maintaining computational efficiency for deployment on resource-constrained edge devices.

## Key Features

* Ensemble teacher architecture (LGF-Net) combining CNN and Swin Transformer V2 representations.
* Lightweight student network (RTDF-Net) for real-time inference.
* Lesion-Aware Knowledge Distillation (LA-KD) for disease-focused knowledge transfer.
* Designed for practical deployment in consumer-oriented agricultural applications.

## Dataset

The proposed framework was evaluated on publicly available plant disease datasets containing images collected under real-world agricultural conditions.

### Supported Datasets

* Durian Leaf Image Dataset (DLID): "Thanh Truong, Nguyen; Xuan Linh, Nguyen; Thang, Cap Pham Dinh; Tuong, Le (2025), “A Durian Leaf Image Dataset of Common Diseases in Vietnam for Agricultural Diagnosis ”, Mendeley Data, V4, doi: 10.17632/pxzvksbwnj.4"
* Sugarcane Leaf Disease Dataset (SCLD): "Daphal, Swapnil; Koli, Sanjay (2022), “Sugarcane Leaf Disease Dataset”, Mendeley Data, V1, doi: 10.17632/9424skmnrk.1"

## Framework

The proposed framework consists of three major components: an ensemble teacher network, a lightweight student network (RTDF-Net), and the proposed lesion-aware knowledge distillation strategy.

### Teacher Network

The teacher model integrates complementary feature representations from:

* Local Feature Extractor (CNN)
* Global Feature Extractor (Swin Transformer V2)

The extracted local and global representations are adaptively fused to generate discriminative disease-aware features that guide the student network.

### Student Network (RTDF-Net)

RTDF-Net is a lightweight architecture specifically designed for plant disease classification on edge devices. It consists of:

* Tri-Domain Fusion (TDF)
* Weighted Contextual Routing (WCR)
* Cosine Margin Classification Head

The network achieves an effective balance between classification accuracy and computational efficiency.

### LA-KD Loss

The overall training objective is defined as:

$$[
L = \omega_S L_{CE} + \omega_L L_{LAKD} + \omega_C L_{LPCD}
]$$

where:

* $(L_{CE})$: Cross-Entropy Loss
* $(L_{LAKD})$: Lesion-Aware Knowledge Distillation Loss
* $(L_{LPCD})$: Lesion Patch-Level Contrastive Distillation Loss

Default loss weights:

* $(\omega_S = 0.5)$
* $(\omega_L = 0.3)$
* $(\omega_C = 0.2)$

## Applications

* Plant disease diagnosis
* Precision agriculture
* Mobile and edge AI systems
* Smart farming solutions
* Resource-constrained agricultural monitoring platforms


```
