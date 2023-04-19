## input 함수 
#
* 사용자가 입력할 수 있도록 기다려주는 것

```python
print("Enter your name: ")
somebody = input() #입력된 값은 somebody 라는 변수에 저장된다.
print ("Hello", somebody , "How are you today?") 
# str
```
```python
temperature = float(input("Enter temperature: "))
print(temperature)
print(type(temperature))
```
```python
print("%s %s" % ("Hello", "world"))
print("{} {}".format("Hello", "world"))
print("%d %d" % (1, 2))
print("{}      {}".format(1, 2))
```

## %-format
#

* "%datatype" % (variable) 형태로 출력 양식을 표현

```python
print("I eat %d apples." % 3)
print("I eat %s apples." % "five")
number = 3; day = "three"
print("I ate %d apples. I was sick for %s days."
      % (number, day))
print("Product: %s, Price per unit: %f." % ("Apple", 5.243))
```

*  %s = 문자열 , %d = 정수(integer) , %f = floating-point

```python
print("Art: %5d, Price per Unit: %8.2f" % (453, 59.058))
# 5는 5칸을 비워라. 8은 8칸을 비워라.  .2 는 소수점 둘째자리까지
```

 → Art:   453, Price per Unit:    59.06


 ## str.format() 함수  
#


```python
age = 36; name = 'Sungchul Choi'
print("I'm {0} years old.". format(age))
print("My name is {0} and {1} years old.".format(name,age))
print("Product: {0}, Price per unit: {1: .3f}.".format("Apple", 5.243))
```

 → " " 스트링 타입 지정 후 .format

 ## f-string
 #
 * 앞에 스트링을 그릴 때 f 를 붙인다. 
 * 변수명을 써주면 그대로 들어간다.
 * 기본적으로 왼쪽 정렬이다.

 ```python
 name = "Sungchul"
age = 41
print(f"Hello, {name}. You are {age}. ")
print(f'{name:20}')
print(f'{name:>20}') # 오른쪽으로 정렬
print(f'{name:*<20}') # 왼쪽으로 정렬 후 * 로 채우기
print(f'{name:*>20}') # 오른쪽으로 정렬 후 * 로 채우기
print(f'{name:*^20}') # 가운데로 정렬 후 * 로 채우기
```
<br>
<br>
<br>
<br>

```python
print("본 프로그램은 섭씨를 화씨로 변환해주는 프로그램입니다")
print("변환하고 싶은 섭씨 온도를 입력해 주세요: ")
cel = float(input()) 
# input() 함수를 통해 입력받은 값은 기본적으로 문자열(string) 형태로 저장된다.
# 그래서 문자열을 숫자로 변환해주어야한다.
def fah(cel):
    return ((9/5)* cel + 32)

print("섭씨온도 : ", cel)
print("화씨온도 : ", fah(cel))
# 하지만 이렇게 하면 화씨온도가 소수점이 길어진다.
```
<br>

```python
# 4칸 포맷팅을 사용한 예시
# 중요한 변경 사항은 cel 변수를 float 형으로 변환해 준 것
print("본 프로그램은 섭씨를 화씨로 변환해주는 프로그램입니다")
print("변환하고 싶은 섭씨 온도를 입력해 주세요: ")
cel = input()
def fah(cel):
    return ((9/5)* float(cel) + 32)

print(f"섭씨온도 : {cel:>4}")
print(f"화씨온도 : {fah(cel):>4.2f}")
```
→ 이렇게 하면 

본 프로그램은 섭씨를 화씨로 변환해주는 프로그램입니다

변환하고 싶은 섭씨 온도를 입력해 주세요: 

32.2

섭씨온도 : 32.2

화씨온도 : 89.96

<br/>

<br/>
출력이 된다!!! ㅎㅎ

챗gpt야 사랑해



<br/>

#
## 답

```python
print("본 프로그램은 섭씨를 화씨로 변환해주는 프로그램입니다")
print("변환하고 싶은 섭씨 온도를 입력해 주세요: ")
cel = input()
fah = ((9/5)* cel) + 32

print(f"섭씨온도 : {cel}")
print(f"화씨온도 : {fah:.2f}")
```



## 퀴즈(2023.04.19)

# 

 workspace/function/quiz_17 디렉토리에 BMI_calculator.py 라는 파일을 생성하세요. 이 파일에서 다음과 같은 기능을 가진 파이썬 코드를 작성해주세요.

<br/>

사용자로부터 몸무게(kg)와 키(cm)를 입력받아, BMI(체질량지수)를 계산하여 출력하는 함수 calculate_BMI()를 작성하세요.
 
<br/>

몸무게를 입력하세요(kg): 60

키를 입력하세요(cm): 170

BMI: 20.76

<br/> 

 몸무게를 입력하세요(kg): 75

키를 입력하세요(cm): 180

BMI: 23.15

 <br/>

몸무게를 입력하세요(kg): 50

키를 입력하세요(cm): 160

BMI: 19.53

<br/>

```python
def get_BMI(kg, cm):
    return  (kg / (cm**2))

kg = float(input("몸무게를 입력하세요(kg): "))

cm = float(input("키를 입력하세요(cm): ")) / 100

calculate_BMI = get_BMI(kg, cm)
print(f"BMI: {calculate_BMI:.2f}")


#bmi지수 몸무게/키*키
```

