---
layout: single
title: "[JavaScript] Truthy vs Falsy"
date: 2021-08-24
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Truthy, Falsy]
toc: true
comments: true
---

## Truthy vs Falsy
자바스크립트의 모든 값은 크게 Truthy(진실)와 Falsy(거짓), 이 두 가지로 나눌 수 있다. 

- Truthy: true을 반환하는 값들
  -  Falsy값을 제외한 모든 값
  ```javascript
  if(true) console.log('true'); //returns "true"
  if({}) console.log('true'); //returns "true"
  if([]) console.log('true'); //returns "true"
  if('0') console.log('true'); //returns "true"
  if('false') console.log('true'); //returns "true"
  if(-123) console.log('true'); //returns "true"
  if(Infinity) console.log('true'); //returns "true"
  if(-Infinity) console.log('true'); //returns "true"
  ```
- Falsy: false을 반환하는 값들
  - false
  - 0
  - -0
  - 0n
  - "" '' ``
  - null
  - undefined
  - NaN
  ```javascript
  if(false) console.log('Not Falsy'); //returns nothing
  if(0) console.log('Not Falsy'); //returns nothing
  if(-0) console.log('Not Falsy'); //returns nothing
  if("") console.log('Not Falsy'); //returns nothing
  if('') console.log('Not Falsy'); //returns nothing
  if(null) console.log('Not Falsy'); //returns nothing
  if(undefined) console.log('Not Falsy'); //returns nothing
  if(NaN) console.log('Not Falsy'); //returns nothing

  //주의: if 조건문이 false면 오른쪽 statement는 실행되지 않는다. 
  ```
