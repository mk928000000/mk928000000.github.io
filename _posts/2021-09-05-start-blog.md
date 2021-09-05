---
layout: post
title: "GIT BLOG 시작"
author: "mk928000000"
tags: mk928
excerpt_separator: <!--more-->
---

깃 블로그 시작! 
<br>
여기저기서 만드는 방법을 찾아보는데 볼때마다 막혀 정리했다.
<br><br>
###jekyll로 깃 블로그 만들기
<br>

> 사전준비 : <br><br> **. Ruby / git bash 설치<br> . gitHub 계정<br> . 에디터 (webStorm 사용)**

<sub>GitBlog 는 Git commit 으로 관리하지만 고치기 번거롭다. 로컬 서버를 띄워 바로 확인하기 위해 Ruby를 사용한다.</sub>

<br>

1. jekyll theme 으로 깃블로그 repo 생성
   * jekyll theme 선택 
   * jekyll theme repo 카피 repo 생성 &mdash; _(fork)_
   * 카피 repo 의 계정명 변경 &mdash; _(gitHub계정명.github.io )_
   * 깃블로그 저장소로 이용할 로컬 지정 _(c:\gitRepo 지정)_
   * git bash 로 깃블로그 저장소로 이동 &mdash; _(cd c:\gitRepo)_ 
   * 카피 repo의 clone 생성 &mdash; _(git clone 복사한 주소)_  
<hr>

2. jekyll 설치
   * cmd 로 깃블로그 저장소로 이동, jekyll 설치 &mdash; _(gem install jekyll bundler)_
   * cmd로 bundle 설치 &mdash; _(bundle install)_
   * theme 에 필요한 plugins 설치 &mdash; _(테마마다 다름. 내가 설치한 Tale theme 은 '4.참조' 확인)_
   * jekyll server 실행 &mdash; _(bundle exec jekyll serve)_
   * 확인되는 서버 주소를 인터넷 창에 입력하면 로컬 서버로 현재 깃블로그 확인이 가능하다. <br>바꾼 내용을 새로고침으로 바로바로 볼 수 있다.
<hr>
   
3. 깃블로그에 반영
   * 깃 푸쉬
   * 'gitHub계정명.github.io' 을 주소창에 치면 사용한 테마가 반영된 깃블로그가 확인된다.
<hr>

4. 참조
   * 사용 jekyll theme : [Tale 테마](https://jamstackthemes.dev/demo/theme/jekyll-tale-theme/) 
     1. <sub>깃블로그 저장소 \ GemFile</sub> 'gem "tale"' 을 추가하고 저장.
     2. <sub>_config.yml</sub> 'theme : tale' 추가
     3. <sub>cmd</sub> bundle install
     4. <sub>cmd</sub> bundle exec jekyll serve 
     5. 로컬 사이트로 접속해 테마가 반영되었는지 확인
     <br><br>
     
   * 설치 plugin : &mdash; (_config.yml 의 plugin 목록 설치)<br>
   
   {% highligh markdown %}
     <sub>- jekyll-feed</sub><br>
     <sub>- jekyll-paginate</sub><br>
     <sub>- jekyll-seo-tag</sub>   
     1. _config.yml 에 플러그인 목록 기재 확인
     2. <sub>cmd</sub> gem install jekyll-feed jekyll-paginate jekyll-seo-tag<br><br>
   {% endhighlight %}
     3. 
   * _config.yml
       1. baseurl 주석. <br><sub>'/' 말고 다른거하면 sass css 다 깨진다; 나중엔 포스트를 볼 수 없게되서 주석처리함</sub>
       2. url : 깃블로그 주소  "https://깃아이디.github.io/"
       3. authour 공란. <br><sub>재밌는게, tale 은 authour.xml 이나  tags.xml 이 없다. md 마다 상단 기재로 알아서 태그 등록되고 작성자로 써진다.</sub>
<hr>
       
5. 실행 때 오류
    * cannot load such file -- webrick (LoadError) 오류<br>
        1. <sub>cmd</sub> bundle add webrick
        2. <sub>cmd</sub> bundle exec jekyll serve 
        3. 로컬 사이트 확인
   
<br>

_The end_



