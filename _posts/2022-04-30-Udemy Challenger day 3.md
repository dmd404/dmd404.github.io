---
date: 2022-04-30
layout: post
title: 컴퓨터와 대화하는 방법을 배우는 중
subtitle: python!
description: 
image: /img/posts/udemy/udemy3/sum.png
optimized_image:
category: study
tags:
  - study
  - udemy
  - code
  - python
author: lgtromm
---

<h1 style="text-align: center">Day 3</h1>

배울 내용: Conditional statements, logical operators, code blocks and scope.<br/>
프로젝트: [어드벤처 게임](treasure-island-end.apbrewery.repl.run)<br/>
사용자가 결정을 내리고, 선택한 것에 맞게 게임 속 이야기가 전개 된다.

## if / else 및 조건 연산자를 통한 흐름 제어
if else 문은 특정 조건에 따라 A 또는 B 둘 중 하나를 수행하는 것이다.
![ifelse](/img/posts/udemy3/ifelse.png)
키워드 if가 있고, 판단을 할 condition(조건), 그 다음 : 을 찍고 코드블럭을 들여쓰기 해서 조건이 충족되는 경우(참인 경우) 실행될 코드 블럭을 넣어준다. 그리고 조건이 거짓인 경우 else의 코드블럭이 실행될 것이다. 

draw.io 사이트는 이 때 매우 유용하다. 어떤 종류의 순서도든 만들 수 있다. 
![flowchart](/img/posts/udemy3/flowchart.png)
이 순서도를 보면 if 와 else 의 논리를 보다 쉽게 이해할 수 있다.

키가 120cm 이하일 경우 표를 구매할 수 없고, 키가 120cm를 넘는다면 표 구매 가능.

---

<h2 style="text-align:center; color: cornflowerblue" > 코딩연습 1: 홀수 짝수 모듈로</h2>

modulo(%) - 나눠서 얻는 나머지 값을 반환

![coding1](/img/posts/udemy3/coding1.png)

---

## 중첩 if 문과 elif 문

![nested](/img/posts/udemy3/nested.png)
중첩 if 문에서는 첫번째 조건이 통과 되야지만 다음 조건을 확인할 수 있다. 

**if/elif/else**

단순한 if/else 조건문은 하나의 조건만 있다. 참이면 이걸 하고, 거짓이면 저걸 하고. elif 조건은 원하는 만큼 많이 추가할 수 있다.  
![elif](/img/posts/udemy3/elif.png)
참이라면 A를 하고, 참이 아니면 조건 2를 확인하라. 조건 2가 참이면 B를 실행하고, 모든 조건이 거짓이라면 마지막을 실행하라.

<h2 style="text-align:center; color: cornflowerblue" > 코딩연습 2: BMI 계산기 2.0 </h2>

## 다중 연속 if문
## 논리 연산자
