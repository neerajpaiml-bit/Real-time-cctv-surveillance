# 🎥 Face Recognition CCTV System

An AI-powered CCTV monitoring application that detects and recognizes faces from a live camera feed using deep learning and machine learning techniques.

The project combines **Flask, MTCNN, FaceNet, KNN, OpenCV, and SQLite** to provide a web-based interface for camera selection, live video streaming, face recognition, and snapshot storage.

## ✨ Features

- 🔐 **User Login** — Provides a login interface for accessing the application.
- 📹 **Camera Selection** — Allows users to select an available camera.
- 🎥 **Live CCTV Streaming** — Displays real-time video through a web interface.
- 👤 **Face Detection** — Uses MTCNN to detect faces in camera frames.
- 🧠 **Face Recognition** — Extracts facial embeddings using FaceNet.
- 🎯 **Face Classification** — Uses a K-Nearest Neighbors (KNN) classifier to identify faces based on saved embeddings.
- 📸 **Snapshot Capture** — Saves face snapshots to a dataset directory.
- 🗄️ **Metadata Storage** — Uses SQLite to store associated metadata.
- 🌐 **Web-Based Interface** — Provides a simple interface powered by Flask.

## 🏗️ System Architecture

```text
              ┌─────────────────────────┐
              │      User / Admin       │
              └────────────┬────────────┘
                           │
              ┌────────────▼────────────┐
              │      Flask Web App      │
              │ Login | Camera | Stream │
              └────────────┬────────────┘
                           │
              ┌────────────▼────────────┐
              │   Camera / Video Feed   │
              │         OpenCV           │
              └────────────┬────────────┘
                           │
              ┌────────────▼────────────┐
              │    MTCNN Face Detection │
              └────────────┬────────────┘
                           │
              ┌────────────▼────────────┐
              │ FaceNet Embedding Model │
              │    InceptionResnetV1    │
              └────────────┬────────────┘
                           │
              ┌────────────▼────────────┐
              │     KNN Classifier      │
              │   Face Classification  │
              └────────────┬────────────┘
                           │
                 ┌─────────┴─────────┐
                 │                   │
          ┌──────▼──────┐    ┌──────▼──────┐
          │   Dataset   │    │   SQLite    │
          │  Snapshots  │    │  Metadata   │
          └─────────────┘    └─────────────┘
```

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core application development |
| Flask | Backend web framework |
| OpenCV | Camera access and video processing |
| MTCNN | Face detection and alignment |
| FaceNet | Facial feature extraction |
| InceptionResnetV1 | Deep learning model for face embeddings |
| KNN | Face classification |
| PyTorch | Deep learning framework |
| SQLite | Metadata database |
| HTML, CSS, JavaScript | Web interface |

## 🔄 How It Works

1. **Login:** The user accesses the application through the login page.
2. **Camera Selection:** The user selects an available camera.
3. **Live Streaming:** The application captures and displays video frames.
4. **Face Detection:** MTCNN detects faces within the video frames.
5. **Feature Extraction:** FaceNet converts detected faces into numerical embeddings.
6. **Face Classification:** The KNN classifier compares embeddings against the trained dataset.
7. **Snapshot Storage:** Relevant snapshots are saved to the dataset folder.
8. **Metadata Management:** Associated information is stored in the SQLite database.

## 📁 Project Structure

```text
Face-Recognition-CCTV/
├── app.py
├── requirements.txt
├── templates/
│   ├── login.html
│   ├── camera_selection.html
│   └── live_stream.html
├── static/
│   └── ...
├── dataset/
│   └── ...
├── database/
│   └── ...
├── .gitignore
└── README.md
```

*Note: This is a suggested structure. Adjust the file and folder names to match your actual repository.*

## 🚀 Installation and Setup

### Prerequisites

- Python 3.10 or another version supported by your dependencies
- Git
- A webcam or compatible camera
- pip package manager

### Step 1: Clone the Repository

```powershell
git clone https://github.com/neerajpaiml-bit/Real-time-cctv-surveillance.git
cd Face-Recognition-CCTV
```

Replace the repository URL and directory name with the correct values for your project.

### Step 2: Create a Virtual Environment

```powershell
python -m venv .venv
```

### Step 3: Activate the Environment

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, use Command Prompt instead:

```cmd
.venv\Scripts\activate.bat
```

### Step 4: Install Dependencies

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

If PyTorch installation fails, consult the official [PyTorch installation guide](https://pytorch.org/get-started/locally/) to select the appropriate CPU or CUDA configuration for your system.

### Step 5: Run the Application

```powershell
python app.py
```

### Step 6: Open the Web Application

Open your browser and navigate to:

**http://127.0.0.1:5000**

Log in, select an available camera, and access the live video stream.

## 🧪 Testing Checklist

- [ ] Login page loads correctly.
- [ ] Camera selection displays available cameras.
- [ ] Live video streaming works.
- [ ] MTCNN detects faces in the video feed.
- [ ] FaceNet generates embeddings successfully.
- [ ] KNN classification works with the available training dataset.
- [ ] Snapshots are saved in the correct directory.
- [ ] SQLite metadata is stored and retrieved correctly.
- [ ] The application handles unavailable cameras gracefully.
- [ ] The system works without a CUDA-enabled GPU when configured for CPU execution.

## ⚠️ Known Limitations

- The current login implementation uses a simple hardcoded user and requires stronger authentication.
- Recognition accuracy depends on dataset quality, lighting, camera position, and model configuration.
- PyTorch and related dependencies may require system-specific installation steps.
- Camera access can fail if another application is using the device.
- GPU acceleration requires a compatible hardware and software configuration.
- A basic KNN classifier may require additional tuning for larger datasets.

## 🔮 Future Enhancements

- 🔐 Implement secure authentication with hashed passwords and role-based access control.
- 👥 Add user registration and authorized face enrollment.
- 🚨 Introduce configurable alerts for recognized or unknown faces.
- 📊 Build an admin dashboard for viewing recognition events and snapshots.
- 🔎 Add search and filtering for historical records.
- 🧵 Move video processing and model inference into background workers when needed.
- ⚡ Optimize inference for faster real-time performance.
- 🌐 Support multiple CCTV cameras.
- 🛡️ Add secure data retention, access controls, and privacy safeguards.

## 🔒 Security and Privacy

Facial images and embeddings are sensitive biometric information. Use this application only with appropriate authorization and consent, and follow applicable privacy and surveillance laws.

For deployment beyond local testing:

- Replace hardcoded credentials with secure authentication.
- Restrict access to camera feeds, snapshots, and biometric data.
- Protect database files and secret configuration values.
- Configure appropriate retention and deletion policies.
- Avoid committing personal biometric data or credentials to GitHub.

## 🤝 Contributing

Contributions and suggestions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Implement your changes.
4. Commit and push your changes.
5. Submit a pull request describing your improvements.



**Face Recognition CCTV System** — Combining computer vision and deep learning to explore intelligent, real-time video monitoring.

*Developed using Python, Flask, OpenCV, PyTorch, MTCNN, FaceNet, KNN, and SQLite.*
