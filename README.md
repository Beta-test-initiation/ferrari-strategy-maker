# Ferrari F1 Strategy Maker

An AI-powered race strategy optimization tool for the **Ferrari Formula 1 team**, combining machine learning, physics-based modeling, and real-time data feeds.

---

## Overview

This application helps optimize **F1 race strategies** through advanced ML models, real-time data, and interactive visualizations. It provides intelligent recommendations for:

- ⏱️ **Pit stop timing**
- 🛞 **Tire compound selection**
- 🏁 **Race pace management**
- 🌦️ **Weather adaptation**
- 🏎️ **Competitor behavior modeling**

---

##  Key Features

- Real-time strategy optimization during races
- Predictive modeling of tire wear and compound performance
- Weather impact analysis with uncertainty estimation
- Competitor move forecasting
- Interactive and visual race plan editor
- Deep historical performance analytics

---

##  Machine Learning Architecture

To make intelligent, risk-aware decisions under uncertainty, we leverage a hybrid of interpretable, predictive, and sequential decision-making models.

| Component                  | Model / Technique                 | Why This Model?                                                                 |
|----------------------------|-----------------------------------|----------------------------------------------------------------------------------|
| 🏁 Race Outcome Predictor   | **Bayesian Regression (NGBoost)** | Provides probabilistic predictions and confidence intervals for risk assessment |
| 🛞 Tire Degradation Model   | **PySINDy**                       | Learns interpretable dynamic equations for tire wear using physics-informed ML  |
| 🌦️ Weather Impact Analyzer | **Gaussian Process Regression**   | Handles sparse data and offers uncertainty-aware predictions                     |
| 🧠 Competitor Modeling      | **Gradient Boosting + RL**        | Predicts moves and simulates reactions using policy learning                    |

###  ML Folder Structure

```
ml/
├── models/
│   ├── bayesian_race_predictor.py
│   ├── pysindy_tire_model.py
│   ├── gpr_weather_model.py
│   └── rl_competitor_policy.py
├── training/
│   └── ...
├── evaluation/
│   └── ...
```

All models are trained on data from the [OpenF1 API](https://ergast.com/mrd/) and various weather + telemetry datasets. Evaluation notebooks are provided for tuning and validation.

---

##  Technical Stack

**Frontend**:  
- React  
- Tailwind CSS (optional for UI polish)

**Backend**:  
- Python (FastAPI)  
- ML integration with `scikit-learn`, `xgboost`, `pysindy`, `ngboost`, and `stable-baselines3`

**Database**:  
- PostgreSQL (for strategy data, model inputs/outputs, and race telemetry)

**Data Sources**:  
- [OpenF1 API](https://ergast.com/mrd/) for historical and live F1 telemetry  
- Real-time weather API (e.g., OpenWeatherMap)

---

## 🚀 Project Structure

```
ferrari-strategy-maker/
├── backend/
│   ├── api/               # FastAPI endpoints
│   ├── models/            # Data schemas
│   ├── services/          # Business logic
│   └── utils/
├── frontend/
│   ├── src/               # React app
│   └── public/
├── ml/                    # ML models, training, evaluation
├── data/
│   ├── raw/               # Raw telemetry/weather data
│   └── processed/         # Cleaned + feature-engineered datasets
└── README.md
```

---

## ⚙️ Setup & Run

### 1. Clone the repo

```bash
git clone https://github.com/your-username/ferrari-strategy-maker.git
cd ferrari-strategy-maker
```

### 2. Install dependencies

**Backend**:

```bash
pip install -r requirements.txt
```

**Frontend**:

```bash
cd frontend
npm install
```

### 3. Set up environment variables

Create a `.env` file for both backend and frontend with your API keys (e.g., weather API).

### 4. Run the application

**Backend**:

```bash
uvicorn backend.main:app --reload
```

**Frontend**:

```bash
npm start
```

---

## 📊 Interactive Strategy Dashboard

The React dashboard includes:
- Lap-by-lap strategy editor
- Real-time visualization of competitor gaps
- Pit stop simulation sliders
- Weather overlays for adaptation planning

---

## 🧪 Evaluation & Testing

Each ML model includes:
- Unit tests for correctness
- Cross-validation for predictive performance
- Out-of-distribution simulation (for RL and GPR)

Run evaluation notebooks:

```bash
jupyter notebook ml/evaluation/
```

---

## 📘 Roadmap

- [ ] Real-time telemetry ingestion from live F1 streams  
- [ ] Multi-agent simulation for team-wide strategy coordination  
- [ ] Visual explanation of model decisions (SHAP for XGBoost, equation viewer for PySINDy)  
- [ ] Driver-specific tuning and preference learning  

---
