---
layout: single
title: "[JavaScript] indexOf() vs search() 비교 분석"
date: 2021-08-22
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, String Methods, indexOf(), search()]
toc: true
comments: true
---

## indexOf() vs search() 비교 분석

<table>
  <thead>
    <tr>
      <th>\</th>
      <th>indexOf()</th>
      <th>search()</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>공통점</td>
      <td colspan=2>> 두 메서드는 인자값에 의해 해당 문자(열)이 있는 첫 번째 위치를 index값으로 반환한다.<br/> > 해당 문자(열)을 찾지 못하면 -1를 반환한다.</td>
    </tr>
    <tr>
      <td>차이점</td>
      <td>> 검색값을 이용해 문자열을 처리한다.(정규식 x)<br/> > fromIndex값을 통해 검색을 시작할 위치를 정할 수 있다. .</td>
      <td>> 정규식을 이용해 문자열을 처리한다.<br/> > flags값을 통해 전역검색 및 대소문자 구분없이 검색할 수 있다.</td>
    </tr>  
    <tr>
      <td>Syntax</td>
      <td>indexOf(searchValue)<br/> indexOf(searchValue, fromIndex)</td>
      <td>search(/regexp/)<br/> search(/regexp/flags)</td>
    </tr>
  </tbody>
</table>  

> [정규식에 대해 더 알아보고 싶다면?](https://jihyungong.github.io/til/javascript/RegularExpressions/)


아래의 예시를 통해 더 자세히 알아보자. 
> 주의사항: index값은 0부터 시작한다.
```javascript
var str = 'Hello, world';

//indexOf()
console.log(str.indexOf('')); //returns 0
console.log(str.indexOf('Hello')); //returns 0
console.log(str.indexOf('hello')); //returns -1
console.log(str.indexOf('Hello ')); //returns -1
console.log(str.indexOf('o')); //returns 4
console.log(str.indexOf('o', 5)); //returns 8
console.log(str.indexOf('Hello', 5)); //returns -1

//search()
console.log(str.search(/Hello/)); //returns 0
console.log(str.search(/hello/)); //returns -1
console.log(str.search(/Hello /)); //returns -1 
console.log(str.search(/HELLO/i)); //returns 0
console.log(str.search(/[A-Z]/g)); //returns 0
```
   
***결론: 정규식을 써야하는 복잡한 문자열이 아니라면, indexOf()가 더 빠르고 사용이 편할 것이다.***
