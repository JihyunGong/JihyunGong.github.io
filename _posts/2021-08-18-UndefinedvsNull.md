---
layout: single
title: "[JavaScript] null과 undefined값의 차이"
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, null, undefined]
toc: true
comments: true
---

## null과 undefined값의 차이
JavaScript에서 null과 undefined은 모두 **"값이 없다"** 를 뜻한다.

그러나, '없다'의 의미는 각기 다르니, 아래의 설명을 참고하자. 
- ***null***: 해당 변수에 <u>명시적으로</u> 값이 없음을 말한다. 즉, 의도적으로 변수에 null값을 대입한 것이다. 
- ***undefined***: 해당 변수에 <u>값을 대입한 적 없음을</u> 말한다.(변수나 매개변수에 어떠한 값도 대입하지 않을 경우, 기본값으로 undefined값이 들어간다.)

아래 예시 코드를 통해 더 자세히 알아보자. 
```javascript 
var a = null; //변수 a에 null값을 대입했다. 
var b; //변수 b에는 아무 값도 대입하지 않았다. 

console.log(a); //returns null
console.log(b); //returns undefined

var obj = {
  name: "John" //객체의 속성(Property)
};

console.log(obj.name); //returns "John"
console.log(obj.age); //returns undefined
```
위의 예시처럼, 객체에 존재하지 않는 속성(Property)에 접근하려고 할 경우 undefined값을 return시킨다. 
