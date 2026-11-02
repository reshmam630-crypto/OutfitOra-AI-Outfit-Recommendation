# OutfitOra — AI-Powered Personalized Outfit Recommendation

An intelligent outfit recommendation system that transforms weather forecasts and daily activities into personalized clothing suggestions.

OutfitOra combines **weather intelligence, rule-based reasoning, and machine learning** to help users decide what to wear based on weather conditions, planned events, transportation, and personal comfort preferences.

## Overview

Traditional weather applications tell us the temperature and probability of rain. OutfitOra takes the next step by translating weather information into practical, personalized clothing recommendations.

The system considers not only the weather but also when users will be outdoors, what activities they have planned, and how comfortable they feel in different conditions.

## Key Features

- **Weather-Based Recommendations** — Personalized clothing suggestions based on temperature, precipitation, wind, UV, and feels-like temperature.
- **Event-Aware Outfit Planning** — Classifies daily events into outdoor/indoor activities and dress codes.
- **Exposure-Aware Forecasting** — Considers commute and outdoor exposure periods rather than the entire day.
- **Personal Comfort Learning** — Machine learning adjusts recommendations based on user feedback.
- **Wear, Bring & Avoid Suggestions** — Clear, actionable clothing recommendations.
- **Weather Visualization** — Hourly weather charts and intuitive forecast summaries.
- **Calendar Integration** — Supports importing events through `.ics` calendar files.
- **Privacy-Focused Design** — Personal comfort weights are stored locally in the browser.

## System Architecture

```text
          React + Vite Frontend
                  |
                  | REST API
                  v
           FastAPI Backend
                  |
        +---------+---------+
        |         |         |
     Weather   Rules     ML Model
      API     Engine    (Comfort)
        |         |         |
        +---------+---------+
                  |
                  v
       Personalized Outfit Advice
```

## Technology Stack

| Component | Technologies |
|---|---|
| Frontend | React, JavaScript, Vite |
| Backend | Python, FastAPI |
| Machine Learning | Online Linear Regression, SGD, Ridge Regularization |
| Weather Data | Open-Meteo API |
| Data Visualization | Hourly weather charts |
| Testing | Pytest |
| Development Tools | Git, GitHub, VS Code |

## Machine Learning Approach

OutfitOra uses an online learning model to adapt recommendations to individual comfort preferences.

The model considers contextual features such as:

- Wind conditions
- Transportation type
- Cycling and walking activity
- Rain
- Sport and dress-code context

User feedback updates the model's comfort offset, allowing recommendations to become more personalized over time.

## Project Structure

```text
OutfitOra/
├── backend/
│   ├── app/
│   │   ├── engine.py
│   │   ├── events.py
│   │   ├── main.py
│   │   ├── ml.py
│   │   ├── schemas.py
│   │   ├── texts.py
│   │   └── weather.py
│   ├── tests/
│   ├── requirements.txt
│   └── README.md
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── App.jsx
│   │   ├── api.js
│   │   ├── main.jsx
│   │   └── styles.css
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
│
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.10+
- Node.js and npm

### 1. Clone the repository

```bash
git clone https://github.com/reshmam630-crypto/OutfitOra-AI-Outfit-Recommendation.git

cd OutfitOra-AI-Outfit-Recommendation
```

### 2. Set up the backend

```bash
cd backend

python -m venv .venv
```

Activate the virtual environment:

**Windows**
```bash
.venv\Scripts\activate
```

**macOS / Linux**
```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the backend:

```bash
uvicorn app.main:app --reload
```

### 3. Set up the frontend

Open a new terminal:

```bash
cd frontend

npm install
npm run dev
```

Open the local URL displayed by Vite in your browser.

## Testing

Run the backend tests:

```bash
cd backend

pytest
```

## Project Results

- Implemented rule-based clothing recommendation logic.
- Integrated hourly weather forecasting.
- Developed personalized comfort learning using online machine learning.
- Implemented event classification and exposure-window calculations.
- Created a modular frontend and backend architecture.
- **18 pytest tests passed** during project evaluation.

## Ethical Considerations

- User calendar information is processed without permanent server-side storage.
- Personal comfort weights remain in browser local storage.
- Recommendations are transparent and explainable through rules.
- Weather predictions may be inaccurate; recommendations are advisory, not a safety system.

## Contributors

Developed as a Master's AI project at Jönköping University by:

- Ardra Suresh
- Jinsy Panamkkattu
- Neethu Jose Chully
- Reshma Mani

## Acknowledgements

- Jönköping University
- Open-Meteo for weather forecasting and geocoding services

---

*OutfitOra — Making everyday outfit decisions smarter through Artificial Intelligence.*
