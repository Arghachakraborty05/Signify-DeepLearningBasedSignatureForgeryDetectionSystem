# ✍️ Signify – Deep Learning-Based Signature Forgery Detection System

![Python](https://img.shields.io/badge/Python-3.13.12-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.20.0--rc0-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-3.11.0-D00000?style=for-the-badge&logo=keras&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-2.2.3-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-3.0.0-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit--Learn](https://img.shields.io/badge/Scikit--Learn-1.8.0-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.10.0-11557C?style=for-the-badge)
![Protobuf](https://img.shields.io/badge/Protobuf-6.31.1-4285F4?style=for-the-badge)
![OpenCV](https://img.shields.io/badge/OpenCV-4.13.0.92-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-3.1.3-000000?style=for-the-badge&logo=flask&logoColor=white)
![Flask--CORS](https://img.shields.io/badge/Flask--CORS-6.0.2-000000?style=for-the-badge)
![License](https://img.shields.io/badge/License-Academic-blue?style=for-the-badge)

---

# 📌 Overview

**Signify** is a **full-stack AI-powered offline signature verification system** developed as a B.Tech Final Year Project. It combines **Deep Learning, Computer Vision, and Web Technologies** to detect handwritten signature forgeries with high accuracy.

The system employs a **MobileNetV2-based Siamese Neural Network using Transfer Learning** to generate discriminative feature embeddings for writer-independent signature verification.

Users can register multiple genuine signatures, and the system automatically constructs a signature profile by computing the centroid of extracted embeddings. During verification, uploaded signatures are compared against the stored profile using Euclidean distance and an adaptive threshold to determine whether the signature is **Genuine** or **Forged**, along with a confidence score.

---

# ✨ Features

- 🔐 Secure customer signature registration
- ✍ Offline handwritten signature verification
- 🧠 MobileNetV2-based Siamese Neural Network
- 🚀 Transfer Learning for feature extraction
- 📈 Deep embedding generation
- 🎯 Adaptive centroid-based verification
- 📊 Automatic confidence score generation
- 🖼 OpenCV preprocessing pipeline
- 🌙 Dark / Light mode UI
- 📱 Fully responsive frontend
- 🖼 Image upload preview
- ✔ Client-side validation
- 🔗 REST API communication
- ⚙ Flask backend
- 💾 JSON-based customer database

---

# 📷 Demo

> **Screenshots**

### 🏠 Home Page

<p align="center">
<img src="assets/demo/home.png" width="90%">
</p>

### ➕ Signature Registration

<p align="center">
<img src="assets/demo/register.png" width="90%">
</p>

### ✔ Signature Verification

<p align="center">
<img src="assets/demo/verify.png" width="90%">
</p>

> **Note:** This project contains a Flask backend and TensorFlow model, so it cannot be deployed using GitHub Pages.

---

# 🏗 System Architecture

```text
                    ┌────────────────────────────┐
                    │   Responsive Web Frontend  │
                    │   HTML • CSS • JavaScript  │
                    └─────────────┬──────────────┘
                                  │
                            HTTP REST API
                                  │
                    ┌─────────────▼──────────────┐
                    │        Flask Backend       │
                    └─────────────┬──────────────┘
                                  │
                 ┌────────────────┴────────────────┐
                 │                                 │
                 ▼                                 ▼
      Customer Registration            Signature Verification
                 │                                 │
                 ▼                                 ▼
      OpenCV Image Preprocessing      OpenCV Image Preprocessing
                 │                                 │
                 ▼                                 ▼
           MobileNetV2 Siamese Network  (Transfer Learning)
                 │                                 │
                 ▼                                 ▼
        Deep Feature Embeddings        Test Signature Embedding
                 │                                 │
                 └──────────────┬──────────────────┘
                                ▼
                  Euclidean Distance Calculation
                                │
                                ▼
                    Adaptive Threshold Decision
                                │
                                ▼
                Genuine / Forged + Confidence Score
```

---

# 🧠 Deep Learning Pipeline

## Stage 1

### Image Upload

↓

## Stage 2

### OpenCV Image Preprocessing

- Grayscale Conversion
- Otsu Thresholding
- Morphological Noise Removal
- Signature Region Cropping
- Image Resizing (224 × 224)
- Pixel Normalization

↓

## Stage 3

### MobileNetV2 Feature Extraction (Transfer Learning)

↓

## Stage 4

### Deep Embedding Generation

↓

## Stage 5

### Centroid-Based Signature Modeling

↓

## Stage 6

### Adaptive Threshold Verification

↓

### Prediction

- Genuine Signature
- Forged Signature
- Confidence Score

---

# 🖥 Tech Stack

## Frontend

- HTML5
- CSS3
- JavaScript (ES6)
- Responsive Design
- Dark / Light Mode
- Fetch API

---

## Backend

- Python
- Flask
- Flask-CORS
- REST API

---

## Deep Learning

- TensorFlow
- Keras
- MobileNetV2
- Siamese Neural Network
- Transfer Learning
- Contrastive Loss

---

## Computer Vision

- OpenCV
- NumPy

---

## Storage

- JSON Customer Database
- Uploaded Signature Images

---

# 🔗 REST API Endpoints

|  Method  |      Endpoint       |          Description         |
|----------|---------------------|------------------------------|
|  **GET** |         `/`         |           Home Page          |
| **POST** |   `/add-customer`   | Register customer signatures |
| **POST** | `/verify-signature` |   Verify uploaded signature  |

---

# 📂 Dataset

The model was trained on an offline handwritten signature dataset consisting of:

- **144 Individuals**
- **4,277 Signature Images**
- Genuine Signatures
- Forged Signatures

---

# 📂 Project Structure

```text
Signify/
│
├── backend/
│   ├── app.py
│   ├── loader.py
│   ├── preprocessing.py
│   ├── model/
│   │     └── signature_siamese_model1.keras
│   ├── uploads/
│   └── data/
│
├── frontend/
│   ├── index.html
│   └──assets/
│         ├── css/
│         ├── js/
│         ├── img/
│         └── demo/
│
├── requirements.txt
└── README.md
```

---

# ⚙ How It Works

## Customer Registration

1. Enter customer name and customer ID.
2. Upload **6–12 genuine signatures**.
3. Images are preprocessed.
4. Deep embeddings are extracted.
5. Signature centroid is generated.
6. Customer profile is stored.

---

## Signature Verification

1. Enter customer ID.
2. Upload a signature.
3. Image preprocessing.
4. Generate embedding.
5. Compare with stored centroid.
6. Compute Euclidean distance.
7. Apply adaptive threshold.
8. Predict:

- Genuine Signature
- Forged Signature
- Confidence Score

---

# 🚀 Installation

## Clone Repository

```bash
git clone https://github.com/Arghachakraborty05/Signify-DeepLearningBasedSignatureForgeryDetectionSystem.git
```

```bash
cd Signify-DeepLearningBasedSignatureForgeryDetectionSystem
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Run Flask Server

```bash
python backend/app.py
```

Open your browser

```text
http://127.0.0.1:5000
```

---

# 📊 Model Performance

|   Metric  |    Score   |
|-----------|------------|
| Accuracy  | **98.68%** |
| Precision | **99.13%** |
| Recall    | **98.27%** |
| F1-Score  | **98.70%** |
| ROC-AUC   | **0.9989** |

**Evaluation Dataset**

- 455 unseen signature pairs
- 51 individuals

---

# 🏆 Key Achievements

- ✅ Developed a complete **full-stack AI-powered signature verification system**
- ✅ Designed and implemented a **responsive frontend** using HTML, CSS, and JavaScript
- ✅ Developed a **Flask REST API backend** for customer registration and signature verification
- ✅ Built a **MobileNetV2-based Siamese Neural Network using Transfer Learning**
- ✅ Implemented a disciplined **6-stage OpenCV preprocessing pipeline**
- ✅ Generated discriminative deep feature embeddings for writer-independent offline signature verification
- ✅ Designed an adaptive centroid-based verification algorithm using Euclidean distance
- ✅ Implemented confidence score estimation for prediction reliability
- ✅ Achieved **98.68% Accuracy**, **99.13% Precision**, and **0.9989 ROC-AUC**
- ✅ Built a lightweight architecture suitable for practical deployment

---

# 💡 Future Improvements

- MySQL / PostgreSQL integration
- JWT Authentication
- Docker Support
- Cloud Deployment (AWS, Azure, GCP)
- User Authentication System
- Admin Dashboard
- Batch Signature Verification
- Digital Signature Support
- Model Retraining Interface

---

# 📜 License

This project was developed for **academic and educational purposes** as part of a B.Tech Final Year Project.

---

# 👨‍💻 Author

## **Argha Chakraborty**

**B.Tech in Computer Science & Engineering**

**Meghnad Saha Institute of Technology**

📧 Email: argha.chakraborty9635@gmail.com

💼 LinkedIn: *(Add your LinkedIn URL)*

🐙 GitHub: https://github.com/Arghachakraborty05

---

# ⭐ Support

If you found this project useful, please consider giving it a **⭐ Star** on GitHub.

It motivates future improvements and helps others discover the project.
