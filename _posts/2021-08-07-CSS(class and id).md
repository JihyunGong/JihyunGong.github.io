---
layout: single
title: "[CSS] Selectors 'class'와 'id'의 차이"
comments: true
categories: [TIL, CSS]
tags: [TIL, CSS, HTML, class, id]
toc: true
---

## Selectors 정의
쉽게 말해, 선택자(Selectors)는 HTML파일에 스타일을 입힐 범위를 정한다. 

선택자에는 다양한 것들이 있는데 오늘 살펴볼 선택자는 **class**와 **id**이다.  

이것들은 CSS의 선택자(selectors)이자 HTML의 속성(attribute)이다. 이러한 선택자를 통해 HTML파일의 원하는 요소에 접근할 수 있다.  

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


## class와 id의 차이
class와 id의 큰 차이는 이름(name)에서 난다. 아래의 테이블을 통해 알아보자. 
\ | class | id
 --- | --- | ---
특징 | > 하나의 파일안에 동일한 이름의 class를 여러 개 가질 수 있다.</br> > 한 태그에 여러개의 class 이름이 사용 가능하다.(공백으로 구분하며 대소문자 구분 X)| > 하나의 파일안에 중복되지 않는 고유한 이름의 id를 가질 수 있다.</br> > 이름에 공백을 넣으면 안된다.(만약 공백을 넣을 시, 브라우저는 공백 또한 이름의 일부로 처리함)
예시 | `<p class="class name">samplePara</p> //두 개의 이름을 가지고 있는 class` | `<h1 id="name">sampleHeading</h1>`</br>`<p id="name">samplePara</p> //한 파일안에 중복된 id이름을 사용할 수 없다.`</br>`<p id="name ">samplePara</p> //이름에 공백이 들어가면 안된다.`



