---
layout: post
title: "HTML 공부 기록"
author: "mk928000000"
tags: HTML
excerpt_separator: <!--more-->
---


부스트코스 기초강의 보면서 몰랐던 부분들에 대한 기록이다.
<!--more-->
<br><br><br>
<hr>

## #두칸 이상의 띄어쓰기
기본 HTML 은 두칸 이상의 띄어쓰기는 모두 한 칸의 띄어쓰기로 처리한다.
<br><br>

## #태그의 의미
태그는 단순 표시가 아니라 의미를 가져 웹 검색 시에 해당 의미가 반영 된다.<br>
예를 들어, `<h~ >`코드로 쓰인 글은 title 을 의미해 검색 시 반영이 되나, 단순히 글자 크기를 키우고 두껍게 한 글은 글자 꾸밈으로, 
검색 시 우선순위에서 떨어진다. 
<br><br>

## #`<dl>`태그
dl(definition/description list) 태그이다. 용어와 그에 대한 정의를 표현할때 사용한다.<br>
`<dl>`코드는 `용어<dt>`와 `설명<dd>`이 하나의 세트로 항목을 이루고 리스트가 이루어지는 구조이다. <br>

{% highlight markdown %}
//부스트코스 예시
    <dl>
        <dt>리플리 증후군</dt>
        <dd>허구의 세계를 진실이라 믿고 거짓된 말과 행동을 상습적으로 반복하는 반사회적 성격장애를 뜻하는 용어</dd>
        <dt>피그말리온 효과</dt>
        <dd>타인의 기대나 관심으로 인하여 능률이 오르거나 결과가 좋아지는 현상</dd>
        <dt>언더독 효과</dt>
        <dd>사람들이 약자라고 믿는 주체를 응원하게 되는 현상</dd>
    </dl>
{% endhighlight %}

<br><br>

## #Table 구조 관련 태그
스크린 리더기와 같이 표를 음성으로 전달하기 위해 표를 해석하는데 도움이 되는 태그를 사용해야 한다.
* `<caption>`:표의 제목을 나타낸다
* `<thead>`  :제목행 그룹을 나타낸다
* `<tfoot>`  : 바닥행 그룹을 나타낸다
* `<tbody>`  : 본문행 그룹을 나타낸다

{% highlight js linenos %}
//부스트코스 예시
<table>
    <caption>Monthly Savings</caption>
    <thead>
        <tr>
            <th>Monday</th>
            <th>Saving</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>January</td>
            <td>$100</td>
        </tr>
        <tr>
            <td>Feburary</td>
            <td>$70</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>SUM</td>
            <td>$170</td>
        </tr>
    </tfoot>
</table>
{% endhighlight%}

<br>

## #Table 구조 관련 태그
`<label>` 은 form 요소의 이름과 form 요소를 명시적으로 연결시켜준다. <br>
스크린 리더기로 접근 시 해당 form 요소에 접근하면 `<label>` 을 함께 읽어준다. 중요하므로 써주는게 좋다.

{% highlight js linenos %}
//부스트코스 예시
    <label for="name">이름</label>: <input type="text" id="name"><br>
    <label for="nickname">이름</label>: <input type="text" id="nickname"><br>
    <label for="address">이름</label>: <input type="text" id="address"><br>
{% endhighlight%}


<br><br>

## #시멘틱 요소
HTML5 에서 새로 생긴 요소들이다. 의미를 갖고 구획을 나눈다.<br>
`<div>` 태그와의 차이점은 `<div>` 태그는 의미를 갖지 않는다. <br>
* `<article>`    : 주 내용이 들어감 (보통 section으로 속에서 나뉨.)
* `<aside>`      : 옆에 달린 작은 설명 같은 것.
* `<figcaption>` : 자막 같은 용도. `<figure>` 태그를 설명하는 역할.
* `<figure>`     : 그림, 사진, 도표 등을 명시.
* `<footer>`     : 문서의 바닥.
* `<header>`     : 문서의 머릿말.
* `<main>`       : 본문, <article> 태그와 속성이 비슷.
* `<mark>`       : 본문 중 특정 부분을 강조.
* `<nav>`        : 문서 내의 링크들의 조합. 
* `<section>`    : 문서의 특정 구역.
* `<time>`       : 시간을 강조. 

<br><br>

## #시멘틱 마크업
시멘틱 마크업은 컴퓨터가 html 요소의 `의미`를 잘 이해하도록 돕는 것이다.
<br>
#### HTML 태그 VS 시멘틱 마크업
HTML 태그쪽은 단순 텍스트 꾸미기 이지만, 시멘틱 마크업은 `의미`를 갖는다.
{% highlight markdown %}
//HTML 텍스트               //시멘틱 마크업
<b>굵은</b>           vs    <strong>중요한</strong>
<i>기울어진</i>        vs   <em>강조하는</em>
<u>밑줄친</u>         vs    <ins>새롭게 추가된</ins>
<s>중간선이 있는</s>   vs    <del>삭제된</del>
{% endhighlight%}

<br><br>

## #`블록레벨`요소와 `인라인레벨`요소
`블록레벨`은 <br> 
부모 요소의 가로 영역에 맞게 꽉 채워져 표현되는 요소이다. <br>
한 줄 꽉차게 박스를 만들어 양옆으로 다른 요소가 배치되지 않는다. 다만, `<h1~h6>`과 `<p>`는 내부요소로 Phrasing Content 는 허용한다  <br>
블록레벨 요소는 일반적인 모든 요소라고 볼 수 있다.
<br><br>
`인라인레벨`은 <br> 
하나의 라인 안에서 자신의 내용만큼 박스를 만드는 요소이다.<br>
양 옆으로 다른 인라인요소들이 배치될 수 있다. <br>
인라인 레벨 요소는 `블록레벨 요소의 자식` 으로 분류된다. 때문에, `자손으로 블록레벨 요소를 포함할 수 없다`. 다만, `<a>` 태그는 가능하다.
 `"span, i, img, em, strong, a ...."`
<br><br>

<br><br><br>
_The end_
