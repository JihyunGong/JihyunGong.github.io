---
layout: single
title: "[JavaScript] 프로토타입 & 상속"
date: 2021-10-04
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Prototype, Inheritance]
<!-- toc: true -->
comments: true
---


자바스크립트는 프로토타입 기반의 언어이며, 이 덕분에 객체 간의 상속도 가능하다.

이번 포스팅은 프로토타입과 상속의 개념, 그리고 그 둘의 관계에 대해 설명한다.  

## 프로토타입과 상속의 관계
둘의 관계를 알기 전, 먼저 프로토타입이 무엇인지 알아보자.

**프로토타입을 직역하면 '원형'이라는 뜻을 가지고 있다.** 자바스크립트에서 프로토타입은 이 '원형'이라는 뜻과 깊은 연관이 있다.

**자바스크립트의 모든 객체는 해당 객체보다 상위 객체(부모 객체)를 참조하고 있으며, 참조 대상이 되는 객체를 '프로토타입(원형 객체)'이라고 부른다.**

즉 하위 객체(자식 객체)는 그들의 원형 객체를 참조(공유)하는 것이다. 

**이를 '상속'이라고 하며, 자식 객체가 부모 객체의 속성과 메서드를 물려 받는다.** 

여기서 상속이란 단순히 속성과 메서드를 물려 받는 개념에서 그치지 않고, **필요에 따라 속성이나 메서드를 추가하여 자식 객체의 기능을 확대할 수 있음을 말한다.**

상속의 장점은 위에서 알 수 있듯이 <u>중복된 코드 작성을 줄이고 코드의 재사용성을 높인다.</u> 

**결론적으로 프로토타입은 객체의 상속을 위해 존재한다고 봐도 무방하다.** 

참고로 모든 객체의 최상위 프로토타입은 <u>Object.prototype</u>이다.


아래의 예시를 통해 프로토타입과 상속의 개념을 정리해보자.
```javascript
function Car(name, price, years){
  this.name = name;
  this.price = price;
  this.years = years;
  this.info = function(){
    return "Name: " + this.name + "\n Price: " + this.price + "\n Years: " + this.years;
  };
} // 생성자 함수 Car 정의

const audi = new Car("Audi", 2000, "2021"); 
// 객체 audi는 프로토타입인 생성자 함수 Car를 참조함

audi.used = false; // 객체 audi에 프로퍼티 추가
audi.info = function(){
  return "Name: " + audi.name + "\n Price: " + audi.price + 
          "\n Years: " + audi.years + "\n Used: " + audi.used;
}; // 생성자 함수로부터 물려받은 메서드 수정(오버라이딩)

console.log(audi);
console.log(audi.info());


// Expected Output:
// [object Object] {
//   info: function(){
//   return "Name: " + audi.name + "\n Price: " + audi.price + 
//           "\n Years: " + audi.years + "\n Used: " + audi.used;
// },
//   name: "Audi",
//   price: 2000,
//   used: false,
//   years: "2021"
// }
// "Name: Audi
//  Price: 2000
//  Years: 2021
//  Used: false"
```
