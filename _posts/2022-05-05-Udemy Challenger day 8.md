---
date: 2022-05-05
layout: post
title: caesar cipher
subtitle: 구글에 caesar 검색하면 연관 검색어 1위는 샐러드
description: 
image: /img/posts/udemy/udemy8/sum.jpeg
optimized_image:
category: study
tags:
  - study
  - udemy
  - code
  - python
author: lgtromm
---

<h1 style="text-align: center">Day 8</h1>

배운 내용: Functions with inputs, arguments and parameters
프로젝트: [암호 프로그램(ceaser cipher)](caesar-cipher-end.appbrewery.repl.run)

parameter: 데이터의 이름
argument: 사용되는 데이터의 실제 값

positional argument(위치 인자): 파이썬 코딩에서는 함수를 호출 할 때 어떤 파라미터에 어떤 데이터가 할당 될지 위치만으로 결정한다.

keyword argument(키워드 인자): 각각 파라미터의 이름과 등호를 이용해 할당할 수 있다. 이 경우에는 순서를 바꿔 입력하더라도 영향을 받지 않는다. 

키워드 인자를 사용하면 에러를 줄일 수 있지만, 코드가 길어진다. 상황에 따라 위치 인자와 키워드 인자 중 적합한 것을 사용하면 된다.

어제 유튜브 알고리즘 추천으로 메모 관련 영상을 하나 시청했는데 모든 걸 요약하려 하지 말고, 핵심 키워드 2개만 딱 뽑아내려고 하라지 뭐던가. 수업의 모든 걸 적을 필요는 없다. 나는 속기사가 아니니까 말이다. 또한 핵심 키워드를 찾아내려고 하는 자세로 인해 정보들을 더 집중해서 듣게 되고, 기록으로 옮길 때 비로소 '자기화' 할 수 있다고 한다. 보고 옮겨적는 건 다른 영역이다. 

메모의 핵심은 요약과 분류. 어린이날에 또 한 번 성장한 스스로가 대견하다!


<h2 style="text-align:center; color: cornflowerblue" > 과제 1: 페인트 면적 계산기 </h2>

``` py
#Write your code below this line 👇
import math

def paint_calc(height, width, cover):
    cans = math.ceil(height * width / cover)
    print(f"You'll need {cans} cans of paint.")
    
#Write your code above this line 👆
# Define a function called paint_calc() so that the code below works.   

# 🚨 Don't change the code below 👇
test_h = int(input("Height of wall: "))
test_w = int(input("Width of wall: "))
coverage = 5
paint_calc(height=test_h, width=test_w, cover=coverage)
```

학교 수학 시간과 비슷했다. prime number(소수)는 본인과 1외로 나누어지지 않는 성질 때문에 cicadas, 비트코인, 암호화 등에 사용한다고 하는데 대체 어떤 원리이려나.

---

<h2 style="text-align:center; color: cornflowerblue" > 과제 2: 소수 확인기 </h2>

``` py
#Write your code below this line 👇
def prime_checker(number):
    is_prime = True
    if number > 1:
        for i in range (2, n):
            if n % i == 0:
                is_prime = False
        if is_prime:
            print("It's a prime number.")
        else: 
            print("It's not a prime number.")

#Write your code above this line 👆
    
#Do NOT change any of the code below👇
n = int(input("Check this number: "))
prime_checker(number=n)
```

---

<h1 style="text-align:center; color: MediumSeaGreen" > 프로젝트: 시저 암호 암호화</h1>

``` py

alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n")
text = input("Type your message:\n").lower()
shift = int(input("Type the shift number:\n"))
print(alphabet.index(text[1]))

#TODO-1: Create a function called 'encrypt' that takes the 'text' and 'shift' as inputs.
def encrypt(plain_text, shift_amount):
    cipher_text = ""
    #TODO-2: Inside the 'encrypt' function, shift each letter of the 'text' forwards in the alphabet by the shift amount and print the encrypted text.
    for letter in plain_text:
        position = alphabet.index(letter)
        new_position = position + shift_amount
        new_letter = alphabet[new_position]
        cipher_text += new_letter
    print(f"The encoded text is {cipher_text}")
    # print(f"The encoded text is {cipher_text}")
    #e.g. 
    #plain_text = "hello"
    #shift = 5
    #cipher_text = "mjqqt"
    #print output: "The encoded text is mjqqt"

    ##HINT: How do you get the index of an item in a list:
    #https://stackoverflow.com/questions/176918/finding-the-index-of-an-item-in-a-list

    ##🐛Bug alert: What happens if you try to encode the word 'civilization'?🐛

#TODO-3: Call the encrypt function and pass in the user inputs. You should be able to test the code and encrypt a message. 
encrypt(text, shift)
```
---

<h1 style="text-align:center; color: MediumSeaGreen" > 프로젝트: 시저 암호 복호화</h1>

``` py
alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n")
text = input("Type your message:\n").lower()
shift = int(input("Type the shift number:\n"))

def encrypt(plain_text, shift_amount):
  cipher_text = ""
  for letter in plain_text:
    position = alphabet.index(letter)
    new_position = position + shift_amount
    cipher_text += alphabet[new_position]
  print(f"The encoded text is {cipher_text}")

#TODO-1: Create a different function called 'decrypt' that takes the 'text' and 'shift' as inputs.
def decrypt(cipher_text, shift_amount):
    plain_text = ""

  #TODO-2: Inside the 'decrypt' function, shift each letter of the 'text' *backwards* in the alphabet by the shift amount and print the decrypted text.  
    for letter in cipher_text:
        position = alphabet.index(letter)
        new_position = position - shift_amount
        plain_text += alphabet[new_position]
    print(f"The decoded text is {plain_text}")
  #e.g. 
  #cipher_text = "mjqqt"
  #shift = 5
  #plain_text = "hello"
  #print output: "The decoded text is hello"


#TODO-3: Check if the user wanted to encrypt or decrypt the message by checking the 'direction' variable. Then call the correct function based on that 'drection' variable. You should be able to test the code to encrypt *AND* decrypt a message.
if direction == "encode":
    encrypt(text, shift)
elif direction == "decode":
    decrypt(text, shift)
```

---

<h1 style="text-align:center; color: MediumSeaGreen" > 프로젝트: 시저 암호 코드 재구성</h1>

``` py
alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n")
text = input("Type your message:\n").lower()
shift = int(input("Type the shift number:\n"))

#TODO-1: Combine the encrypt() and decrypt() functions into a single function called caesar(). 
def caesar(start_text, shift_amount, cipher_direction):
    end_text = ""
    if cipher_direction == "decode":
            shift_amount *= -1
    for letter in start_text:
        position = alphabet.index(letter)
        new_position = position + shift_amount
        end_text += alphabet[new_position]
    print(f"The {cipher_direction}d text is {end_text}")

#TODO-2: Call the caesar() function, passing over the 'text', 'shift' and 'direction' values.
caesar(text, shift, direction)
```

---

<h1 style="text-align:center; color: MediumSeaGreen" > 프로젝트: 시저 암호 유저 경험 개선</h1>

``` py
alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']

def caesar(start_text, shift_amount, cipher_direction):
  end_text = ""
  if cipher_direction == "decode":
    shift_amount *= -1
  for char in start_text:
    if char in start_text:
        if char in alphabet:
            position = alphabet.index(char)
            new_position = position + shift_amount
            end_text += alphabet[new_position]
        else:
            end_text += char
            
    #TODO-3: What happens if the user enters a number/symbol/space?
    #Can you fix the code to keep the number/symbol/space when the text is encoded/decoded?
    #e.g. start_text = "meet me at 3"
    #end_text = "•••• •• •• 3"

    
  print(f"Here's the {cipher_direction}d result: {end_text}")

#TODO-1: Import and print the logo from art.py when the program starts.
from art import logo
print(logo)
#TODO-4: Can you figure out a way to ask the user if they want to restart the cipher program?
#e.g. Type 'yes' if you want to go again. Otherwise type 'no'.
#If they type 'yes' then ask them for the direction/text/shift again and call the caesar() function again?
#Hint: Try creating a while loop that continues to execute the program if the user types 'yes'. 
should_continue = True
while should_continue:
    direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n")
    text = input("Type your message:\n").lower()
    shift = int(input("Type the shift number:\n"))
    
    #TODO-2: What if the user enters a shift that is greater than the number of letters in the alphabet?
    #Try running the program and entering a shift number of 45.
    #Add some code so that the program continues to work even if the user enters a shift number greater than 26. 
    #Hint: Think about how you can use the modulus (%).
    shift = shift % 26
    
    caesar(start_text=text, shift_amount=shift, cipher_direction=direction)
    result = input("Type 'yes' if you want to go again. Otherwise, type 'no'.\n")
    if result == "no":
        should_continue = False
        print("Good Bye")
```