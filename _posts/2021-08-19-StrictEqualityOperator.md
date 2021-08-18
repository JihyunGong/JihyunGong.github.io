---
layout: single
title: "[JavaScript] Logical operator: Equality(==) vs Strict Equality(===)"
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Logical Operator]
toc: true
comments: true
---

## 1. Logical operator 정의
**Logical operator(논리적 연산자)** 의 역할은 left-operand(왼쪽 피연산자)와 right-operand(오른쪽 피연산자)의 값을 비교하여 boolean타입의 결과값을 반환시키는 것이다.
```javascript
console.log(1 > 2); //returns false 
console.log(3 === 3) //returns true 
```

## Equality(==)와 Strict Equality(===)의 차이
> Equality(==) operator: 양쪽의 피연사자들의 값을 비교하여 true 또는 false 값을 반환한다.

> Strict Equality(===) operator: 양쪽의 피연산자들의 값뿐만아니라 타입도 비교하여 둘다 일치하면 true, 하나라도 다르면 false값을 반환한다. 

