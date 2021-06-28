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

`array = ["사과", "자두", "초콜릿", "바나나", "체리"]`

`output = [fruit for fruit in array if fruit != "초콜릿"]`

---

## 가변매개변수

제일 뒤에 써서 매개변수를 여러개 받는 것. function 이름(매개변수1, 매개변수2, ... , *가변매개변수)

