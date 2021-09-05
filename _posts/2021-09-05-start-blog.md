---
layout: post
title: "GIT BLOG 시작"
author: "mk928000000"
tags: blog
excerpt_separator: <!--more-->
---

깃 블로그 시작! 
<br>
여기저기서 만드는 방법을 찾아보는데 볼때마다 막혀 정리했다. <!--more-->
<br><br><br>

### 사전준비
{% highlight markdown %}
 . Ruby / git bash 설치 
 . gitHub 계정 
 . 에디터 (webStorm 사용)
{% endhighlight %}

<sub>GitBlog 는 Git commit 으로 관리하지만 고치기 번거롭다. 로컬 서버를 띄워 바로 확인하기 위해 Ruby를 사용한다.</sub>

<br><br>

## Jekyll theme 으로 깃블로그 repo 생성
   * jekyll theme 선택 
     > 사용 jekyll theme : [Tale 테마](https://jamstackthemes.dev/demo/theme/jekyll-tale-theme/)
     
<br>

   * jekyll theme repo 카피 repo 생성
     > ![fork](/assets/img/fork.PNG "fork 선택")
     > _[ 우측 상단 Fork 선택 ]_
     
<br>

   * 카피 repo 의 계정명 변경
     > ![repositoryName](/assets/img/repositoryName.PNG "repoName 변경")
     >_[ 상단 Settings > RepositoryName 변경 / `gitHub계정명`.github.io 형식]_

<br>

   * 카피 repo 의 주소 복사
     > ![copyAddr](/assets/img/copyAddr.PNG "repo 주소 복사")
     > _[ 카피 repo의 주소 복사. git bash 로 clone 생성에 사용한다. ]_

<br>

   * 깃블로그 저장소로 이용할 로컬 지정
     > `c:\GITrepo` 폴더 생성
     
<br>

   * git bash 로 깃블로그 저장소로 이동 
     > cd c:\GITrepo
           
<br>

   * 카피 repo의 clone 생성 
     > git clone `복사한 주소`
   
     <sub>위에서 복사한 카피 repo의 주소. 이제 c:\GITrepo 아래에 저장소 이름으로 폴더가 생기고 repo가 복사된다. </sub>

<br><br><br>   
## cmd로 Jekyll 설치
   * cmd 로 깃블로그 저장소로 이동
     > cd c:\GITrepo\ `저장소이름`
         
<br>

   * Jekyll 설치     
     > gem install jekyll bundler

<br>

   * Bundle 설치 
     > bundle install
    
<br>

   * jekyll server 실행 
     > bundle exec jekyll serve
     
<br>

   * 로컬서버 확인. 
     > ![localServer](/assets/img/localServer.PNG "로컬서버 체크")
     > _[ 변경 내용을 커밋없이 새로고침을 통해 바로바로 볼 수 있다. 근데 아직 테마 설치 전이라 못생기게 나올 것이다. ]_
    
<br>   
   * theme 설치 (Tale 테마기준)
     {% highlight markdown %}
          1. `c:\GITrepo\GemFile` 파일을 에디터로 열어 `gem "tale"` 을 추가하고 저장.
          2. `_config.yml` 파일에 `theme : tale` 추가
          3. bundle install
          4. bundle exec jekyll serve          
     {% endhighlight %}

<br>

   * plugins 설치 (Tale 테마기준)
     {% highlight markdown %}
         . jekyll-feed
         . jekyll-paginate
         . jekyll-seo-tag
     {% endhighlight %}

     <sub> 설치 테마와 플러그인은 테마마다 다르다. `_config.yml` 파일의 `plugins` 목록을 참조한다.</sub>

<br>

   * 테마 적용 확인
     > ![checkTheme](/assets/img/checkTheme.PNG "theme 반영 혹인")
     > _[ 로컬 주소로 들어가 테마가 반영되었는지 확인한다 ]_
<br><br><br>

## 깃블로그에 반영
<sub></sub>
   * 깃 푸쉬
     > git bash 로 푸쉬하거나 webStorm 으로 할 수 있다.
     > git bash 로 푸쉬
     > ![gitBashPush](/assets/img/gitPush.PNG "gitBash 로 푸쉬")
     > webStorm 으로 푸쉬
     > ![webStormPush](/assets/img/gitPush.PNG "gitBash 로 푸쉬")
   * 'gitHub계정명.github.io' 을 주소창에 치면 사용한 테마가 반영된 깃블로그가 확인된다.

<br><br><br>   
## 참조
   * 사용 jekyll theme : [Tale 테마](https://jamstackthemes.dev/demo/theme/jekyll-tale-theme/) 
     1. <sub>깃블로그 저장소 \ GemFile</sub> `gem "tale"` 을 추가하고 저장.
     2. <sub>_config.yml</sub> `theme : tale` 추가
     3. <sub>cmd</sub> bundle install
     4. <sub>cmd</sub> bundle exec jekyll serve 
     5. 로컬 사이트로 접속해 테마가 반영되었는지 확인
     <br><br>
     
   * 설치 plugin : &mdash; (_config.yml 의 plugin 목록 설치)<br>
     <sub>- jekyll-feed</sub><br>
     <sub>- jekyll-paginate</sub><br>
     <sub>- jekyll-seo-tag</sub>   
     1. _config.yml 에 플러그인 목록 기재 확인
     2. <sub>cmd</sub> gem install jekyll-feed jekyll-paginate jekyll-seo-tag<br><br>
   

   * _config.yml
       1. baseurl 주석. <br><sub>'/' 말고 다른거하면 sass css 다 깨진다; 나중엔 포스트를 볼 수 없게되서 주석처리함</sub>
       2. url : 깃블로그 주소  "https://깃아이디.github.io/"
       3. authour 공란. <br><sub>재밌는게, tale 은 authour.xml 이나  tags.xml 이 없다. md 마다 상단 기재로 알아서 태그 등록되고 작성자로 써진다.</sub>

<br><br>
### 실행 때 오류

   * cannot load such file -- webrick (LoadError) 오류<br>
       1. <sub>cmd</sub> bundle add webrick
       2. <sub>cmd</sub> bundle exec jekyll serve 
       3. 로컬 사이트 확인


<br><br>
_The end_



