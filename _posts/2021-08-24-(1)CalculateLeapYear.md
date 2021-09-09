---
layout: single
title: "[Algorithm] 자바스크립트를 이용한 윤년 구하기"
date: 2021-08-24
categories: [TIL, Algorithm]
tags: [TIL,Algorithm, JavaScript, LeapYear]
toc: true
comments: true
---

## 윤년 계산법
> 윤년이란? 양력으로 4년마다 한번씩 2월이 29일까지 있는 해를 뜻한다. 

연도를 4로 나누어 나머지가 0으로 떨어지는 해는 윤년이다. 그러나, 그 중 100으로 나누어 떨어지는 해는 윤년이 아니다. 

앞의 조건이 참이건 거짓이건 연도를 400으로 나누어 떨어지는 해는 윤년이다. 


<br/>아래 코드를 통해 이해해보자. 

```javascript
var year = [2000, 2004, 2100, 2021];

for(var i = 0; i < year.length; i++){
  if((year[i] % 4 === 0 && year[i] % 100 !== 0) || year[i] % 400 === 0 ){
  console.log(year[i] + ' year is Leap Year.');
  } else{
  console.log(year[i] + ' year is not Leap Year.');
  }
}

//Expected Output:
// "2000 year is Leap Year."
// "2004 year is Leap Year."
// "2100 year is not Leap Year."
// "2021 year is not Leap Year."
```
