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
- **Backend:** Python (Flask)
- **ML:** Scikit-learn, XGBoost, LightGBM, SHAP
- **Frontend:** React.js, Tailwind CSS, Lucide-React
- **Sustainability:** CodeCarbon (Emissions Tracking)
- **Data Engineering:** Pandas, NumPy

## Dataset
The model is trained on the **Global Weather Repository** dataset, which includes comprehensive historical weather and pollution data.

* **Key Features:** Temperature, Humidity, Wind Speed, Air Pressure, PM2.5, PM10, NO2, SO2, CO.
* **Location:** The dataset file (`GlobalWeatherRepository.csv`) is placed in the `backend/` folder.
* **Note:** Due to GitHub's file size limits, the raw CSV file is **not included** in this repository.
  * *If you are cloning this repo, please place your own dataset named `GlobalWeatherRepository.csv` inside the `backend/` folder before running the training script.*
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
### 1. Start the Backend (First)
- Open your terminal, navigate to the backend folder, and run the Flask app.
```bash
cd backend
pip install -r requirements.txt
python app.py
```
*Status: The server will start on http://127.0.0.1:5000. Keep this terminal open.*

### 2. Start the Frontend (Second)
- Open a new terminal window, navigate to the frontend folder, and start the React server.
```bash
cd frontend
npm install
npm start
```
*Status: The browser will automatically open http://localhost:3000.*

### 3. Model Training (Optional)
- To manually retrain the models with new data:
```bash
python backend/train_model.py
```
*This will generate new .pkl files for both Nowcasting (current) and Forecasting (future).*





