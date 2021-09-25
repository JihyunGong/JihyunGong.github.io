---
layout: single
title: "[JavaScript] 제어문: break & continue"
date: 2021-08-25
categories: [TIL, JavaScript]
tags: [TIL, JavaScript, 제어문, break, continue]
toc: true
comments: true
---

## 1. break란?
**break문** 은 <u>반복문, switch(조건문) 그리고 레이블문</u>에서 다양하게 활용가능하며 이들을 **종료하는 역할을 한다.** 

아래의 코드를 통해 break문이 무엇인지 알아보자. 
```javascript
for(var i = 0; i < 10; i++){
  if(i === 5){
    console.log(i);
    break;
  }
}
// Expected Output:
//5

// 위의 코드는 변수 i가 5가 될 때 까지 1씩 증감하는 반복문이다. 
// 만약 i가 5가 되면 i값을 출력 후 반복문을 멈추도록 break문을 설정해놓았다. 
```


### break의 중요성
만약 반복문이나 switch문, 특히 switch문에서 break를 사용하지 않으면 예상치 못한 코드들이 실행된다. 

따라서 **break문을 적절히 사용하면 불필요한 코드나 반복된 코드를 피할 수 있다.** 

아래의 예시를 통해 알아보자.  

- break문을 적절히 사용했을 때
```javascript
switch("happy"){
  case "amazed":
    console.log("I am feeling amazed.");
    break;
  case "excited":
    console.log("I am feeling excited.");
    break;
  case "happy":
    console.log("I am feeling happy.");
    break;
  case "fantastic":
    console.log("I am feeling fantastic.");
    break;
  default: 
    console.log("I am feeling nothing.");
    //break; default문은 마지막에 쓰는 것이 일반적이므로, 이 경우 break문을 굳이 사용할 필요는 없다. 
}
// Expected Output:
// "I am feeling happy."
```
- break문을 적절히 사용하지 못했을 때
```javascript
switch("happy"){
  case "amazed":
    console.log("I am feeling amazed.");
    break;
  case "excited":
    console.log("I am feeling excited.");
    break;
  case "happy":
    console.log("I am feeling happy.");
    //break;
  case "fantastic":
    console.log("I am feeling fantastic.");
    //break;
  default: 
    console.log("I am feeling nothing.");
    //break; default문은 마지막에 쓰는 것이 일반적이므로, 이 경우 break문을 굳이 사용할 필요는 없다. 
}
// Expected Output:
// "I am feeling happy."
// "I am feeling fantastic."
// "I am feeling nothing."
```
위의 예제로 알 수 있듯이, break문을 쓰지 않으면 불필요한 코드까지 실행된다. 


## 2. continue란?
**continue문** 은 break문과 달리 구문을 탈출하는 것이 아닌 **코드 블록 실행을 현시점에서 멈추고 다시 구문을 시작하게 한다.** 

또한, continue문은 <u>반복문과 래이블문</u>과 함께 사용 가능하다. 


### continue문의 코드 흐름 읽기
for문을 예로, continue문이 실행되면 반복문의 코드 실행을 잠시 멈추고 반복문의 증감식으로 이동한다. 

증감식으로 이동 후, 조건문을 체크하고 true일 경우 반복문을 계속 실행시킨다. 

    continue; -> 증감식 -> 조건문 -> (true일 경우)코드실행
    
아래의 예시를 통해 코드의 흐름을 파악해보자.
```javascript
var str = '';

for(var i = 0; i < 10; i++){
  if(i === 5) {
    continue;
  }
  str += i;
}

console.log(str);
// Expected Output:
// "012346789"

// 위의 코드는 0부터 9까지 숫자 중 5를 제외하고 프린트하는 반복문이다. 
// 따라서 변수 i가 5일 때 continue문을 사용해 아래의 코드 실행을 멈추었다. 
```
    

### 레이블(label)문이란?
**레이블문** 은 고유의 식별자(indentifier)가 붙은 구문으로 <u>프로그램의 실행 순서를 제어하기 위해 사용한다.</u> 

주로 <u>break와 continue문과 함께 쓰이며</u> 사용법은 반복문 앞에 **"식별자:"** 를 써주면 된다.

아래의 예시처럼 레이블문은 중첩된 for문을 탈출할 때 용이하지만, 이외의 경우에는 레이블문 사용을 지양해야한다. 

그 이유는 레이블문은 코드의 가독성을 떨어트리고 예상치 못한 오류를 발생시킬 가능성이 있기 때문이다. 

```javascript
var i, j;

loop1:
for(var i = 1; i < 7; i++){
  loop2:
  for(var j = 1; j < 7; j++){
    if(i === 3){
      continue loop1;
    }
    if(i + j === 7){
      console.log('(' + i + ', ' + j + ')');
    } 
  }
}
// Expected Output:
// "(1, 6)"
// "(2, 5)"
// "(4, 3)"
// "(5, 2)"
// "(6, 1)"

// 이 코드는 주사위의 7점의 원리를 보여주는 것이다.
// 레이블문과 continue문을 이용해 중복된 for문을 정상적으로 빠져나왔다. 
```
