# MedAssist AI

A healthcare triage and consultation web app that uses machine learning to predict disease risk from reported symptoms and connect patients with specialized doctors.

🔗 **Live Demo:** [https://medi-ai-frontend-3t5h.onrender.com](https://medi-ai-frontend-3t5h.onrender.com)

---

## What It Does

The app includes three role-based dashboards:

- **Patient**: Select symptoms, get an instant ML risk score and condition prediction, read health advisory guidelines, and view doctor prescriptions.
- **Doctor**: View a queue of patient cases matched by specialty, review reported symptoms and ML predictions, and submit diagnostic notes and prescriptions.
- **Admin**: Check system metrics, view disease and risk trend charts, and manage patient/doctor accounts.

---

## Tech Stack

- **Frontend**: React 19, Vite, Lucide React, Oxlint, Vanilla CSS3
- **Backend**: Python 3.11, Flask, Flask-CORS, PyMongo, Gunicorn, python-dotenv
- **Machine Learning & Data**: Scikit-learn (Random Forest, Pipelines, One-Hot Encoding, Preprocessing), Pandas, NumPy, Joblib
- **Database**: MongoDB Atlas
- **DevOps & Deployment**: Docker, Docker Compose, Nginx, Render

---

## Project Structure

```text
medi_ai/
├── frontend/       # React + Vite client
├── backend/        # Flask REST API and ML inference engine
├── datastorage/    # Datasets and trained .pkl models
├── training/       # Model training scripts
└── docker-compose.yml
```

---

## Quick Start

### Option 1: Using Docker Compose (Recommended)

Make sure you have Docker installed, then run:

```bash
docker-compose up --build
```

- Frontend: `http://localhost:80`
- Backend API: `http://localhost:5000/api`

---

### Option 2: Running Locally

#### 1. Backend

```bash
cd backend
pip install -r requirements.txt
python server.py
```

The API starts at `http://localhost:5000/api`.

#### 2. Frontend

In a second terminal:

```bash
cd frontend
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.
