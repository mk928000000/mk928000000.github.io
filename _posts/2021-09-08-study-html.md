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

<br>

## #Table 구조 관련 태그
스크린 리더기와 같이 표를 음성으로 전달하기 위해 표를 해석하는데 도움이 되는 태그를 사용해야 한다.
* `<caption>`:표의 제목을 나타낸다
* `<thead>`  :제목행 그룹을 나타낸다
* `<tfoot>`  : 바닥행 그룹을 나타낸다
* `<tbody>`  : 본문행 그룹을 나타낸다
//부스트코스 예시
{% highlight js linenos %}
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
//부스트코스 예시
{% highlight js linenos %}
    <label for="name">이름</label>: <input type="text" id="name"><br>
    <label for="nickname">이름</label>: <input type="text" id="nickname"><br>
    <label for="address">이름</label>: <input type="text" id="address"><br>
{% endhighlight%}

<br><br><br>
_The end_
