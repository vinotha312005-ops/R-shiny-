# Compound Poisson Process with Exponential Interarrival Times and Exponential Jumps

## Introduction
This project studies a compound stochastic process defined as:

S(t) = X₁ + X₂ + ... + Xₙ(t)

where N(t) represents the number of arrivals up to time t and Xᵢ are the jump sizes associated with each arrival.

The model assumes:
- Interarrival times are exponentially distributed with rate λ
- Jump sizes Xᵢ are independent exponentially distributed random variables with parameter θ
- N(t) and Xᵢ are independent

---

## Distribution of Arrival Process

Since interarrival times follow an exponential distribution, the process N(t) follows a Poisson distribution:

N(t) ~ Poisson(λt)

The probability mass function is:

P(N(t) = n) = ( (λt)ⁿ e⁻ˡᵗ ) / n!

---

## Jump Size Distribution

Each jump Xᵢ follows an exponential distribution with density:

f(x) = θ e⁻ᶿˣ for x > 0

---

## Distribution of S(t)

### Mass at Zero

If no event occurs during time t, then S(t) = 0.

P(S(t) = 0) = e⁻ˡᵗ

---

### Continuous Distribution

If N(t) = n, then S(t) is the sum of n exponential variables, hence it follows a Gamma distribution:

S(t) | N(t) = n ~ Gamma(n, θ)

The density becomes a mixture:

fS(t)(s) = Σₙ₌₁^∞ [ e⁻ˡᵗ (λt)ⁿ / n! ] × [ θⁿ sⁿ⁻¹ e⁻ᶿˢ / (n-1)! ]

This shows that the distribution of S(t) is a **Poisson–Gamma mixture**.

---

## Laplace Transform

The Laplace transform of S(t) is:

L{S(t)}(u) = exp( λt ( θ / (θ + u) − 1 ) )

---

## Mean and Variance

Expected value:

E[S(t)] = λt / θ

Variance:

Var(S(t)) = 2λt / θ²

---

## Histogram Behaviour (Simulation Results)

### t = 10
- Most probability is concentrated at zero.
- Distribution is highly skewed.

### t = 100
- More arrivals.
- Distribution spreads out.

### t = 1000
- Shape becomes smooth and continuous.

### t = 10000
- Distribution approaches normal form (Central Limit Theorem).

---

## Impact of Parameters

### Effect of λ (Arrival Rate)
- Higher λ → more frequent arrivals → larger total value.
- Lower λ → fewer arrivals → more mass at zero.

### Effect of θ (Jump Parameter)
- High θ → smaller average jumps.
- Low θ → larger and heavier tail.

---

## R Shiny Deployment

An interactive R Shiny app was used to:

- Change λ and θ using sliders.
- Observe real-time effect on S(t).
- View hi
