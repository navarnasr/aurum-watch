# Model governance

Aurum Watch treats model evaluation as part of the product rather than as a one-time offline exercise.

## Evaluation loop

1. An eligible forecast is recorded before its outcome is known.
2. The first fresh market observation at or after the five-minute boundary resolves it.
3. The realized move is compared with the forecast-specific neutral band.
4. Directional accuracy, probability quality, calibration, and class-level metrics are updated.
5. Training and holdout observations remain logically separated for promotion decisions.

## Champion and challenger approach

The active model is the champion. A newly trained candidate is treated as a challenger and is promoted only after satisfying minimum data and holdout requirements. Rejected candidates remain visible for comparison instead of silently replacing the active model.

## Why this matters

Financial relationships drift. A model that performed well previously can weaken as volatility, liquidity, and market regimes change. Continuous scoring, explicit versioning, and rollback reduce the risk of treating an outdated model as permanently reliable.

## Interpretation limits

- Adjacent short-horizon forecasts are not fully independent.
- Accuracy alone can hide class imbalance and poor probability calibration.
- Backtests do not reproduce every live-data or execution constraint.
- External events can invalidate relationships learned from recent history.
- A directionally correct forecast may still be economically unusable after trading costs.
