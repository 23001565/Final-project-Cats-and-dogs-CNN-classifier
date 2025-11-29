# 🤖 Introduction to AI Mini-Project Report

**📋 Project Information:**

* **📚 Course:** MAT3508 - Introduction to Artificial Intelligence  
* **📅 Term:** Term 1 - 2025-2026 
* **🏫 Institution:** VNU-HUS (Vietnam National University - Hanoi University of Science)  
* **📝 Project Title:** CNN for Cat–Dog Classification  
* **📅 Submission Date:** 30/11/2025  
* **📄 PDF Report:** 📄 [Link to the PDF report in this repository]  
* **🖥️ Presentation Slides:** 🖥️ [Link to the presentation slides in this repository]  
* **📂 Repository:** https://drive.google.com/drive/folders/1eoQ2REdIvF-qhs9Ozx2E0LV29fD3ZTvc?usp=drive_link

**👥 Team Members:**

| 👤 Name           | 🆔 Student ID        | 🐙 GitHub Username   | 🛠️ Contribution |
|------------------|---------------------|---------------------|----------------------|
| Hồ Huyền Trang   |     23001565         |       23001565       |      All           |

---

## 📑 Report Structure Overview

### Chapter 1: Introduction
**📝 Executive Summary**
  This project explores how self-supervised contrastive learning (SimCLR) and knowledge distillation (KD) can enhance the performance of a lightweight CNN (MobileNetV2 trained from scratch) on the classic cats vs. dogs binary classification task. The work focuses on achieving strong performance under limited computational resources and minimal labeled data, demonstrating how modern training strategies can compensate for model size and data constraints.

**❓ Problem Statement**
   Large deep learning models require heavy computation, long training times, and abundant labeled data, making them difficult to deploy in resource-constrained settings. In contrast, many real-world applications need lightweight, fast, and easily deployable models, especially when labeled data is limited.
This project addresses these challenges by exploring how techniques like SimCLR and knowledge distillation can improve the performance of a lightweight CNN while reducing dependence on computation and labeled data.

### Chapter 2: Methodology & Implementation
**⚙️ Methodology**
   - 🔍 Description of the approach, theoretical foundation, algorithms, and data used
   - CNNs extract spatial features from images using convolutional filters and hierarchical representations, enabling efficient and accurate image classification.
   - SimCLR: Self-supervised contrastive learning improves feature representations without labels by maximizing similarity between augmented views of the same image.
   - Knowledge Distillation (KD): A larger teacher model guides the lightweight CNN via softened outputs, improving accuracy while keeping the model efficient.
   - Data: 3 unlabeled train sets (10 000/6000/3000), 1 finetune (420), 1 validation (180), 1 test (5000)
     
**💻 Implementation**
   - 🧩 Description of the system, tools, and code structure
   - Run on Google Colab free tier, training is done mostly on GPU
   - Libraries:
     + torchvision.models for MobileNetV2 and ResNet50,
     + lightly module installed for SimCLR augmentation and loss function (NT-Xent),
     + loss function for KD is composed of multiple functions (CE, softmax, log_softmax, kl_div) from torch.nn.functional
   - Code structure:
     + SimCLR pretraining and finetuning;
     + Finetune ResNet50(weights=IMAGENET_1K) + Distillation;
     + Test the models.

### Chapter 3: Results & Analysis
**📊 Results & Discussion**
   Experimental results show that a MobileNetV2 student trained purely via knowledge distillation reaches — and sometimes exceeds — the performance of one initialized with SimCLR pretraining, while requiring significantly less training time.

### Chapter 4: Conclusion
**✅ Conclusion & Future Work**
   - 🔭 Summary of contributions and suggestions for improvement
   - Contributions: demonstrate the effectiveness of the lightweight CNN model MobileNetV2 and the 2 training techniques, how they enhance model performance under constrained environment.
   - Further experiments: Hyperparameter Tuning, Model Variations, Richer Distillation, Adaptivity.

### References & Appendices
**📚 References**
   - MIT 6.S191 (2024): Convolutional Neural Networks  \url{https://www.youtube.com/watch?v=2xqkSUhmmXU}
   - T. Chen, S. Kornblith, M. Norouzi, and G. Hinton, ``A Simple Framework for Contrastive Learning of Visual Representations,'' in International Conference on Machine Learning (ICML), 2020.
   - SimCLR Lightly doc \url{https://docs.lightly.ai/self-supervised-learning/examples/simclr.html}
   - Hinton, Geoffrey E., Oriol Vinyals, and Jeff Dean, ``Distilling the Knowledge in a Neural Network.'' arXiv preprint arXiv:1503.02531, 2015.



---


