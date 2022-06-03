---
date: 2022-05-06
layout: post
title: 내 사전에 불가능은 없다!
subtitle: impossible n’est pas français
description: 
image: /img/posts/udemy/udemy9/sum.jpeg
optimized_image:
category: study
tags:
  - study
  - udemy
  - code
  - python
author: lgtromm
---

<h1 style="text-align: center">Day 9</h1>

**배운 내용 :** Dictionaries & Nesting <br/>
**프로젝트 :** [비밀경매 프로그램](blind-auction-completed.appbrewery.repl.run)



## 파이썬 딕셔너리: 깊게 파보기
딕셔너리는 딕셔너리(사전)와 비슷하게 작동한다. 키(단어)가 있고 값(단어의 뜻)이 존재한다.

---

<h2 style="text-align:center; color: cornflowerblue" > 과제 1: 등급 매기는 프로그램 </h2>

``` py
student_scores = {
  "Harry": 81,
  "Ron": 78,
  "Hermione": 99, 
  "Draco": 74,
  "Neville": 62,
}

# create empty dictionary called student_grades
student_grades = {}

# add the grades to student_grades.👇
for key in student_scores:
    score = student_scores[key]
    if score > 90:
        student_grades[key] = "Outstanding"
    elif score > 80:
        student_grades[key] = "Exceeds Expectations"
    elif score > 70:
        student_grades[key] = "Acceptable"
    else:
        student_grades[key] = "Fail"

print(student_grades)
```

---

## 리스트와 딕셔너리 중첩하기
``` py
#Nesting 
capitals = {
  "France": "Paris",
  "Germany": "Berlin",
}

#Nesting a List in a Dictionary

travel_log = {
  "France": ["Paris", "Lille", "Dijon"],
  "Germany": ["Berlin", "Hamburg", "Stuttgart"],
}

#Nesting Dictionary in a Dictionary

travel_log = {
  "France": {"cities_visited": ["Paris", "Lille", "Dijon"], "total_visits": 12},
  "Germany": {"cities_visited": ["Berlin", "Hamburg", "Stuttgart"], "total_visits": 5},
}

#Nesting Dictionaries in Lists

travel_log = [
{
  "country": "France", 
  "cities_visited": ["Paris", "Lille", "Dijon"], 
  "total_visits": 12,
},
{
  "country": "Germany",
  "cities_visited": ["Berlin", "Hamburg", "Stuttgart"],
  "total_visits": 5,
},
]
```

---

<h2 style="text-align:center; color: cornflowerblue" > 과제 2: 리스트 속 딕셔너리 </h2>

``` py
travel_log = [
{
  "country": "France",
  "visits": 12,
  "cities": ["Paris", "Lille", "Dijon"]
},
{
  "country": "Germany",
  "visits": 5,
  "cities": ["Berlin", "Hamburg", "Stuttgart"]
},
]
#🚨 Do NOT change the code above

#TODO: Write the function that will allow new countries
#to be added to the travel_log. 👇
def add_new_country(new_country, num_visits, cities_visited):
    new_dict = {}
    new_dict["country"] = new_country
    new_dict["visits"] = num_visits
    new_dict["cities"] = cities_visited
    travel_log.append(new_dict)

#🚨 Do not change the code below
add_new_country("Russia", 2, ["Moscow", "Saint Petersburg"])
print(travel_log)
```

---

## 비밀 경매 프로그램과 순서도



## 비밀 경매 프로그램 해설 및 완전한 코드

## 동기와 책임
