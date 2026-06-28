# 😷 3-Class Face Mask Detector – YOLOv8 vs MobileNetV2

[![Python](https://img.shields.io/badge/python-3.9%2B-blue)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.10-orange)](https://tensorflow.org)
[![Ultralytics](https://img.shields.io/badge/Ultralytics-YOLOv8-brightgreen)](https://ultralytics.com)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.7-green)](https://opencv.org)
[![License](https://img.shields.io/badge/license-MIT-brightgreen)](LICENSE)

> **Real-time detection of 3 mask states: `with_mask`, `without_mask`, and `mask_weared_incorrect`.** Compare YOLOv8 (end-to-end) vs MobileNetV2 (Haar + CNN).

![Demo](outputs/demo.gif)

---

## 📌 The Problem
Mask compliance isn't binary – people often wear masks incorrectly (below nose/chin). This project detects **3 classes** and benchmarks two architectures to find the best solution.

## 🔬 Model Comparison

| Pipeline | mAP@0.5 | FPS (CPU) | Classes | Robustness |
|----------|---------|-----------|---------|------------|
| Haar + MobileNetV2 | 89.3% | 25 | 3 | ❌ Flickers on angles |
| **YOLOv8n (End-to-End)** | **95.7%** | **35** | **3** | ✅ Stable, handles occlusion |

> **Winner:** YOLOv8n – jointly learns localization & classification, handles incorrect mask wear better.

## 🗂️ Dataset (Your Custom 3-Class Data)
- Classes:
  - `0: mask_weared_incorrect`
  - `1: with_mask`
  - `2: without_mask`
- Structure (YOLO format):
