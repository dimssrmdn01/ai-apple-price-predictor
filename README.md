#  AI Apple Price Predictor

> **🚀 Live Demo:**(https://dimssrmdn01.github.io/ai-apple-price-predictor/)
> *(Available once GitHub Pages is enabled-see Deployment section below)*

A front-end web application that simulates AI-driven price forecasting for Apple products. Users select a product (iPhone, iPad, or MacBook), specify a forecast period, and receive an instant predicted price along with a trend chart comparing historical and forecasted values.

This project was built as a portfolio piece to demonstrate front-end engineering, UI/UX design, and data-presentation skills using plain HTML, CSS, and JavaScript  **no frameworks or build tools required.**

---

##  Table of Contents
- [Overview](#-overview)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Deployment](#-deployment)
- [Model Comparison](#-model-comparison)
- [Roadmap](#-roadmap)
- [License](#-license)

---

##  Overview
AI Apple Price Predictor presents itself as an AI-powered pricing platform, styled after Apple's own product marketing pages. The site is composed of a landing page introducing the "system," a section explaining the underlying methodology, a model-performance comparison table, and an interactive prediction tool.

The interface is designed to look and feel like a production SaaS product: dark theme, restrained animation, and a data-first visual language. It reads well as a portfolio piece even though the forecasting logic itself is a client-side simulation rather than a trained machine learning model.

---

##  Features
* **Landing Page:** Features a hero section, key stats (models used, accuracy, product coverage, years of historical data), and a scroll-guided introduction.
* **About Section:** Outlines the three pillars of the system: AI-powered modeling, real-time analysis, and proven accuracy.
* **Model Comparison Table:** Presents five forecasting models (XGBoost, Random Forest, LSTM, Prophet, and ARIMA) evaluated on RMSE, MAE, MAPE, and R², highlighting the best-performing model.
* **Feature Grid:** Describes supporting capabilities like multiple evaluation metrics, historical data coverage, automatic model selection, and feature engineering.
* **Prediction Tool:** Allows users to select a product, period type (daily, weekly, monthly, or yearly), and a period value.
* **Instant Results Panel:** Displays predicted price, price change (with directional coloring), current price, the model used, and a confidence score.
* **Trend Chart:** Rendered in inline SVG, plotting historical price points against the forecasted price without any external charting library.
* **Accessibility:** Fully responsive layout, keyboard-accessible form controls, and support for reduced-motion preferences.

---

##  How It Works
All logic runs client-side in a single JavaScript file embedded in `index.html`:

1. A static list of Apple products (iPhone, iPad, and MacBook variants) is used as the base dataset, each with a reference price.
2. When a prediction is requested, a seeded pseudo-random generator produces a short synthetic price history for the selected product, ending at its current reference price.
3. A simple drift-and-noise formula projects the price forward across the requested number of days, based on the selected period type and value.
4. The result is rendered into the results panel, and the trend chart is redrawn as an SVG polyline with a dashed segment connecting the last historical point to the forecast.

> **Note:** No network requests, backend server, or trained models are involved. This keeps the project fully static and deployable on GitHub Pages with zero configuration.

---

##  Tech Stack
* **HTML5:** Structure and semantic markup
* **CSS3:** Custom properties (CSS variables) for theming (No external UI framework)
* **Vanilla JavaScript (ES6+):** Interactivity and simulated prediction logic
* **Inline SVG:** Price trend chart rendering (No charting library)
* **Google Fonts:** Inter (display/body text) and IBM Plex Mono (numeric/data elements)

---

##  Project Structure
```text
ai-apple-price-predictor/
├── index.html      # Full application: markup, styles, and JS logic
├── README.md       # Project documentation
└── LICENSE         # MIT license
```

The entire application is intentionally kept in a single HTML file to make it trivial to run, review, and deploy.

##  Getting Started

### Prerequisites
No dependencies, package manager, or build step are required. Any modern web browser is sufficient.

### Run Locally
Clone the repository and open the file directly:

```bash
git clone https://github.com/dimssrmdn01/ai-apple-price-predictor.git
cd ai-apple-price-predictor

# Open the file based on your OS:
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Alternatively, serve it with any static file server:

```bash
python3 -m http.server 8000
# Then open http://localhost:8000 in your browser
```

---

##  Deployment
The project is a static site, which makes GitHub Pages the simplest deployment target.

1. Push the repository to GitHub.
2. In the repository, go to **Settings → Pages**.
3. Under "Source," select the `main` branch and the `/ (root)` folder, then click **Save**.
4. After a short build delay, the site will be available at your designated GitHub Pages link.

---

##  Model Comparison
The technology section of the site displays the following illustrative evaluation metrics, used to demonstrate how a real forecasting pipeline might compare candidate models before selecting one for production:

| Model | RMSE | MAE | MAPE | R² |
|---|---|---|---|---|
| XGBoost | 14.906634 | 10.503636 | 1.420909 | 0.948770 |
| Random Forest | 20.992757 | 16.159691 | 2.184153 | 0.898398 |
| LSTM | 62.030641 | 49.572189 | 6.702927 | 0.112739 |
| Prophet | 90.595417 | 74.716630 | 10.142177 | -0.864283 |
| ARIMA | 99.780285 | 81.880075 | 11.325294 | -1.261460 |

XGBoost has the lowest error across RMSE, MAE, and MAPE, and the highest R², so it is presented as the automatically selected model for generating predictions.

---

##  Roadmap
Potential extensions if this project is developed further:

- Replace the simulated forecasting logic with a real backend (e.g., Python/Flask service using scikit-learn, XGBoost, Prophet, or statsmodels).
- Source and incorporate genuine historical pricing data for each product.
- Add persistent storage for prediction history.
- Add unit tests for the prediction and charting logic.
- Add screenshots and a demo GIF to this README.

---

##  Limitations and Disclaimer
This project is a front-end simulation built for demonstration and portfolio purposes. It does not use real historical pricing data, and no machine learning model is trained, hosted, or called at runtime. Predicted prices are generated by a simple deterministic-with-noise formula in the browser, and the model comparison table is illustrative rather than the output of an actual evaluation pipeline.

This project should not be used to make real purchasing, investment, or business decisions.

---

##  License
This project is released under the MIT License. You are free to use, modify, and distribute it.

---

