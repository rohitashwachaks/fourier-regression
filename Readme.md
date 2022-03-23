# Trippy Generator

## Objective

Generate / Predict /  Forecast future cycles.

## Assumptions

We assume that the data given to us contains cyclical patterns.

Right now, we work on a simple wave function; to test our model

Future work includes:

- Auto-Regressive time series data like music (rhythm)
- Generalised Regression, where the cycles in the dependent variables are dependent, not on itself, but instead the cycles of the independent variables. (Fourier Transformation of the predictors)

## Methodology

For the Auto-regressive case, we assume that the past data is a good approximator of the future data. i.e: History repeats itself.

- **Step 1:**
  - Break down data in chunks (size = cycle duration)
    - If not known, Cross Validation (Future score)
  - Remove Linear trends in the data
  - Run Linear regression on the data set, and focus on the residuals
- **Step 2:**
  - Decompose residuals into frequencies (Fourier Transformation)
  - Select frequencies using Regression (across time-chunks) and minimising SSE of error (residual - predicted value from the fourier transform)
- **Step 3:**
  - Predict / Forecast linear component (= 0 for now)
  - Predict / Forecast cyclic component (from the model in Step 2)
- **Step 4:**
  - Pat yourself on the back and realise you're _wicked shmart_
  - Find a corner and cry when you realise someone beat you to this by a few (2-80) years
