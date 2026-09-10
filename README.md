# AI-Based Hotspot Detection in Solar Panels

An AI-based computer vision project for detecting thermal hotspots in solar panels using infrared thermal imagery.

## Overview

This project investigates two different deep learning approaches for automated solar-panel hotspot detection:

- **YOLOv5** for object detection
- **U-Net** for semantic segmentation

The goal was to compare the two approaches and understand their strengths and limitations for solar-panel inspection.

## Dataset

The training dataset consisted of **501 thermal images** of solar panels. The images were processed into grayscale and manually annotated for hotspot regions.

The annotations were converted into:

- YOLO-format labels for object detection
- Binary segmentation masks for U-Net

The training images were resized to **416 × 416** pixels.

## Models

### YOLOv5

Two YOLOv5 variants were investigated:

- **YOLOv5s (Small)**
- **YOLOv5m (Medium)**

The YOLOv5 models were trained for hotspot object detection using bounding-box annotations.

The YOLOv5m model showed stronger performance in scenarios involving clustered hotspots and provided a good balance between detection performance and model complexity.

### U-Net

A custom **U-Net** model was trained for pixel-level semantic segmentation of thermal hotspot regions.

Unlike object detection, segmentation produces a pixel-level mask representing the detected hotspot area.

The U-Net approach was particularly useful for analyzing the shape and spatial extent of hotspot regions.

## Results

The project compares object detection and semantic segmentation through quantitative evaluation and visual inspection.

### YOLOv5

The trained YOLOv5 models produced strong hotspot detection results and were able to detect multiple hotspots within thermal images.

The YOLOv5m model showed better performance in cases where hotspots were close together, while YOLOv5s offered a lighter alternative.

### U-Net

The U-Net model was developed for pixel-level hotspot segmentation.

The current repository includes the trained U-Net model weights. Evaluation and deployment are still being refined, so numerical segmentation metrics are not reported here unless they can be independently reproduced from the published implementation and evaluation procedure.

## Current Status

- **Dataset preparation:** Completed
- **Model training:** Completed
- **YOLOv5 hotspot detection:** Available
- **U-Net hotspot segmentation:** Available
- **Deployment:** Not yet implemented

The models have **not yet been deployed**.

## Future Work

Planned future improvements include:

- Expanding the dataset to improve model generalization
- Further refining the segmentation model and evaluation pipeline
- Investigating larger YOLOv5 architectures
- Deploying the selected model as an API
- Integrating the system with thermal cameras
- Exploring automated hotspot alerts for solar-panel inspection

## Project Structure

```text
solar-panel-hotspot-detection/
│
├── detection/
│   ├── best.pt
│   └── data.yaml
│
├── segmentation/
│   └── trained_unet2.pth
│
├── examples/
│   ├── yolo_validation_1.jpg
│   ├── yolo_validation_2.jpg
│   └── yolo_validation_3.jpg
│
├── results/
│   ├── confusion_matrix.png
│   ├── F1_curve.png
│   ├── PR_curve.png
│   └── results.png
│
├── docs/
│
├── README.md
├── .gitignore
└── .gitattributes
