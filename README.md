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
$$S_{t+1}=S_t \mu dt + S_t \sigma dW_t$$
$$S_{t+1}=S_te^{(r-0.5\sigma^2)d{t}+\sigma\epsilon\sqrt{d{t}}}$$
$$\ln{S_{t+1}}=\ln{S_t} + e^{(r-0.5\sigma^2)d{t}+\sigma\epsilon\sqrt{d{t}}}$$

計算call及put的價值
$$C_T=\max(S_T-K,0)$$ 
$$P_T=\max(K-S_T,0)$$

取期望值再折現
$$C_t=e^{-r(T-t)}E(C_T)$$
$$P_t=e^{-r(T-t)}E(P_T)$$

## 程式碼及文章連結
BSmodel.ipynb 
https://medium.com/@minkuanchen/python-%E9%81%B8%E6%93%87%E6%AC%8A%E5%AE%9A%E5%83%B9black-scholes-model-9ee04dc26287

MCS.ipynb 
https://medium.com/@minkuanchen/python-%E9%81%B8%E6%93%87%E6%AC%8A%E5%AE%9A%E5%83%B9monte-carlo-simulation-d62a535b2dac

TaiwanOptionQuoteAndIndexQuote.ipynb 
https://minkuanchen.medium.com/python-%E7%88%AC%E8%9F%B2%E5%8F%B0%E6%8C%87%E9%81%B8%E6%93%87%E6%AC%8A%E5%8F%8A%E5%A4%A7%E7%9B%A4%E5%A0%B1%E5%83%B9-873dd4a3978a
