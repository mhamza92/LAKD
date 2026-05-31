##LA-KD: Lesion-Aware Knowledge Distillation for Plant Disease Classification
##Overview

LA-KD is a lesion-aware knowledge distillation framework designed for efficient plant disease classification in complex real-field environments. The framework employs an ensemble teacher network to transfer disease-relevant knowledge into a lightweight student network through lesion-aware supervision, enabling accurate and computationally efficient deployment on edge devices.

##Key Features
Ensemble teacher network combining CNN and Swin Transformer V2.
Lightweight student network (RTDF-Net).
Lesion-Aware Knowledge Distillation (LA-KD).
Lesion-Weighted Knowledge Distillation (LWKD).
Lesion Patch-Level Contrastive Distillation (LPCD).
Designed for consumer-oriented agricultural edge applications.
##Repository Structure
LA-KD/
│
├── Teacher/
│   └── Teacher network implementation
│
├── Student/
│   └── RTDF-Net implementation
│
├── Loss/
│   └── LA-KD loss functions
│
├── README.md
└── requirements.txt
##Framework

The proposed framework consists of:

##Teacher Network

The teacher model combines:

Local Feature Extractor (CNN)
Global Feature Extractor (Swin Transformer V2)

The extracted features are fused to generate discriminative disease representations.

##Student Network (RTDF-Net)

RTDF-Net is a lightweight architecture containing:

Tri-Domain Fusion (TDF)
Weighted Contextual Routing (WCR)
Cosine Margin Head

The network is designed for efficient deployment on resource-constrained devices.

##LA-KD Loss

The total training objective is:

[
L = \omega_S L_{CE} + \omega_L L_{LAKD} + \omega_C L_{LPCD}
]

where:

(L_{CE}): Cross-Entropy Loss
(L_{LAKD}): Lesion-Aware Knowledge Distillation Loss
(L_{LPCD}): Lesion Patch-Level Contrastive Distillation Loss

Default weights:

ωS = 0.5
ωL = 0.3
ωC = 0.2
