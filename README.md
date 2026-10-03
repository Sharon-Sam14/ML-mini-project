<div align="center">
  <br />
  <img src="frontend/public/Main%20hero.png" alt="Main Hero Image" width="100%" style="border-radius: 12px; box-shadow: 0 4px 6px rgba(0,0,0,0.1);" />
</div>
<br />

# 🎬 IMDb Movie Box Office Success & Search Engine

> A fully completed, end-to-end Machine Learning search engine and analytics dashboard that predicts a movie's box office revenue, success tier, profitability, and market cluster using pre-production metadata.

![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![Next.js](https://img.shields.io/badge/Next.js-15-black?style=for-the-badge&logo=next.js)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688?style=for-the-badge&logo=fastapi)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-ML-orange?style=for-the-badge&logo=scikit-learn)
![TypeScript](https://img.shields.io/badge/TypeScript-Frontend-blue?style=for-the-badge&logo=typescript)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-Styling-38B2AC?style=for-the-badge&logo=tailwind-css)

---

## 📖 Overview

This project implements a full-stack, monorepo architecture separating a high-performance **FastAPI / Scikit-Learn backend** from a sleek, modern **Next.js / Tailwind CSS frontend**. 

The system leverages a cleaned dataset of 2,407 IMDb movie records to fulfill five core Machine Learning lab practical objectives (**CO1–CO5**), executing predictions in real-time when users search for a movie.

---

## 🧠 Machine Learning Objectives (CO1–CO5)

| Lab Objective | Task & Algorithm | Implementation File |
| :--- | :--- | :--- |
| **CO1: Preprocessing** | Feature extraction, missing value handling, and success tier binning. | `backend/src/preprocessing.py` |
| **CO2: Regression** | **Multivariate Linear Regression** to forecast exact Box Office Revenue. | `backend/src/train_regression.py` |
| **CO3: Ensemble** | **Random Forest Classifier** to predict Success Tiers (Flop, Average Hit, Blockbuster). | `backend/src/train_classification.py` |
| **CO4: SVM** | **Support Vector Machine (RBF Kernel)** to calculate the probability of profitability. | `backend/src/train_classification.py` |
| **CO5: Unsupervised** | **PCA** (Dimensionality Reduction) + **GMM** (Expectation-Maximization) for market clustering. | `backend/src/train_unsupervised.py` |

---

## 📸 Application Previews

| Live Analytics Dashboard | Cinematic Search UI Flow |
| :---: | :---: |
| <img src="frontend/public/Dashboard%20screenshot.png" alt="Dashboard Screenshot" /> | <img src="frontend/public/dashboard%20mockup.png" alt="Dashboard Mockup" /> |
| **Revenue Forecasting (Linear Regression)** | **Market Clustering & PCA Analytics** |
| <img src="frontend/public/Prediction%20graph.png" alt="Prediction Graph" /> | <img src="frontend/public/analytics%20graphic.png" alt="Analytics Graphic" /> |
| **Raw 2,407-Row IMDb Dataset** | **ML Engine Core Logo** |
| <img src="frontend/public/Dataset.png" alt="Dataset" /> | <img src="frontend/public/Main%20logo.png" alt="Main Logo" width="150" /> |

---

## 🏗️ Monorepo Architecture

```text
IMDb-Movie-Prediction/
│
├── backend/                              # FastAPI & ML Engine
│   ├── dataset/
│   │   └── imdb_movies_6000_box_office_clean.csv
│   ├── models/                           # Serialized Joblib pipelines (.pkl)
│   ├── src/                              # ML Training Scripts (CO1-CO5)
│   ├── main.py                           # FastAPI Server Entrypoint
│   └── requirements.txt
│
├── frontend/                             # Next.js 15 UI
│   ├── public/                           # Logos and screenshot assets
│   ├── src/app/
│   │   ├── page.tsx                      # Bento Grid Home Page
│   │   ├── dashboard/page.tsx            # Live Analytics Dashboard
│   │   └── search/page.tsx               # Cinematic ML Search Engine
│   ├── package.json
│   └── tailwind.config.ts
│
└── README.md

```

---

## 🚀 Getting Started

To run the application locally, you will need to spin up both the Python backend and the Node.js frontend.

### 1️⃣ Start the Machine Learning Backend (FastAPI)

Open a terminal and navigate to the `backend` folder:

```bash
cd backend

# Create and activate a virtual environment
python -m venv venv
# On Windows: venv\Scripts\activate
# On Mac/Linux: source venv/bin/activate

# Install dependencies
python -m pip install -r requirements.txt

# Train the ML Models (Generates .pkl files in /models)
python -m src.train_regression
python -m src.train_classification
python -m src.train_unsupervised

# Start the FastAPI Server
uvicorn main:app --reload --port 8000

```

*The API is now running at `http://localhost:8000`. You can test the endpoints at `http://localhost:8000/docs`.*

### 2️⃣ Start the Frontend Web App (Next.js)

Open a **new** terminal window and navigate to the `frontend` folder:

```bash
cd frontend

# Install Node modules
npm install

# Start the development server
npm run dev

```

*The web app is now live at `http://localhost:3000`. Navigate here to view the UI and search engine!*

---

## 🛡️ Key Features

* **Singleton Model Loader:** The FastAPI backend caches Scikit-Learn `.pkl` files in memory on startup, ensuring real-time `0ms` inference latency when a user searches for a movie.
* **Strict Data Separation:** Pre-production data (budget, genre, release year) is mathematically strictly separated from post-release data (revenue, popularity) during model training to prevent data leakage.
* **Dynamic Frontend Fetching:** The Next.js dashboard uses React `useEffect` hooks and Next.js `fetch` to stream prediction outputs directly from the FastAPI endpoints.

---

## 👥 Contributors

| Contributor | GitHub Profile |
| --- | --- |
| **Sharon Sam** | [@Sharon-Sam14](https://github.com/Sharon-Sam14) |
| **Ronald** | [@Ronald372](https://github.com/Ronald372) |
| **Sam Manoj** | [@Sam-Manoj](https://github.com/Sam-Manoj)]

---

## 📄 License

This project is licensed under the **MIT License**.

```

```
