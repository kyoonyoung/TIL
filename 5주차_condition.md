 ## condition

 #

 * 프로그램 작성 시, <span style="color:blue"> 조건에 따른 판단</span>과 <span style="color:blue"> 반복</span>은 <span style="color:blue"> 필수</span>

 <br/>
<br/>

# 조건문이란?

## - 조건에 따라 특정한 동작을 하게하는 명령어

<br/>

## - 프로그램 예시 in 생활
   
   - <span style="color:red"> 빨강</span> = 조건 , <span style="color:blue"> 파랑</span> = 행동
   1. 지하철 <span style="color:red"> 앞 차 간격이 10m 이하</span>면 <span style="color:blue"> 속도를 10km 이하로 늦춰라</span>
   2. <span style="color:red"> 사용자가 10세 이하</span>면 <span style="color:blue"> VOD를 플레이 하지 마라</span> 
   3. <span style="color:red"> 휴대폰 패턴이 5회 틀리면</span> <span style="color:blue"> 20초 동안 대기 상태로 만들어라</span>

<br/>

조건문은 <span style="color:red"> 조건을 나타내는 기준</span>과 <span style="color:blue"> 실행해야 할 명령</span>으로 구성됨

조건의 참, 거짓에 따라 실행해야 할 명령이 수행되거나 되지 않음

<br/>

## 파이썬은 조건문으로 <span style="color:blue"> if, else, elif</span>등의 예약어를 사용함

<br/>

<br/>

# if else 문법

```python
if <조건>:          # if를 쓰고 조건 삽입 후 ":" 입력
    <수행 명령 1-1> # 들여쓰기(indentation)후 수행명령 입력 (true)
    <수행 명령 1-2> # 같은 조건하에 실행일 경우 들여쓰기 유지
else:              # 조건 불일치(false)할 경우 수행할 명령 block
    <수행 명령 2-1> # 조건 불일치 시 수행할 명령 입력
    <수행 명령 2-2> # 조건 불일치 시 수행할 명령 들여쓰기 유지
```

1. 조건 판단 방법
2. 조건 일치 시 수행 명령 block ":"와 들여쓰기
3. 조건 불일치 시 수행 명령 block

<br/>

```python
print ("Tell me your age?")
myage = int(input())  # 나이를 입력 받아 myage 변수에 할당
if myage < 30:        # myage 가 30 미만일 때
    print ("Welcome to the club")
else:                 # myage 가 30 이상일 때
    print("Get out of here!!!!")
```

입력 받은 값이 "30 미만" 이라는 조건에 따라 명령 실행

<br/>

## 조건 판단 방법

#

## - if 다음에 조건을 표기하여 참 또는 거짓을 판단함 

## - 참/거짓의 구분을 위해서는 비교 연산자를 활용

<br/>

|비교연산자|비교상태|설명|
|:------:|:---:|:---:|
|x < y| ~보다 작음 | x와 y보다 작은지 검사|
|x > y| ~보다 큼| x와 y보다 큰지 검사|
|x == y</br> x is y| 같음 |x와 y가 같은 지 검사</br>(값과 메모리 주소) 
|x ! = y</br>x is not y|같지 않음| x와 y가 다른 지 검사<br/>(값과 메모리 주소)|
|x >= y|크거나 같음|x와 y보다 이상인지 검사|
|x <= y |작거나 같음|x와 y보다 이하인지 검사|

<br/>
<br/>

## 조건 참/거짓의 구분

#

## - 숫자형의 경우는 수학에서의 참/거짓 과 동일
## - 컴퓨터는 존재하면 참 없으면 거짓이라고 판단함

<br/>
<br/>

## 논리 키워드 사용: and, or, not  
- and : 하나라도 False면 False
- or : 하나라도 True면 True

#

## - 조건문을 표현할 때 <span style="color:blue"> 집합의 논리 키워드</span>를 함께 사용하여 참과 거짓을 판단하기도 함

<br/>

<div style="background-color: #000000; padding: 10px;">
a = 8, b = 5 일 때

if a == 8 and b == 4  &emsp;&emsp;&emsp;  <span style="color:skyblue"> # 거짓</span>

if a > 7 or b > 7 &emsp;&emsp;&emsp; <span style="color:skyblue"> # 참</span>

if not (a > 7) &emsp;&emsp;&emsp; <span style="color:skyblue"> # 거짓, a > 7 인 것이 참 이므로 거짓으로 판단됨</span>
</div>

<br/>
<br/>


```python
value = 12
True if value % 2 == 0 else False # 결과: True

"Hello" if value % 2 == 0 else "World"  # 결과: Hello
# value 값을 2로 나눈 나머지가 0 이면 True 아니면 False
```


```python
value = 55
"Hello" if value % 2 == 0 else "world" # 결과: World

# value % 2 가 1 일때는 True 아닐때는 False
"Hello" if value % 2 else "world" # 결과: Hello

"Hello" if value % 2 else "world" # 결과: World
```

<br/>

# 조건 판단 연습

## 다음 프로그램 수행 결과는?

```python
score = int(input())
if score >= 90:
    grade = 'A'
if score >= 80:
    grade = 'B'
if score >= 70:
    grade = 'C'
if score >= 60:
    grade = 'D'
if score < 60:
    grade = 'F'
print(grade)
```

|score|예상 grade|실제 grade|
|:------:|:---:|:---:|
|38| <span style="color:red"> F</span> |<span style="color:blue"> F</span> |
|37| <span style="color:red"> F</span> | <span style="color:blue"> F</span>|
|7| <span style="color:red"> F</span> |<span style="color:blue"> F</span>| 
|16|<span style="color:red"> F</span> |<span style="color:blue"> F</span>|
|95|**<span style="color:red"> A</span>**|**<span style="color:blue"> D</span>**| 
|71 |**<span style="color:red"> C</span>** |**<span style="color:blue"> D</span>**|


- 묶어서 하지 않고 한줄로 식을 쓰면 if 문이 계속 실행 되어서 95 를 입력했을 때 D 가 출력됨.


<br/>

# 조건 판단 연습 수정

## - 수행할 명령문이 한 줄이면 붙여쓰기 가능
## - else 키워드 뒤엔 조건 삭제

```python
if score >= 90: grade = 'A'  </br> # 90 이상일 경우 A
elif score >= 80: grade = 'B' </br> # 80 이상일 경우 B
elif score >= 70: grade = 'C' </br> # 70 이상일 경우 C
elif score >= 60: grade = 'D' </br> # 60 이상일 경우 D
else: grade = 'F' </br></br> # 모든 조건에 만족하지 못할 경우 F
```

- 스코어가 95점이면 만족을 하고 grade A를 받고 전체 if문을 빠져나가게 된다.

<br/>

# [연습] 무슨 학교 다니세요?

## - 태어난 연도를 계산하여 학교 종류를 맞추는 프로그램

<div style="background-color: #000000; padding: 10px;">
당신이 태어난 년도를 입력하세요

1994  <br/> <span style="color: red;"> # 자신이 태어난 연도 입력</span>

대학생
</div>

<br/>

- 나이는 현재년도 - 태어난 년도 +1 로 계산

- 26세 이하 20세 이상 이면 "대학생", 20세 미만 17세 이상 이면 "고등학생"
- 17세 미만 14세 이상 이면 "중학생", 14세 미만 8세 이상이면 "초등학생"
- 그 외의 경우는 학생이 아닙니다 출력

```python
print("당신이 태어난 년도를 입력하세요")
birth_year = int(input())

age = 2023 - birth_year + 1

if age <= 26 and age >= 20 :
    print("대학생")
elif age < 20 and age >= 17:
    print("고등학생")
elif age < 17 and age >= 14:
    print("중학생")
elif age < 14 and age >= 8:
    print("초등학생")
else:
    print("학생이 아닙니다.")
```

