---
layout: single
title: "[Javascript] Immutability & Mutability"
date: 2021-09-30
categories: [TIL, Javascript]
tags: [TIL, JavaScript, Immutability, Mutability]
toc: true
comments: true
---


자바스크립트의 모든 값은 'Immutable'한가 'Mutable'한가로 나눌 수 있다. 

그렇다면 그 차이가 무엇인지 알아보자. 


## 1. Immutability & Mutability
- **Immutability: 변경 불가능한 값** 
  (ex: Primitive type - String, Number, Boolean, Null, Undefined, Symbol)
- **Mutability: 변경 가능한 값** 
  (ex: Reference type - Object(Array, Function))
  > - "값"은 데이터를 말한다.  
  > - "변경 불가능하다"는 메모리 영역에서 변경이 불가능하다는것을 말한다. 값의 재할당은 가능하다.

아래의 예시를 통해 알아보자.

- **Immutable value**

```javascript
let str = "Jane";
str = "Doe";
```
Primitive type의 변수는 값의 재할당은 가능하나 변경이 불가능하다. 

  재할당의 과정을 좀 더 자세히 살펴보자.

  변수 str에 "Jane"이라는 문자열을 대입했을 때, str은 메모리를 할당하고 그 메모리에 "Jane"이라는 데이터를 놓는다.

  이후 str에 "Doe"라는 문자열을 재할당했을 때, str은 새로운 메모리를 할당하고 그 메모리에 "Doe"라는 데이터를 놓는다.

  메모리 상에는 "Jane"과 "Doe", 두 데이터 모두 존재한다. 결과적으로 "Jane"이라는 문자열을 수정한 것이 아니다. 

- **Mutable value**

```javascript
const obj = {
  name: "Jane",
  age: 20,
  hobby: "Tennis"
}

obj.name = "John";
```
Reference type의 변수는 값의 변경이 가능하다.

  <u>참조형 변수는 데이터가 아닌 주소값을 저장한다는 사실을 기억해야 한다.</u>

  따라서 주소값이 가리키는 데이터를 변경하는 것은 주소값을 변경하는 것이 아니다. 

  변수 obj에는 객체를 가리키는 주소값이 저장되어 있고 name의 값을 변경하는 것은 주소값을 변경하는 것이 아니라는 얘기다. 


## 2. 객체의 Mutability
객체 타입은 Mutable한 특성때문에 종종 예기치 않은 객체의 변경이 발생한다. 

이를 방지하기 위해, 객체를 불변화하는 3가지 방법이 존재한다. 

- **Object.assign:** 기존 객체를 변경하지 않고 객체를 복사하여 변경 및 수정을 가능하게 한다.
- **Object.freeze:** 객체를 불변화하여 객체의 변경을 막는다.
   > 위의 두 가지 방법은 번거롭기도 하고 성능상 이슈가 있어 복잡한 객체에는 사용하지 않는 것이 좋다.
- **Immutable.js:** Immutable.js는 Facebook에서 제공하는 기능이다. 


참고: [PoiemaWeb - 객체와 변경불가성(Immutability)](https://poiemaweb.com/js-immutability)
