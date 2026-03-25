# LAB_08 — Object Detection & Instance Segmentation

**Course:** 01418362-65 Introduction to Machine Learning  
**Lab:** LAB 08 — Object Detection and Instance Segmentation

---

## 📋 Overview

This laboratory explores two state-of-the-art deep learning architectures for object detection and instance segmentation:

| Notebook | Model | Task |
|---|---|---|
| `YOLO/YOLOv5.ipynb` | YOLO11 (ultralytics) | Object Detection |
| `Mast-RCNN/Mask_RCNN_Object_Segmentation.ipynb` | Mask R-CNN (Matterport) | Instance Segmentation |

Both experiments use the **Dog & Cat Objects** dataset, downloaded via the Roboflow API.

---

## 📁 Repository Structure

```
LAB_08/
├── YOLO/
│   └── YOLOv5.ipynb              # YOLO11 training + evaluation notebook
├── Mast-RCNN/
│   └── Mask_RCNN_Object_Segmentation.ipynb  # Mask R-CNN notebook
├── Datasets.txt                  # Link to the dataset on Roboflow Universe
├── YOLO_Result.xlsx              # Training results summary
├── requirements.txt              # Python dependencies
└── README.md                     # This file
```

---

## 🔧 Setup & Installation

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd LAB_08
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure Your Roboflow API Key

The notebooks use [Roboflow](https://roboflow.com/) to download the dataset.  
Before running, set your API key as an environment variable:

```bash
# Windows (PowerShell)
$env:ROBOFLOW_API_KEY = "your_api_key_here"

# Linux / macOS
export ROBOFLOW_API_KEY="your_api_key_here"
```

Then update the notebook cell to read from the environment:

```python
import os
from roboflow import Roboflow

rf = Roboflow(api_key=os.environ["ROBOFLOW_API_KEY"])
```

---

## 📊 Dataset

- **Name:** Dog & Cat Objects  
- **Source:** [Roboflow Universe](https://universe.roboflow.com/appledetect/dog_cat_objects/dataset/1)  
- **Classes:** `cats`, `dogs`  

---

## 🧠 Models

### YOLO11 (Object Detection)
- Pre-trained weights: `yolo11n.pt` (Nano model)
- Training: 5 epochs, image size 640×640
- Framework: [Ultralytics](https://github.com/ultralytics/ultralytics)

### Mask R-CNN (Instance Segmentation)
- Framework: [Matterport Mask-RCNN](https://github.com/matterport/Mask_RCNN)
- Dataset format: COCO

---

## 🏆 Results (YOLO11)

| Metric | Value |
|---|---|
| mAP@50 | 0.381 |
| Precision | 0.442 |
| Recall | 0.446 |
| Epochs | 5 |

---

## 📌 Notes

- Large files (`.zip`, `.pt`, `runs/`, `yolov5/`) are excluded from the repository via `.gitignore`.  
  Download datasets via the Roboflow notebook cells, and model weights will be auto-downloaded by `ultralytics`.
- This project was tested on CPU; GPU is strongly recommended for faster training.
