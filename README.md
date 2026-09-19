# Hybrid Multi-Domain Image Forensics for AI-Assisted Manipulation Detection and Localization

> A Digital Image Processing and Deep Learning based framework for detecting selected AI-assisted image manipulations and localizing suspicious regions using spatial, frequency, local and deep image features.

---

## 📌 Project Overview

With the rapid development of AI-based image editing tools, images can now be modified by removing objects, adding new objects, or filling missing regions automatically. These edits can look very natural and may be difficult to identify through visual inspection alone.

This project proposes a **Hybrid Multi-Domain Image Forensics** system that analyzes images using multiple types of visual evidence.

The system combines:

- Spatial-domain features
- Frequency-domain features
- Local image features
- Deep CNN features
- Machine learning classification
- Manipulation localization

The main goal is to determine whether an image is **authentic or manipulated**, identify the type of selected manipulation, and highlight the suspicious region using a **heatmap or binary mask**.

---

## 🎯 Objectives

The main objectives of this project are:

1. Detect whether an input image is authentic or manipulated.
2. Detect selected AI-assisted manipulations.
3. Detect AI-based object removal/inpainting.
4. Detect AI-based object addition.
5. Use conventional image forgery as a baseline.
6. Extract complementary features from different image domains.
7. Combine spatial, frequency, local and deep features.
8. Classify images using machine learning/deep learning models.
9. Localize suspicious or manipulated regions.
10. Evaluate the robustness of the system under common image degradations.

---

## 🔍 Problem Statement

Traditional image forgery detection methods often focus on a single type of manipulation or a single feature representation.

However, modern AI editing tools can perform operations such as:

- Object removal
- Object addition
- AI inpainting
- Image retouching
- Background modification

These manipulations may not always produce obvious visual artifacts.

Therefore, this project investigates whether combining information from different domains can improve the detection and localization of selected image manipulations.

---

## 💡 Proposed Solution

The proposed system follows a multi-stage forensic analysis pipeline.

```text
                    INPUT IMAGE
                         │
                         ▼
                  PREPROCESSING
                         │
             ┌───────────┼───────────┐
             │           │           │
             ▼           ▼           ▼
        SPATIAL       FREQUENCY    LOCAL
        FEATURES     FEATURES     FEATURES
             │           │           │
             │           │           │
       Histogram       DCT/DFT     SIFT
       GLCM            Spectrum    Harris
       LBP                         SURF
       Edges
             │           │           │
             └───────────┼───────────┘
                         │
                         ▼
                  CNN DEEP FEATURES
                         │
                         ▼
                  FEATURE FUSION
                    PCA / LDA
                         │
                         ▼
               CLASSIFICATION MODEL
                    SVM / CNN
                         │
             ┌───────────┴───────────┐
             ▼                       ▼
       IMAGE DECISION          LOCALIZATION
             │                       │
             ▼                       ▼
      Authentic /              Heatmap / Mask
      Manipulated                   │
                                    ▼
                          Suspicious Region
