# AI-Powered Predictive Maintenance System ⚙️

An end-to-end Machine Learning solution designed to predict industrial machine failures before they occur. This project utilizes sensor data (temperature, torque, rotational speed) to provide real-time risk assessments and maintenance recommendations through an interactive dashboard.

## 🚀 Project Overview
This system is trained on the **AI4I 2020 Predictive Maintenance Dataset**. It uses an optimized **XGBoost** classifier to achieve high recall, ensuring that critical maintenance issues are identified early to reduce unplanned downtime.

### Key Features
* **Real-time Prediction:** Instant failure probability calculations based on sensor inputs.
* **Interactive Dashboard:** A modern UI built with Streamlit featuring a "Glass-morphic" design.
* **Actionable Insights:** Categorizes risk into Low, Medium, and High, providing specific maintenance timelines (e.g., "Schedule within 2-4 hours").
* **Alert History:** Keeps a session-based log of all validations for export and review.
* **Technical Transparency:** Includes detailed evaluation reports and model comparison data.

---

## 📊 Performance Metrics
The model was selected after rigorous comparison with Random Forest, SVM, and Gradient Boosting.

| Metric | Score |
| :--- | :--- |
| **Accuracy** | 98% |
| **Recall (Failures)** | 84% |
| **Precision (Failures)** | 66% |
| **ROC-AUC** | 0.976 |

*Note: High recall is prioritized to ensure 8 out of 10 potential failures are caught, even at the cost of some false alarms.*

---

## 📂 File Structure
* `app.py`: The main Streamlit dashboard application.
* `predict.py`: Core prediction logic, data cleaning, and risk categorization.
* `final_model.pkl`: The trained XGBoost model.
* `final_scaler.pkl`: The StandardScaler for feature normalization.
* `Machine_Failure_Prediction_System.ipynb`: Complete research, EDA, and training pipeline.
* `model_evaluation_report.txt`: Performance breakdown and confusion matrix.
* `requirements.txt`: Python dependencies required for the project.

---

## 🛠️ Installation & Setup

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/predictive-maintenance-ai.git](https://github.com/YOUR_USERNAME/predictive-maintenance-ai.git)
    cd predictive-maintenance-ai
    ```

2.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Application:**
    ```bash
    streamlit run app.py
    ```

---

## 🔧 How it Works
The system follows a 4-step pipeline:
1.  **Feature Engineering:** Converts raw inputs and machine types into model-ready features.
2.  **Scaling:** Normalizes features like RPM and Torque using the pre-trained `final_scaler.pkl`.
3.  **Inference:** The XGBoost model calculates the probability of failure.
4.  **Heuristics:** A custom logic engine in `predict.py` translates probabilities into human-readable risk levels and maintenance advice.

---

## 💡 Recommendations for Use
* **Alert Thresholds:** Set up automated alerts for any prediction with a probability > 0.8.
* **Continuous Learning:** Periodically retrain the model with new sensor data from the `ai4i2020.csv` or actual industrial logs.
* **Monitoring:** Track the "False Alarm" rate in the dashboard to fine-tune the decision thresholds.

---
