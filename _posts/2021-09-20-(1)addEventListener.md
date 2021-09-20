---
layout: single
title: "[Javascript] addEventListener()를 이용한 이벤트 등록하기"
date: 2021-09-20
categories: [TIL, Javascript]
tags: [TIL, JavaScript, DOM]
toc: true
comments: true
---


## 이벤트 등록하기
addEventListener()를 이용해 웹 페이지에서 일어난 [이벤트](https://jihyungong.github.io/til/javascript/Events/)를 감지하고 해당 이벤트의 대상에 이벤트 리스너를 등록한다.

> 등록 시 유의할 점: 
> - 이벤트 등록은 DOM 요소 단위로 이루어진다.
> - 하나의 요소에 복수의 이벤트 리스너 등록이 가능하다.
> - 복수의 요소에 하나의 이벤트 리스너를 재사용해 등록이 가능하다.

이제 addEventListener()를 어떻게 사용하는지 알아보자.

**Syntax: addEventListener(type, listener, options/useCapture);**
1. type: 감지할 이벤트 명을 적는다.
2. listener: 이벤트를 감지할 때 실행시킬 함수를 적는다. 일반적으로 이 함수를 'Event Handler'라고 부른다.
    - Event Object: 함수의 인자로 이벤트 객체를 넣기도 하며, 이 객체는 현재 발생한 이벤트에 대한 상세 정보를 담고 있다.
        > 장점: 이벤트 객체를 이용해 DOM 요소를 제어할 수 있으며, 복수의 요소에 하나의 리스너를 재사용할 수도 있다.
3. options(optional): 이벤트 리스너에 대한 특징을 명시한다. (ex- [capture, once, passive...](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener#syntax))
4. useCapture(optional): 중첩된 HTML 태그에 대한 이벤트 전파 흐름을 제어한다. 
    - Capturing: 부모 요소부터 자식 요소 순서로 전파한다.
    - Bubbling: 자식 요소부터 부모 요소 순서로 전파한다. 

> - 등록된 이벤트 리스너의 기본 동작 취소하기: preventDefault();  
> - 등록된 이벤트 리스너 제거하기: removeEventListener();


## 예시
- 이벤트 등록하기
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Event</title>
  </head>
  <body>
    <h2>아래의 설명대로 실행해보세요.</h2>
    <button class="clk">클릭 하세요</button>
    <p class="movr">마우스 커서를 올려보세요</p>
  </body>
  </html>
  ```
  ```javascript
  const bt = document.querySelector(".clk");
  const mo = document.querySelector(".movr");

  bt.addEventListener("click", function (){
    alert("클릭하셨습니다.");
  });
  mo.addEventListener("mouseover", function(){
    alert("마우스 커서를 올리셨습니다.");
  });
  ```
  [아웃풋 확인](https://jsbin.com/faqewim/edit?html,js,output)
  
- 이벤트 객체 이용하기 1
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Event</title>
  </head>
  <body>
    <p>숫자를 클릭해보세요.</p>
    <div>
      <button>1</button>
      <button>가</button>
      <button>2</button>
      <button>나</button>
      <button>3</button>
    </div>
  </body>
  </html>
  ```
  ```javascript
  const div = document.querySelector("div");

  div.addEventListener("click", function(ev){
    if(isNaN(ev.target.textContent)){
      alert("숫자가 아닙니다: " + ev.target.textContent);
    } else{
      alert("숫자를 클릭하셨습니다: " + ev.target.textContent);
    }
  });
  ```
  [아웃풋 확인](https://jsbin.com/cemubah/edit?html,js,output)

- 이벤트 객체 이용하기 2
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Event</title>
  </head>
  <body>
    <button id="button1">클릭하세요1</button>
    <button id="button2">클릭하세요2</button>
  </body>
  </html>
  ```
  ```javascript
  const btn1 = document.querySelector("#button1");
  const btn2 = document.querySelector("#button2");

  function on_click(ev){
    alert(ev.target.textContent);
  }

  btn1.addEventListener("click", on_click);
  btn2.addEventListener("click", on_click);
  ```
  [아웃풋 확인](https://jsbin.com/qinuguz/edit?html,js,output)

- 이벤트 전파 흐름 제어하기
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Event</title>
  </head>
  <body>
    <style>
      div{
        border: 2px solid red;
      }
      p{
        border: 2px solid blue;
      }
      span{
        border: 2px solid green;
      }
    </style>
    <!-- 중첩된 HTML 태그 -->
    <div>div
      <p>p
        <span>span</span>
      </p>
    </div>
  </body>
  </html>
  ```
  ```javascript
  for(let e of document.querySelectorAll("*")){
    //Capturing
    e.addEventListener("click", function(){
      alert(e.tagName);
    }, true);
    //Bubbling
    e.addEventListener("click", function(){
      alert(e.tagName);
    })
  }
  ```
  [아웃풋 확인](https://jsbin.com/qebuwal/edit?html,js,output)

- 이벤트 기본 동작 취소하기
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Event</title>
  </head>
  <body>
    <label><input type="checkbox">이벤트를 멈추고 싶다면 체크하세요</label><br/>
    <button>클릭하세요</button>
  </body>
  </html>
  ```
  ```javascript
  const btn = document.querySelector("button");
  const pvt = document.querySelector("input");

  btn.addEventListener("click", function(ev){
     if(pvt.checked){
       ev.preventDefault();
     } else{
         alert("버튼을 클릭했습니다.");
     }
  });
  ```
  [아웃풋 확인](https://jsbin.com/bimiqaz/edit?html,js,output)

- 이벤트 제거하기
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Event</title>
  </head>
  <body>
    <label><input type="checkbox">이벤트를 제거하고 싶다면 체크하세요</label><br/>
    <button>클릭하세요</button>
  </body>
  </html>
  ```
  ```javascript
  const btn = document.querySelector("button");
  const rm = document.querySelector("input");

  function on_click(ev){
    if(rm.checked){
      btn.removeEventListener("click", on_click);
    } else{
      alert("버튼을 클릭했습니다.");
    }
  }

  btn.addEventListener("click", on_click);
  ```
  [아웃풋 확인](https://jsbin.com/tilocut/edit?html,js,output)
