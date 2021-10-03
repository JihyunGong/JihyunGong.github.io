---
layout: single
title: "[JavaScript] DOM에서 요소를 선택하는 4가지 방법"
date: 2021-09-16
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, DOM]
toc: true
comments: true
---


DOM에서 요소를 선택하는 4가지 방법에 대해 소개한다.

## 1. ID 이름
**Syntax: document.getElementById("");**

id는 기본적으로 각 HTML 문서에서 하나의 고유한 이름을 가진다. 

따라서 위의 Syntax를 보면 'Element'라고 단수로 표기되어 있으며 단 한 개의 요소를 선택한다.


## 2. CLASS 이름
**Syntax: document.getElementsByClassName("");**

class 이름은 HTML 문서에서 여러 번 재사용 가능하다.

따라서 class 이름을 이용하여 선택하는 방법은 일치하는 모든 요소를 선택한다.

선택된 요소들은 유사 배열(배열과 유사한 상태)의 형태이며 하나의 요소가 선택되더라도 동일한 형태를 가진다. 

요소에 접근하는 방법은 배열과 같다. 


## 3. TAG 이름
**Syntax: document.getElementsByTagName("");**

tag 이름을 이용해서 선택하는 방법은 class 이름을 이용하는 방법과 동일한 특징을 갖는다.


## 4. CSS 선택자
**Syntax: document.querySelector(""); or document.querySelectorAll("");**

- document.querySelector(""); - 괄호 안의 문자열과 일치하는 첫 번째 요소를 선택한다.

- document.querySelectorAll(""); - 괄호 안의 문자열과 일치하는 모든 요소를 유사 배열의 형태로 선택한다. 

CSS 선택자를 이용해서 요소를 선택하는 방법이 가장 자주 쓰인다.


> 선택된 요소는 Node 혹은 HTML Element라고 부른다. Node가 HTML Element보다 상위 개념이다.
> - Node는 DOM에 존재하는 모든 요소를 Node라고 부른다.
> - HTML Element는 HTML 문서에서 대그로 적은 Node를 뜻한다.
