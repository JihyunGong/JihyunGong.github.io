---
layout: single
title: "[JavaScript] 자주 사용하는 배열 메서드 TOP 10"
date: 2021-09-04
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Array, Methods]
toc: true
comments: true
---

## 1. push()
배열 끝에 새로운 요소를 추가한다.
```javascript
const fruits = ["apple", "banana", "orange"];
fruits.push("watermelon");

console.log(fruits);

// Expected Output:
// ["apple", "banana", "orange", "watermelon"]
```

## 2. pop()
배열의 가장 마지막 요소를 제거한다.
```javascript
const fruits = ["apple", "banana", "orange"];
fruits.pop();

console.log(fruits);

// Expected Output:
// ["apple", "banana"]
```

## 3. shift()
배열의 첫번째 요소를 제거하고 나머지 요소들의 위치를 -1씩 이동한다.
```javascript
const fruits = ["apple", "banana", "orange"];
fruits.shift();

console.log(fruits);

// Expected Output:
// ["banana", "orange"]
```

## 4. unshift()
배열의 첫번째 요소 위치에 새로운 요소를 추가하고 기존 요소들의 위치를 +1씩 이동한다.
```javascript
```

## 5. forEach()

## 6. indexOf()

## 7. includes()

## 8. splice()

## 9. slice()

## 10. sort()
