---
layout: single
title: "[JavaScript] 전역 스코프를 신중히 사용해야 하는 이유"
date: 2021-09-25
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Scope, global scope]
<!-- toc: true -->
comments: true
---


## 전역 스코프를 신중히 사용해야 하는 이유 
- **배경 조건**  
전역 스코프(Global Scope)는 "최상위 공간"이다. 

  즉 어디서나 접근이 가능하고 <u>누구나 변수에 접근 및 수정, 삭제가 가능하다.</u>


- **문제**  
대표적인 문제는 "네이밍 충돌(Naming Collisions)"이다. 

  예를 들어 전역 스코프에 var 키워드로 변수를 선언할 때, 누군가 그 변수를 재선언하여 예상치 못한 값을 불러 일으킬 수 있다. 

  또한 let, const 키워드로 변수를 선언한다면 해당 변수를 재선언 또는 변수에 값을 재할당하려고 할 때 에러를 발생시킨다. 
  
    ```javascript
  // 전역 스코프
  var a = 10;
  var a = 5; // 예상치 못한 결과 값 발생 (var 변수는 재선언할 수 있다)

  let b = 10;
  let b = 5; // 에러 발생 (let 변수는 재선언할 수 없다)

  const c = 10;
  const c = 5; // 에러 발생 (const 변수는 재선언할 수 없다)
  ```

  > [var, let, const 특징 참고](https://jihyungong.github.io/til/javascript/Variables/)


- **결론**  
전역 스코프의 변수는 언제, 어디서, 누구나 접근 및 변경을 할 수 있기 때문에 많은 부작용을 유발한다. 

  따라서 이러한 점을 유의하여 전역 스코프에 변수를 선언하는 것은 신중히 판단해야 한다. 
