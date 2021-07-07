## 시간 측정하기

```
%time

for i in range(10):
  print(i)
````

# numPy
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
**reshape할때는 개수가 맞아야함**

## Shuffle & sort
```
A = np.random.randint(1,100,size = (10, 10))

np.random.shuffle(A)

np.sort(A, axis = 1) -> 가로정렬
np.sort(A, axis = 0) -> list[0]값을 기준으로 세로 정렬
```

# Pandas
## 특정 조건의 값만 바꾸기
```
df4[df4<0] = 0
```

## missing data
```
# E 값이라는 행 만들기(값은 NaN인 상태)
df5 = df3.reindex(index=d1[0:4], columns = list(df3.columns) + ['E'])
df5

# missing data 삭제
df5.dropna(how = 'any')
```

## Reshaping
```
df = pd.DataFrame({"id":[1,2,3,4,5,6], "raw_grade":['a','b','a','a','e']})
df["grade"] = df["raw_grade"].astype("category")
```

## Styling the DataFrame
```
df.style.highlight_max() -> 11111
df.style.hightlisht_min(axis=1) -> --------
df.style.highlight_null(null_color = "red")

# 글자도 nan대신에 OutofScope라고 써준다.
df.style.set_na_rep("OutofScope").highlight_null(null_color = "red")

# styling 하기
```

## 한국어 설치
```
!sudo apt-get install -y fonts-nanum
!sudo fc-cache -fv
!rm ~/.cache/matplotlib -rf
```

## csv 파일 실습
>> thousands는 문자열을 숫자로 바꿔주기 --> ',' 제거
>> encoding은 한글로 바꿔주는 것(만약 안된다면 utf-8말고 딴거 사용)
>> 
```
# 파일 읽어오기
cctv = pd.read_csv('drive/MyDrive/cctv.csv', encoding='utf-8', thousands = ',')
cctv.head()

# 목차만 보고싶을 때
cctv.columns

# 총계라는 목차를 기준으로 내림차순 정렬
cctv.sort_values(by='총계', ascending=False).head(5)

# 새로운 목차 지정해서 값 넣기
cctv['최근증가율'] = (cctv['2020년']+cctv['2019년']+cctv['2018년']) / (cctv['2017년']+cctv['2016년']+cctv['2015년']) * 100
