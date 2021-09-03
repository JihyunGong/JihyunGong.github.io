---
layout: single
title: "[JavaScript] 변수를 선언하는 3가지 방법: var, let, const"
date: 2021-09-02
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Variables, var, let, const]
toc: true
comments: true
---


변수를 선언하는 방법은 3가지 키워드를 통해 구분된다. 

## var
- var의 특징:
  - 재선언할 수 있다.
  ```javascript
  var x = 5;
  var x = 10; // This is OK
  ```
  - 블록 스코프(Block scope)를 가지지 않는다.
    ```javascript
    var x = 5;

    { var x = 10; } // block scope is useless

    console.log(x); // returns 10
    ```
  
  - 변수 선언과 초기값이 호이스팅(Hoisting)된다.
  ```javascript
  x = 5; // This is OK because var x is hoisted with initialization
  var x = 10;
  ```
  
- 사용 예: 현재는 잘 사용하지 않는 구시대적 유물이다.  

> <'var' 사용을 지양하는 이유>
> - var는 언제 어디서든 재선언할 수 있기 때문에 대규모의 프로젝트를 진행할 경우 변수를 무한 재사용하여 예상치 못한 결과를 불러일으킬 수 있다.
> - var는 선언과 초기값이 함께 호이스팅되기 때문에 논리적이지 못하다. (let, const를 사용한 변수는 사용 전 반드시 선언(및 정의)해야 한다.)


## let
- let의 특징: 
  - 재선언할 수 없다.
  ```javascript
  let x = 5;
  let x = 10; // "SyntaxError: Identifier 'x' has already been declared 
  ```
  - 블록 스코프를 가진다.  
    ```javascript
    let x = 5;

    { let x = 10; } // redeclaring variables in the different block scope is fine

    console.log(x); // returns 5
    ```
  
  - 사용하기 전에 반드시 선언해야 한다.
  - 변수 선언은 호이스팅되지만, 초기값은 호이스팅 되지 않는다.
  ```javascript
  x = 5; // "ReferenceError: Cannot access 'x' before initialization
  let x = 10;
  ```

- 사용 예: ES6 (2015)에서 새롭게 도입된 이후로 var를 대신하여 쓰인다.


## const
- const의 특징:
  - 재선언할 수 없다.
  ```javascript
  const x = 5;
  const x = 10; // "SyntaxError: Identifier 'x' has already been declared
  ```
  - 값을 재할당할 수없다.
  ```javascript
  const x = 5;
  x = 10; // "TypeError: Assignment to constant variable.
  ```
  - 블록 스코프를 가진다.  
    ```javascript
    const x = 5;

    { const x = 10; } // redeclaring variables in the different block scope is fine

    console.log(x); // returns 5
    ```
  
  - 선언과 동시에 값을 할당해야 한다.
  ```javascript
  const x; // "SyntaxError: Missing initializer in const declaration
  x = 5;
  ```
  - 변수 선언은 호이스팅되지만, 초기값은 호이스팅 되지 않는다.
  ```javascript
  x = 5; // "ReferenceError: Cannot access 'x' before initialization
  const x = 10;
  ```

- 사용 예: 
  - ES6 (2015)에서 새롭게 도입되었으며 변수값이 바뀔 일이 없을 때 사용한다.  
  ※ 여기서 주의해야할 점은 변수의 데이터값이 아닌 참조값이 바뀌지 않을 때를 말한다.
  ```javascript
  const arr = [1, 2, 3, 4, 5];
  // arr = [6, 7, 8, 9, 10]; // "TypeError: Assignment to constant variable.
  arr[0] = 0; // This is OK because this is not to change reference value of 'arr'
  ```
  - 주로 Array, Object, Function, Regular Expressions에 사용된다.  


> <키워드 사용 우선순위>
> 1. const: 값의 재할당이 필요없을 때
> 2. let: 값의 재할당이 필요할 때
> 3. var: 특별히 전역변수가 필요할 때
