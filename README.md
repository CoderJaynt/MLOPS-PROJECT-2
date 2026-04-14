<div align="center">

<!-- Animated Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=🎌%20Anime%20Recommender%20System&fontSize=40&fontColor=fff&animation=twinkling&fontAlignY=35&desc=A%20Full-Stack%20MLOps%20Pipeline%20with%20Hybrid%20Recommendation%20Engine&descAlignY=55&descSize=16" width="100%"/>

<!-- Badges -->
<p>
  <img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/TensorFlow-2.x-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white"/>
  <img src="https://img.shields.io/badge/Flask-Web%20App-000000?style=for-the-badge&logo=flask&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
</p>
<p>
  <img src="https://img.shields.io/badge/Jenkins-CI%2FCD-D24939?style=for-the-badge&logo=jenkins&logoColor=white"/>
  <img src="https://img.shields.io/badge/Google%20Cloud-GCP-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white"/>
  <img src="https://img.shields.io/badge/Kubernetes-Orchestration-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white"/>
  <img src="https://img.shields.io/badge/DVC-Data%20Versioning-945DD6?style=for-the-badge&logo=dvc&logoColor=white"/>
</p>
<p>
  <img src="https://img.shields.io/badge/CometML-Experiment%20Tracking-262c3e?style=for-the-badge&logo=comet&logoColor=white"/>
  <img src="https://img.shields.io/badge/GitHub-Code%20Versioning-181717?style=for-the-badge&logo=github&logoColor=white"/>
  <img src="https://img.shields.io/badge/GCR-Container%20Registry-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white"/>
</p>

<br/>

> **🚀 An end-to-end MLOps project featuring a Hybrid Recommendation Engine (Content + User-Based) trained on 5 million+ ratings, deployed on GCP using Jenkins, Docker, and Kubernetes.**

</div>

---

## 📋 Table of Contents

- [🌟 Project Overview](#-project-overview)
- [🏗️ Architecture](#-architecture)
- [🔄 MLOps Workflow](#-mlops-workflow)
- [🤖 Model Details](#-model-details)
- [📁 Project Structure](#-project-structure)
- [⚙️ Tech Stack](#-tech-stack)
- [🚀 Getting Started](#-getting-started)
- [🐳 Docker Setup](#-docker-setup)
- [🔧 Jenkins CI/CD Setup](#-jenkins-cicd-setup)
- [☁️ GCP Deployment](#-gcp-deployment)
- [📊 Experiment Tracking](#-experiment-tracking)
- [🗃️ Data Versioning with DVC](#-data-versioning-with-dvc)
- [🌐 Web Application](#-web-application)
- [📦 Dataset](#-dataset)

---

## 🌟 Project Overview

The **Anime Recommender System** is a production-grade MLOps project that delivers personalized anime recommendations by combining **User-Based Collaborative Filtering** and **Content-Based Filtering** into a unified **Hybrid Recommendation Engine**.

A user simply enters their **User ID**, and the system returns the **Top 10 Anime Recommendations** tailored to their watch history and preferences — powered by a deep learning embedding model trained on over **5 million user ratings**.

```
📥 User enters User ID
        ↓
🤝 Find Similar Users (Collaborative Filtering)
        ↓
🎯 Get User Preferences (Genre, Synopsis)
        ↓
🔍 Find Similar Animes (Content-Based Filtering)
        ↓
⚖️  Combine Scores (Hybrid Weighting: 0.5 + 0.5)
        ↓
🏆 Return Top 10 Recommendations
```

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                        MLOps Architecture                           │
├──────────────┬──────────────┬──────────────────┬────────────────────┤
│  DATA LAYER  │  MODEL LAYER │   SERVING LAYER  │  INFRA LAYER       │
│              │              │                  │                    │
│  Kaggle      │  TensorFlow  │  Flask App       │  Jenkins CI/CD     │
│  Dataset     │  Embeddings  │  (application.py)│  Docker Container  │
│              │              │                  │                    │
│  GCP Bucket  │  User Tower  │  REST API        │  Google Container  │
│  (DVC)       │  Anime Tower │                  │  Registry (GCR)    │
│              │              │                  │                    │
│  GitHub      │  Hybrid      │  Top-10          │  Kubernetes (GKE)  │
│  (Git)       │  Scoring     │  Recommender     │  GCP               │
└──────────────┴──────────────┴──────────────────┴────────────────────┘
```

---

## 🔄 MLOps Workflow

```
 ┌──────────────────────────────────────────────────────────────────┐
 │                      End-to-End Pipeline                         │
 └──────────────────────────────────────────────────────────────────┘

  1️⃣  DATABASE SETUP
      └─ Configure GCP Buckets for raw data storage
         Set up project environment and dependencies

  2️⃣  PROJECT SETUP
      └─ Initialize Python project with setup.py
         Configure logging, config files, utils

  3️⃣  DATA INGESTION
      └─ Pull animelist.csv, anime.csv, synopsis data
         5,000,000+ user-anime rating records

  4️⃣  JUPYTER NOTEBOOK TESTING
      └─ Exploratory Data Analysis
         Prototype Collaborative + Content models
         Validate hybrid recommendation function

  5️⃣  DATA PROCESSING
      └─ Encode user_id → user2user_encoded
         Encode anime_id → anime2anime_encoded
         Filter & clean rating matrix

  6️⃣  MODEL TRAINING
      └─ Train Embedding model (User + Anime towers)
         Extract user_weights & anime_weights
         Compute cosine similarities

  7️⃣  EXPERIMENT TRACKING
      └─ Log metrics, params & artifacts to CometML
         Compare runs and select best model

  8️⃣  TRAINING PIPELINE
      └─ pipeline/training_pipeline.py
         Orchestrate: Ingest → Process → Train → Save

  9️⃣  DATA VERSIONING  (DVC + GCP)
      └─ dvc add artifacts/
         dvc push → GCP Bucket
         Track data versions alongside code

  🔟  CODE VERSIONING  (GitHub)
      └─ git commit + push
         Branch strategy for features/experiments

  1️⃣1️⃣  FLASK APP
      └─ application.py serves prediction endpoint
         User enters ID → Hybrid model returns Top 10

  1️⃣2️⃣  CI/CD DEPLOYMENT
      └─ Jenkins detects GitHub push (Jenkinsfile)
         Docker build → Push to GCR
         Deploy to Kubernetes (GKE) on GCP
```

---

## 🤖 Model Details

### Hybrid Recommendation Engine

The system combines two approaches with configurable weights:

| Component | Type | Description |
|---|---|---|
| **User Tower** | Collaborative Filtering | Finds users with similar taste using embedding cosine similarity |
| **Anime Tower** | Content-Based Filtering | Finds anime similar in genre/synopsis using embedding similarity |
| **Hybrid Scorer** | Weighted Combination | Combines both scores (default: `user_weight=0.5, content_weight=0.5`) |

### Deep Learning Architecture

```python
# Embedding Model (TensorFlow / Keras)
Input: user_id  ──→  Embedding(n_users, 64)  ──→  user_vector
Input: anime_id ──→  Embedding(n_animes, 64) ──→  anime_vector
                              ↓
                     Dot Product (cosine)
                              ↓
                     Sigmoid Activation
                              ↓
                     Predicted Rating Score
```

**Training Data Stats:**

| Metric | Value |
|---|---|
| Total Ratings | 5,000,000+ |
| Unique Users | ~300,000+ |
| Unique Anime | ~17,000+ |
| Embedding Dimension | 64 |
| Optimizer | Adam |
| Callbacks | EarlyStopping, ModelCheckpoint, LearningRateScheduler |

### Hybrid Recommendation Logic

```python
def hybrid_recommendation(user_id, user_weight=0.5, content_weight=0.5):
    # Step 1: Find similar users via user embeddings
    similar_users = find_similar_users(user_id, user_weights, ...)
    
    # Step 2: Get this user's anime preferences
    user_pref = get_user_preferences(user_id, rating_df, df)
    
    # Step 3: Get user-based recommendations
    user_recommended_animes = get_user_recommendations(similar_users, user_pref, ...)
    
    # Step 4: For each recommended anime, find content-similar animes
    for anime in user_recommended_anime_list:
        similar_animes = find_similar_animes(anime, anime_weights, ...)
    
    # Step 5: Combine scores with weights → return Top 10
    return sorted(combined_scores)[:10]
```

---

## 📁 Project Structure

```
📦 PROJECT
├── 📂 artifacts/              # Model artifacts & processed data
├── 📂 config/                 # Configuration files
├── 📂 custom_jenkins/         # Jenkins Docker setup
│   └── Dockerfile             # Jenkins-DinD image
├── 📂 logs/                   # Application & training logs
├── 📂 notebook/               # Jupyter notebooks (EDA + prototyping)
├── 📂 pipeline/               # ML pipelines
│   └── training_pipeline.py   # End-to-end training orchestrator
├── 📂 src/                    # Core source modules
├── 📂 static/                 # Flask static assets (CSS, JS)
├── 📂 templates/              # Flask HTML templates
├── 📂 utils/                  # Utility functions
│   ├── __init__.py
│   ├── common_functions.py
│   └── helpers.py
├── 📄 .dvcignore              # DVC ignore rules
├── 📄 .gitignore              # Git ignore rules
├── 📄 application.py          # Flask web application entry point
├── 📄 deployment.yaml         # Kubernetes deployment manifest
├── 📄 Dockerfile              # Project Docker image
├── 📄 Jenkinsfile             # Jenkins pipeline definition
├── 📄 requirements.txt        # Python dependencies
├── 📄 setup.py                # Package setup
└── 📄 tester.py               # Testing scripts
```

---

## ⚙️ Tech Stack

| Category | Tool | Purpose |
|---|---|---|
| **Language** | Python 3.12 | Core development |
| **ML Framework** | TensorFlow / Keras | Embedding model training |
| **Data Processing** | Pandas, NumPy | Data manipulation |
| **Web Framework** | Flask | REST API & UI serving |
| **Experiment Tracking** | CometML | Metrics, params, model logging |
| **Data Versioning** | DVC | Dataset versioning with GCP |
| **Code Versioning** | GitHub | Source control |
| **Containerization** | Docker | App packaging |
| **CI/CD** | Jenkins | Automated build & deploy pipeline |
| **Container Registry** | GCR (Google Container Registry) | Docker image storage |
| **Orchestration** | Kubernetes (GKE) | Production deployment |
| **Cloud Provider** | GCP | Infrastructure & storage |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.12+
- Docker Desktop
- Git
- GCP Account
- CometML Account

### Local Setup

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/anime-recommender-mlops.git
cd anime-recommender-mlops

# 2. Create virtual environment
python -m venv .venv
source .venv/bin/activate        # Linux/Mac
.venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install -e .

# 4. Pull data with DVC
dvc pull

# 5. Run training pipeline
python pipeline/training_pipeline.py

# 6. Start Flask app
python application.py
```

The app will be available at `http://localhost:5000`

---

## 🐳 Docker Setup

### Build & Run the Project Container

```bash
# Build the Docker image
docker build -t anime-recommender .

# Run the container
docker run -d -p 5000:5000 anime-recommender
```

The `Dockerfile` automatically:
1. Installs all dependencies
2. Runs `training_pipeline.py` to train the model
3. Starts the Flask server on port `5000`

---

## 🔧 Jenkins CI/CD Setup

### Step 1 — Build Custom Jenkins Image

```bash
# Navigate to custom_jenkins folder
cd custom_jenkins

# Build Jenkins with Docker-in-Docker support
docker build -t jenkins-dind .

# Run Jenkins container
docker run -d --name jenkins-dind \
  --privileged \
  -p 8080:8080 -p 50000:50000 \
  -v //var/run/docker.sock:/var/run/docker.sock \
  -v jenkins_home:/var/jenkins_home \
  jenkins-dind
```

### Step 2 — Get Jenkins Initial Password

```bash
docker logs jenkins-dind
# Copy the initial admin password from logs
```

Go to `http://localhost:8080` → Paste password → Install suggested plugins → Create user.

### Step 3 — Install Python inside Jenkins Container

```bash
docker exec -u root -it jenkins-dind bash
apt update -y && apt install -y python3 python3-pip python3-venv
ln -s /usr/bin/python3 /usr/bin/python
exit
docker restart jenkins-dind
```

### Step 4 — Install Google Cloud CLI

```bash
docker exec -u root -it jenkins-dind bash
apt-get update && apt-get install -y curl apt-transport-https ca-certificates gnupg
curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
echo "deb https://packages.cloud.google.com/apt cloud-sdk main" | tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
apt-get update && apt-get install -y google-cloud-sdk
exit
```

### Step 5 — Grant Docker Permissions to Jenkins

```bash
docker exec -u root -it jenkins-dind bash
groupadd docker
usermod -aG docker jenkins
usermod -aG root jenkins
exit
docker restart jenkins-dind
```

### Jenkinsfile Pipeline Flow

```
GitHub Push
    ↓
Jenkins Detects Change (Webhook)
    ↓
Build Docker Image
    ↓
Push Image to GCR
    ↓
Deploy to Kubernetes (GKE) via deployment.yaml
    ↓
✅ App Live on GCP
```

---

## ☁️ GCP Deployment

### Services Used

| GCP Service | Purpose |
|---|---|
| **GCS Bucket** | Raw data & DVC remote storage |
| **GCR** | Docker image registry |
| **GKE** | Kubernetes cluster for deployment |
| **IAM** | Service account & permissions |

### Kubernetes Deployment

```bash
# Apply deployment manifest
kubectl apply -f deployment.yaml

# Check pod status
kubectl get pods

# Get external service IP
kubectl get services
```

---

## 📊 Experiment Tracking

All training experiments are tracked with **CometML**:

- ✅ Model hyperparameters (embedding dim, learning rate, batch size)
- ✅ Training & validation loss curves
- ✅ Model artifacts (weights files)
- ✅ Dataset metadata
- ✅ System metrics (GPU/CPU usage)

Compare runs at: `https://www.comet.com/`

---

## 🗃️ Data Versioning with DVC

```bash
# Add data to DVC tracking
dvc add artifacts/raw/

# Push data to GCP bucket
dvc push

# Pull specific version of data
dvc pull

# Check DVC status
dvc status
```

`.dvc` files are committed to GitHub, actual data lives in the GCP bucket — giving you **Git-like version control for datasets**.

---

## 🌐 Web Application

The Flask application (`application.py`) serves the recommendation engine:

```
User enters User ID
        ↓
POST /recommend
        ↓
Load trained model weights
        ↓
Run hybrid_recommendation(user_id)
        ↓
Return Top 10 Anime as JSON
        ↓
Render results in HTML template
```

**App Preview:** The UI features an anime-themed yellow gradient design where users enter their ID to instantly receive personalized recommendations.

---

## 📦 Dataset

**Anime Recommendation Database 2020** — Kaggle

🔗 [https://www.kaggle.com/datasets/hernan4444/anime-recommendation-database-2020](https://www.kaggle.com/datasets/hernan4444/anime-recommendation-database-2020)

| File | Description | Size |
|---|---|---|
| `animelist.csv` | User-anime ratings (user_id, anime_id, rating) | 5M+ rows |
| `anime.csv` | Anime metadata (name, genre, episodes, score) | ~17K anime |
| `synopsis.csv` | Anime synopsis / plot descriptions | ~17K anime |

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer&animation=twinkling" width="100%"/>

**Built with ❤️ | MLOps • Deep Learning • Cloud • CI/CD**

⭐ **Star this repo if you found it helpful!** ⭐

</div>