# River Plastic Detection UAV Sensor

An automated system for detecting and mapping river plastic pollution using UAV imagery and deep learning. The project aims to provide efficient monitoring of plastic waste in waterways, particularly focusing on rural and transboundary rivers.

## Project Overview

This project addresses the critical global issue of plastic pollution in waterways through automated detection and mapping using UAV imagery. The system employs YOLOv8n for object detection, optimized for identifying small plastic debris in various river environments.

### Key Features

- Real-time plastic debris detection in river systems
- UAV-based image capture and processing
- Deep learning model optimized for small object detection
- Support for varied lighting conditions and environments
- Automated mapping and quantification of plastic pollution

## Technical Architecture

### Data Specifications
- Image Resolution: 256 × 256 pixels
- Ground Coverage: 2m × 2m terrain patches
- Dataset Size: 1000 images total (500 per location)
- Testing Locations:
  - Houay Mak Hiao River, Laos
  - Khlong Nueng canal in Talad Thai

### Preprocessing Pipeline
1. Tiling (2 x 2 grid)
2. Auto-Orientation correction
3. Resize-Stretch to 640x640 pixels

### Data Augmentation
- Saturation adjustment for enhanced color distinction
- Brightness variation for improved visibility
- Implemented to increase dataset diversity and model robustness

### Dataset Distribution
- Training Set: 800 images (80%)
- Validation Set: 100 images (10%)
- Testing Set: 100 images (10%)

## Model Architecture

### YOLOv8n Implementation
- Framework: Ultralytics YOLOv8
- Model Variant: YOLOv8n (optimized for small object detection)
- Input Size: 640x640 pixels
- Architecture Details:
  - Speed CPU ONNX: 80.4ms
  - mAP val 50-95: 37.3
  - Parameters: 3.2M
  - FLOPs: 8.7B

## Performance Metrics

### Training Parameters
- Epochs: 40
- Training Time: 0.18 hours
- Batch Size: 16
- mAP: 0.673

### Validation Metrics
- Precision: 0.875
- Recall: 0.736
- F1 Score: 0.799

## Requirements

```python
torch>=2.1.0
ultralytics>=8.0.0
opencv-python>=4.5.0
numpy>=1.19.0
```

-----

