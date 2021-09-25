---
layout: single
title: "[CMD] CLI로 내 파일 관리하는 법"
date: 2021-08-12
categories: [TIL, CMD]
tags: [TIL, CMD]
toc: true
comments: true
---


**CLI** 즉, **Command Line Interface**는 Windows OS 기준 **'명령 프롬프트(cmd)'** 창을 열어서 명령어를 통해 컴퓨터내 폴더와 파일을 관리해주는 것이다.

오늘의 주제는 cmd를 이용해 폴더와 파일을 생성, 삭제, 이동하는 법에 대해 알아보자. 


## 1. cmd창 열기 

![open_cmd](https://user-images.githubusercontent.com/88199458/132727207-d2312bbe-5d86-4e6e-b283-9919a724bf8d.png)


## 2. directory(folder) 생성하기
> **desktop에 'test'폴더 만들기**
- desktop으로 이동  
TIP: directory를 생성하기 위해서 먼저 <u>directory를 생성할 위치로</u> 이동해주는 것이 좋다.  
![cd_directory](https://user-images.githubusercontent.com/88199458/132727169-3ace5213-1754-438b-a0b8-02f005240dca.png)
- 'test' directory 생성  
![create_directory](https://user-images.githubusercontent.com/88199458/132727172-4c69c401-88e3-48e2-8e96-6c69c777a715.png)
- directory 생성확인  
명령어 'dir'을 입력해주면 current working directory에 있는 <u>하위 directory들을 목록화시켜준다.</u> 
![list_directory](https://user-images.githubusercontent.com/88199458/132727198-d76f89d3-c882-4029-98a9-475c32d0e630.png)

> **'test'폴더안에 'txt_file'폴더 생성하기**  
- 'txt_file' directory 생성  
![create_nested_directory](https://user-images.githubusercontent.com/88199458/132727179-cfabde5b-55a6-4937-914a-666970231a2c.png)


## 3. file 생성하기
> **'test'폴더안에 'jihyun.txt'파일 만들기**
- 'jihyun.txt' 생성
![create_empty_file](https://user-images.githubusercontent.com/88199458/132727176-4874521d-934c-4f5b-97e3-3d2b451d13f4.png)

> **'jihyun.txt'파일 안에 인삿말 넣기**
- text 입력
![enter_text_in_file](https://user-images.githubusercontent.com/88199458/132727189-491f1667-a137-46e4-9186-7b346557297c.png)


## 4. file 이동하기
> **'jihyun.txt'파일을 'txt_file'폴더로 이동하기**
- file 이동
![move_file](https://user-images.githubusercontent.com/88199458/132727203-bf644c6a-b942-40ed-b650-917c9dbed3ff.png)


## 5. directory 삭제하기
> **'txt_file'폴더 삭제하기**
- 'txt_file' directory 삭제  
ERROR: 'txt_file'폴더는 빈파일이 아니라서 에러가 뜬다. 
![delete_directory_error](https://user-images.githubusercontent.com/88199458/132727185-2cd86cc6-b856-489f-9fe4-b275d37da97d.png)
SOLUTION: 'rmdir' 명령어 오른쪽에 **'/s'** 를 붙여주면 된다.
![delete_directory](https://user-images.githubusercontent.com/88199458/132727182-221306d7-92e6-4acc-a5e9-84f1e92af219.png)

> **'test'폴더 삭제하기**
- 'test' directory 삭제  
'test' directory는 이제 비어있기 떄문에 'rmdir'명령어만 써도 된다. 
![delete_empty_directory](https://user-images.githubusercontent.com/88199458/132727187-9b0639b6-6176-457e-b63f-3920b8059730.png)
- directory 삭제확인
![list_directory2](https://user-images.githubusercontent.com/88199458/132727200-ff52f2eb-1ef5-4d39-8767-d41f11ad340d.png)

<br/><br/>
**결론: 접근이 용이한 GUI를 쓰는 대신, 어려운 명령어를 써야하는 CLI를 쓰는 이유는 속도가 빠르고 메모리 소비가 낮아서이다.**  

***NOTE:*** GUI(Graphical User Interface)란?  
아래와 같이 아이콘이나 이미지, 스크롤 등으로 파일 관리 및 기타 작업을 수행한다. 
![GUI](https://user-images.githubusercontent.com/88199458/132727191-2e5e93a0-5401-4b4f-ab19-81f0ea319383.png)
