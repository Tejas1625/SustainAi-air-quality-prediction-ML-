# SustainAI: Intelligent Air Quality Prediction System

## Project Overview
**SustainAI** is an Air Quality Prediction system. It utilizes advanced Machine Learning to perform both **Nowcasting** and **Forecasting** of Air Quality Index (AQI) for major cities around the world.

The system focuses on **transparency** (Explainable AI) and **sustainability** (Green AI).

## Key Features
- **Dual-Mode Prediction:**
  - **Nowcasting:** Estimates current AQI levels in real-time using immediate weather data.
  - **Forecasting:** Predicts future AQI trends based on historical patterns.
- **Explainable AI (XAI):** Integrated **SHAP** values to show exactly how weather parameters (e.g., Humidity, PM2.5) influence the prediction.
- **Green AI Tracking:** Monitors energy consumption (kWh) and CO2 emissions (g) during model training using **CodeCarbon**.
- **Interactive Dashboard:** Built with React and Tailwind CSS, featuring city-wise analytics and sustainability reports.

## Tech Stack
- **Backend:** Python (Flask), Scikit-learn, XGBoost, LightGBM
- **Frontend:** React.js, Tailwind CSS, Lucide-React
- **Sustainability:** CodeCarbon (Emissions Tracking)
- **Data Engineering:** Pandas, NumPy

## Project Structure
```text
SustainAI/
│
├── backend/                     # Python Flask API & ML Logic
│   ├── artifacts/               # Trained models (.pkl) & features.json
│   ├── models/                  # ML model storage
│   ├── data/                    # Folder for datasets
│   ├── app.py                   # Main Flask API entry point
│   ├── train_model.py           # ML training pipeline (Nowcast + Forecast)
│   ├── start_backend.py         # Automated setup script
│   └── requirements.txt         # Backend dependencies
│
├── frontend/                    # React Web Application
│   ├── public/                  # Static assets
│   ├── src/                     # React source code components
│   ├── package.json             # Frontend dependencies
│   ├── tailwind.config.js       # CSS Configuration
│   └── postcss.config.js        
│
├── .gitignore                   # Files to exclude from Git
└── README.md                    # Project Documentation
```
## How to Run Locally
### 1. Backend setup
- Navigate to the backend folder and start the server.
```bash
cd backend
pip install -r requirements.txt
python start_backend.py
```
*Note: The script automatically trains the model if artifacts are missing.*
### 2. Frontend setup
- Open a new terminal, navigate to the frontend folder, and launch the UI.
```bash
cd frontend
npm install
npm start
```
- Access: Open your browser and go to http://localhost:3000.

### 3. Model Training (Optional)
- To manually retrain the models with new data:
```bash
python backend/train_model.py
```
*This will generate new .pkl files for both Nowcasting (current) and Forecasting (future).*
