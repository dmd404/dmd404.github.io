---
date: 2022-04-29
layout: post
title: 내가 바로 상위 50%!
subtitle: Tim Urban's Life in Weeks
description: 
image: /img/posts/udemy/udemy2/weeks_you.png
optimized_image: 
category: study
tags:
  - 100daysofpython
  - python
  - coding
  - udemy
author: lgtromm
---

<h1 style="text-align: center"> Day 2 </h1>
배울 내용: 데이터 형식, 연산, 형 변환, f-문자열 등

만들 프로젝트: [팁 계산기](tip-calculator-end.appbrewery.repl.run)<br/>
팁을 포함한 인당 지불해야 할 금액을 알려준다.

## 파이썬의 기본 데이터 형식
- **String:** 일련의 글자<br/>
<u>Subscript</u>: 문자열에서 특정 요소를 추출하는 방법. 대괄호의 숫자는 어떤 문자를 추출할지 결정하고 hello의 경우 0부터 4까지 증가한다.

- **Integer:** 소수점 이하의 정수<br/>
정수를 만들거나, 정수형 데이터를 선언하려면 다른 것 없이 숫자만 사용하면 된다. 

- **Float:** 소수점이 있는 숫자<br/>

- **Boolean:** 참 또는 거짓<br/>
두 가지의 값만 존재한다. 항상 이 값은 대문자 T 또는 F로 시작하고 따옴표를 사용하지 않는다. 이 데이터 형식은 프로그램에서 무언가를 테스트를 할 때 자주 쓰인다.

![datatypes](/img/posts/udemy2/data types.png)
<u>프로그래머들은 이진수를 다루기 때문에 항상 0부터 숫자를 세기 시작한다. 따라서 어떤 것의 맨 처음의 위치는 항상 0이다.</u>

### Type error(형식 오류)
어떻게 하면 형식 오류를 방지하고, 작업중인 데이터의 형식을 파악할 수 있을까?<br/>
답: type() 함수

type 함수는 괄호 안에 입력된 것이 어떤 데이터 형식인지 알려준다.

### Data Conversion/Casting(데이터 형 변환 또는 캐스팅)
데이터간의 형식 변경

![str](/img/posts/udemy2/str.png)
num_char는 정수형. 이를 문자열로 변경해서 코드가 깨지지 않게 하려면 str 함수를 이용할 수 있다.

string, int, float 함수 등을 이용해서 그 데이터 형식으로 바꿀 수 있다.

---
<h2 style="text-align:center; color: cornflowerblue" > 코딩연습 1: 데이터 형식 </h2>
임의의 두자리 숫자를 받아서, 각 자리에 있는 숫자를 더하기.

![coding1](/img/posts/udemy2/coding1.png)
입력함수를 통해 얻은 값은 자동으로 문자열로 저장이 된다. 때문에 int 함수를 통해 정수로 변환해서 풀이.

---
<h2 style="text-align:center; color: cornflowerblue" > 코딩연습 2: BMI 계산기 </h2>
사용자가 입력한 몸무게와 키에 기초하여 체질량 지수(BMI)를 알아내기.

3 + 5<br/>
7 - 4<br/>
3 * 2<br/>
6 / 3 (기억해야 할 점은, 숫자를 나누면 항상 float 형태로 출력된다는 점이다. 이 경우에는 2.0이 출력된다.)<br/>
2 ** 3 (거듭제곱)

**PEMDAS**<br/>
(): Parentheses<br/>
**: Exponents<br/>
*: Multiplication<br/>
/: Division<br/>
+: Addition<br/>
-: Subtraction<br/>

계산은 왼쪽에서 오른쪽으로 행해진다.

![coding2](/img/posts/udemy2/coding2.png)
BMI는 몸무게를 키제곱 값으로 나눈 값이다. 형 변환을 사용해 풀이.

만약 키를 정수로 밖에 받지 못한다면 1미터 2미터 밖에 없을 것이다. 따라서 height은 반드시 float 형태여야 한다. 그리고 결과를 int로 변환해 보기 쉽게한다.

---
<h2 style="text-align:center; color: cornflowerblue" > 코딩연습 3: 삶을 주(week)로 표현해 보기</h2>
round() - 반올림 함수. 정수로 반환. 반올림 자릿수 지정 가능<br/>
floor() - 버림 함수. 어떤 숫자를 나누던 소수로 반환이 된다. 버림 함수를 통해 뒤 소수점을 모두 버려 정수로 변환할 필요 없이 바로 원하는 정수를 얻을 수 있다.
![f-string](/img/posts/udemy2/f-string.png)
f-string() - 서로 다른 데이터 유형을 통합. 문자열 앞에 f를 붙이고 중괄호 안에 다양한 변수를 입력해서 사용 가능

**<u>90살까지 살 수 있다고 가정했을 때, 실제로 며칠, 몇 주, 몇 달이 남아있는 알려주는 프로그램</u>**

수학 연산과 f-string을 통해 
![coding3](/img/posts/udemy2/coding3.png)
과제의 분위기는 어두웠지만 좋은 프로그래머가 되면 인생에서 지루하고 반복적인 일들을 줄일 수 있다는 걸 잊지 말자.

---

<h1 style="text-align:center; color: MediumSeaGreen" > 프로젝트: 팁 계산기 </h1>
1. 최종 계산서는 소수점 둘째 자리까지만 나오게 반올림
2. 팁은 백분율

![project](/img/posts/udemy2/project.png)
{:.2f} - float을 string으로 소수점 둘째 자리까지 변환

---
<p style="text-align:center; color:SlateBlue; font-weight:bold">무언가를 시작했지만 끝내지 않는 사람들은 50%가 넘는다. 그러니 계속 공부하고📝, 휴식을 취하고🛁, 즐겁게 숙면하자💤.</p>




