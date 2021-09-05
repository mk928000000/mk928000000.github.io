---
layout: post
title: "FrontMatter 설명"
author: "mk928000000"
tags: Blog
excerpt_separator: <!--more-->
---


기본 포스트의 머릿글에 대한 설명이다.
<!--more-->
<br><br><br>
<hr>

## 기본 구성
> layout: post <br>
> title: "GIT BLOG 시작" <br>
> author: "mk928000000" <br>
> tags: Blog <Br>
> excerpt_separator: <!--more--> <br>

* layout : md 가 입을 layout 유형. post 라는 html 이 /_layouts 에 있다.
* title  : 포스트 제목
* author : 포스트 상단에 노출되는 작성자
* tags   : 내맘대로 태그를 추가할 수 있다. 여기 쓰면 홈페이지 상단 Tags 메뉴에 자동으로 분리되어 저장된다. 
* excerpt_seperator : `<!--more-->` 목록에서 어디까지 보여줄지 md 파일에서 지정하는 태그를 `<!--moer-->` 로 한다는 설정이다.

<br>
<br>

## 추가 구성
> sticky: true<br>
> hidden: true<br>
> comments: true

* sticky / hidden : 
<br> 어느 페이지를 가던 해당 포스트를 맨 상단에 공지처럼 붙인다는 표시이다. 
<br> hidden 을 true 로 둬야 페이지당 보이는 갯수를 무시하고 상단에 노출시킬 수 있으므로 둘은 세트로 볼 수 있다. 
<br> 가 제작자 설명인데 hidden 을 지워봐도 작동 잘된다. 세트라니까 같이 써야겠다.
* comment         : 댓글란을 표시한다. /_confing.yml 로 테마를 바꾸면 댓글스타일을 바꿀 수 있다고한다.

<br><br><br>
_The end_
