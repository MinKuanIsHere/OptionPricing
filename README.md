# OptionPricing
Used Black-Scholes model and Monte Carlo simulation to compute the option price

We follow the BS model to compute the call and put option price

### Call price
$C=S_tN(d1)+e^{-r(T-t)}KN(d2)$
$d1=\frac{\ln{\frac{S_t}{K}}+(r+\frac{1}{2}\sigma^2)(T-t)}{\sigma\sqrt{T-t}}$
$d2=\frac{\ln{\frac{S_t}{K}}+(r-\frac{1}{2}\sigma^2)(T-t)}{\sigma\sqrt{T-t}}=d1-\sigma\sqrt{T-t}$

### Put price
$$P=e^{-r(T-t)}KN(-d2)-S_tN(-d1)$$
