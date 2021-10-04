---
layout: single
title: "[JavaScript] 생성자 함수와 new 연산자"
date: 2021-10-04
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Constructor function, new operator]
toc: true
comments: true
---


생성자 함수와 new 연산자는 뗄래야 뗄 수 없는 관계이다. 

## 1. 생성자 함수란?
**생성자 함수는 같은 타입의 객체를 여러 개 생성할 수 있는 함수이며, 줄여서 '생성자'라고도 부른다.**

생성자를 사용할 때 몇 가지 규칙이 있다.
- *규칙1) 생성자 함수의 이름은 대문자로 시작한다. (일반 함수와 구분을 짓기 위함)*
- *규칙2) 생성자 함수에 속성이나 메서드를 추가하기 위해서는 생성자에 직접 추가하거나, 프로토타입을 이용해 추가할 수 있다.* 
> [프로토타입](https://jihyungong.github.io/til/javascript/(2)Inheritance/)은 다음 포스팅에서 다룰 예정이다.


## 2. new 연산자란?
new 연산자는 생성자 함수와 함께 쓰이며, 객체를 생성하는데 직접적인 역할을 한다.

아래 예시를 통해 객체가 생성되는 과정을 살펴 보자. 
```javascript
function Person(name, age, hobby){
  this.name = name;
  this.age = age;
  this.hobby = hobby;
  this.info = function(){
    return "Name: " + this.name + "\n Age: " + this.age + "\n Hobby: " + this.hobby;
  }
} // 생성자 함수안에 객체를 정의할 속성 및 메서드를 작성

const jane = new Person("Jane", 20, "Tennis"); // 생성자 함수와 new 연산자를 통해 객체 jane을 생성

console.log(jane); // 객체 jane 로그
console.log(jane.info()); // 객체 jane의 메서드 info 호출 및 결과값 로그


// Expected Output:
// [object Object] {
//   age: 20,
//   hobby: "Tennis",
//   info: function(){
//     window.runnerWindow.proxyConsole.log("Name: " + this.name + "\n Age: " + this.age + "\n Hobby: " + this.hobby);
//   },
//   name: "Jane"
// } 
// "Name: Jane
//  Age: 20
//  Hobby: Tennis"
```
객체 jane의 생성 과정은 아래와 같다.  
1. *new 연산자로 빈 객체를 만들어 this에 할당한다. (즉, 이 this는 빈 객체를 참조한다.)*
2. *생성자 함수를 호출 및 실행하여 this를 수정한다.*  
3. *수정된 this를 반환한다.*  
4. *반환된 this를 변수 'jane'에 할당한다.*  

**위 과정에서 new 연산자의 역할은 빈 객체 생성 및 생성자 함수 호출, 객체(this) 반환이다.**

> 여기서 유의해야 할 점은 일반적으로 생성자 함수에는 return문을 사용하지 않는다는 것이다. 
>
> 생성자 함수는 return문을 작성하지 않아도 this를 자동으로 반환해주기 때문이다. 
>
> 만약 명시적으로 다른 객체를 반환하도록 return문을 작성할 경우, 생성자 함수의 본질을 잃게 된다. 
