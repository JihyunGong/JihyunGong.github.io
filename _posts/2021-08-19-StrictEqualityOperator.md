---
layout: single
title: "[JavaScript] Strict Equality(===)를 써라"
date: 2021-08-19
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Logical Operator]
toc: true
comments: true
---

## Logical operator 정의
Equality operator와 Strict equality operator는 모두 Logical operator에 속해있다. 

**Logical operator(논리적 연산자)** 의 역할은 left-operand(왼쪽 피연산자)와 right-operand(오른쪽 피연산자)의 값을 비교하여 boolean타입의 결과값을 반환시키는 것이다.
```javascript
console.log(1 > 2); //returns false 
console.log(3 === 3); //returns true 
```

## Equality(==)와 Strict Equality(===)의 차이

Equality(==) | Strict Equality(===)
--- | ---
양쪽 피연산자들의 값을 비교하여 true 또는 false 값을 반환한다. | 양쪽 피연산자들의 값뿐만아니라 타입을 비교하여 둘다 일치하면 true, 하나라도 다르면 false값을 반환한다. 

아래 예시를 통해 알아보자. 
```javascript
console.log(2 == 2); //returns true 이유: 2와 2 값 일치
console.log(2 === 2); //returns true 이유: 2와 2 값과 타입 일치

console.log(2 == '2'); //returns true 이유: 2와 '2' 값 일치 
console.log(2 === '2'); //returns false 이유: 2는 number type, '2'는 string type 

console.log(1 == true); //returns true 이유: 1은 true값, 0은 false값
console.log(1 === true); //returns false 이유: 1은 number type, true는 boolean type

console.log(null == undefined); //returns true 이유: '값이 없음' 일치 (사실 null과 undefined값은 다르지만, JavaScript는 둘다 '값이 없음'을 나타내므로 상대적으로 같다고 계산한다.) 
console.log(null === undefined); //return false 이유: null은 object type, undefined는 undefined type
```


**결론: Strict equality(===)는 Equality(==)보다 더 정확한 값을 반환할 수 있다. 따라서, 대부분의 경우 Strict equality 연산자를 쓰는 것이 좋다.** 
