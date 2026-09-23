# 🌍 Air Quality Index (AQI) Prediction System — MLOps

An end-to-end Machine Learning Operations (MLOps) project designed to predict the **Air Quality Index (AQI)** based on atmospheric pollutant concentrations. The system packages a trained regression model into a responsive **Flask Web Application**, containerized with **Docker**, and integrated with a **GitHub Actions CI/CD Pipeline**.

---

## 📌 Project Overview

Air pollution is a major environmental and public health concern. This project enables users to input concentrations of key atmospheric pollutants and instantly receive the predicted **AQI value** along with its health advisory category (ranging from *Good* to *Severe*).

### ✨ Key Features
- **Accurate AQI Estimation**: Machine learning regression model trained on pollutant features.
- **Instant Categorization**: Classifies air quality into standard health impact tiers with dynamic color coding.
- **Interactive Web Interface**: Clean, responsive UI built with Flask, HTML5, and CSS3.
- **Containerized Deployment**: Dockerized application ensuring environment consistency across environments.
- **CI/CD Automation**: GitHub Actions workflow for automated testing and dependency validation on every commit.

---

## 📊 Input Pollutants & AQI Classification

### 1. Model Inputs
The prediction model takes 6 atmospheric pollutant values:

| Pollutant | Full Name | Unit |
| :--- | :--- | :--- |
| **PM2.5** | Fine Particulate Matter (< 2.5 µm) | µg/m³ |
| **PM10** | Coarse Particulate Matter (< 10 µm) | µg/m³ |
| **NO₂** | Nitrogen Dioxide | µg/m³ |
| **SO₂** | Sulfur Dioxide | µg/m³ |
| **CO** | Carbon Monoxide | mg/m³ |
| **O₃** | Ozone | µg/m³ |

### 2. AQI Categories & Severity Levels

| AQI Range | Category | Color Indicator | Health Impact |
| :---: | :---: | :---: | :--- |
| **0 – 50** | **Good** | 🟢 Green | Minimal impact |
| **51 – 100** | **Satisfactory** | 🟡 Light Green | Minor breathing discomfort to sensitive people |
| **101 – 200** | **Moderate** | 🟠 Orange | Breathing discomfort with lung/heart disease |
| **201 – 300** | **Poor** | 🔴 Red | Breathing discomfort to most people on prolonged exposure |
| **301 – 400** | **Very Poor** | 🟣 Purple | Respiratory illness on prolonged exposure |
| **401 – 500+** | **Severe** | 🟤 Maroon | Affects healthy people and seriously impacts those with existing diseases |

---

## 🛠️ Tech Stack

- **Machine Learning**: Scikit-Learn, NumPy, Pickle
- **Backend**: Python 3.10, Flask
- **Frontend**: HTML5, CSS3 (Custom Responsive Styling)
- **DevOps & MLOps**: Docker, GitHub Actions CI/CD
- **Version Control**: Git & GitHub

---

## 📂 Project Structure

```text
AQI-Prediction-Mlops-concept/
├── .github/
│   └── workflows/
│       └── ci_cd.yml         # GitHub Actions CI/CD pipeline
├── app/
│   ├── static/
│   │   └── style.css         # Styling for web interface
│   ├── templates/
│   │   └── index.html        # Web application user interface
│   ├── app.py                # Flask application & prediction API
│   ├── Dockerfile            # Docker configuration for containerization
│   └── requirements.txt      # Python dependencies
├── models/
│   └── AQI_model.pkl         # Serialized pre-trained ML model
├── .gitignore                # Files ignored by Git
└── README.md                 # Project documentation
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10+ installed on your system
- Git
- (Optional) Docker for containerized run

### 1. Clone the Repository
```bash
git clone https://github.com/DavidJaison7/AQI-Prediction-Mlops-concept.git
cd AQI-Prediction-Mlops-concept
```

### 2. Set Up a Virtual Environment
```bash
# Create virtual environment
python3 -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r app/requirements.txt
```

### 4. Run the Flask App
```bash
python app/app.py
```
Open your browser and navigate to:
```
http://localhost:5000
```

---

## 🐳 Docker Deployment

To build and run the application inside a Docker container:

```bash
# Build the Docker image
docker build -t aqi-predictor -f app/Dockerfile .

# Run the container
docker run -p 5000:5000 aqi-predictor
```
Access the application at `http://localhost:5000`.

---

## 🔄 CI/CD Pipeline

The repository includes a GitHub Actions workflow configured in `.github/workflows/ci_cd.yml`:
1. **Trigger**: Executes on every push to the `main` branch.
2. **Environment**: Runs on `ubuntu-latest` with Python 3.10.
3. **Tasks**:
   - Checks out the latest source code.
   - Sets up Python environment and installs dependencies.
   - Validates the application initialization and dependencies.

---

## 🔮 Future Enhancements

- [ ] Automated model retraining pipeline with DVC / MLflow tracking.
- [ ] Integration with live OpenWeather / Air Quality APIs for real-time sensor fetching.
- [ ] Deployment to Cloud platforms (AWS ECS / GCP Cloud Run / Render).
- [ ] Model explanation using SHAP / LIME values.

---

## 👤 Author

**David Jaison**
- GitHub: [@DavidJaison7](https://github.com/DavidJaison7)

---

## 📝 License

This project is licensed under the [MIT License](LICENSE) (or academic use).
