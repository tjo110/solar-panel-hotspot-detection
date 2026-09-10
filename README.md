# AI-Based Hotspot Detection in Solar Panels

An AI-based computer vision project for detecting thermal hotspots in solar panels using infrared thermal imagery.

## Overview

This project investigates two different deep learning approaches for automated solar-panel hotspot detection:

- **YOLOv5** for object detection
- **U-Net** for semantic segmentation

The goal was to compare the two approaches and understand their strengths and limitations for solar-panel inspection.

## Dataset

The training dataset consisted of 501 thermal images of solar panels. The images were processed into grayscale and manually annotated for hotspot regions.

The annotations were converted into:

- YOLO-format labels for object detection
- Binary segmentation masks for U-Net

## Models

### YOLOv5

Two YOLOv5 variants were investigated:

- YOLOv5s
- YOLOv5m

The YOLOv5m model generally performed better when hotspots were clustered together.

### U-Net

A U-Net model was trained for pixel-level semantic segmentation of hotspot regions.

The segmentation approach provides more detailed information about the shape and extent of detected hotspots.

## Results

The project compared object detection and semantic segmentation using both quantitative evaluation and qualitative visual inspection.

The final project analysis found that:

- YOLOv5 is suitable for fast hotspot detection and real-time applications.
- U-Net provides more detailed hotspot localization.
- U-Net performed better on thermal images captured from greater distances.

## Current Status

Model development and evaluation have been completed.

**Deployment has not yet been implemented.** Future work will focus on deploying the model as an API and exploring integration with thermal cameras for automated inspection and alerts.

## Future Work

- Expand the dataset to improve model generalization.
- Investigate larger YOLOv5 models.
- Deploy the selected model as an API.
- Explore integration with thermal-camera-based inspection systems.

## Authors

**Thaer Obeidat**  
**Ramsay Al-Shehab**

Bachelor of Science — Electrical & Computer Engineering  
German Jordanian University