---
layout: single
title: "[Javascript] target과 currentTarget의 차이"
date: 2021-09-22
categories: [TIL, Javascript]
tags: [TIL, JavaScript, DOM]
toc: true
comments: true
---


이벤트 객체 속성에 포함된 target과 currentTarget의 차이를 알아보자. 

## target과 currentTarget의 차이
- target: 이벤트가 발생한 실제 요소를 가리킨다.
- currentTarget: 발생한 이벤트 리스너가 등록된 요소를 가리킨다.

아래의 예시를 살펴보자.
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>Event</title>
</head>
<body>
  <p>아래의 버튼을 클릭해보세요.<p>
  <div>
    <button>1</button>
    <button>2</button>
    <button>3</button>
    <button>4</button>
    <button>5</button>
  </div>
</body>
</html>
```
```javascript
const t = document.querySelector("div");

t.addEventListener("click", function(ev){
  console.log(ev.target.tagName);
  console.log(ev.currentTarget.tagName);
});
```
```
// 아래의 아웃풋은 버튼 1, 2, 3, 4, 5를 차례대로 클릭한 결과이다.
// Expected Output:
"BUTTON"
"DIV"
"BUTTON"
"DIV"
"BUTTON"
"DIV"
"BUTTON"
"DIV"
"BUTTON"
"DIV"
```
