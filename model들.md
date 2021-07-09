# 선형 회귀 분석
## 단순 선형 회귀
1. Gradient Descent 방법
![image](https://user-images.githubusercontent.com/69943167/125013579-0734e780-e0a7-11eb-8dfb-72844aa5b8ee.png)

```
def g_W(x,y,iters):
  total=0.0
  for i in range(len(x)):
    total=w[iters]*(x[i]**2) + b[iters]*x[i] - x[i]*y[i]
  return total

def g_b(x,y,iters):
  total=0.0
  for i in range(len(x)):
    total=w[iters]*x[i] + b[iters] - y[i]
  return total
  ```
  
## 결과 확인하기
```
model.coef_ //기울기
model.intercept_ //y절편

//randodmg seed 만들기
import numpy as np

rng = np.random.RandomState(42)
rng.rand(20)
```
  
