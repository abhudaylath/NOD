# 🧠 Cooperative Novel Object Detection (NOD)

**Transforming closed-set detectors into open-set vision systems using foundational models**

---

## 🚀 Overview

This project introduces a **training-free**, plug-and-play pipeline that upgrades existing object detectors like **Mask-RCNN** into **open-set object detectors**. It leverages powerful pre-trained foundational models—**CLIP**, **SAM**, and **GDINO**—to detect both **known** and **novel object categories** without requiring **any additional training or annotations**.

---

## 📈 Highlights

- 🔍 **17.42 mAP** on novel classes and **42.08 mAP** on known classes (LVIS dataset)
- 🏆 **49.6 AP50** on COCO-OVD benchmark — competitive with SOTA open-vocabulary detectors
- 🧩 Modular and flexible architecture using:
  - **CLIP** for zero-shot classification
  - **SAM** for segmentation-based region refinement
  - **GDINO** for language-driven object detection
- 💡 Includes:
  - **Synonym Averaged Embedding Generator (SAEG)**
  - **Score Refinement Module (SRM)**

---

## 🔍 Motivation

Traditional object detectors (e.g., Mask-RCNN) work in **closed-set** settings, meaning they can only detect objects they were trained on. However, real-world applications demand **open-set** capabilities—identifying objects **never seen during training**. Our method solves this challenge **without retraining** by cooperatively integrating multiple foundational vision-language models.

---

## 🛠️ Components

| Component | Role |
|----------|------|
| **CLIP** | Assigns semantic labels to novel objects using zero-shot classification |
| **SAM** | Refines noisy bounding boxes and masks |
| **GDINO** | Provides initial language-conditioned detection |
| **SRM** | Combines confidence scores from multiple models for robust filtering |
| **SAEG** | Enhances zero-shot labeling via synonym-aware embeddings |

---

## 📊 Experimental Results

| Method        | Novel mAP | Known mAP | All mAP |
|---------------|-----------|-----------|---------|
| Mask-RCNN     | 0.00      | 17.77     | 1.55    |
| GDINO         | 13.47     | 37.13     | 15.30   |
| **Ours (full)** | **17.42** | **42.08** | **19.33** |

> 🚀 Our full pipeline significantly outperforms existing baselines on both known and novel categories.
---
## 📚 Based On

This repository replicates and extends the research presented in:

**"Enhancing Novel Object Detection via Cooperative Foundational Models"**  
*Rohit Bharadwaj, Muzammal Naseer, Salman Khan, Fahad Shahbaz Khan*  
[arXiv:2311.12068](https://arxiv.org/abs/2311.12068)

All core ideas, methods (CLIP + SAM + GDINO integration), and metrics are credited to the original authors.

---
## 📄 Citation

If you use this code or base your research on this method, please cite the original paper:

```bibtex
@article{bharadwaj2025cooperativeNOD,
  title={Enhancing Novel Object Detection via Cooperative Foundational Models},
  author={Rohit Bharadwaj and Muzammal Naseer and Salman Khan and Fahad Shahbaz Khan},
  journal={arXiv preprint arXiv:2311.12068},
  year={2025}
}
