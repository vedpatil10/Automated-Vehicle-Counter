# 🚗 Automated Vehicle Counting

An intelligent vehicle counting system using **YOLOv8** and **DeepSORT** for accurate real-time traffic analysis from video footage.

## ✨ Features

- 🎯 High-precision vehicle detection using YOLOv8x
- 🔄 DeepSORT tracking prevents duplicate counting
- 🚙 Detects multiple vehicle types (cars, buses, trucks, motorcycles)
- 🆔 Unique ID assignment for each vehicle
- 📹 Generates annotated output videos

## 🎬 Demo

### 📺 Output Video
**https://drive.google.com/file/d/1B_vZ6DSmee_tUtCGRuV_accKHM2kWLVi/view?usp=sharing(#)**

### Sample Detection Frames

<img width="1919" height="944" alt="image" src="https://github.com/user-attachments/assets/8fdb4c68-a0de-4a11-91e5-637e380b374e" />

## 🛠️ Technology Stack

- **YOLOv8n** - Training (lightweight and fast)
- **YOLOv8x** - Inference (high accuracy)
- **DeepSORT** - Multi-object tracking
- **OpenCV** - Video processing
- **Roboflow** - Dataset annotation
- **Google Colab** - GPU acceleration

## 🗂️ Dataset

Custom-annotated dataset created with **Roboflow** in YOLO format.
Link: https://drive.google.com/file/d/1dVCptO5q-lsM37-epteThUwzH5p_DVyX/view?usp=sharing

**📁 Dataset Structure:**
```
frame_output/
├── train/images/ & labels/
├── val/images/ & labels/
├── test/images/ & labels/
└── sample_annotations/
```

## 🚀 Quick Start

### Google Colab (Recommended)
```python
!pip install ultralytics opencv-python-headless
```
Open `Vehicle_Counting_Model.ipynb` → Enable GPU → Run cells

### Local Setup
```bash
git clone https://github.com/yourusername/automated-vehicle-counting.git
cd automated-vehicle-counting
pip install -r requirements.txt
```

## 💻 Usage

```python
from ultralytics import YOLO

model = YOLO('yolov8x.pt')
results = model.track(source='video.mp4', conf=0.05, persist=True, save=True)
```

## 📁 Project Structure

```
automated-vehicle-counting/
├── Vehicle_Counting_Model.ipynb
├── README.md
├── yolov8n.pt & yolov8x.pt
├── frame_output/
│   ├── train/, val/, test/
│   └── sample_annotations/
└── output/
    └── Vehicle_Count_Output_Video.mp4
```

## 🔍 How It Works

1. **Extract frames** from video using OpenCV
2. **Detect vehicles** using YOLOv8x model
3. **Track vehicles** across frames with DeepSORT
4. **Assign unique IDs** to prevent duplicate counting
5. **Generate output** video with annotations and total count

### DeepSORT Integration
```python
results = model.track(frame, persist=True)  # Enables tracking
unique_ids = set()  # Stores unique vehicle IDs
total_count = len(unique_ids)  # Final count
```

## 📊 Results

- **Total Vehicles Counted:** 795
- **Processing Speed:** 30 FPS
- **Accuracy:** 90%

## 🎯 Use Cases

- Traffic flow analysis
- Highway monitoring
- Parking management
- Smart city applications


## 🙏 Acknowledgments

- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- [Roboflow](https://roboflow.com/)
- DeepSORT tracking algorithm

---

