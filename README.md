# 🤖 Introduction to AI Mini-Project Report

**📋 Project Information:**

[This information should also be included in the PDF report and presentation slides.]

* **📚 Course:** [Course Code] - Introduction to Artificial Intelligence  
* **📅 Term:** [Term - Year] (e.g., Term 1 - 2025-2026)  
* **🏫 Institution:** VNU-HUS (Vietnam National University - Hanoi University of Science)  
* **📝 Project Title:** [CNN for Cat–Dog Classification]  
* **📅 Submission Date:** 30/11/2025  
* **📄 PDF Report:** 📄 [Link to the PDF report in this repository]  
* **🖥️ Presentation Slides:** 🖥️ [Link to the presentation slides in this repository]  
* **📂 Repository:** 📁 Include code, data, and docs in this repo (or provide external links)

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
     1, Data split;
     2, SimCLR pretraining and finetuning;
     3, Finetune ResNet50(weights=IMAGENET_1K) + Distillation;
     4, Test the students.

### Chapter 3: Results & Analysis
**📊 Results & Discussion**
   - 📈 Main findings, performance metrics, and analysis

### Chapter 4: Conclusion
**✅ Conclusion & Future Work**
   - 🔭 Summary of contributions and suggestions for improvement

### References & Appendices
**📚 References**
   - MIT 6.S191 (2024): Convolutional Neural Networks  \url{https://www.youtube.com/watch?v=2xqkSUhmmXU}
   - T. Chen, S. Kornblith, M. Norouzi, and G. Hinton, ``A Simple Framework for Contrastive Learning of Visual Representations,'' in International Conference on Machine Learning (ICML), 2020.
   - SimCLR Lightly doc \url{https://docs.lightly.ai/self-supervised-learning/examples/simclr.html}
   - Hinton, Geoffrey E., Oriol Vinyals, and Jeff Dean, ``Distilling the Knowledge in a Neural Network.'' arXiv preprint arXiv:1503.02531, 2015.



---

## 📝 Submission Guidelines

### 📋 Requirements
- **Format:** 
  + 🖨️ The report must be typed and clearly formatted, exported as a PDF (recommended to use LaTeX).  
  + 🔁 A copy of the report must be stored in the GitHub repository corresponding to the project, two submitted on Canvas (one for the instructor and one for the TA (if any)), and two printed copies (one for the instructor and one for the TA (if any)). The same for presentation slides (no printed copies required).
- **Repository:** 🗂️ Include PDF report, slides, and all relevant code and materials. (If the size exceeds GitHub's limit, consider uploading to other platforms like Google Drive or Dropbox and put the link to the documentation)
- **Team Work:** 🤝 Ensure to acknowledge contributions from all team members
- **Code Documentation:** All code must be well-documented with:
  + 🧾 Clear comments explaining complex logic and algorithms  
  + 🧪 Function/method docstrings describing parameters, return values, and purpose  
  + 📘 README files for code modules explaining setup and usage  
  + 📝 Inline comments for non-obvious code sections

### ✅ Checklist Before Submission
- [X] ✅ Put X in the brackets to mark as complete  
- [ ] ✍️ Fill out all sections in this README template  
- [ ] 📄 Complete detailed PDF report following the structure above  
- [ ] 🎨 Follow instructor's formatting and content guidelines  
- [ ] ➕ Add project-specific sections as necessary  
- [ ] 🔍 Proofread for clarity, grammar, and technical accuracy  
- [ ] ⬆️ Upload PDF report, presentation slides, and code  
- [ ] 🧩 Ensure all code is properly documented with comments and docstrings  
- [ ] 🔗 Verify all links and references work correctly

---

*Mẫu cập nhật lần cuối: 🗓️ Tháng 7/2025*

