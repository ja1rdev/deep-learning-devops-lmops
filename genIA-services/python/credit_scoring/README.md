# 🧮 Credit Scoring Service

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

## 📋 Overview

Credit Scoring Service is a lightweight AI/ML microservice for credit risk assessment. It exposes an API for real‑time scoring, a reproducible training flow, and experiment tracking with MLflow.

## ✨ Features

- 🤖 Real‑time credit score via REST API
- 🧼 Reusable data preprocessing
- 🧪 Reproducible training with MLflow tracking
- 📈 Metrics and model versioning
- 🐳 Docker‑ready

## 🛠️ Technologies

- **Backend**: FastAPI (+ Uvicorn)
- **AI/ML**: scikit‑learn, PyTorch (optional), NumPy, pandas, SciPy
- **Experiment Tracking**: MLflow
- **Infrastructure**: Docker

## 📦 Installation

```bash
# Clone the monorepo
git clone https://github.com/<your-org>/deep-learning-devops-lmops.git
cd deep-learning-devops-lmops/genIA-services/python/credit_scoring

# (Optional) Create and activate a virtual environment
python3 -m venv venv
source venv/bin/activate  # on Windows: venv\Scripts\activate

# Install dependencies
pip install --upgrade pip
pip install -r requirements.txt
```

## 🚀 Quickstart (API)

Assuming your FastAPI app is `server/main.py` and the app instance is `app`:

```bash
uvicorn server.main:app --host 0.0.0.0 --port 8000 --reload
```

- Open `http://localhost:8000/docs` for interactive API docs.
- Adjust the module path (`server.main:app`) to match your codebase if different.

## 🔌 Example

Request:

```bash
curl -X POST http://localhost:8000/predict \
  -H "Content-Type: application/json" \
  -d '{
        "age": 35,
        "income": 4200.5,
        "loan_amount": 15000,
        "loan_term_months": 24,
        "num_open_accounts": 3,
        "delinquency_12m": 0
      }'
```

Response (sample):

```json
{
  "score": 0.82,
  "approved": true
}
```

## 🧪 Training (minimal)

```bash
python training/train.py --config training/config.yaml
# Inspect runs locally
mlflow ui --port 5000  # then open http://localhost:5000
```

## 🐳 Docker (optional)

```bash
docker build -t credit-scoring:latest .
docker run --rm -p 8000:8000 credit-scoring:latest
```

For GPU hosts (optional):

```bash
docker run --gpus all --rm -p 8000:8000 credit-scoring:latest
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m "feat: add amazing feature"`
4. Push the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License — see `LICENSE`.

## 📞 Contact

Project Lead — [@ja1rdev](https://github.com/ja1rdev)

Email: [jairenriquez1715@gmail.com](mailto:jairenriquez1715@gmail.com)
