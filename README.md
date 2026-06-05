# Edge AI Compression Pipeline

A complete Edge AI model compression pipeline built from scratch.

## What this repo contains

### MNIST Pipeline
- `original_model.pth` — Baseline neural network, 97.29% accuracy, 430 KB
- `quantized_model.pth` — Post-training quantization, 112 KB, 4x smaller
- `qat_model.pth` — Quantization aware training, 117 KB
- `pruned_30_model.pth` — 30% weights pruned
- `pruned_60_model.pth` — 60% weights pruned
- `combined_model.pth` — Pruning + quantization combined, 112 KB

### HAR Sensor Data Pipeline
- `har_teacher.pth` — Teacher model, 1772 KB, 95.05% accuracy
- `har_student_alone.pth` — Student trained alone, 317 KB, 18.05%
- `har_distilled.pth` — Student trained via distillation, 317 KB, 95.18%
- `har_pruned.pth` — Distilled + 40% pruned, 317 KB, 94.30%
- `har_quantized.pth` — Fully compressed, 84 KB, 94.40%

## Key Results

| Technique | Size | Accuracy |
|-----------|------|----------|
| Teacher | 1772 KB | 95.05% |
| Student alone | 317 KB | 18.05% |
| Distillation | 317 KB | 95.18% |
| Pruned + Quantized | 84 KB | 94.40% |

**21x compression. 0.65% accuracy cost. Edge-ready.**

## Techniques covered
- Post-Training Quantization (PTQ)
- Quantization Aware Training (QAT)
- Unstructured Pruning (L1)
- Knowledge Distillation
- Full compression pipeline combining all three

## Built with
PyTorch | Google Colab
