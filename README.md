# Deepfake Video Detection Based on VTT and MHA

A high-performance deepfake detection system utilizing **Vision Temporal Transformer (VTT)** and **Multi-Head Attention (MHA)** to identify facial manipulations. This project focuses on analyzing spatial-temporal inconsistencies across video frames to provide accurate detection results.

---

## 🚀 Key Features
* **Vision Temporal Transformer (VTT):** Advanced architecture for capturing long-range temporal dependencies in video sequences.
* **Multi-Head Attention (MHA):** Enhances model focus on localized facial artifacts and inconsistencies.
* **Real-time Face Detection:** Integrated with **YOLOv8** for precise face localization and tracking.
* **Hybrid Architecture:** Combines deep learning inference with a scalable mobile and web-ready backend.

---

## 🏗️ Project Architecture

The system follows a multi-platform modular architecture:
1. **Preprocessing:** Frames are extracted and faces are detected using YOLOv8.
2. **Feature Extraction:** Spatial and temporal features are processed via the VTT backbone.
3. **Classification:** The MHA layers weigh the importance of specific frame features to determine the final "Real" or "Fake" score.
4. **Interface:** * **Web Dashboard:** A responsive web interface for desktop users to upload and analyze videos.
    * **Mobile App:** A dedicated mobile application for on-the-go deepfake detection.
    * **Backend API:** A Python-based FastAPI/Flask server that powers both platforms.

---

## 📂 Repository Structure
| File/Folder | Description |
| :--- | :--- |
| `backend/` | Contains the API and video processing logic. |
| `Mobile App/` | Source code for the mobile client interface. |
| `best_lipinc_model_enhanced.h5` | The core trained VTT-MHA model weights. |
| `updated_api.py` | Main script for handling inference requests. |
| `yolov8n.pt` | Pre-trained weights for the YOLOv8 face detector. |
| `start_all.bat` | Automation script to launch both backend and frontend services. |

---

## 🛠️ Installation & Usage

### 1. Clone the Repository
```bash
git clone https://github.com/YourUsername/Deepfake-Video-Detection-Based-on-VTT-and-MHA-.git
cd Deepfake-Video-Detection-Based-on-VTT-and-MHA-
```
### 2. Install Dependencies
Make sure you have a virtual environment active, then run:
```
pip install -r requirements.txt
```

### 3. Execution

The project includes batch scripts for easy deployment on Windows:

1. **Launch Full System:** Double-click `start_all.bat`  
2. **Launch Backend Only:** Double-click `start_backend.bat`  
3. **Launch Frontend Only:** Double-click `start_frontend.bat`  

---

### 🔬 Methodology

The system processes videos by following these steps:

1. **Extracting Frames:** Sampling the video at a specific FPS to create a sequence.  
2. **Face Alignment:** Localizing and cropping the face using YOLOv8 to remove background noise.  
3. **VTT Processing:** Passing sequences of frames through the Vision Temporal Transformer to analyze motion consistency.  
4. **MHA Scoring:** Applying Multi-Head Attention to weigh the importance of specific features and compute the final probability of manipulation.

---

## 🏷️ Keywords
`Deepfake Detection` `Vision Transformer` `VTT` `Multi-Head Attention` `MHA` `Computer Vision` `YOLOv8` `AI Security` `Machine Learning`
