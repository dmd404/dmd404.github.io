---
date: 2022-05-01
layout: post
title: 프로그래밍은 오픈북 시험
subtitle: 그래도 프로그래밍 근육 키우려면 매일 코딩!
description: 
image: /img/posts/udemy/udemy4/life.jpeg
optimized_image:
category: study
tags:
  - study
  - udemy
  - code
  - python
author: lgtromm
---
<h1 style="text-align: center"> Day 4 </h1>
배울 내용: Randomization(무작위화) & Lists<br/>
만들 프로젝트: [가위바위보 게임](rock-paper-scissors-end.appbrewery.repl.run)

## Random 모듈

일정 수준의 예측 불가능성이 존재하는 컴퓨터 프로그램을 개발할 때를 위해 무작위화는 중요하다. 가장 대표적인 카테고리는 게임. 예를 들어, 테트리스 게임을 할 때 마다 다음 블록이 예측 가능하다면 전혀 재미가 없을거다. 

자연과 일상 생활에서는 무작위성을 만들어내기가 매우 쉽다. tv의 노이즈 화면, 엎질러진 페인트 등. 

하지만 컴퓨터는 deterministic(결정적) 하다. 이 말은, 컴퓨터가 완벽히 예측 가능한 방식으로 반복적인 행동을 수행함을 의미한다. 그렇다면 기본적으로 1과 0을 기반으로 작동하는 이 기계에서 random number(난수)를 생성하려면 어떻게 해야 할까?

유사 난수 생성을 위해 적용할 수 있는 다양한 수식이 존재하는데 파이썬은 [메르센 트위스터](https://en.wikipedia.org/wiki/Mersenne_Twister)를 사용한다.

[칸 아카데미 동영상](https://www.khanacademy.org/computing/computer-science/cryptography/crypt/v/random-vs-pseudorandom-number-generators)을 보는 것도 도움이 된다.

하지만 이 복잡하고 어려운 수식을 직접 구현할 필요는 없다. 감사하게도 파이썬 팀이 이미 random 모듈을 개발해주었기 때문!

```
import random

# random을 부르고 randint를 사용해 ()안에 시작지점과 끝날 지점 입력하면 끝. 간단하다
random_integer = random.randint(1, 10)
print(random_integer)

# 1을 포함하지 않고 0과 1사이 존재하는 숫자를 출력해준다.
random_float= random.random()
```

![module](/img/posts/udemy4/module.png)
모듈을 만들어 다른 파일에서 접근할 수 있는 방법을 배운 건 꽤나 흥미로웠다. 전부 한 파일에 코드를 적게 되면 코드가 엄청 길어지게 되지 않을까 막연히 상상을 한 적이 있었는데, 역시. 해결책이 존재했다 ㅎㅎ


<h1 style="text-align:center; color: cornflowerblue" > 코딩연습 1: 가상 동전 던지기 </h1>
생성된 난수에 따라 앞면이나 뒷면이 표시

```
# random import하는 거 기억!
import random

coin_toss = random.randint(0, 1)

if coin_toss == 0:
  print("Heads")
else:
  print("Tails")
```
---
# Lists
리스트는 데이터 구조다. 무슨 뜻인고 하면, 그냥 데이터를 체계화하고 저장하는 방식을 말한다.


```
fruits = [item1, item2]
```
구조는 상당히 단순하다. 대괄호 안에 항목이 저장되는데 모든 데이터 형식이 저장 가능하며, 혼합 저장도 가능하다.


> 자료와 구글이 존재하는 이유는, 세상에는 암기할 수 없을 정도로 많은 정보가 존재하기 때문이다. 또한 암기는 효율적이지 않은 학습 방식이다. 이는 어떻게 일이 진행되는 지와 같은 중요한 일(작동원리, 원하는 작업을 처리하기 위한 방법)을 처리하기 위해 필요한 뇌의 능력을 낭비하는 것이 된다.

새로운 개념을 만나면, 자료를 살펴보고 어떤 작업이 가능할지 확인해 보는 공부 방식을 추천한다. 어떤 작업이 가능할지 안다면, 구글에서 정확한 자료를 찾고 이를 구현하면 된다.

그렇기에 프로그래밍은 오픈 북 시험과 같다. 모든 걸 암기하려 하는 대신 다양한 작업을 시도해 보고 제대로 동작하도록 하는데 시간을 투자해야 한다.

<h1 style="text-align:center; color: cornflowerblue" > 코딩연습 2: 금융가 룰렛 </h1>

```
# Split string method
names_string = input("Give me everybody's names, separated by a comma. ")
names = names_string.split(", ")
# 🚨 Don't change the code above 👆

#Write your code below this line 👇
import random

num_people = len(names)
# list의 마지막 인덱스 부분이 헷갈렸는데 그냥 -1 하면 그만!
order = random.randint(0, num_people-1)

who_pays = names[order]

print(f"{who_pays} is going to buy the meal today!")
```
나의 풀이가 안젤라의 풀이와 다르지 않을 때 오는 뿌듯함이란! (다양한 풀이방식이 존재하겠지만 그래도 안젤라의 방식이 가장 효율적이라 생각이 들어서)

이 과제 덕분에 확실히 리스트의 마지막 인덱스는 총 항목의 개수보다 1개 적다는 사실을 이해했다. 성장하는 스스로를 느끼는 건 언제나 재밌다.

---
<h1 style="text-align:center; color: cornflowerblue" > 코딩연습 3: 보물지도 </h1>


코드를 가지고 노는 게 중요하다. 잘못될 것이 없기 때문이다.
```
# 🚨 Don't change the code below 👇
row1 = ["⬜️","⬜️","⬜️"]
row2 = ["⬜️","⬜️","⬜️"]
row3 = ["⬜️","⬜️","⬜️"]
map = [row1, row2, row3]
print(f"{row1}\n{row2}\n{row3}")
position = input("Where do you want to put the treasure? ")
# 🚨 Don't change the code above 👆

#Write your code below this row 👇
l_position = list(position)
column = int(l_position[0])
row = int(l_position[1])

map[row-1][column-1] = "X"
#Write your code above this row 👆

# 🚨 Don't change the code below 👇
print(f"{row1}\n{row2}\n{row3}")
```


<h1 style="text-align:center; color: MediumSeaGreen" > 프로젝트: 가위바위보 </h1>

4일차 부터는 안내가 조금씩 없어지기 시작했다. 3개의 과제중 하나와 프로젝트에 그 어떤 로직도 제공되지 않았다는 점...... 그래도 풀 수 있었고, 재미있었지만 약간 아쉽다. 네 발 자전거 타다가 보조 바퀴를 떼었을 때, '그래도 넘어질 걱정은 안 해서 좋았었는데, 쩝......' 그 때와 비슷한 느낌.

![project](/img/posts/udemy4/project.png)
가위바위보를 한국어로 바꾸어서 살짝 헷갈렸는데 그래도 잘 해냈다!

반복과 연습을 실력을 끌어올리는데 중요하다. 

<p style="text-align:center; font-weight:bold; color:midnightblue">프로그래밍은 헬스장에 가는 것과 같다. 그리고 근육도 계속 자극을 주는 게 아니라 적절히 휴식을 해야 더 잘 큰다. 이제 휴식시간🌿</p>
