---
layout: single
title: "[HTML] article vs section 차이"
categories: [TIL, HTML]
tags: [TIL, HTML, semantic elements, article, section]
toc: true
comments: true
---

## 1. article과 section 정의
**article** 과 **section** 은 모두 **"Semantic Elements"** 들이다.  

> ***NOTE:*** Semantic Elements란?  
semantic을 직역하면 *"의미론적인"* 이라는 뜻이다. HTML에서 elements는 non-semantic elements와 semantic elements로 나뉜다.  
**non-semantic elements** : 의미없는 내용을 담고있는 요소 ex) div, span, p  
**semantic elements** : 의미있는 내용은 담고있는 요소 ex) header, main, section, article, footer  
***cf)*** 의미없는 내용을 담을 경우 non-semantic elements를 사용하면 안된다. 예를 들어, 내용들 간 구역만 나누고 싶을 때는 div 요소를 사용해주면 된다. 


## 2. article과 section 차이

article | section
--- | ---
홀로 독립적인 내용을 담고 싶을 때 사용<br/> ex) 블로그, 뉴스 | 서로 관련있는 내용을 담고 싶을 때 사용<br/> ex) 목차, 설명글

아래 예시를 통해 자세히 알아보자. 
```html
//article inside section
<section>
  <h1>News</h2>
  <article>News1</article>
  <article>News2</article>
  <article>News3</article>
</section>
```
```html
//section inside article
<article> 
  <h1>News1</h1>
  <section>News title</section>
  <section>News author</section>
  <section>News content</section>
</article>
```
위의 예시처럼, 서로 독립적인 내용을 담고있는 뉴스들은 'article'로 나누어 주었다. 하지만, 한 뉴스의 제목, 작성자, 내용등 서로 밀접한 관계가 있는 부분들은 'section'으로 나누어 주었다. 

√ 여기서 주목해야할 점은 각 예시에 'article'과 'section'을 적절히 섞어 사용했다는 점이다.
- 첫번째 예시에서는 각 뉴스를 'article'로 나누어 주었고, 각 뉴스들을 'section'으로 담고있도록 해주었다. 
- 두번째 예시에서는 한 뉴스내에 관련있는 내용들은 'section'으로 나누어 주었고, 그 부분들을 한 'article'로 감싸고 있도록 해주었다. 

**따라서, <u>article</u> 과 <u>section</u> 의 특성을 잘 이해하고 적절한 곳에 잘 사용할 수 있어야 한다.**
