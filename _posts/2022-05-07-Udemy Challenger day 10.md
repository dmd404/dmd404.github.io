---
date: 2022-05-07
layout: post
title: 그냥 print() 쓰면 되는데?
subtitle: 다 이유가 있는 법
description: 
image: /img/posts/udemy/udemy10/sum.jpeg
optimized_image:
category: study
tags:
  - study
  - udemy
  - code
  - python
author: lgtromm
---

<h1 style="text-align: center">Day 10</h1>

**배운 내용 :** Functions with outputs <br/>
함수를 사용해서 코드 길이 줄이기, 입력과 출력을 함수에 제공,
**프로젝트 :** [계산기 앱](calculator-final.appbrewery.repl.run)

<h1 style="text-align: center">Day 10</h1>

## 출력과 함수

**기본 함수**

``` py
def my_function ():
    # Do this 
    # Then do this
    # Finally do this 

my_function()
```
이 함수를 호출할 때마다 본문 작업이 실행된다. 이 첫 번째 유형의 함수는 반복적으로 실행하려는 명령어를 가지고 있을 때 작성해야 하는 코드의 양을 줄이는데 유용하다. 


**입력과 함수**

``` py
def my_function (something):
    # Do this with something
    # Then do this
    # Finally do this 

my_function(123)
```
다음 유형의 함수는 괄호 안에 무언가(입력)를 가지고 있다. 입력은 함수를 호출할 때 전달될 수 있고 위의 경우 123이 인자인데, 이 인자는 무언가로 불리는 매개변수에 전달되고 함수 본문 내에서 사용이 된다. 두 번째 유형의 함수는 입력을 감안하여 함수 내부의 코드를 수정하고 매번 다른 작업을 수행할 수 있는 능력을 준다.

**출력과 함수**

``` py
def my_function():
    result = 3 * 2
    return result

my_function()
output = my_function()
```
이 함수에서는 함수가 완성이 되고 난 후에 출력을 가질 수 있다. 본문 안에서 3 * 2 계산을 하고 그 값을 result라고 하는 변수에 저장을 했다. 이 작업이 끝난 뒤에는 출력 키워드를 사용할 수 있는데, 이를 return이라고 한다. 그리고 키워드 다음으로 원하는 해당 함수의 출력을 입력할 수 있다. 이제 함수가 호출된 코드는 result르 갖게 되었으니 또 다른 변수에 이것을 저장할 수 있다.
output = 6을 의미한다.   

출력을 가진 함수를 만들기 위해서 return 키워드는 정말 중요하다. 키둬드 뒤에 오는 모든 것이 함수가 호출된 부분을 대체하게 되기 때문이다.  

## 다양한 리턴값
함수가 하나 이상의 리턴문을 가진 경우 무슨 일이 일어날까? 컴퓨터는 리턴을 가진 줄을 만났을 때 그것이 함수의 마지막이라는 것을 알게 된다.

조기 리턴을 사용해서 함수를 종료시키는 방법도 있다. 

<h2 style="text-align:center; color: cornflowerblue" > 과제 1: 월별 일수 </h2>

``` py
def is_leap(year):
  if year % 4 == 0:
    if year % 100 == 0:
      if year % 400 == 0:
        return True
      else:
        return False
    else:
      return True
  else:
    return False

def days_in_month(input_year, input_month):
    if input_month > 12 and input_month < 1:
        return "Invalid month"
    month_days = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    if is_leap(input_year) and month == 2:
        return 29
    return month_days[input_month - 1]

year = int(input("Enter a year: "))
month = int(input("Enter a month: "))
days = days_in_month(year, month)
print(days)
```

---

## 독스트링
독스트링은 미니 버전의 문서를 만드는 방법이다. 코딩 에디터에 len()을 입력하면
![len](/img//posts/udemy10/len.png)
바로 이런 독스트링이 나타나 해당 함수가 하려는 작업을 설명해 준다.

독스트링은 함수 선언 바로 다음 줄에 """ 세 개의 따옴표를 사용해 작성이 가능하다. 
![docstring](/img//posts/udemy10/docstring.png)
독스트링을 작성한 후 함수를 적으면 미리 작성한 독스트링이 표시되는 게 보인다.

<h2 style="text-align:center; color: cornflowerblue" > 계산기 파트 1: 딕셔너리와 함수 결합하기 </h2>

``` py

# Add
def add(n1, n2):
    return n1 + n2

# Subtract
def subtract(n1, n2):
    return n1 - n2

# Multiply
def multiply(n1, n2):
    return n1 * n2

# Divide
def divide(n1, n2):
    return n1 / n2

# create dictionary to call functions
operations = {
    "+" : add,
    "-" : subtract,
    "*" : multiply,
    "/" : divide,
}

num1 = int(input("What's the first number?: ")
for symbol in operations:
    print(symbol)
operation_symbol = input("Pick an operation from the line above: ")
num2 = int(input("What's the second number?: "))
calculation_function = operations[operation_symbol]
answer = calculation_function(num1, num2)

print(f"{num1} {operation_symbol} {num2} = {answer}")
```

---

## 출력 vs. 반환

결과를 반환하는 대신 출력하지 않는 이유는 무얼까? 실제 차이는 무엇이고, return을 사용하는 이유는 무엇일까? 
print() = 값을 출력하기 위함
return = 함수의 값을 반환하고 함수 종료

---

## While 반복문, 플래그, 재귀



## 계산기 마감 작업 및 버그 수정


내일은 캡스톤 프로젝트라고 하는 무언가가 기다리고 있다고 한다. 강의 목차에 보면은 블랙잭 게임 만들기라고 나와있기는 한데...... 캡스톤은 다른건가? 이제 이 udemy challenger도 다음주면 끝이구나. 끝까지 아자아자다!