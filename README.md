# EDGE-AI — From Scratch to Deployment

> Built by a first-year CSE student in 2 days.
> Every line understood, not copy-pasted.

---

## What this repo contains

### 1. Neural Network Compression Pipeline (MNIST)
Built a complete model compression pipeline from scratch.

| Model | Size | Accuracy |
|-------|------|----------|
| Original | 430 KB | 97.29% |
| Post-Training Quantization | 112 KB | 96.8% |
| Quantization Aware Training | 117 KB | 97.1% |
| Pruned 30% | 430 KB | 97.1% |
| Pruned 60% | 430 KB | 96.5% |
| Pruned + Quantized | 112 KB | 97.0% |

**Techniques:** PTQ, QAT, L1 Unstructured Pruning, Combined Pipeline

---

### 2. Knowledge Distillation — MNIST, CIFAR-10, HAR
Proved distillation works on complex data.

| Dataset | Teacher | Student Alone | Student Distilled |
|---------|---------|---------------|-------------------|
| MNIST | 97.3% | 95.0% | 95.2% |
| CIFAR-10 | 56.6% | 54.1% | 55.3% (+1.29%) |
| HAR Sensors | 93.8% | 18.1% | 95.2% (+77%) |

HAR result is the key finding — without distillation the student
completely fails. With distillation it matches the teacher at 1/5th the size.

---

### 3. Full Edge AI Pipeline — HAR Sensor Data
Human Activity Recognition compressed for edge deployment.

| Model | Size | Accuracy |
|-------|------|----------|
| Teacher | 1772 KB | 95.05% |
| Student alone | 317 KB | 18.05% |
| Student distilled | 317 KB | 95.18% |
| Pruned 40% | 317 KB | 94.30% |
| Pruned + Quantized | 84 KB | 94.40% |

**21x smaller than teacher. 0.65% accuracy cost. Edge-ready.**

This model can run on an ESP32 or STM32 microcontroller offline.
No internet. No cloud. No Python required.

---

### 4. Construction Site Helmet Detector (YOLOv8)
Custom trained YOLOv8n for real-time safety violation detection.

| Metric | Value |
|--------|-------|
| Architecture | YOLOv8n (3M parameters) |
| Dataset | 3,813 construction site images |
| helmet_on mAP50 | 89.5% |
| helmet_off mAP50 | 89.2% |
| Overall mAP50 | 89.4% |
| Inference speed | 7.7ms per image |
| Model size | 6.2 MB |

**Features:**
- Detects helmet violations in real time
- CLAHE preprocessing for dusty/hazy environments
- Count-based violation detection
- Fail-safe design — uncertain = violation

---

### 5. CNN on MNIST
Implemented convolutional neural network from scratch.

| Model | Parameters | Accuracy |
|-------|------------|----------|
| Flat Network | ~100K | 97.29% |
| CNN | 421,642 | 98.61% |

Architecture: Conv2d → MaxPool → Conv2d → MaxPool → Linear

---

### 6. ONNX Export + Deployment
Models exported to ONNX for cross-platform deployment.
Verified running outside PyTorch using ONNX Runtime.
Compatible with Raspberry Pi, mobile, edge chips.

---

## Key Concepts Implemented From Scratch

- Forward pass, backpropagation, gradient descent
- Vanishing gradients, dying ReLU problem
- Post-Training Quantization (PTQ)
- Quantization Aware Training (QAT)
- L1 Unstructured Pruning + sparse storage
- Knowledge Distillation with temperature scaling
- Feature Pyramid Networks (YOLO multi-scale)
- Non-Maximum Suppression
- CLAHE contrast enhancement
- Fail-safe system design principles
- Accuracy-latency tradeoff for edge hardware

---

## Real World Impact

**Helmet Detector use case:**
- Deployable at construction sites, factories, warehouses
- Runs on Raspberry Pi offline — no internet required
- Detects violations in 7.7ms — faster than human reaction
- Potential to prevent workplace accidents

**HAR pipeline use case:**
- Runs on ESP32/STM32 wearable device
- Recognizes 6 human activities from accelerometer data
- 84 KB model — fits on microcontroller flash memory
- Medical monitoring, sports tracking, fall detection

---

## Tech Stack
PyTorch · YOLOv8 · ONNX Runtime · OpenCV · NumPy · Google Colab

---

## What's Next
- Raspberry Pi deployment — real hardware inference
- TFLite conversion — Android + microcontroller deployment
- Autonomous agent combining SLAM + YOLO + Edge LLM
- Real construction site testing and client demo

---

## Goal
Becoming world-recognized in Edge AI + Autonomous Systems
within 3 years by building things that actually work in the real world —
not just on benchmark datasets.

*First year CSE student. Every project here is proof of work.*
