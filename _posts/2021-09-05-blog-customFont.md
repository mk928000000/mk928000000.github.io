---
layout: post
title: "블로그 폰트 바꾸기"
author: "mk928000000"
tags: Blog
excerpt_separator: <!--more-->
---




영어기준이라 기본 한글폰트가 심히 못생겼다. 깃블로그에 네이버의 D2Coding 폰트를 적용했다.
<br>
 _[2021-09-08] : Segoe UI 로 폰트를 바꿨다. 윈도우 GIT HUB 기본 폰트로 나오는데 이게 훨씬 보기 좋다._
<!--more-->
<br><br><br>
<hr>

## 폰트 파일 준비 
무료 배포중인 네이버의 d2coding 폰트를 준비했다. [네이버 폰트 배포](https://github.com/naver/d2codingfont) <br>
버전을 선택해 압축파일을 풀어 설치하면 `C:/Windows/Fonts` 경로에 `D2Coding.ttf` 파일이 생긴다.<br> 
로컬 깃블로그 폴더의 `/assets` 아래에 `fonts` 폴더를 만들어 ttf 파일을 넣어준다.<br><br><br>

## /main.scss 에 폰트 추가
/assets/main.scss 에 폰트 정보를 추가한다.

{% highlight javascript %}
 @font-face {
 font-family: 'D2Coding';
 src: url('`/assets/fonts`/D2Coding-Ver1.3.2-20180524-ligature.ttf') format('truetype');
 font-weight: normal;
 font-style: normal;
}
{% endhighlight %}

* font-family 는 컴퓨터에 설치된 해당 폰트의 이름이다.
* src 는 폰트파일이 있는 경로이고, format 은 확장자이다. ttf 는 'truetype' 으로 넣는다.
<br><br><br>

## /_variables.scss 에 폰트명 추가

main.scss 에 등록한 font-family 이름을 각 폰트 변수들의 맨 앞자리에 넣어준다.
<br>
이제 블로그의 모든 사항이 D2Coding 으로 나올 것이다!

<br><br><br>
_The end_