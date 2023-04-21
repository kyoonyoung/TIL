# list

- 시퀀스 자료형, 여러 데이터들의 집합
- int, float 같은 다양한 데이터 타입 포함

<br/>

## 인덱싱 (indexing)
```python
colors = ["red", "blue", "green"]
print (colors[0])     # red
print (colors[2])     # green
print (len(colors))   # 3
                        # len은 list의 길이를 반환
```

```python
type(colors[2])    # <class 'str'>
len(colors)        # 3
```
<br/>


## 슬라이싱 (Slicing)

```python
cities = ["서울", "부산", "인천", "대구", "광주", "울산", "수원"] 
print(cities) 
# ['서울', '부산', '인천', '대구', '광주', '울산', '수원']

cities[0:3] 
# ['서울', '부산', '인천'] 
# 0부터 3까지 ※ 마지막 값은 출력이 되지 않음.

cities[3:5] # ['대구', '광주']
cities[-2:] # ['울산', '수원']
cities[-5:-3] # ['인천', '대구']

cities[:] 
# ['서울', '부산', '인천', '대구', '광주', '울산', '수원']
cities[-50:50] 
# ['서울', '부산', '인천', '대구', '광주', '울산', '수원']

cities[0:10:2] # ['서울', '인천', '광주', '수원'] 
# [여기부터:여기까지:step칸 씩 띄워서]

cities[10::-1] # ['수원', '울산', '광주', '대구', '인천']

cities[3:6] # ['대구', '광주', '울산']
cities[-1:-5:-2] #['수원', '광주'] 
```

<br/>


## 리스트의 연산
- concatenation, is_in, 연산 함수들

```python
color = ["red", "blue", "green"]
color2 = ["orange", "black", "white"]
print(color + color2) 
# ['red', 'blue', 'green', 'orange', 'black', 'white']

color[0] = "yellow" # ['yellow', 'blue', 'green'] 

"blue" in color # True
"blue" in color # False

total_color = color + color2 
# ['yellow', 'blue', 'green', 'orange', 'black', 'white']

color.append("white") # ['yellow', 'blue', 'green', 'white']
color.extend(["black", "purple"]) 
# ['yellow', 'blue', 'green', 'white', 'black', 'purple']
color.insert(0,"orange")  
# ['orange', 'yellow', 'blue', 'green', 'white', 'black', 'purple']
color.remove("white") 
# ['orange', 'yellow', 'blue', 'green', 'black', 'purple']
del color[0] # ['yellow', 'blue', 'green', 'black', 'purple'] 
# 0번째 주소 리스트 객체 삭제
```

<br/>


## Python 리스트만의 특징
- 다양한 Data Type이 하나의 List에 들어감

```python
a = ["color", 1, 0.2]
color = ["yellow", "blue", "green", "black", "purple"]
a[0] = color # 리스트 안에 리스트도 입력 가능
print(a)
# [['yellow', 'blue', 'green', 'black', 'purple'], 1, 0.2]
```
<br/>

## 리스트 메모리 저장 방식
- 파이썬은 해당 리스트 변수에는 리스트 주소 값이 저장됨

```python
a = [5,4,3,2,1]
b = [1,2,3,4,5]
b = a
print (b) # [5,4,3,2,1]
a.sort() # [1,2,3,4,5]
print (b) # [1,2,3,4,5]  # a와 b의 메모리 주소가 같기 때문
b = [6,7,8,9,10]
print (a,b) # [1,2,3,4,5] [6,7,8,9,10]
```

<br/>

## 패킹과 언패킹
- 패킹: 한 변수에 여러 개의 데이터를 넣는 것
- 언패킹: 한 변수의 데이터를 각각의 변수로 반환

```python
t = [1,2,3]   # 1,2,3을 변수 t에 패킹
a, b, c = t   # t에 있는 값 1,2,3 을 변수 a, b, c에 언패킹
print(t,a,b,c) # [1,2,3] 1 2 3
```

<br/>

## 이차원 리스트(two dimensional list)
- 리스트 안에 리스트를 만들어 행렬(Matrix) 생성

```python
kor_score = [49,79,20,100,80]
math_score = [43,59,85,30,90]
eng_score = [49,79,48,60,100]
midterm_score = [kor_score, math_score, eng_score]
print (midterm_score[0][2]) # 20
```

||A|B|C|D|E|
|:------:|:---:|:---:|:---:|:---:|:---:|
|국어점수|49|79|20|100|80|
|수학점수|43|59|85|30|90|
|영어점수|49|79|48|60|100| 

<br/>

## 정체 모를 문제
```python
def simple_calculator(a,b,c):
    return eval(f"{a}{c}{b}")

a = input("첫 번째 숫자:")
b = input("두 번째 숫자:")
c = input("연산자:")

result = simple_calculator(a,b,c)
print("결과:", result)
```

>이 코드는 간단한 계산기를 만드는 코드입니다.

simple_calculator 함수는 세 개의 인수 a, b, c를 받습니다. 이 함수는 eval 함수를 사용하여 문자열로 입력된 수식을 계산하고, 결과를 반환합니다.

그리고 사용자로부터 input 함수를 사용하여 첫 번째 숫자(a), 두 번째 숫자(b), 연산자(c)를 입력 받습니다. 그 다음 simple_calculator 함수에 입력된 값을 전달하여 계산 결과를 result 변수에 저장하고 출력합니다.

예를 들어, 사용자가 2, 3, +를 입력하면 simple_calculator 함수는 eval("2+3")을 수행하여 5를 반환하고, result 변수에는 5가 저장됩니다. 마지막으로 print 함수를 사용하여 "결과: 5"와 같은 형식으로 결과를 출력합니다.