# Fruits-360 Image Processing & Classification
### SSN College of Engineering — SSN-LMS Assignment

---

## Overview

This assignment applies classical image processing techniques and deep learning classification models to the **Fruits-360** dataset — a publicly available collection of 173,786 fruit, vegetable, nut, and seed images across 250 classes, each standardized to 100×100 pixels on a white background.

The work is divided into two parts:

- **Part 1** — Classical image processing (color models, filtering, segmentation, object detection)
- **Part 2** — Deep learning classification (CNN baseline, variants, AlexNet, SqueezeNet)

---

## Files

| File | Description |
|------|-------------|
| `fruits360_full_colab.ipynb` | Main Colab notebook — full pipeline, all 250 classes |
| `fruits360_report.tex` | IEEE-format LaTeX report |

---

## Dataset

**Fruits-360** by Mihai Oltean  
- GitHub: [github.com/fruits-360/fruits-360-100x100](https://github.com/fruits-360/fruits-360-100x100)  
- Kaggle: [kaggle.com/moltean/fruits](https://www.kaggle.com/moltean/fruits)  
- 173,786 total images | 250 classes | 100×100 pixels | License: CC BY-SA 4.0

---

## How to Run

1. Open [colab.research.google.com](https://colab.research.google.com)
2. Go to **File → Upload notebook** and select `fruits360_full_colab.ipynb`
3. Set runtime: **Runtime → Change runtime type → T4 GPU**
4. Run all cells top to bottom (`Runtime → Run all`)

> The notebook automatically clones the full dataset (~2 GB). The clone takes 3–5 minutes — wait for it to complete before proceeding.

---

## Part 1 — Image Processing Techniques

All techniques follow the SSN-LMS Image Processing lab material:

| Section | Technique |
|---------|-----------|
| 2 | Read image with OpenCV |
| 3 | Read multiple images from directory |
| 4 | Image properties (height, width, channels, total pixels) |
| 5–6 | Single pixel intensity, 5×5 region intensities |
| 7 | Sub-image / crop region |
| 8 | Color models — RGB, HSV, CMY, Grayscale, Binary + normalization |
| 9 | Point processing — Negative, Brightness +50, Contrast ×1.5, Contrast Stretching |
| 10 | Noise models — Gaussian, Salt & Pepper, Uniform |
| 11 | Spatial filters — Mean, Median, Gaussian + manual convolution |
| 12 | Histogram equalization — before/after comparison |
| 13 | Thresholding — Global, Adaptive, Otsu |
| 14 | Segmentation — Canny edge detection |
| 15 | Segmentation — Contour detection |
| 16 | Segmentation — K-Means clustering (K=2) |
| 17 | Object detection — bounding boxes, area, perimeter, centroid, circularity |
| 18 | Dataset-wide class distribution chart + sample grid |

---

## Part 2 — Deep Learning Classification

All models follow the SSN-LMS Deep Learning lab material:

| Section | Model | Epochs |
|---------|-------|--------|
| 7 | Normal CNN (baseline, from scratch) | 10 |
| 8 | CNN — No MaxPooling variant | 10 |
| 9 | CNN — With Batch Normalization | 10 |
| 10 | Feature map visualization | — |
| 11 | AlexNet (pretrained, fine-tuned) | 5 |
| 12 | SqueezeNet (pretrained, fine-tuned) | 5 |
| 13 | Accuracy comparison bar chart | — |

**Training configuration (same for all models):**
- Optimizer: Adam, lr = 0.0001
- Loss: Cross-Entropy
- Batch size: 32
- Input size: 224×224 (resized from 100×100)
- Split: 80% train / 20% test

---

## Requirements

All packages are pre-installed in Google Colab. No manual installation needed.

```
torch
torchvision
opencv-python (cv2)
numpy
matplotlib
scikit-learn
scikit-image
```

---

## Report

The LaTeX report (`fruits360_report.tex`) is written in **IEEE conference format** and covers:

- Abstract
- Introduction
- Related Work
- Dataset description
- Methodology (image processing + DL pipeline)
- Results and Discussion
- Conclusion

To compile: upload to [Overleaf](https://overleaf.com) and build with **pdfLaTeX**.  
Fill in the accuracy table (Section V) with values from your Colab output.

---

## References

- Oltean, M. — *Fruits-360 dataset*, 2017–. https://github.com/fruits-360  
- Krizhevsky et al. — *ImageNet Classification with Deep CNNs*, NeurIPS 2012  
- Muresan & Oltean — *Fruit recognition from images using deep learning*, 2018  
- Iandola et al. — *SqueezeNet*, arXiv:1602.07360, 2016
