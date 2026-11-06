# 🏥 MedAssist AI — Intelligent Healthcare Diagnosis & Prediction System

[![Live Demo](https://img.shields.io/badge/Live_Demo-medi--ai--frontend.onrender.com-06b6d4?style=for-the-badge&logo=render&logoColor=white)](https://medi-ai-frontend-3t5h.onrender.com)
[![React](https://img.shields.io/badge/Frontend-React_19_+_Vite-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Flask](https://img.shields.io/badge/Backend-Python_Flask-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![MongoDB](https://img.shields.io/badge/Database-MongoDB_Atlas-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/atlas)
[![Docker](https://img.shields.io/badge/Deployment-Docker_%26_Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)

**MedAssist AI** is an end-to-end, full-stack intelligent healthcare triage and clinical decision support system. It integrates trained Machine Learning pipelines with real-time tele-health collaboration, connecting Patients, Doctors, and Administrators in an intuitive, responsive glassmorphic web application.

---

## 🌐 Live Application

🚀 **Experience the live deployed application:**  
👉 **[https://medi-ai-frontend-3t5h.onrender.com](https://medi-ai-frontend-3t5h.onrender.com)**

---

## 🔑 Demo Login Credentials

You can test any role immediately using the pre-configured accounts below:

| Role | Username | Password | Access & Features |
| :--- | :--- | :--- | :--- |
| **👤 Patient** | `alex_patient` | `password123` | Symptom Checker, AI Risk Assessment, Health Advisory, Doctor Advice, Case History |
| **🩺 Doctor** | `dr_sarah` | `password123` | Live Patient Case Queue, Clinical Notes & Prescriptions, Consultation History, Doctor Profile |
| **🛡️ Administrator** | `admin` | `admin123` | System Directory, Analytics & Health Trends, User Credential Management, Diagnostic Reports |

*(You can also click **"Sign Up"** on the login page to create a brand new Patient or Doctor account at any time!)*

---

## ✨ Key Capabilities & Dashboards

### 1. 👤 Patient Dashboard
- **Interactive Symptom Input**: Select from categorized multi-system symptoms (cardiovascular, respiratory, neurological, dermatological, etc.) with custom severity and duration tags.
- **AI Risk Assessment Engine**: Multi-disease differential diagnosis, calculated risk index score (0–100%), urgency triage tier, and probability breakdown.
- **AI Health Advisory Dossier**: Pre-consultation clinical guidelines, vitals monitoring protocols (BP, heart rate, temperature), and self-care recommendations.
- **Doctor Advice & E-Prescriptions**: View specialized doctor diagnostic notes, prescribed medications with dosages, and follow-up schedules.
- **Isolated Case History**: Private, instant 0ms history tracking strictly filtered to the logged-in patient's cases.
- **Downloadable Clinical Report Cards**: Generate and print standardized patient clinical summaries.

### 2. 🩺 Doctor Dashboard
- **Live Patient Case Queue**: Real-time queue displaying patient submissions matched to medical specialties (Cardiology, Dermatology, Neurology, General Medicine, etc.).
- **Clinical Review Modal**: Deep-dive into patient medical profile, reported symptoms, AI triage prediction, and vital parameter logs.
- **Prescription & Advisory Workflow**: Submit clinical diagnostic notes, prescription regimens, and follow-up consultation timelines.
- **Consultation History Log**: Track all historical evaluations and prescriptions submitted by the specialist.
- **Doctor Profile Management**: Live update medical qualifications, degrees, experience years, and clinic contacts.

### 3. 🛡️ Admin Dashboard & Health Analytics
- **Live System Metrics**: Real-time counts of active patients, registered specialists, pending assessments, and resolved cases.
- **User Management Directory**: View all registered credentials, filter by roles, toggle password audits, and manage accounts.
- **Healthcare Trends Visualizer**: Interactive trend charts showing disease distribution, risk category allocations, and historical submission timelines.
- **Diagnostic Report Repository**: Centralized access to all completed clinical report cards across the system network.

---

## 🤖 Trained Machine Learning Models

MedAssist AI utilizes three pre-trained machine learning models located in `backend/` and `datastorage/`:

1. **Multi-Disease Prediction Model (`disease_prediction_model.pkl`)**:
   - Random Forest Classifier pipeline trained to predict conditions and match patients to the appropriate medical specialist.
2. **Symptom Severity Weighting Engine (`symptom_severity.pkl`)**:
   - Maps reported symptom intensity across 132 symptom features to calculate composite clinical urgency.
3. **Cardiovascular Risk Prediction Pipeline (`cvd_prediction_model.pkl`)**:
   - Assesses cardiovascular vulnerability based on symptom clusters, patient age, severity, and chronic indicators.

---

## 📂 Project Architecture

The codebase is organized into modular directories:

```text
medi_ai/
│
├── frontend/                     # React 19 + Vite Web Application
│   ├── src/
│   │   ├── components/
│   │   │   ├── PatientDashboard/ # SymptomChecker, RiskAssessment, PatientHistory, DoctorAdvice
│   │   │   ├── DoctorDashboard/  # CaseList, CaseDetailModal, DoctorHistory, DoctorProfile
│   │   │   ├── AdminDashboard/   # AdminDashboard, AnalyticsDashboard, TrendVisualization
│   │   │   ├── AuthModal.jsx     # Authentication & registration modal
│   │   │   └── Navbar.jsx        # Navigation & profile header
│   │   ├── services/
│   │   │   ├── db.js             # Client database & API connector with non-blocking sync
│   │   │   └── aiPredictor.js    # Client-side heuristic predictor fallback
│   │   └── App.jsx               # Main application router & role switcher
│   ├── package.json              # Frontend npm dependencies
│   ├── vite.config.js            # Vite build configuration
│   └── Dockerfile                # Multi-stage Nginx production container
│
├── backend/                      # Python Flask Backend & ML Engine
│   ├── server.py                 # REST API endpoints (Auth, Cases, Analytics, Users, Reports)
│   ├── ml_model.py               # ML Model loading & inference engine
│   ├── recommendations.py        # Clinical recommendations generator
│   ├── advisory_engine.py        # AI health advisory dossier generator
│   ├── requirements.txt          # Python production dependencies (Flask, Scikit-Learn, PyMongo)
│   └── Dockerfile                # Production Gunicorn WSGI container
│
├── datastorage/                  # Datasets & ML Model Weights
│   ├── Disease_symptom_and_patient_profile_ds.csv
│   ├── CVD_cleaned.csv
│   ├── Symptom-severity.csv
│   └── *.pkl                     # Pre-trained ML model binaries
│
├── training/                     # ML Model Training & Preprocessing
│   ├── train.py                  # Primary training pipeline
│   ├── train_model-1.py          # Symptom severity trainer
│   └── train_model-3.py          # CVD model trainer
│
├── docker-compose.yml            # Multi-container orchestration (Frontend + Backend)
├── .env.example                  # Environment variable template
└── .dockerignore                 # Container build exclusion rules
```

---

## 🚀 Running the Project Locally

### Prerequisites
- Node.js (v18+)
- Python (v3.10+)
- Git

### Quick Setup

#### 1. Clone the Repository
```bash
git clone https://github.com/Ganesh-2808/MedAssist-AI.git
cd MedAssist-AI
```

#### 2. Start the Backend API
```bash
cd backend
pip install -r requirements.txt
python server.py
```
*The backend API will run on `http://127.0.0.1:5000/api`*

#### 3. Start the Frontend Application
Open a new terminal window:
```bash
cd frontend
npm install
npm run dev
```
*Open your browser and navigate to `http://localhost:5173`*

---

### Running with Docker Compose

To build and run both the frontend and backend in isolated production containers:

```bash
docker-compose up --build
```
- **Frontend App**: `http://localhost:80`
- **Backend API**: `http://localhost:5000/api`

---

## 🔒 Security & Data Safety
- **No Sensitive Secrets Committed**: Database credentials and secrets are managed strictly through environment variables (`.env`).
- **Data Protection**: MongoDB Atlas TLS SSL communication with fail-safe error handling to prevent UI blocking.
- **Strict User Isolation**: Patient medical records and doctor prescriptions are filtered strictly by user session identity.

---

## 👨‍💻 Author

**Ganesh Reddy**  
- **GitHub**: [@Ganesh-2808](https://github.com/Ganesh-2808)  
- **Repository**: [MedAssist-AI](https://github.com/Ganesh-2808/MedAssist-AI)  
- **Live Web App**: [medi-ai-frontend-3t5h.onrender.com](https://medi-ai-frontend-3t5h.onrender.com)
