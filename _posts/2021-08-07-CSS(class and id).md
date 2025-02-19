---
layout: single
title: "[CSS] Class와 Id의 차이"
date: 2021-08-07
categories: [TIL, CSS]
tags: [TIL, CSS, HTML, class, id]
toc: true
comments: true
---

## 1. Selectors란?
쉽게 말해, **선택자(Selectors)** 는 HTML파일에 스타일을 입힐 범위를 정한다. 

선택자에는 다양한 것들이 있는데 오늘 살펴볼 선택자는 **class** 와 **id** 이다.  

이것들은 CSS의 <u>선택자(selectors)</u>이자 HTML의 <u>속성(attribute)</u>이다. 이러한 선택자를 통해 HTML파일의 원하는 요소에 접근할 수 있다.  

아래 예시를 통해 알아보자.
```html
<!-- HTML -->
<h1>This is heading</h1>
<p id="test">This is paragraph</p>
```
```css
/*css*/
#test {
  color: green;
}
```
위의 코드는 선택자 id #test를 통해 HTML파일에 "test"값을 가진 요소에 접근하여 폰트 색상을 입힌 것이다. 


## 2. Class와 Id의 차이
class와 id의 큰 차이는 *이름(name)* 에서 난다. 아래의 테이블을 통해 알아보자. 

\ | class | id
 --- | --- | ---
특징 | > 하나의 파일안에 동일한 이름의 class를 여러 개 가질 수 있다.<br/> > 한 태그에 여러개의 class 이름이 사용 가능하다.(공백으로 구분하며 대소문자 구분 X)| > 하나의 파일안에 중복되지 않는 고유한 이름의 id를 가질 수 있다.<br/> > 이름에 공백을 넣으면 안된다.(만약 공백을 넣을 시, 브라우저는 공백 또한 이름의 일부로 처리함)
예시 | `<p class="class name">samplePara</p> //두 개의 이름을 가지고 있는 class` | `<h1 id="name">sampleHeading</h1>`<br/>`<p id="name">samplePara</p> //한 파일안에 중복된 id이름을 사용할 수 없다.`<br/>`<p id="name ">samplePara</p> //이름에 공백이 들어가면 안된다.`


### class의 집합 성질
class는 집합의 성질을 가지고 있다. 아래의 예시로 확인해보자. 

**배경**
- HTML파일에 "a b"그리고 "a" 두개의 class가 있다.  

**문제**
- "a b"와 "a" class에 폰트 크기를 똑같이 10px로 줄 것. 
- 단, "a b" class의 폰트 색은 파란색으로 지정할 것.  

**풀이1**
```css
.a b{
font-size: 10px;
color: blue;
}

.a{
font-size: 10px;
}
```

**풀이2**
```css
.a{
font-size: 10px;
}

.b{
color: blue;
}
```

**설명**  
풀이1과 풀이2를 비교해보자. 

풀이1은 폰트 크기를 정하는 코드가 두 번 들어갔다. 

하지만, 풀이2는 css파일에 .a{}와 .b{}로 따로 나누어 "a b"와 "a" class의 공통된 스타일은 .a{}에 명령해주었고, "a b" class에만 명시해주고 싶은 스타일은 .b{}에 따로 명령해주었다.  

**따라서, class의 집합적인 성질을 통해 중복된 코드를 줄일 수 있다.** 
