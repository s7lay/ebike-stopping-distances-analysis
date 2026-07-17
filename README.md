# E-Bike Stopping Distance Analysis

This repository contains a Jupyter Notebook that analyzes and models the relationship between an electric bicycle's speed (km/h) and its stopping distance (meters). It compares a **Linear Regression** model against a **Quadratic (Polynomial) Regression** model to determine which best fits the physical nature of stopping distances—especially at lower speeds.

##  Project Overview
Stopping distance is physically expected to have a quadratic relationship with speed due to kinetic energy ($E_k = \frac{1}{2}mv^2$). This project demonstrates this concept by:
1. Fitting a **Linear Model** to mid-to-high speed e-bike data.
2. Highlighting the flaw in the linear model (it predicts physically impossible negative stopping distances at low speeds).
3. Introducing a low-speed dataset to calibrate the model.
4. Fitting a **Quadratic Model** on the combined dataset to achieve a physically accurate curve and a higher $R^2$ score.

##  Datasets
*   `ebike-stopping-distances.csv`: Contains speed and stopping distance data for normal riding speeds (15 to 36 km/h).
*   `ebike-data-low-speed.csv`: Contains calibrated stopping distance data for low speeds (0 to 13 km/h).

##  Model Performance & Results

### 1. Linear Model
*   **Formula:** $y = 0.45x - 3.64$
*   **Goodness of Fit ($R^2$):** `0.968`
*   *Limitation:* Predicts negative stopping distances for speeds below ~8 km/h.

### 2. Quadratic Model (Polynomial Degree 2)
*   **Formula:** $y = 0.01x^2 + 0.14x - 0.43$
*   **Goodness of Fit ($R^2$):** `0.989`
*   *Advantage:* Provides a much better, physically realistic fit across all speed ranges (from 0 to 40 km/h).

##  Tech Stack & Dependencies
This project is written in Python and uses the following libraries:
*   **Pandas:** For data manipulation and loading CSV files.
*   **Matplotlib:** For data visualization and plotting regression lines/curves.
*   **Scikit-Learn:** For implementing `LinearRegression` and `PolynomialFeatures`.

