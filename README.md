# Deepfake Video Detection Based on Vision Temporal Transformer (VTT) and Multi-Head Attention (MHA)

A comprehensive deepfake detection ecosystem utilizing a custom-trained **VTT-MHA** model. This project features a unified backend that supports both a **Web Dashboard** and a **Mobile Application**.

---

## 🚀 Key Features
* **Custom VTT-MHA Model:** High-accuracy detection focusing on spatial-temporal inconsistencies.
* **Multi-Platform Support:** Fully functional Web interface and Mobile app.
* **Real-time Processing:** Integrated with **YOLOv8** for fast and precise face localization.
* **Automated Deployment:** Ready-to-use batch scripts for Windows environments.

---

## 🏗️ Project Architecture
The system is built on a modular architecture:
1. **Inference Engine:** Processes videos using the custom-trained `.h5` model.
2. **Backend API:** A Python-based server (FastAPI/Flask) that handles requests from all interfaces.
3. **Frontend Layers:** * **Web:** Responsive dashboard for desktop analysis.
    * **Mobile:** Dedicated app for portable detection.

---

## 📂 Repository Structure

| File/Folder | Description |
| :--- | :--- |
| `LastV/` | Core execution folder containing the Backend and API integration. |
| `LastV/updated_api.py` | Main entry point that launches both Backend and Frontend services. |
| `src/` | Source code for the Web Frontend interface. |
| `Mobile App/` | Source code for the mobile client application. |
| `best_lipinc_model_enhanced.h5` | **Custom-trained model** based on VTT and MHA (Result of research). |
| `yolov8n.pt` | YOLOv8 weights used for high-precision face localization. |
| `start_all.bat` | Automation script to launch the entire ecosystem in one click. |

---

## 📊 Dataset Information

The model was trained and validated using high-quality benchmarks to ensure robustness against various deepfake generation techniques. These datasets were scanned and processed directly from Kaggle.

### 1. Primary Data Sources
| Dataset | Provider | Description | Link |
| :--- | :--- | :--- | :--- |
| **FaceForensics++ (FF-C23)** | TU Munich | A benchmark dataset containing various facial manipulations, used here in its compressed C23 version. | [Kaggle Link](https://www.kaggle.com/datasets/xdxd003/ff-c23) |
| **Celeb-DF-v2** | Academic | A large-scale, challenging dataset with high-quality deepfake videos featuring celebrities. | [Kaggle Link](https://www.kaggle.com/datasets/reubensuju/celeb-df-v2) |

### 2. Data Preparation & Statistics
To ensure the highest accuracy during training, the following steps were implemented in the `Project V7.ipynb` notebook:

* **Automated Scanning:** The system performs a full scan of the `DFD`, `FaceForensics++`, and `Celeb-DF` directories to index all available samples.
* **Balanced Sampling:** The dataset was automatically balanced (50% Real / 50% Fake) to avoid model bias during the learning process.
* **Train/Val/Test Split:** * **Training (70%):** Used for learning temporal artifacts using the VTT-MHA architecture.
    * **Validation (15%):** Used for real-time hyperparameter tuning.
    * **Testing (15%):** Used for final performance evaluation on unseen data.
* **Preprocessing:** Each video was processed to extract 8 sequential frames focusing on facial regions using **YOLOv8** for precise localization.

---
---

## 🧠 Model Details
The system uses a unique hybrid approach:
* **Face Detection:** YOLOv8 identifies and crops the facial region.
* **Deepfake Classification:** The **Vision Temporal Transformer (VTT)** analyzes the sequence of frames, while **Multi-Head Attention (MHA)** focuses on specific artifact-heavy regions to determine if the video is real or fake.

---

## 🛠️ Installation & Usage

### 1. Clone the Repository
```bash
git clone [https://github.com/YourUsername/Deepfake-Detection-VTT-MHA.git](https://github.com/YourUsername/Deepfake-Detection-VTT-MHA.git)
cd Deepfake-Detection-VTT-MHA
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
