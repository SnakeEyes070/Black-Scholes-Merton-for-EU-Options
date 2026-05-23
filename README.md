# Black-Scholes Merton to Price European Options

## Overview
The **Black-Scholes model** is a widely used mathematical model for pricing European-style options. It is based on the assumption that the price of the underlying asset follows a geometric Brownian motion. The model provides a closed-form solution to price both **call** and **put** options.

This project implements the **Black-Scholes model** for pricing European options and calculates the **Greeks**—Delta, Gamma, Theta, Vega, and Rho—which help understand the sensitivity of the option's price to various factors like the underlying asset price, volatility, time to maturity, and interest rates.

---

## Assumptions of the Black-Scholes Model
The model relies on the following assumptions:

1. **No dividends** are paid during the life of the option.
2. **No transaction costs** in buying or selling the option.
3. The price of the underlying asset follows **geometric Brownian motion**.
4. **Markets are efficient**, meaning that all available information is reflected in the prices.
5. **Risk-free rate and volatility** are constant and known.
6. The option is **European**, which means it can only be exercised at expiration.

---

## Black-Scholes Formula

The **Black-Scholes** formula for a **call option (C)** and a **put option (P)** is: <br>
<br>
![BSM Formula](https://quicklatex.com/cache3/52/ql_d7304578ade14d9b07a93d8393c59f52_l3.png)

---

## Greeks Calculations

### The Greeks

The Greeks are key metrics that measure the sensitivity of the option price to various factors. These include:

- **Delta** (Δ): Measures the sensitivity of the option price to changes in the underlying asset's price.  
   <br>![Delta](https://quicklatex.com/cache3/9c/ql_b86f616063655971d815745a3c575c9c_l3.png)
  
- **Gamma** (Γ): Measures the rate of change of Delta with respect to the underlying asset's price.  
  <br>![Gamma](https://quicklatex.com/cache3/62/ql_3e29d6ac5840d91c5d68b3751a842662_l3.png)

  
- **Theta** (Θ): Measures the sensitivity of the option price to the passage of time.  
  <br>![Theta](https://quicklatex.com/cache3/cd/ql_92e1a602ce779aa517df2435943073cd_l3.png)


- **Vega** (ν): Measures the sensitivity of the option price to changes in volatility.  
  <br>![Vega](https://quicklatex.com/cache3/61/ql_822b97eed0d75a8ec41736cbf5152c61_l3.png)

  
- **Rho** (ρ): Measures the sensitivity of the option price to changes in the risk-free interest rate.  
  <br>![Rho](https://quicklatex.com/cache3/f5/ql_cbd28126234c2cbcd1871d83370afaf5_l3.png)

---

## Results and Analysis
``` code
Considering these inputs:  
S = 40 # Underlying Price of the Asset
K = 50 # Strike Price
T = 2 # Time to Expiration (Maturity)
r = 0.1 # Risk-Free Rate
vol = 0.1 # Volatility (σ, standard deviation)
```

### 1. BSM Options Pricing Results 
The value of `d1` is:  -0.0929  
The value of `d2` is:  -0.2344  
The price of the call option is: $1.84  
The price of the put option is: $2.78


### 2. **Delta vs. Underlying Asset Price**  
![Delta vs. Underlying Price](https://github.com/1Aditya7/Black-Scholes-Merton-for-EU-Options/blob/main/bsmPlots/delta.png)
- **Delta** represents the rate of change of the option's price with respect to changes in the price of the underlying asset.
- As the underlying asset price increases, **Delta** increases for call options and decreases for put options.

**Inference**: The plot shows how the Delta of call and put options changes with the underlying asset price. Delta measures the sensitivity of an option's price to changes in the underlying asset price. Call options have positive Delta, meaning their value increases as the underlying price increases, while put options have negative Delta, meaning their value decreases as the underlying price increases.

---

### 3. **Gamma vs. Underlying Asset Price**  
![Gamma vs. Underlying Price](https://github.com/1Aditya7/Black-Scholes-Merton-for-EU-Options/blob/main/bsmPlots/gamma.png)
- **Gamma** measures the rate of change of Delta with respect to the underlying asset's price. It helps assess the stability of Delta.
- As the underlying price moves away from the strike price, **Gamma** tends to decrease.

**Inference**: The plot shows how the Gamma of an option changes with the underlying asset price. Gamma measures the rate of change of Delta with respect to the underlying price. The plot shows that Gamma is highest around the option's strike price and decreases as the underlying price moves away from the strike price. This implies that the option's Delta, or sensitivity to price changes, is most sensitive to changes in the underlying price near the strike price.

---

### 4. **Theta vs. Underlying Asset Price**  
![Theta vs. Underlying Price](https://github.com/1Aditya7/Black-Scholes-Merton-for-EU-Options/blob/main/bsmPlots/theta.png)
- **Theta** represents the rate of change in the option’s price with respect to time to expiration.
- As time passes, the value of both call and put options generally decreases due to time decay, with the rate of decay increasing as the option nears expiration.

**Inference**: The plot shows how the Theta of call and put options changes with the underlying asset price. Call options have negative Theta, meaning their value decreases over time, while put options have positive Theta, meaning their value increases over time.

---

### 5. **Vega vs. Underlying Asset Price**  
![Vega vs. Underlying Price](https://github.com/1Aditya7/Black-Scholes-Merton-for-EU-Options/blob/main/bsmPlots/vega.png)
- **Vega** measures the sensitivity of the option price to changes in volatility.
- As volatility increases, both call and put options typically increase in value, though this effect is more pronounced for options that are at-the-money.

**Inference**: The plot shows how the Vega of an option changes with the underlying asset price. Vega measures the sensitivity of an option's price to changes in implied volatility. Vega is highest for at-the-money options and decreases as the option moves further out-of-the-money or in-the-money.

---

### 6. **Rho vs. Underlying Asset Price**
![Rho vs. Underlying Price](https://github.com/1Aditya7/Black-Scholes-Merton-for-EU-Options/blob/main/bsmPlots/rho.png)
- **Rho** measures the sensitivity of the option price to changes in the risk-free interest rate.
- For call options, an increase in interest rates increases the option’s price, while for put options, the price decreases.

**Inference**: The plot shows how the Rho of call and put options changes with the underlying asset price. Rho measures the sensitivity of an option's price to changes in the risk-free interest rate. Call options have positive Rho, meaning their value increases as interest rates increase, while put options have negative Rho, meaning their value decreases as interest rates increase. Rho is generally larger for longer-term options.

---

## Conclusion
The **Black-Scholes option pricing model** provides a theoretical approach to pricing European-style options and calculating the Greeks to assess the impact of various market factors. By understanding how the Greeks behave, investors can better manage their portfolios and assess risks associated with options trading.

The plots presented here give valuable insights into how the option price changes in response to different factors such as the underlying asset price, time to maturity, volatility, and interest rates.
