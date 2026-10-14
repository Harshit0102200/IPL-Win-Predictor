# 🏏 IPL Win Predictor

An interactive end-to-end Machine Learning web application that predicts the real-time win probability of Indian Premier League (IPL) teams during the second innings of a match based on current match conditions.

🔗 **Live Demo:** [Streamlit App](https://ipl-win-predictor-6xyy9cmbslrq43qcgwfa7j.streamlit.app/)

---

## 📌 Overview

T20 cricket, especially the IPL, is known for rapid shifts in momentum. The **IPL Win Predictor** estimates the winning probability dynamically as the second innings progresses by taking into account key match variables such as target score, current score, overs completed, and wickets lost.

### Key Highlights
- **Historical Data:** Trained on IPL ball-by-ball and match dataset spanning from **2008 to 2019**.
- **Interactive Web UI:** Built and deployed seamlessly using **Streamlit**.
- **Instant Probabilities:** Generates split winning percentages for both the batting and bowling sides in real time.

---

## ⚙️ How It Works

The model evaluates the state of the chase using dynamic game metrics:
1. **Runs Remaining:** `Target - Current Score`
2. **Balls Remaining:** `120 - Total Balls Bowled`
3. **Wickets in Hand:** `10 - Wickets Fallen`
4. **Current Run Rate (CRR):** `Runs Scored / Overs Bowled`
5. **Required Run Rate (RRR):** `(Runs Remaining * 6) / Balls Remaining`

These derived features, combined with the teams involved and host venue, are passed into a pre-trained scikit-learn pipeline (`pipe.pkl`) to compute the calibrated win probabilities.

---

## 🗂️ Repository Structure

```text
├── .devcontainer/             # Container configuration
├── app.py                     # Streamlit frontend & application logic
├── iplWinnerPredictor.ipynb   # Exploratory Data Analysis, Feature Engineering & Model Training
├── pipe.pkl                   # Exported trained ML model pipeline
├── Procfile                   # Deployment process configuration
├── requirements.txt           # Python dependencies
├── setup.sh                   # Environment setup script
└── README.md                  # Project documentation
