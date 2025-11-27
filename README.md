# Object Detection for Autonomous Vehicles (Ongoing)

A real-time **object detection and alert system** for autonomous vehicles that uses **YOLOv8**, **FastAPI**, and **ReactJS** to detect objects, calculate distances, provide visual and voice alerts, and tag events with GPS coordinates.

---

## **Tech Stack**
- **Frontend:** ReactJS, HTML5, CSS3, ShadCN/UI, TailwindCSS  
- **Web APIs:** Camera API, Canvas API, Geolocation API, Speech Synthesis API, File API  
- **Backend:** Python, FastAPI, OpenCV, NumPy, Pillow  
- **ML Model:** YOLOv8 (Ultralytics)  
- **Database:** MongoDB (Motor async client)  
- **Utilities:** uuid, datetime, tempfile, logging, base64  

---

## **Features**
- Live webcam detection using **Camera API**  
- Mobile IP camera stream support  
- **Frame extraction** with **Canvas API**  
- **Distance estimation** for detected objects  
- **Visual warnings** (color-coded bounding boxes)  
- **Voice alerts** using **Speech Synthesis API**  
- **GPS-tagged alerts** using **Geolocation API**  
- Image and video upload detection  
- MongoDB logging for alerts and detection history  
- Modular backend with FastAPI endpoints  

---

## **Installation**

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/av-object-detection.git
cd av-object-detection

# 1. Create virtual environment
python -m venv venv

# 2. Activate virtual environment
# Windows:
venv\Scripts\activate
# Linux / Mac:
# source venv/bin/activate

# 3. Install Python dependencies
pip install -r requirements.txt

# 4. Create a .env file with these variables (example):
# MONGO_URL=your_mongodb_url
# DB_NAME=av_detection
# CORS_ORIGINS=http://localhost:3000

# 5. Start FastAPI backend
uvicorn server:app --reload

# 6. Start React frontend
cd frontend
npm install
npm start

Architecture Overview
[Web Browser]
   ├── Camera API → Canvas API → Frames → Backend API
   ├── Geolocation API → GPS coordinates → Backend API
   ├── Speech Synthesis API ← Backend alerts
[FastAPI Backend]
   ├── YOLOv8 model → Object detection
   ├── Distance estimation → Alert classification
   ├── Annotated frames/videos → Return to frontend
[MongoDB]
   ├── Detection logs
   └── GPS-tagged alerts
