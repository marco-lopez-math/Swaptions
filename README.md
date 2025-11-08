# Swaptions
This project explores the pricing of interest rate derivatives, swaptions in particular.

### The Risk

Lenders and borrowers are exposed to changes in interest rates. For a borrower paying a variable interest rate there is a risk of interest rates rising suddenly. If they pay a fixed interest rate and the reference interest rate decreases they may be interested in opportunities to take advantage of more favorable rate. There are similar considerations from the lending side.

### Swaps

The type of derivative we will focus on is a **_swaption_**, which is an option contract with swaps as the underlying asset. A _**swap**_ is a contract between 2 entities, A and B, where A pays B a floating rate at regular time intervals, and B pays A a fixed interest rate,, called the _**swap rate**_, at the same time intervals.

![Image](https://github.com/user-attachments/assets/a3927090-e003-41d6-a997-2b98ff5371f8)

### The Code

The code includes the following functions:

1. `SR(per, start, duration, discount)`  computes the swap-rate assuming the variable forward rates are known. The forward rates in turn can be expressed in terms of zero-coupon bonds, which are inputed into the function as the _discount_. The other inputs are the periodicity of the cash flows, the starting time, and the duration of the contract.
2. The function `payers_swaption(B, X, K, sig, T1)` calculates the present value of a _payers swaption_, i.e., the swaption for the entity to pay the fixed rate in the swap contract. The calculation is done via a closed-form formula known as Black's formula (solution to Black-Scholes equation). The inputs are the annuity at time 0, the swap-rate at time zero, the strike rate, volatility, and the expiration period.
3. `GBM_SR(X0, sigma, T1, n_sims, n_steps)` models the evolution of the swap rate by Geometric Brownian Motion.
4.  Finally, we compare the prices obtained via Black's formula and the Monte Carlo simulation.
