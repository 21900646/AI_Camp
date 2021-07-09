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
  
## 로지스틱회귀
```
//데이터 준비
import pandas as pd
from sklearn.datasets import load_iris
import seaborn as sns; sns.set()
%matplotlib inline

iris = load_iris()
df = pd.DataFrame(iris.data, columns = iris.feature_names)
df['species']=pd.Series(iris.target)
df.info()

//학습시킬 새로운 데이터 frame만들기
sl_df = pd.DataFrame()

sl_df['speacial_health'] = df['sepal length (cm)']
sl_df['species'] = df['species']
sl_df.info()

sl_df = sl_df[:100] //class만
sl_df.info()

sl_df.describe()

//데이터 확인
sns.pairplot(sl_df, hue='species')

//학습 데이터, 테스트 데이터 나누기
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(sl_df.iloc[:,:1], sl_df.iloc[:, 1:], test_size=0.33)

//모델을 인스턴스화
from sklearn.linear_model import LogisticRegression
lr = LogisticRegression()

//특징과 대상 벡터로 배치
X = x[:, np.newaxis]
x.shape
X.shape

//학습시키기
lr.fit(X_train,y_train)

//모델 그래프 그리기
import seaborn as sns; sns.set()
sns.lmplot(x='sepal_length', y='species', data=sl_df, logistic=True)

//학습된 데이터 성능 평가
from sklearn.metrics import classification_report, confusion_matrix
print(confusion_matrix(y_train, lr.predict(X_train)))
print(classification_report(y_train, lr.predict(X_train)))

//테스트 데이터 성능 평가
print(confusion_matrix(y_test, lr.predict(X_test)))
print(classification_report(y_test, lr.predict(X_test)))
```







