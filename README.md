# 🧠 Player Re-Identification in Sports Footage

Real-time player tracking and re-identification in sports videos using YOLOv8, OC-SORT, and ResNet50 appearance features.

## 🎯 Overview

This project implements consistent player ID assignment across video frames, even when players leave and re-enter the field of view.

**Key Components:**
- **YOLOv8**: Player detection
- **OC-SORT**: Motion-based tracking  
- **ResNet50**: Appearance embedding extraction
- **Cosine Similarity**: Identity matching with gallery system

## 📁 Project Structure

```
player-reid-submission/
├── player_reid_final.ipynb        # Main executable notebook
├── yolov8_model.pt                # Trained YOLOv8 model
├── 15sec_input_720p.mp4           # Input video
├── output_final_with_gallery.mp4  # Output with IDs
├── OC_SORT/                       # Tracking module
├── README.md                      # Documentation
└── report.pdf                     # Detailed analysis
```

## 🚀 Quick Start

**Requirements:** Google Colab (no local setup needed)

1. **Upload files** to Colab runtime or Drive

2. **Install dependencies:**
   ```python
   !pip install ultralytics opencv-python-headless torchvision torch filterpy scikit-learn
   ```

3. **Run notebook:**
   Execute all cells in `player_reid_final.ipynb`

4. **Output:**
   Generated video saved as `output_final_with_gallery.mp4`

## 🔧 System Architecture

| Component | Function |
|-----------|----------|
| YOLOv8 | Player detection in frames |
| OC-SORT | Motion tracking via Kalman filter |
| ResNet50 | Appearance feature extraction |
| ID Gallery | Stores player embeddings for re-identification |

## 🧠 Re-ID Logic

- **Gallery System**: Maintains embeddings of known player identities
- **Similarity Matching**: Cosine similarity threshold > 0.7 for ID assignment
- **New Player Handling**: Assigns new ID if no match found in gallery
- **Persistence**: Players retain same ID when re-entering frame

## 📋 Dependencies

```
Python ≥ 3.8
PyTorch ≥ 2.0
ultralytics
opencv-python-headless
torchvision
scikit-learn
filterpy
```

## 👨‍💻 Author

**Harilaxman Salendra**  
*Submission for Liat.ai AI Internship (July 2025)*

---
