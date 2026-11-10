
# Computer Vision — Evaluation Metrics

**Master Data & AI | Computer Vision Project**

## 1. Project Overview

This project focuses on evaluating machine learning models for three major Computer Vision tasks:

- **Image Classification**
- **Object Detection**
- **Semantic and Instance Segmentation**

The main objective is to understand and implement evaluation metrics, compare model predictions with Ground Truth annotations, and interpret the obtained results.

## 2. Project Structure

```text
computer-vision-evaluation/
│
├── README.md
│
├── notebooks/
│   └── Computer_Vision_Evaluation_Lab.ipynb
│
└── requirements.txt
```

## 3. Datasets

Two datasets are used in this project:

### 3.1 Digits Dataset

Used for image classification.

- Contains images of handwritten digits.
- 10 different classes.
- Used to train and evaluate a classification model.

### 3.2 Penn-Fudan Pedestrian Dataset

Used for object detection and segmentation.

- Contains 170 pedestrian images.
- Provides annotations for individual pedestrians.
- Ground Truth bounding boxes and instance masks are used for evaluation.

## 4. Models

The experiments use the following models:

| Task | Model |
|---|---|
| Image Classification | Classification model implemented in the notebook |
| Object Detection | YOLO11n |
| Semantic Segmentation | YOLO11n-seg |
| Instance Segmentation | YOLO11n-seg |

## 5. Evaluation Metrics

### 5.1 Image Classification

The following metrics are used:

- **Accuracy:** Percentage of correctly classified images.
- **Precision:** Measures the reliability of positive predictions.
- **Recall:** Measures the proportion of positive examples correctly identified.
- **F1-score:** Harmonic mean of Precision and Recall.
- **Confusion Matrix:** Visualizes correct predictions and classification errors.

### 5.2 Object Detection

The evaluation focuses on bounding boxes.

- **IoU (Intersection over Union):** Measures the overlap between predicted and Ground Truth bounding boxes.
- **TP, FP and FN:** Identify correct detections, false detections and missed objects.
- **Precision–Recall Curve:** Shows the trade-off between Precision and Recall.
- **AP@0.50:** Average Precision at an IoU threshold of 0.50.
- **mAP@0.50:0.95:** Mean Average Precision calculated across ten IoU thresholds, from 0.50 to 0.95.

### 5.3 Semantic Segmentation

The evaluation is performed at the pixel level using four metrics:

- **IoU:** Measures overlap for each class.
- **mIoU:** Mean Intersection over Union across the evaluated classes.
- **Dice:** Measures overlap between predicted and Ground Truth masks.
- **Pixel Accuracy:** Percentage of correctly classified pixels.

### 5.4 Instance Segmentation

The evaluation considers each object individually.

- **Mask IoU:** Measures overlap between predicted and Ground Truth instance masks.
- **TP, FP and FN:** Evaluate correctly detected, incorrectly detected and missed instances.
- **Precision–Recall Curve:** Evaluates the relationship between Precision and Recall.
- **Mask AP@0.50:** Average Precision using a Mask IoU threshold of 0.50.
- **Mask mAP@0.50:0.95:** Average Precision across ten Mask IoU thresholds.

## 6. Experimental Results

The following table summarizes the main results obtained in the notebook.

| Task | Metric | Result |
|---|---|---:|
| Classification | Accuracy | 97.22% |
| Classification | Macro F1-score | 97.19% |
| Object Detection | AP@0.50 | 0.9640 |
| Object Detection | mAP@0.50:0.95 | 0.8587 |
| Semantic Segmentation | IoU (Person) | 0.6478 |
| Semantic Segmentation | IoU (Background) | 0.8932 |
| Semantic Segmentation | mIoU | 0.7705 |
| Semantic Segmentation | Dice | 0.7862 |
| Semantic Segmentation | Pixel Accuracy | 0.9107 |
| Instance Segmentation | Mask AP@0.50 | 0.9580 |
| Instance Segmentation | Mask mAP@0.50:0.95 | 0.6361 |

### Results Interpretation

- **Classification:** The model achieves high accuracy, correctly classifying most images.
- **Object Detection:** YOLO11n achieves strong detection performance, although stricter IoU thresholds reduce the evaluation score.
- **Semantic Segmentation:** The background is segmented more accurately than the person class.
- **Instance Segmentation:** The model achieves good mask overlap at IoU 0.50, but performance decreases under stricter overlap requirements.

## 7. Installation and Execution

### Prerequisites

- Python
- Jupyter Notebook or Google Colab
- Required Python libraries
- Access to the datasets

### Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/computer-vision-evaluation.git

cd computer-vision-evaluation
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

### Run the notebook

Open the notebook using Jupyter:

```bash
jupyter notebook
```

Alternatively, upload the notebook to Google Colab.

Before running the experiments:

1. Make sure the datasets are available.
2. Check the dataset paths.
3. Execute the notebook cells in order.
4. Inspect the evaluation metrics and visualizations.

## 8. Evaluation Protocol

The detection and instance segmentation experiments include an evaluation inspired by the COCO protocol.

AP is calculated at ten IoU thresholds, from 0.50 to 0.95, and averaged to obtain the corresponding mAP score.

The notebook implements a simplified evaluation procedure rather than the complete official COCO evaluation API.

## 9. Conclusion

This project demonstrates how evaluation metrics differ according to the Computer Vision task.

Classification evaluates image-level predictions, object detection evaluates bounding boxes, semantic segmentation evaluates pixels, and instance segmentation evaluates individual object masks.

The experiments highlight the importance of selecting appropriate evaluation metrics to understand model performance and limitations.

---

**Course:** Master Data & AI  
**Project:** Evaluation Metrics for Computer Vision Tasks
