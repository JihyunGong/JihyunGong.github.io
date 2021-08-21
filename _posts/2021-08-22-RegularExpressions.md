---
layout: single
title: "[JavaScript] Regular Expressions (a.k.a. 규식씨)"
date: 2021-08-22
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Regular Expressions]
toc: true
comments: true
---

## 1. 정규식(Regular Expressions) 이란?
**정규식(정규 표현식)** 은 일정한 규칙을 가진 문자열을 다루는 <u>패턴</u>이다. 

자바스크립트에서 정규식은 RegExp의 exec(), test() 그리고 String의 match(), matchAll(), replace(), replaceAll(), search(), split() 메소드와 함께 쓰인다.

또한, 자바스크립트에서 정규식은 <u>객체타입</u>이다. 


## 2. 정규식 작성법
정규식을 작성하는 방법은 2가지가 있으니 아래의 문법을 참고하면 된다. 

- 정규식 패턴이 바뀔 가능성이 없을 때 

variable | identifier | = | / | patterns | / | flags;
--- | --- | --- | --- | --- | --- | ---
var | regEx | = | / | [A-Z] | / | g;

- 정규식 패턴이 바뀔 가능성이 있을 때 

variable | identifier | = | new | constructor | ("patterns" | ,"flags");
--- | --- | --- | --- | --- | --- | ---
var | regEx | = | new | RegExp | ("[A-Z]" | ,"g");

> flags는 <u>optional</u>이다. 


## 3. 정규식 패턴 만들기
> **유의할 점: 대소문자 구분 할 것.(CASE-SENSITIVE)**

### - Brackets(괄호)
다양한 괄호를 이용해 패턴의 범위를 정할 수 있다. 

Bracket | Description
--- | ---
abc | 문자열 'abc'를 찾는다. 
123 | 숫자문자열 '123'을 찾는다.
[abc] | a, b, c 중 일치하는 한 문자를 찾는다. 
[123] | 1, 2, 3 중 일치하는 한 숫자문자를 찾는다. 
[^abc] | a, b, c를 제외한 한 문자를 찾는다. 
[^123] | 1, 2, 3을 제외한 한 숫자문자를 찾는다.
[a-z] | a부터 z까지 중 일치하는 한 문자를 찾는다. 
[0-9] | 0부터 9까지 중 일치하는 한 숫자문자를 찾는다. 
[^a-c] | a부터 c까지를 제외한 한 문자를 찾는다. 
[^1-3] | 1부터 3까지를 제외한 한 숫자문자를 찾는다. 
(x\|y) | x 또는 y에 일치하는 하나를 찾는다. 
a{3} | a가 3번 연속 반복될 때 일치하는 문자열을 찾는다.
a{3,5} | a가 3번 이상 5번 이하 연속 반복될 때 일치하는 문자열을 찾는다. 

### - Metacharacters(메타문자)
메타문자(특별한 의미를 가진 문자)를 이용해 패턴을 만들수 있다. 

Metacharacter | Description
--- | ---
. | 모든 형식의 한 문자를 찾는다.(특수문자 포함)
\w | 한 문자나 숫자문자를 찾는다.(대소문자 구분 x)
\W | 문자와 숫자가 아닌 한 문자를 찾는다.(ex- ,.:)
\d | 한 숫자문자를 찾는다.
\D | 숫자문자가 아닌 한 문자를 찾는다.(특수문자 포함) 
\s | 하나의 공백문자를 찾는다.
\S | 공백문자를 제외한 한 문자를 찾는다.(특수문자 포함)
\0 | NULL 문자를 찾는다.
\n | 새로운 줄(new line)을 찾는다. 
\t | tab 문자를 찾는다. 
\ | 특수문자를 문자자체로 해석한다.(ex- \. \+)
^ | 문자열 시작부분에서 찾는다.
$ | 문자열 끝부분에서 찾는다.
\* | 0번 이상 반복되는 문자를 찾는다.
\+ | 1번 이상 반복되는 문자를 찾는다.
? | 0번 또는 1번 반복되는 문자를 찾는다.


## 4. 정규식 패턴 변경자 
정규식 패턴 변경자는 **'flags', 'modifiers'** 등으로 불리며 <u>선택사항(optional)</u>이다.

Flags | Description
--- | ---
g | 전역 검색
i | 대소문자 구분없이 검색
m | 여러 줄에 걸쳐 검색
y | 현재 위치에서 검색

***결론: 정규식(Regular Expressions)은 가독성이 떨어지고 특수문자와 각종 규칙들로 사용이 어렵지만, 문자열을 처리할 때 일반 코드보다 훨씬 간결한 코드를 얻을 수 있다.***

*참고: 위의 정규식을 하나하나 써보고 싶다면 ["RegexOne"](https://regexone.com/lesson/introduction_abcs)이라는 사이트를 추천한다.*
