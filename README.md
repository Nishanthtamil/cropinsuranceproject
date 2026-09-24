# 🌾 Crop Insurance AI Platform

<div align="center">
  <img src="https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi" alt="FastAPI" />
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" alt="OpenCV" />
  <img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite" />
</div>

<br/>

**Crop Insurance AI Platform** is an intelligent, end-to-end AI system that streamlines crop damage inspection and insurance claim evaluation. A farmer can simply point their phone camera at their field, and the platform automatically identifies the crop type, estimates the percentage of damage, calculates the estimated loss, computes NDVI satellite values, and cross-checks the claim for potential fraud — all in real-time.

---

## ✨ Features

- **🌿 AI Crop Identification**: Uses a fine-tuned **MobileNet** model (via TensorFlow/Keras) to classify crops from live camera images into 4 categories: **Cotton, Maize, Rice, and Wheat**.
- **📊 Damage Assessment**: Automatically estimates the percentage of crop damage and loss from the captured image using computer vision techniques.
- **🛡️ Fraud Detection Pipeline**: A dedicated fraud detection system cross-references claim submissions against the database, flagging duplicate or suspicious claims.
- **🗺️ Geolocation & NDVI Mapping**: Captures device GPS coordinates at the time of the claim. Calculates NDVI (Normalized Difference Vegetation Index) values and plots the farm location on an interactive **OpenStreetMap** map.
- **📷 Browser-Based Camera Capture**: A simple HTML/JS frontend lets users capture live webcam snapshots directly from the browser — no app installation needed.
- **🗄️ SQLite Logging**: All claims, predictions, and metadata are persistently logged to a local SQLite database for audit trails.

## 🛠️ Technology Stack

| Technology | Purpose |
| ---------- | ------- |
| **FastAPI** | High-performance asynchronous backend API |
| **TensorFlow / Keras** | MobileNet-based crop classification model |
| **OpenCV** | Image preprocessing and manipulation |
| **NumPy** | Numerical computation for NDVI analysis |
| **SQLite** | Lightweight, persistent claim database |
| **HTML / JS** | Browser-based frontend with webcam & geolocation |
| **OpenStreetMap (Leaflet)** | Interactive geospatial map rendering |

## 🚀 Getting Started

### Prerequisites
- Python 3.9+

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/Nishanthtamil/cropinsuranceproject.git
cd cropinsuranceproject
```

2. **Install dependencies:**
```bash
pip install -r requirements.txt
```

3. **Start the Backend Server:**
```bash
uvicorn fraud_system.api:app --reload
```
You should see `✅ Connected successfully to SQLite`. The API will be live at `http://127.0.0.1:8000`.

4. **Open the Frontend:**
Simply open `index.html` in your browser. Accept camera and location permissions when prompted.

## 🎮 How to Use
1. Open `index.html` in your browser.
2. Allow camera and GPS location access.
3. Point your camera at the crop field and click **Capture & Analyze**.
4. The platform will return:
   - ✅ Identified crop type and confidence score
   - 📉 Estimated damage percentage and financial loss
   - 🛰️ NDVI vegetation index values
   - 📍 Your GPS coordinates pinned on an interactive map
   - 🚨 Fraud risk assessment for the claim

## 🏗️ Project Structure

```text
cropinsuranceproject/
├── fraud_system/
│   ├── api.py              # Main FastAPI application and routing
│   ├── pipeline.py         # Business logic pipeline (fraud check, inference, DB)
│   ├── predictoncode.py    # TensorFlow MobileNet inference logic
│   ├── db_connect.py       # SQLite connection management
│   └── fraud_db.py         # Database query and claim validation logic
├── dataset/                # Test images for various crop conditions
├── index.html              # Browser-based frontend UI
├── script.js               # Webcam capture and API fetching logic
├── map.html                # Interactive OSM map viewer
├── requirements.txt        # Python dependencies
└── crop_insurance.db       # SQLite database
```

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the issues page.
