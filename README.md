# Polymarket-Parlay-Optimiser
## Overview

The Parlay Stake Optimizer helps users allocate their bankroll across multiple binary markets (e.g., Polymarket YES/NO markets) to maximize long‐run expected value (EV). By modeling dependencies between markets via a Gaussian copula and solving a constrained optimization, the tool recommends how much to stake on each leg of a parlay.

## Key Features

Marginal Probabilities: Ingest current YES‐prices (interpreted as probabilities) from Polymarket via API.

Dependence Modeling: Estimate pairwise dependence using Kendall’s τ and a Gaussian copula.

Joint Probability: Compute the probability that all selected markets resolve YES together.

Expected Value Calculation: Define EV as joint probability × minimum stake minus cost of stakes.

Optimization: Use Differential Evolution to maximize EV under a total bankroll constraint.

API Endpoint: FastAPI /recommend route returning recommended stakes and EV.