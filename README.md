# OptionPricing
Used Black-Scholes model and Monte Carlo simulation to compute the option price

## Black-Scholes model

### Call price
$$C=S_tN(d1)+e^{-r(T-t)}KN(d2)$$

$$d1=\frac{\ln{\frac{S_t}{K}}+(r+\frac{1}{2}\sigma^2)(T-t)}{\sigma\sqrt{T-t}}$$

$$d2=\frac{\ln{\frac{S_t}{K}}+(r-\frac{1}{2}\sigma^2)(T-t)}{\sigma\sqrt{T-t}}=d1-\sigma\sqrt{T-t}$$

### Put price
$$P=e^{-r(T-t)}KN(-d2)-S_tN(-d1)$$

## Monte Carlo simulation
模擬多條股票路徑
$$S_{t+1}=S_te^{(r-0.5\sigma^2)\Delta{t}+\sigma\epsilon\sqrt{\Delta{t}}}$$
$$\ln{S_{t+1}}=\ln{S_t} + e^{(r-0.5\sigma^2)\Delta{t}+\sigma\epsilon\sqrt{\Delta{t}}}$$

計算call及put的價值
$$C_T=\max(S_T-K,0)$$ 
$$P_T=\max(K-S_T,0)$$

取期望值再折現
$C_t=c_te^{-r(T-t)}E(C_T)$
$P_t=p_te^{-r(T-t)}E(P_T)$
