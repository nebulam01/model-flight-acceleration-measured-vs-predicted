# Model-Flight Acceleration — Measured vs. Predicted

An interactive **Google Colab** engineering tool built with `ipywidgets`, `NumPy`, `Pandas`, and `Matplotlib` to compare **predicted vertical acceleration (`[g]`)** against **measured acceleration (`[g]`)** during model-flight maneuvers using either a manual peak input (`Manual Peak Value [g]`) or simulated phone IMU data (`Simulated Phone IMU`), with an explanatory cause-and-effect verdict.

## Overview

Evaluating model-flight dynamics involves comparing expected load factors from a predictive model with measured sensor acceleration (`[g]`). This notebook works directly inside Google Colab without requiring a physical phone, outdoor flight test, or external CSV file, and explains why differences appear between prediction and measurement.

### Supported Flight Maneuvers
- **Smooth Glide & Bank Turn**
- **Climb & Pull-Up**
- **Gusty Approach**

### Measurement Modes
- **Manual Peak Value `[g]`:** Enter a target/measured peak acceleration (`[g]`) directly to test how it compares against the predicted maneuver profile.
- **Simulated Phone IMU:** Generates a realistic IMU-like acceleration trace with maneuver shifts, gusts, bias, and noise.

## Key Features

- **Interactive English UI (`ipywidgets`):** Select the maneuver, measurement mode, manual peak acceleration (`[g]`), sample rate (`Hz`), flight duration (`s`), IMU noise level, and sensor bias (`[g]`), then update live or via **Compare Acceleration**.
- **Predicted vs. Measured & Residual Plots:** Displays predicted and measured acceleration curves side by side with the residual error (`Measured - Predicted [g]`) plot.
- **Error Metrics & Cause-and-Effect Verdict:** Computes `RMSE`, `MAE`, peak acceleration difference, and max measured load, accompanied by a clear explanation of why the result occurred.

## How to Run in Google Colab

1. Open a new notebook in [Google Colab](https://colab.research.google.com/).
2. Paste the acceleration comparison code into a code cell and run it.
3. Adjust the maneuver, measured mode, peak value, noise, or bias to inspect the comparison curves, error metrics, and explanation.

## Engineering Notes

- Differences between predicted and measured acceleration typically stem from maneuver intensity differences, unmodeled gusts/turbulence, sensor bias, and IMU noise.
- Comparing synthetic/manual inputs with real flight logs helps validate load-factor models and error metrics before physical flight testing.
