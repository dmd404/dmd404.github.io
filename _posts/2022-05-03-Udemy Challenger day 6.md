---
date: 2022-05-03
layout: post
title: 스승님을 뛰어넘었다!
subtitle: 아주 잠시였지만......
description: 
image: /img/posts/udemy/udemy6/sum.jpeg
optimized_image:
category: study
tags:
  - study
  - udemy
  - code
  - python
author: lgtromm
---
<h1 style="text-align: center">Day 6</h1>
배운 내용: Code blocks, functions, while loops 
프로젝트: 미로 탈출

## 파이썬 함수 정의 및 호출
[파이썬 문서](https://docs.python.org/3/library/functions.html)를 보면 파이썬에는 수많은 내장 함수가 있다는 걸 알 수 있다. print() 이게 함수인 걸 알 수 있는 이유는 함수 뒤에는 괄호가 붙기 때문이다. 괄호안에 변수를 넣으면 함수가 실행된다. 

만약 나만의 함수를 만들고 싶다면 어떻게 해야 될까? 나만의 함수를 만들고 싶다면 특정 키워드로 시작해야 된다. 바로 def
함수와 변수를 구분하는 건 괄호. 따라서 함수 이름 뒤에 괄호를 넣어주고 콜론(:)으로 마무리. 이 줄 다음에 오거나 들여쓰기 되는 모든 것들은 함수에 속한다는 의미다.

![myfunction](/img/posts/udemy6/myfunction.png)
함수를 호출(실행)하려면 간단히 함수의 이름을 입력하면 된다. 그리고 괄호 안에 필요한 값들을 넣어준다. 위의 경우엔 함수에 입력값이 필요없으므로 괄호는 비워두면 된다.

파이썬에서 함수를 만드는 방법
1. 함수를 정의한다 (def + 함수 이름 + 괄호:)
2. 코드라인 작성 (함수 호출 뒤 실행될 작업)

함수를 사용하면 하나의 명령어만으로도 모든 세부 단계를 수행할 수 있게 된다.

[Reeborg's World](https://reeborg.ca/reeborg.html?lang=en&mode=python&menu=worlds%2Fmenus%2Freeborg_intro_en.json&name=Alone&url=worlds%2Ftutorial_en%2Falone.json)
![reeborg](/img/posts/udemy6/reeborg.png)
코드의 길이가 줄어든다는 것보다 더 중요한 것은 코드 읽기가 쉬워진다는 것이다.

## 반복문으로 장애물 넘기
[reeborg's hurdle](https://reeborg.ca/reeborg.html?lang=en&mode=python&menu=worlds%2Fmenus%2Freeborg_intro_en.json&name=Hurdle%201&url=worlds%2Ftutorial_en%2Fhurdle1.json)
![forndef](/img/posts/udemy6/forndef.png)

## 파이썬에서의 들여쓰기
들여쓰기 되었다는 의미는 스페이스 4칸 만큼 오른쪽으로 이동했다는 것.

들여쓰기에는 두 가지 방법이 있는데 space vs tabs 이다. 아래의 2017년도 스택 오버 플로우 개발자 설문조사를 봐도 알 수 있듯이, 개발자들 사이에서 스페이스를 사용할지 탭을 사용할지는 오래된 설전이다. 
![salary](/img/posts/udemy6/salary.png)

## while 반복문
![while](/img/posts/udemy6/while.png)
while 반복문은 특정 조건이 참일 경우 무언가를 반복한다. 그리고 해당 조건이 거짓이 될 때만 중단된다.

![whilenot](/img/posts/udemy6/whilenot.png)
목적지가 아니면 점프하고 목적지에 도착하면 멈춘다.

지금까지 for 반복문과 while 반복문을 배웠는데, 왜 둘 다 배워야 하는 걸까? 언제 어떤 반복문을 사용해야 할까?

for 반복문의 경우 어떤 것을 반복하고 반복하는 각 아이템에 대해 뭔가를 해야 할 때 유용
loop 반복문의 경우 전체 순서에서 몇 번째에 해당하는지, 어떤 아이템을 반복할지가 아닌, 그저 특정 작업을 설정한 조건에 도달할 때까지 수없이 반복 실행할 때 사용

그리고 만약 while 반복문의 조건이 거짓이 되지 않는다면 infinite loop이 되어버린다. 
![infinite](/img/posts/udemy6/infinite.png)
5가 3보다 크다는 것은 영원한 진리이기 때문에 위의 코드 또한 영원히 실행되버리니 조심해야 한다.

그리고 만약 무한반복 되는 이유를 모르겠다면 조건을 출력해보는 게 유용하다. 
![check](/img/posts/udemy6/check.png)
위의 경우 항상 True(참)이 출력되겠다.

## while 반복문을 사용한 장애물 넘기
매번 벽의 위치가 달라지고 개수도 예측할 수 없기 때문에 for loop을 사용해 6개의 벽을 점프하는 방법은 사용할 수 없다.
![whileif](/img/posts/udemy6/whileif.png)

## 다양한 높이의 장애물 넘기
이번에는 넘어야 할 장애물의 높이가 달라진다. 
![help](/img/posts/udemy6/help.png) 

---

<h1 style="text-align:center; color: MediumSeaGreen" > 프로젝트: 미로찾기 </h1>
코드를 작성해 로봇이 미로를 빠져나올 수 있도록 하기.

미로 자체는 변하지 않지만 로봇의 방향이 무작위로 지정되고 위치 또한 무작위다. 그리고 시작 위치점도 무작위. asdf
![project](/img/posts/udemy6/project.png)