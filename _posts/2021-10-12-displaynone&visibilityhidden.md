---
layout: single
title: "[CSS] display:none과 visibility:hidden의 차이"
date: 2021-10-12
categories: [TIL, CSS]
tags: [TIL, CSS]
<!-- toc: true -->
comments: true
---


display:none과 visibility:hidden은 HTML 요소의 내용을 숨기는 역할을 하는 CSS 속성이다.

이번 포스팅에서는 두 속성의 차이에 대해 설명한다.

## display:none과 visibility:hidden의 차이
**display:none과 visibility:hidden의 차이점은 요소의 영역을 유지하느냐 제거하느냐에 있다.**

- **display:none** - 해당 요소의 내용을 지우고 <u>요소의 영역도 제거한다.</u>
- **visibility:hidden** - 해당 요소의 내용을 지우고 <u>요소의 영역은 유지한다.</u>

아래 예시를 통해 알아보자.
- display:none
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Event</title>
  </head>
  <body>
    <div class="display">This area will be removed.</div>
    <div>Hello, World!</div>
  </body>
  </html>
  ```
  ```css
  .display {
    display:none;
  }
  ```
  OUTPUT:
  ```
  Hello, World!
  ```

- visibility:hidden
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Event</title>
  </head>
  <body>
    <div class="visibility">This area will not be removed.</div>
    <div>Hello, World!</div>
  </body>
  </html>
  ```
  ```css
  .visibility {
    visibility:hidden;
  }
  ```
  OUTPUT:
  ```

  Hello, World!
  ```
