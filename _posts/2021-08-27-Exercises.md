---
layout: single
title: "[JavaScript] 자바스크립트 간단 알고리즘 문제 5종"
date: 2021-08-27
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, Algorithm]
toc: true
comments: true
---

## 1. 문자열 역순 출력하기
**문제:** 반복문을 이용하여 아래에 주어진 문자열을 역순으로 출력하는 코드를 작성해보세요. 
```javascript
var name = "Jihyun";
// 역순으로 한 글자씩 출력하는 반복문을 작성해보세요. 
```

**출력 예시:**
```javascript
"nuyhiJ"
```

**나의 풀이:**
```javascript
var name = "Jihyun";
var reverName = ""; // 역순으로 출력된 문자열을 담을 String타입의 빈 변수

for(var i = name.length-1; i >= 0; i--){
  reverName += name[i]; // 반복문을 이용해 역순으로 한 글자씩 정렬
}
console.log(reverName); //역순으로 정렬된 문자열 출력
```


## 2. 문자열의 홀수번째 글자만 출력하기
**문제:** 반복문을 이용하여 아래에 주어진 문자열의 홀수번째 글자만 출력하는 코드를 작성해보세요. 
```javascript
var longText = "0i1a2m3j4i5h6y7u8n9";
// 홀수번째 글자만 출력하는 코드를 작성해보세요.
```

**출력 예시:**
```javascript
"iamjihyun"
```

**나의 풀이1:**
```javascript
var longText = "0i1a2m3j4i5h6y7u8n9"; // 문자열은 0번째 부터 시작이다. 첫 홀수번째 글자는 'i'가 된다.
var oddText = ""; // 홀수번째 글자만 담을 String타입의 빈 변수

for(var i = 1; i < longText.length; i +=2){ // 변수 i에 2씩 더해 홀수번째 글자를 담는다.
  oddText += longText[i];  
}
console.log(oddText); // 홀수번째 문자열 출력
```
**나의 풀이2:**
```javascript
var longText = "0i1a2m3j4i5h6y7u8n9"; // 문자열은 0번째 부터 시작이다. 첫 홀수번째 글자는 'i'가 된다.
var oddText = ""; // 홀수번째 글자만 담을 String타입의 빈 변수

for(var i = 0; i < longText.length; i++){ 
  if(i % 2 !== 0)  oddText += longText[i]; // 문자열의 index값을 2로 나누어 0으로 떨어지지 않으면 홀수번째 글자로 판단한다.
}
console.log(oddText); // 홀수번째 문자열 출력
```


## 3. FizzBuzz
**문제:** 자바스크립트의 반복문과 조건문 등을 이용하여 아래와 같은 조건을 만족하는 코드를 작성해보세요. 
- 1부터 100까지 console.log를 실행합니다.
- 3의 배수는 "fizz"라는 문자열을 로그합니다.
- 5의 배수는 "buzz"라는 문자열을 로그합니다.
- 3과 5의 공배수는 "fizzbuzz"라는 문자열을 로그합니다.
- 나머지 숫자들은 해당 숫자 자체를 로그합니다.

**출력 예시:**
```javascript
1
2
fizz
4
buzz
fizz
7
8
fizz
buzz
11
fizz
13
14
fizzbuzz
16
.
.
.
98
fizz
buzz
```

**나의 풀이:**
```javascript
for(var i = 1; i <= 100; i++){ // 1부터 100까지의 숫자를 출력하는 반복문
  if(i % (3*5) === 0){
    console.log("fizzbuzz"); // 3과 5의 공배수는 "fizzbuzz" 로그
  } else if(i % 3 === 0){
    console.log("fizz"); // 3의 배수는 "fizz" 로그
  } else if(i % 5 === 0){
    console.log("buzz"); // 5의 배수는 "buzz" 로그
  } else{
    console.log(i); // 나머지 숫자들은 숫자 그자체를 로그
  }
}
```


## 4. Biggest Number 
**문제:** 아래와 같이 세 개의 변수가 숫자를 담고 있습니다. 가장 큰 수가 무엇인지 연산을 하여 console.log하도록 코드를 작성해보세요.
- Math.max를 사용하지 마세요.
- a, b, c 에 담긴 값이 바뀌더라도 항상 정확한 결과가 나올 수 있도록 코드를 작성해보세요. 
```javascript
var a = 10;
var b = 20;
var c = 30;
```

**출력 예시:**
```javascript
30
```

**나의 풀이:**
```javascript
var a = 10;
var b = 20;
var c = 30;

var maxNum = 0; // biggest number를 담을 변수 'maxNum'

if(a > b && a > c){ // a가 b, c보다 크다면 a를 maxNum에 대입
  maxNum = a;
} else if(b > a && b > c){ // b가 a, c보다 크다면 b를 maxNum에 대입
  maxNum = b;
} else{ //위의 두 조건이 맞지 않으면 c가 biggest number가 된다.
  maxNum = c;
}

console.log(maxNum); //maxNum 출력
```


## 5. Word Position
**문제:** 여러분에게 아래와 같이 두 개의 문자열 값이 주어집니다. 
하나의 문자열은 단어 정보를 담고 있고, 다른 하나의 문자열은 문장을 담고 있습니다. 
해당 단어(word 변수의 값)이 문장에서 나타나는 시작 인덱스와 끝 인덱스를 연산하여 console.log 해보세요.  
```javascript
var word = "dolphin";
var sentence = "Where did Jane get the dolphin from, John?";

var indexOfD = SOMETHING; // SOMETHING 부분에 dolphin의 d의 위치를 찾는 코드를 작성해보세요.
var indexOfN = SOMETHING_ELSE; // SOMETHING_ELSE 부분에 dolphin의 n의 위치를 찾는 코드를 작성해보세요.

console.log(indexOfD, indexOfN);
```

**출력 예시:**
```javascript
23, 29
```

**나의 풀이:**
```javascript
var word = "dolphin";
var sentence = "Where did Jane get the dolphin from, John?";

var indexOfD = sentence.indexOf(word); 
// indexOf()를 이용해 sentence문자열에 "dolphin"을 찾아 'd'의 index값을 얻는다. 
var indexOfN = sentence.indexOf(word) + (word.length -1); 
// 위의 index값에 "dolphin"의 문자열 길이에서 1을 뺀 나머지를 더하여 마지막 글자 'n'의 index값을 얻는다.
// "dolphin"의 문자열 길이에서 1을 뺀 이유는 string의 index값은 0부터 시작하기 때문이다.

console.log(indexOfD, indexOfN); // "dolphin"의 'd'와 'n'의 위치 출력
```
> [indexOf()에 대해 더 알고싶다면?](https://jihyungong.github.io/til/javascript/(2)indexOfvsSearch/) 
