---
date: 2022-05-04
layout: post
title: 행운의 숫자 7
subtitle: 라떼는 메이플스토리 레벨72면 전국구였어...
description: 
image: /img/posts/udemy/udemy7/sum.jpeg
optimized_image:
category: study
tags:
  - study
  - udemy
  - code
  - python
author: lgtromm
---
<h1 style="text-align: center">Day 7</h1>

**배운 내용:** 지금까지 배워온 For & while loops, if/else, lists, strings, range, modules 등을 다시 검토해보고 배우는 시간. <br/>
**프로젝트:** [행맨 게임](day-7-hangman-final.appbrewery.repl.run)<br/>
단어를 맞추는 게임으로, 틀린 글자를 제시할 때 마다 이 사람의 목숨이 점점 위험해져 가는 게임.

## 순서도로 복잡한 문제를 단순하게 만들기
프로젝트를 시작하기 전에, 이 게임이 어떻게 진행되는지 알고 어떻게 코드로 짤지 정확히 아는 게 중요하다.<br/>
[위키피디아 행맨](https://en.wikipedia.org/wiki/Hangman_(game))
한번도 이 게임을 해 본적이 없다면 한 번 온라인으로 해보는 걸 추천한다. [행맨 온라인](https://hangmanwordgame.com/?fca=1&success=0#/)

이 게임이 어떻게 진행되는지 이해했다면, 이 프로그램이 어떤 논리로 구성이 될지 검토해보자. 

**Flow Chart Programming**
![flowchart](/img/posts/udemy7/flowchart.png)
순서도는 참고를 많이 하게될 좋은 도구이다. 순서도는 어떤 코드를 짤지에 대해 전반적인 방향성을 제시하기 때문이다. 

<h2 style="text-align:center; color: cornflowerblue" > 과제 1: 무작위 단어를 고르고 정답 확인하기 </h2>

``` py
#Step 1 

word_list = ["ardvark", "baboon", "camel"]

#TODO-1 - Randomly choose a word from the word_list and assign it to a variable called chosen_word.
import random

chosen_word = random.choice(word_list)
print(chosen_word)
#TODO-2 - Ask the user to guess a letter and assign their answer to a variable called guess. Make guess lowercase.
guess = input("guess a letter: ").lower()

#TODO-3 - Check if the letter the user guessed (guess) is one of the letters in the chosen_word.
for letter in chosen_word:
  if guess == letter:
    print("right")
  else:
    print("wrong")
```

![output](/img/posts/udemy7/output1.png)

---

<h2 style="text-align:center; color: cornflowerblue" > 과제 2: 빈칸을 맞춘 글자로 바꾸기 </h2>

``` py
#Step 2

import random
word_list = ["aardvark", "baboon", "camel"]
chosen_word = random.choice(word_list)

#Testing code
print(f'Pssst, the solution is {chosen_word}.')

#TODO-1: - Create an empty List called display.
#For each letter in the chosen_word, add a "_" to 'display'.
#So if the chosen_word was "apple", display should be ["_", "_", "_", "_", "_"] with 5 "_" representing each letter to guess.
display = []
word_length = range(len(chosen_word))
for _ in range(len(chosen_word)):
    display += "_"
print(display)


guess = input("Guess a letter: ").lower()

#TODO-2: - Loop through each position in the chosen_word;
#If the letter at that position matches 'guess' then reveal that letter in the display at that position.
#e.g. If the user guessed "p" and the chosen word was "apple", then display should be ["_", "p", "p", "_", "_"].

for position in word_length:
    letter = chosen_word[position]
    if letter == guess:
        display[position] = letter
    if chosen_word[position] == guess:
        display[position] = guess
# for letter in chosen_word:
#     if letter == guess:
#         print(guess)
#     else:
#         print("Wrong")
#TODO-3: - Print 'display' and you should see the guessed letter in the correct position and every other letter replace with "_".
#Hint - Don't worry about getting the user to guess the next letter. We'll tackle that in step 3.
print(display)
```

---

<h2 style="text-align:center; color: cornflowerblue" > 과제 3: 플레이어가 이겼는지 확인하기 </h2>

``` py
#Step 3

import random
word_list = ["aardvark", "baboon", "camel"]
chosen_word = random.choice(word_list)
word_length = len(chosen_word)

#Testing code
print(f'Pssst, the solution is {chosen_word}.')

#Create blanks
display = []
for _ in range(word_length):
    display += "_"

#TODO-1: - Use a while loop to let the user guess again. The loop should only stop once the user has guessed all the letters in the chosen_word and 'display' has no more blanks ("_"). Then you can tell the user they've won.

end_of_game = False

while not end_of_game:
    guess = input("Guess a letter: ").lower()
    
    #Check guessed letter
    for position in range(word_length):
        letter = chosen_word[position]
        print(f"Current position: {position}\n Current letter: {letter}\n Guessed letter: {guess}")
        if letter == guess:
            display[position] = letter

print(display)

if "_" not in display:
    end_of_game = True
    print("You win")
```

display 빈칸이 모두 없어질 때 까지 유저에게 맞출 문자를 계속 물어보는 것.

1. while 반복문으로 감싸준다.
2. 코드가 반복될 수 있도록 while 반복문 정의.
    - end_of_game 변수를 만들어 false로 초기값 설정
    - 조건문 추가: 빈칸이 모두 유저가 맞춘 글자들로 대체되었을시
        * end_of_game = True 로 변경
        * 반복문이 종료되므로 "You win" 출력

---

<h2 style="text-align:center; color: cornflowerblue" > 과제 4: 플레이어의 남은 목숨 세기 </h2>

![flowchart2](/img/posts/udemy7/flowchart2.png)

``` py
#Step 4

import random

stages = ['''
  +---+
  |   |
  O   |
 /|\  |
 / \  |
      |
=========
''', '''
  +---+
  |   |
  O   |
 /|\  |
 /    |
      |
=========
''', '''
  +---+
  |   |
  O   |
 /|\  |
      |
      |
=========
''', '''
  +---+
  |   |
  O   |
 /|   |
      |
      |
=========''', '''
  +---+
  |   |
  O   |
  |   |
      |
      |
=========
''', '''
  +---+
  |   |
  O   |
      |
      |
      |
=========
''', '''
  +---+
  |   |
      |
      |
      |
      |
=========
''']

end_of_game = False
word_list = ["ardvark", "baboon", "camel"]
chosen_word = random.choice(word_list)
word_length = len(chosen_word)

#TODO-1: - Create a variable called 'lives' to keep track of the number of lives left. 
#Set 'lives' to equal 6.
lives = 6

#Testing code
print(f'Pssst, the solution is {chosen_word}.')

#Create blanks
display = []
for _ in range(word_length):
    display += "_"

while not end_of_game:
    guess = input("Guess a letter: ").lower()

    #Check guessed letter
    for position in range(word_length):
        letter = chosen_word[position]
        # print(f"Current position: {position}\n Current letter: {letter}\n Guessed letter: {guess}")
        if letter == guess:
            display[position] = letter

    #TODO-2: - If guess is not a letter in the chosen_word,
    #Then reduce 'lives' by 1. 
    #If lives goes down to 0 then the game should stop and it should print "You lose."
        
    if guess not in chosen_word:
        lives -= 1
        if lives == 0:
            end_of_game = True
            print("Game over")

    #Join all the elements in the list and turn it into a String.
    print(f"{' '.join(display)}")

    #Check if user has got all letters.
    if "_" not in display:
        end_of_game = True
        print("You win.")

    #TODO-3: - print the ASCII art from 'stages' that corresponds to the current number of 'lives' the user has remaining.
    # print(stages[lives])
    print(stages[lives])
```

1. 유저의 남은 목숨을 추적하고 변할 때 마다 그 상태를 추적할 수 있는 lives 변수 생성
2. 단어 전체에서 guess의 글자가 있는지 확인하는 if 조건문 추가
    - 참일 경우 lives의 값이 1씩 감소
        * lives가 0에 도달하면 게임 오버 문구 출력
        * while 반복문 종료 위해 end_of_game 변수 True로 변경
3. lives 변수 값에 따라 stages 리스트에 있는 아스키 아트 출력

---

<h2 style="text-align:center; color: cornflowerblue" > 과제 5: 유저 경험 개선시키기 </h2>

이번 과제는 module을 사용한다. 

**참조 링크:** https://www.askpython.com/python/python-import-statement

``` py

#Step 5

import random
from hangman_art import logo, stages
from hangman_words import word_list

#TODO-1: - Update the word list to use the 'word_list' from hangman_words.py
#Delete this line: word_list = ["ardvark", "baboon", "camel"]

chosen_word = random.choice(word_list)
word_length = len(chosen_word)

end_of_game = False
lives = 6

#TODO-3: - Import the logo from hangman_art.py and print it at the start of the game.
print(logo)

#Testing code
# print(f'Pssst, the solution is {chosen_word}.')

#Create blanks
display = []
for _ in range(word_length):
    display += "_"



while not end_of_game:
    guess = input("Guess a letter: ").lower()

    #TODO-4: - If the user has entered a letter they've already guessed, print the letter and let them know.
    if guess in display:
        print(f"You've already enterted {guess}")

    #Check guessed letter
    for position in range(word_length):
        letter = chosen_word[position]
        # print(f"Current position: {position}\n Current letter: {letter}\n Guessed letter: {guess}")
        if letter == guess:
            display[position] = letter

    #Check if user is wrong.
    if guess not in chosen_word:
        #TODO-5: - If the letter is not in the chosen_word, print out the letter and let them know it's not in the word.
        print(f"You guessed {guess}, that's not in the word. You lose a life.")
        lives -= 1
        if lives == 0:
            end_of_game = True
            print("You lose.")

    #Join all the elements in the list and turn it into a String.
    print(f"{' '.join(display)}")

    #Check if user has got all letters.
    if "_" not in display:
        end_of_game = True
        print("You win.")

    #TODO-2: - Import the stages from hangman_art.py and make this error go away.
    print(stages[lives])

 ```
1. hangman_words, hangman_art 모듈을 import.
2. 이미 맞춘 글자의 리스트인 display를 활용해 똑같은 글자를 입력할 시 알려준다.
3. 글자가 단어안에 없을 시 없다는 사실을 알려주고 목숨 한 개를 뺏는다.

---

<p style="text-align:center; color:SlateBlue; font-weight:bold"> 이 과정에서 하루치의 코스를 하는데 하루보다 더 걸리더라도 괜찮다. 중요한 건, 매일매일 반복하고 꾸준히 하면서 각각의 강의에 너무 오래 쉬어서 들을 때마다 새롭지만 않으면 된다. 그냥 꾸준히 하면 그만. 매일 꾸준히 따라가면 매일 꾸준히 실력이 는다. 결국엔 도달한 거란 말이다. 🏁 </p>