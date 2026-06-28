# 😷 Real-Time Face Mask Detector – YOLOv8 vs MobileNetV2

[![Python](https://img.shields.io/badge/python-3.9%2B-blue)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.10-orange)](https://tensorflow.org)
[![Ultralytics](https://img.shields.io/badge/Ultralytics-YOLOv8-brightgreen)](https://ultralytics.com)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.7-green)](https://opencv.org)
[![License](https://img.shields.io/badge/license-MIT-brightgreen)](LICENSE)
[![Stars](https://img.shields.io/github/stars/yourusername/Face-Mask-Detector?style=social)](https://github.com/yourusername/Face-Mask-Detector)

> **Two pipelines, one goal: real-time face mask detection. Compare MobileNet+Haar vs. YOLOv8 end-to-end.**

![Demo](outputs/demo.gif)

---

## 📌 The Problem
Manual monitoring of mask compliance is inefficient. This project provides a lightweight, real-time solution that runs on a standard laptop webcam – and I benchmarked two different architectures to prove which one works best.

## 🔬 Model Comparison

| Pipeline | mAP@0.5 | FPS (CPU) | Face Detection | Multi-face | Robustness to angles |
|----------|---------|-----------|----------------|------------|-----------------------|
| Haar + MobileNetV2 | 92.1% | 25 | Haar Cascade | Yes | ❌ Flickers |
| **YOLOv8n (End-to-End)** | **97.8%** | **35** | **Integrated** | **Yes** | ✅ Stable |

> **Winner:** YOLOv8n – it jointly learns localization & classification, handles varied scales, and eliminates cascade false positives.

## 🗂️ Dataset
- Source: [Roboflow Face Mask Dataset](https://universe.roboflow.com/roboflow-58fyf/face-mask-detection-dataset) (YOLO format)
- Classes: `0: without_mask`, `1: with_mask`
- Structure:
