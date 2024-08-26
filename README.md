# HJM

The Heath-Jarrow-Morton (HJM) model is a framework used for modeling the evolution of interest rates over time. Unlike short-rate models, which focus on modeling the instantaneous short-term interest rate, the HJM model directly models the entire forward rate curve. This makes the HJM model particularly useful for pricing and managing interest rate derivatives.


Forward Rate:
The forward rate f(t,T) is the interest rate agreed upon today for a loan that starts at time 
T in the future. The HJM model describes how this forward rate changes over time.

Forward Rate Curve:
The forward rate curve represents forward rates for different maturities at a given point in time. The HJM model allows this entire curve to evolve over time.

Stochastic Differential Equation (SDE):
The HJM framework models the evolution of the forward rate curve using a stochastic differential equation, which incorporates randomness (typically via Brownian motion).



1. HJM Forward Rate Dynamics
In the HJM model, the forward rate f(t,T) at time t for maturity 
T evolves according to the following stochastic differential equation:
df(t, T) = alpha(t, T) * dt + sigma(t, T) * dW(t)
Where:
df(t, T) is the change in the forward rate at time t for maturity T.
alpha(t, T) is the drift term, which ensures no arbitrage.
sigma(t, T) is the volatility term, which can vary over time and with different maturities.
dW(t) is a Wiener process, representing the random shock at time t.

2. Drift Condition (No-Arbitrage Condition)
The drift term alpha(t,T) is not arbitrary; it is determined by the no-arbitrage condition. Under the HJM framework, the drift term is given by:
alpha(t, T) = sigma(t, T) * integral_{t}^{T} sigma(t, s) * ds
This condition ensures that the model does not allow for arbitrage opportunities.

3. Forward Rate Curve Evolution
Given initial forward rates and the volatility structure, the HJM model simulates the forward rate curve's evolution. Over a small time interval dt, the forward rate f(t,T) can be updated as:
f(t + dt, T) = f(t, T) + alpha(t, T) * dt + sigma(t, T) * dW(t)
This equation models how the forward rate for a specific maturity T evolves over time t.


Initialize the Forward Rate Curve:
Start with an initial forward rate curve, f(0,T), for different maturities T.

Specify Volatility:
Define a volatility structure sigma(t,T) that describes how volatility varies over time and across maturities.

Simulate the Forward Rates:
Use the stochastic differential equation to simulate the forward rates f(t,T) over time.
