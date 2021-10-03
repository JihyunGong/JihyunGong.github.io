---
layout: single
title: "[JavaScript] 함수 스코프 vs 블록 스코프"
date: 2021-09-25
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Scope, function scope, block scope]
<!-- toc: true -->
comments: true
---


함수 스코프와 블록 스코프의 차이에 대해 알아보자.

## 함수 스코프 vs 블록 스코프
**함수 스코프와 블록 스코프는 부분집합의 관계를 갖는다.**

- **공통점**  
두 스코프 모두 중괄호{}를 이용해 접근 범위를 형성한다.

- **차이점**  
각 스코프에 var 키워드로 변수를 선언했을 때, 그 접근성에서 차이가 발생한다. 

  만약 블록 스코프에 var 키워드로 변수를 선언할 경우, 어디서든 그 변수에 접근이 가능하다.

  그 이유는 [블록 스코프가 let, const로 선언된 변수에만 유효하기 때문이다.](https://jihyungong.github.io/til/javascript/Variables/)

  반면 함수 스코프의 경우 변수에 어떠한 키워드를 사용하더라도 해당 함수 안에서만 사용이 가능하다.

아래의 코드를 확인해보자. 
```javascript
// 함수 스코프
function func(){
  var a = 1;
}
console.log(a);

// Expected Output:
// ReferenceError: a is not defined
```
```javascript
// 블록 스코프
{
  var a = 1;
}
console.log(a);

// Expected Output:
// 1
```
