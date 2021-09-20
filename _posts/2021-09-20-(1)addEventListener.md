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

> - 등록된 이벤트 리스너의 기본 동작 취소하기: prevent.Default();  
> - 등록된 이벤트 리스너 제거하기: removeEventListener();


## 예시


