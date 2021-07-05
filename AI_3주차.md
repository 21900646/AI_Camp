## 시간 측정하기

```
%time

for i in range(10):
  print(i)
````

## numPy
![image](https://user-images.githubusercontent.com/69943167/124406705-09cccf80-dd7d-11eb-8abf-eed5b2229302.png)

행렬의 길이 알려면, len(arr) or len(arr[0])

### zeros& ones, arange
```
import numpy as np

arrayA = np.zeros((3,6))
arrayB = np.ones((3,6))

np.arange(100, 110)
np.arange(10,22,2)
np.arange(10,22,2).reshape(3,2)
```

```
실행화면 >
array([[0.,0.,0.,0.,0.,0.],
       [0.,0.,0.,0.,0.,0.],
       [0.,0.,0.,0.,0.,0.]])
---
array([100, 101, 102, 103, 104, 105, 106, 107, 108, 109])
array([10, 12, 14, 16, 18, 20])
array([10, 12],
      [14, 16],
      [18, 20])
```
** reshape할때는 개수가 맞아야함 **

