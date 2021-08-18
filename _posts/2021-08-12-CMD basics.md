---
layout: single
title: "[CMD] CLI로 내 파일 관리하는 법"
comments: true
categories: [TIL, CMD]
tags: [TIL, CMD]
toc: true
---

## CLI 정의
**CLI** 즉, **Command Line Interface**는 Windows OS 기준 **'명령 프롬프트(cmd)'** 창을 열어서 명령어를 통해 컴퓨터내 폴더와 파일을 관리해주는 것이다.

오늘의 주제는 cmd를 이용해 폴더와 파일을 생성, 삭제, 이동하는 법에 대해 알아보자. 


## 1. cmd창 열기 

<img src="/assets/images/open_cmd.png" alt="open_cmd">


## 2. directory(folder) 생성하기
> **desktop에 'test'폴더 만들기**
- desktop으로 이동  
TIP: directory를 생성하기 위해서 먼저 <u>directory를 생성할 위치로</u> 이동해주는 것이 좋다.  
<img src="/assets/images/cd_directory.png" alt="cd_directory">
- 'test' directory 생성  
<img src="/assets/images/create_directory.png" alt="create_directory">
- directory 생성확인  
명령어 'dir'을 입력해주면 current working directory에 있는 <u>하위 directory들을 목록화시켜준다.</u> 
<img src="/assets/images/list_directory.png" alt="list_directory">

> **'test'폴더안에 'txt_file'폴더 생성하기**  
- 'txt_file' directory 생성  
<img src="/assets/images/create_nested_directory.png" alt="create_nested_directory">


## 3. file 생성하기
> **'test'폴더안에 'jihyun.txt'파일 만들기**
- 'jihyun.txt' 생성
<img src="/assets/images/create_empty_file.png" alt="create_empty_file">

> **'jihyun.txt'파일 안에 인삿말 넣기**
- text 입력
<img src="/assets/images/enter_text_in_file.png" alt="enter_text_in_file">


## 4. file 이동하기
> **'jihyun.txt'파일을 'txt_file'폴더로 이동하기**
- file 이동
<img src="/assets/images/move_file.png" alt="move_file">


## 5. directory 삭제하기
> **'txt_file'폴더 삭제하기**
- 'txt_file' directory 삭제  
ERROR: 'txt_file'폴더는 빈파일이 아니라서 에러가 뜬다. 
<img src="/assets/images/delete_directory_error.png" alt="delete_directory_error">
SOLUTION: 'rmdir' 명령어 오른쪽에 **'/s'** 를 붙여주면 된다.
<img src="/assets/images/delete_directory.png" alt="delete_directory">

> **'test'폴더 삭제하기**
- 'test' directory 삭제  
'test' directory는 이제 비어있기 떄문에 'rmdir'명령어만 써도 된다. 
<img src="/assets/images/delete_empty_directory.png" alt="delete_empty_directory">
- directory 삭제확인
<img src="/assets/images/list_directory2.png" alt="list_directory2">

<br/><br/>
**결론: 접근이 용이한 GUI를 쓰는 대신, 어려운 명령어를 써야하는 CLI를 쓰는 이유는 속도가 빠르고 메모리 소비가 낮아서이다.**  

***NOTE:*** GUI(Graphical User Interface)란?  
아래와 같이 아이콘이나 이미지, 스크롤 등으로 파일 관리 및 기타 작업을 수행한다. 
<img src="/assets/images/GUI.png" alt="GUI">
