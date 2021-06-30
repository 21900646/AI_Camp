# Python

## 문자열 찾기
 ` string.find("찾을 단어") `

 `string.rfind("찾을 단어") ` : 문자열의 오른쪽부터 찾기
 
 ---
 
 ## 문자열 자르기
 
`a = "string".split(" ")`

---

## 조건문 사용

`if 이름 in "문자열"` : 문자열에 하나라도 포함되어 있으면 true

---

## 리스트
### 리스트에 요소 추가하기
### 리스트에서 요소 제거하기

`리스트명.pop(인덱스)`

`del 리스트명[인덱스]` : 요소 한꺼번에 제거 가능( : )

`리스트명.remove(값)` : 값으로 제거하기

### 리스트 요소 모두 없애기

`리스트명.clear()`

---

## dictionary

`dict['key']` -> {A:B} B부분이 프린트된다.

`dicttionary = {A:[a,b,c,d,e], B:[a,b,c,d]}` -> 가능

`dict['key']` -> {A:B} B부분이 프린트된다.

`dict.get('key')` -> value값을 들고온다.

값 넣을 때는, `dict[key] = 값` 하면 key:값으로 들어간다.

---

## 리스트 이름 = [표현식 for 반복자 in 반복할 수 있는 것 if 조건문]

 ```
array = ["사과", "자두", "초콜릿", "바나나", "체리"]

output = [fruit for fruit in array if fruit != "초콜릿"]
 ```

---

## 가변매개변수

제일 뒤에 써서 매개변수를 여러개 받는 것. 

def 이름(매개변수1, 매개변수2, ... , *가변매개변수)


## 메모화

한번 계산한 값을 저장한 후, 계산하는 과정 대신 나중에 이를 다시 활용하는 테크닉

---

## 튜플

변수 바꾸기 가능 -> a,b = b,a

여러 개의 값 리턴 가능 -> 

 ```
def test():

return (10, 20)

a, b = test()
 ```

---

## 람다

기능을 매개변수로 전달

`function(funt, list)`

---

## try except
 ```
try:

 예외가 발생할 가능성이 있는 코드
 
except:

 예외가 발생했을 때 실행할 코드
 
else:

 예외가 발생하지 않았을 때 실행할 코드
 
finally:

 무조건 실행할 코드
  ```
  
 ---
 
 ## 에러잡기
 
  ```
 try:
 
 except Exception as exception:
  ```
 
### raise 사용하기 (예외를 강제로 발생시킴)

 ```
if    :

 raise NotImplementedError
  ```
 
 ---
 
 ## url 다루는 라이브러리
 
  ```
 target = reequest.urlopen("http://~ ")
 
 output = target.read()
  ```
 
 **beautifulSoup 모듈**
 
 ```
 from urllib import request
 
 soup = BeautifulSoup(target, "html.parser")
 
 for location in soup.select("location"):
  print("도시:", location.select_one("city").string)
 
 ```
 
 **flask 모듈**
 
``` 
from flask import Flask

app = Flask(__name__)


@app.route("/")

def hello():

  return "<h1>Hello World!</h1>"
  
 ```
 
 코드실행
 
 > set FLASK_APP=flask_basic.py
 > flask run
 
 ---
 
```
import requests

from bs4 import BeautifulSoup

url = 'https://movie.naver.com/movie/sdb/rank/rmovie.nhn'

response = requests.get(url)

source = response.text

soup = BeautifulSoup(source, 'html.parser')

top_list = soup.findAll("div",{"class":"tit3"})

for m in top_list:

  print(m.text.strip())
```
 
 
