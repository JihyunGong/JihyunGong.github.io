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
const fruits = ["apple", "banana", "orange"];
fruits.unshift("mango");

console.log(fruits);

// Expected Output:
// ["mango", "apple", "banana", "orange"]
```

## 5. forEach()



## 6. indexOf()
배열에서 주어진 값과 첫번째로 일치하는 요소의 위치를 반환한다. 

일치하는 요소가 없으면 -1을 반환한다.
```javascript
const fruits = ["apple", "banana", "orange"];

console.log(fruits.indexOf("banana"));

// Expected Output:
// 1
```

## 7. includes()
배열에서 주어진 값의 존재 여부를 판별하여 boolean값을 반환한다.
```javascript
const fruits = ["apple", "banana", "orange"];

console.log(fruits.includes("banana"));

// Expected Output:
// true
```

## 8. splice()
배열의 특정한 위치에 요소를 추가하거나 제거한다.

Syntax: 배열이름.splice(새로운 요소를 추가할 위치, 제거할 요소의 개수, 새로운 요소의 값...);
- 특정 위치 요소 추가하기  
```javascript
const fruits = ["apple", "banana", "orange"];

fruits.splice(1, 0, "mango");
console.log(fruits);

// Expected Output:
// ["apple", "mango", "banana", "orange"]
```
- 특정 위치 요소 추가 및 제거하기  
```javascript
const fruits = ["apple", "banana", "orange"];

fruits.splice(1, 2, "mango");
console.log(fruits);

// Expected Output:
// ["apple", "mango"]
```
- 특정 위치 요소 제거하기  
```javascript
const fruits = ["apple", "banana", "orange"];

fruits.splice(0, 1);
console.log(fruits);

// Expected Output:
// ["banana", "orange"]
```

## 9. slice()
배열의 한 부분을 추출하여 새로운 배열에 저장한다. 

Syntax: 배열이름.slice(추출을 시작할 위치, 추출을 마칠 위치(미포함));
```javascript
const fruits = ["apple", "banana", "orange"];

const newFruits = fruits.slice(1); //추출을 마칠 위치를 지정하지 않을 경우, 배열 끝까지 추출을 실행함
const newFruits2 = fruits.slice(0, 1);

console.log(fruits);
console.log(newFruits);
console.log(newFruits2);

// Expected Output:
// ["apple", "banana", "orange"]
// ["banana", "orange"]
// ["apple"]
```

## 10. sort() & reverse()
배열의 요소들을 알파벳 순서대로(혹은 역순으로) 분류한다. 
```javascript
const fruits = ["banana", "apple", "orange"];

console.log(fruits.sort());
console.log(fruits.reverse());

// Expected Output:
// ["apple", "banana", "orange"]
// ["orange", "banana", "apple"]
```
여기서 주의할 점은 sort(), reverse()는 요소가 숫자값이라도 문자열값으로 인식한다는 것이다. 

아래의 코드를 통해 확인해보자.
```javascript
const fruits = [100, 3, 2, 26, 45];

console.log(fruits.sort());
console.log(fruits.reverse());

// Expected Output:
// [100, 2, 26, 3, 45]
// [45, 3, 26, 2, 100]
```
따라서 이 경우 적절한 function을 사용해야 한다. 
```javascript
const fruits = [100, 3, 2, 26, 45];

// 반환값이 음수면 a를 앞으로 분류하고, 양수면 b를 앞으로 분류함 
console.log(fruits.sort(function(a, b){return a - b;}));
console.log(fruits.reverse(function(a, b){return b - a;}));

// Expected Output:
// [2, 3, 26, 45, 100]
// [100, 45, 26, 3, 2]
```
