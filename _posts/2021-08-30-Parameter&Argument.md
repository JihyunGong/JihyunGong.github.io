---
layout: single
title: "[JavaScript] 매개변수과 인자의 차이"
date: 2021-08-30
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Parameter, Argument]
toc: true
comments: true
---

## 매개변수와 인자의 차이
자바스크립트에서 매개변수(parameter)와 인자(argument)는 함수와 함께 사용할 수 있다. 

아래의 설명을 통해 그 차이를 알아보자. 

- **매개변수: 매개변수는 함수를 선언할 때 포함할 수 있으며 함수안에서만 사용되는 변수(지역변수)이다.** 
- **인자: 인자는 함수를 호출할 때 함수의 매개변수로 전달하는 값(data)자체이다. 전달된 값은 해당 매개변수에 할당된다.** 

> 매개변수의 기본값(default value)는 일반변수와 같이 'undefined'이다. 함수 선언부에서 매개변수의 기본값(default value)을 임의로 정의할 수 있다. 
> 
> 따라서 함수 호출 시 인자가 주어지지 않을 경우, 해당 매개변수의 값은 'undefined' 혹은 임의로 정의된 기본값으로 할당된다. 

```javascript
function multiply(x, y){
  var result = x * y;
  return result;
}

console.log(multiply(3)); // 매개변수 y에 대입할 값이 주어지지 않음
console.log(multiply(3, undefined)); // 위의 코드와 동일한 기능을 수행함
console.log(multiply(3, 4));


// Expected Output:
// NaN
// NaN
// 12

//참고: 숫자 * undefined = NaN(숫자가 아님)
```
