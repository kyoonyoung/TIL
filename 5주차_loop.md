# loop
## 정해진 동작을 반복적으로 수행하게 하는 명령문
## 프로그램 예시 in 생활
- 학생 100명의 성적을 산출할 때
- 검색 결과를 출력해 줄 때
- 워드에서 단어 바꾸기 명령 실행

반복문은 **반복 시작 조건**, **종료 조건**, **수행 명령**으로 구성됨

반복문 역시 반복 구문은 **들여쓰기**와 **block**으로 구분됨

**파이썬은 반복문으로 for, while 등의 명령 키워드를 사용함**

# for loop

## - 기본적인 반복문: 반복 범위를 지정하여 반복문 수행

<br/>

for i in [1,2,3,4,5]:  # 반복문 종료조건

...     print(i, "Hello")

...

1 Hello

2 Hello

3 Hello

4 Hello

5 Hello

> 1. looper 변수에 1 할당

>>2. "Hello" 출력

>>>3. 리스트(대괄호 속 숫자들) 있는 값 차례로 looper 할당

>>>>4. 5까지 할당한 후 반복 block 수행 후 종료

만약 100번 반복해야 하는 프로그램을 짜야 한다면?

<br/>

## - range() 사용하기

- 왜 range(1,5) 과 아닌 range (0,5) 인가?

: range()는 마지막 숫자 바로 앞까지 리스트를 만들어줌

 즉, range(1,5) = [1,2,3,4] 까지 같은 의미

 ※ range(0,5) = [0,1,2,3,4] = range(5)는 같은 의미

</br>

 for i in range(0, 5):

...     print(i, "Hello")

...

0 Hello

1 Hello

2 Hello

3 Hello

4 Hello

<br/>

<br/>

for i in range(1,10,2):

...     print(i, "Hello")

...

1 Hello

3 Hello

5 Hello

7 Hello

9 Hello

#[알아두면 상식] 반복문

## **반복문 변수명**
- 임시적인 반복 변수는 대부분 i,j,k로 정함
- 이것은 수학에서 변수를 x,y,z로 정하는 것과 유사한 관례

## **0부터 시작하는 반복문**
- 반복문은 대부분 0부터 반복을 시작
- 이것도 일종을 관례로 1부터 시작하는 언어도 존재
- 2진수가 0부터 시작하기 때문에 0부터 시작하는 걸 권장

## **무한 loop**
- 반복 명령이 끝나지 않는 프로그램 오류
- CPU와 메모리 등 컴퓨터의 리소스를 과다하게 점유

<br/>

# for문의 다양한 반복문 조건 표현
## 문자열을 한 자씩 리스트로 처리하는 시퀀스형
 for i in "abcdefg":

...     print(i)

...

a

b

c

d

e

f

g

## 각각의 문자열 리스트로 처리
for i in ["americano", "latte", "frafuchino"]:

...     print(i)

...

americano

latte

frafuchino

## 간격을 두고 세기
 for i in range(1,10,2):

... # 1부터 10까지 2씩 증가시키면서 반복문 수행

...     print(i)

...

1

3

5

7

9

## 역순으로 반복문 수행
for i in range(10,1,-1):

... # 10부터 1까지 -1씩 감소시키면서 반복문 수행

...     print (i)

...
10

9

8

7

6

5

4

3

2

<br/>
<br/>

# while문
## 조건이 만족하는 동안 반복 명령문을 수행
 i = 1

 while i < 10:

...     print (i)

...     i += 1

...

1

2

3

4

5

6

7

8

9

> i 변수에 1 할당
>> i가 10 미만인지 판단
>>> 조건에 만족할 때 i 출력, i에 1을 더함
>>>> i가 10이 되면 반복 종료

## for문은 while문으로 변환 가능

**반복 실행 횟수를 명확히 알때 :**

for i in range(0,5):

...     print (i)

...

0

1

2

3

4

<br/>

**반복 실행횟수가 명확하지 않을 때 :**

 i = 0

 while i < 5:

...     print(i)

...     i = i + 1

...

0

1

2

3

4

<br/>

# 반복의 제어 - break, continue
## **break 특정 조건에서 반복 종료
for i in range(10):

    if i == 5: break     # i가 5가 되면 반복 종료

    print(i)  

print("EOP")  &emsp;&emsp; # 반복 종료 후 "EOP" 출력

>0

>1

>2

>3

>4

>EOP

## continue 특정 조건에서 남은 반복 명령 skip
for i in range(10):

     if i == 5: continue   # i가 5가 되면 i를 출력하지 않음

     print(i)   

print ("EOP") &emsp;&emsp;  # 반복 종료 후 "EOP" 출력

>0

>1

>2

>3

>4

>6

>7

>8

>9

>EOP

<br/>

# [연습] 구구단 계산기
## 아래와 같이 출력되는 프로그램을 만드시오
구구단 몇 단을 계산할까요?

5

구구단 5단을 계산합니다.

5 X 1 = 5

5 X 2 = 10

5 X 3 = 15

.......

5 x 8 = 40

5 x 9 = 45

- 내가 한 것

```python
print("구구단 몇 단을 계산할까요?")
number = int(input())

print("구구단", number, "단을 계산합니다.")

for i in range(1,10):
    calculate = number * i
    print(number, "x" , i ,"=", calculate)
```

- f-string 사용

```python
print("구구단 몇 단을 계산할까요?")
number = int(input())

print(f"구구단 {number} 단을 계산합니다.")

for i in range(1,10):
    print(f"{number} X {i} = {number * i}")
```

- Reverse

```python
sentence = "I love you"
reverse_sen = " "

for char in sentence:
    print("REVERSE #1", reverse_sen)
    reverse_sen = char + reverse_sen
    print("REVERSE #2", reverse_sen)
```

>REVERSE #1  
>REVERSE #2 I 
>REVERSE #1 I
>REVERSE #2  I
>REVERSE #1  I
>REVERSE #2 l I
>REVERSE #1 l I
>REVERSE #2 ol I
>REVERSE #1 ol I
>REVERSE #2 vol I
>REVERSE #1 vol I
>REVERSE #2 evol I
>REVERSE #1 evol I
>REVERSE #2  evol I
>REVERSE #1  evol I
>REVERSE #2 y evol I
>REVERSE #1 y evol I
>REVERSE #2 oy evol I
>REVERSE #1 oy evol I
>REVERSE #2 uoy evol I

# [연습] 숫자 찾기 게임
## 1~100 임의의 숫자를 맞추시오

```python
import random

true_value = random.randint(1,100)
input_value = 99999 #임의의 값
print("숫자를 맞춰보세요 (1~100)")

while true_value != input_value: # 사용자의 입력값이 true_value 클 때
    input_value = int(input())
    
    if input_value > true_value:
        print("숫자가 너무 큽니다.")
    elif input_value < true_value : # 사용자의 입 력값이 true_value 작을 때
        print("숫자가 너무 작습니다.")
    else: 
        break

print(f"정답입니다. 입력한 숫자는 {true_value} 입니다.")
```
