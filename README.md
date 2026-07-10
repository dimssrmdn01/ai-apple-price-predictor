# AI Apple Price Predictor

A front-end web application that simulates AI-driven price forecasting for Apple products. Users select a product (iPhone, iPad, or MacBook), specify a forecast period, and receive an instant predicted price along with a trend chart comparing historical and forecasted values.

This project was built as a portfolio piece to demonstrate front-end engineering, UI/UX design, and data-presentation skills using plain HTML, CSS, and JavaScript — no frameworks or build tools required.

Live Demo: `https://dimssrmdn01.github.io/ai-apple-price-predictor/`
(Available once GitHub Pages is enabled — see Deployment below.)

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [How It Works](#how-it-works)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Deployment](#deployment)
- [Model Comparison](#model-comparison)
- [Limitations and Disclaimer](#limitations-and-disclaimer)
- [Roadmap](#roadmap)
- [License](#license)

## Overview

AI Apple Price Predictor presents itself as an AI-powered pricing platform, styled after Apple's own product marketing pages. The site is composed of a landing page introducing the "system," a section explaining the underlying methodology, a model-performance comparison table, and an interactive prediction tool.

The interface is designed to look and feel like a production SaaS product: dark theme, restrained animation, and a data-first visual language, so it reads well as a portfolio piece even though the forecasting logic itself is a client-side simulation rather than a trained machine learning model.

## Features

- **Landing page** with a hero section, key stats (models used, accuracy, product coverage, years of historical data), and a scroll-guided introduction to the product.
- **About section** outlining three pillars of the system: AI-powered modeling, real-time analysis, and proven accuracy.
- **Model comparison table** presenting five forecasting models (XGBoost, Random Forest, LSTM, Prophet, and ARIMA) evaluated on RMSE, MAE, MAPE, and R², with the best-performing model highlighted.
- **Feature grid** describing supporting capabilities: multiple evaluation metrics, historical data coverage, automatic model selection, and feature engineering.
- **Prediction tool** where the user selects a product, a period type (daily, weekly, monthly, or yearly), and a period value.
- **Instant results panel** showing predicted price, price change (with directional coloring), current price, the model used, and a confidence score.
- **Trend chart** rendered in inline SVG, plotting historical price points against the forecasted price with no external charting library.
- Fully responsive layout, keyboard-accessible form controls, and support for reduced-motion preferences.

## How It Works

All logic runs client-side in a single JavaScript file embedded in `index.html`:

1. A static list of Apple products (iPhone, iPad, and MacBook variants) is used as the base dataset, each with a reference price.
2. When a prediction is requested, a seeded pseudo-random generator produces a short synthetic price history for the selected product, ending at its current reference price.
3. A simple drift-and-noise formula projects the price forward across the requested number of days, based on the selected period type and value.
4. The result — predicted price, price change, confidence score, and the "model used" — is rendered into the results panel, and the trend chart is redrawn as an SVG polyline with a dashed segment connecting the last historical point to the forecast.

No network requests, backend server, or trained model are involved. This keeps the project fully static and deployable on GitHub Pages with zero configuration.

## Tech Stack

- **HTML5** for structure and semantic markup
- **CSS3** using custom properties (CSS variables) for theming, with no external UI framework
- **Vanilla JavaScript (ES6+)** for all interactivity and the simulated prediction logic
- **Inline SVG** for the price trend chart, rendered without any charting library
- **Google Fonts**: Inter for display and body text, IBM Plex Mono for numeric and data elements

## Project Structure
```
ai-apple-price-predictor/
├── index.html      Full application: markup, styles, and JavaScript logic
├── README.md       Project documentation
└── LICENSE         MIT license
```
The entire application is intentionally kept in a single HTML file to make it trivial to run, review, and deploy.

## Getting Started

### Prerequisites

No dependencies, package manager, or build step are required. Any modern web browser is sufficient.

### Run locally

Clone the repository and open the file directly:

```bash
git clone https://github.com/dimssrmdn01/ai-apple-price-predictor.git
cd ai-apple-price-predictor
open index.html   # macOS; on Windows use "start index.html", on Linux use "xdg-open index.html"
```

Alternatively, serve it with any static file server, for example:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deployment

The project is a static site, which makes GitHub Pages the simplest deployment target.

1. Push the repository to GitHub.
2. In the repository, go to **Settings → Pages**.
3. Under "Source," select the `main` branch and the `/ (root)` folder, then save.
4. After a short build delay, the site will be available at:
   `https://dimssrmdn01.github.io/ai-apple-price-predictor/`

## Model Comparison

The technology section of the site displays the following illustrative evaluation metrics, used to demonstrate how a real forecasting pipeline might compare candidate models before selecting one for production:

| Model         | RMSE      | MAE       | MAPE      | R²        |
|---------------|-----------|-----------|-----------|-----------|
| XGBoost       | 14.906634 | 10.503636 | 1.420909  | 0.948770  |
| Random Forest | 20.992757 | 16.159691 | 2.184153  | 0.898398  |
| LSTM          | 62.030641 | 49.572189 | 6.702927  | 0.112739  |
| Prophet       | 90.595417 | 74.716630 | 10.142177 | -0.864283 |
| ARIMA         | 99.780285 | 81.880075 | 11.325294 | -1.261460 |

XGBoost has the lowest error across RMSE, MAE, and MAPE, and the highest R², so it is presented as the automatically selected model for generating predictions.

## Limitations and Disclaimer

This project is a front-end simulation built for demonstration and portfolio purposes. It does not use real historical pricing data, and no machine learning model is trained, hosted, or called at runtime. Predicted prices are generated by a simple deterministic-with-noise formula in the browser, and the model comparison table is illustrative rather than the output of an actual evaluation pipeline.

This project should not be used to make real purchasing, investment, or business decisions.

## Roadmap

Potential extensions if this project is developed further:

- Replace the simulated forecasting logic with a real backend (for example, a Python/Flask service using scikit-learn, XGBoost, or a time-series library such as Prophet or statsmodels)
- Source and incorporate genuine historical pricing data for each product
- Add persistent storage for prediction history
- Add unit tests for the prediction and charting logic
- Add screenshots and a demo GIF to this README

## License

This project is released under the MIT License. You are free to use, modify, and distribute it.

---

Built as a personal portfolio project.
