---
layout: post
title: "< form:form > 태그 사용법"
author: "mk928000000"
tags: SPRING JAVA
excerpt_separator: <!--more-->
---


model 로 select나 radiobutton 형태의 목록을 전달하면서 동시에 formLform 태그와 @ModelAttribute 로 BoardVO 를 반영할 수 있는지 알아봤다.

<!--more-->
<br><br><br>
<hr>

## 결론
보내려는 목록은 model 로 보내고, 목록의 값은 <form:form> 으로 @ModelAttribute 와 연결된다.<br>
상세보기와 등록을 같은화면으로 돌리면서 동시에, 등록할 때 일일이 value 값을 가져오지 않고 submit 으로 처리할 수 있다. 야호!

<br>

### < form:form > 사용 준비
화면단에 form 태그연결
><%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %> <br>
 <%@ taglib prefix="form" uri="http://www.springframework.org/tags/form" %>

<br>

### 컨트롤러 - 상세페이지 이동
화면단에서 보드번호를 넘겨 받아서 상세보기할 내용을 model 에 담는다 
> http://localhost:8080/board/BoardView?bno=5505323

<br>

{% highlight js %}
 @RequestMapping("/board/BoardView")
 public void getView(
     ModelMap model,
      /// bno 는 BoardVO 의 멤버변수이므로 `@ModelAttribute` 가 BoardVo 에 세팅해준다.
     @ModelAttribute BoardVO bvo
     ) throws Exception{
      // 보내려던 목록들
       model.addAttribute("`boards`", service.getCommonCd("B_GBN"));
       model.addAttribute("`categoryList`", service.getCommonCd("S_GBN"));
    
      // 단순 '새글등록' 버튼으로 들어왔다면 bno 가 없으므로 게시글 정보가 없다.
      if(bvo.getBno() == null){
       model.addAttribute("action","/board/regist");
      }else {
       model.addAttribute("action","/board/modiView");
      // 보일 게시글 상세정보
       model.addAttribute("`boardVO`",service.getBoard(bvo).get(0));
    
      }
 }
{% endhighlight %}
<br>

### 상세화면.jsp
`form:form` 태그로 컨트롤러에서 모델이 담아 보낸 "boardVO" 를 연결한다. <br>
spring 버전에 따라 `modelAttribute` 와 `commandName` 중 모델과 연결할 수 있는 애가 달라진다. <br>
`from:form` 안에서는 `<form:~  path='vo컬럼멍'>` 으로 boardVO 의 컬럼 하나하나를 연결해준다.
{% highlight js %}
.
.
//model 에 담아보낸 boardVO 연결. `path` 에 멤버변수 이름을 설정해 멤버변수 하나하나와 연결시킬 수 있다.
<form:form modelAttribute="boardVO" action="${action}" method="post">
    <tbody>
        <tr><th>게시판</th>
            <td>
                <form:hidden path="bno"/>
                // ${boards}는 컨트롤러에서 모델로 보낸 목록들이다. boardVO 와 별개로 출력되나,
                // form:select path="bGbn" 으로 boardVO 의 멤버변수 bGbn 에 연결된다.
                <form:select path="bGbn">
                <c:forEach var="item" items="${boards}">
                    <form:option value="${item.detailCd}" label="${item.detailCdNm}" />
                </c:forEach>
                </form:select>
            </td>
        </tr>
        <tr><th>카테고리</th>
            <td>
                // ${categoryList}는 컨트롤러에서 모델로 보낸 목록들이다. boardVO 와 별개로 출력되나,
                // form:radiobutton path="sGbn" 으로 boardVO 의 멤버변수 sGbn 에 연결된다.
                <c:forEach var="item" items="${categoryList}">
                    <form:radiobutton path="sGbn" value="${item.detailCd}" label="${item.detailCdNm}"/>
                </c:forEach>
            </td>
        </tr>
        <tr>
            <th>제목</th>
             // `path` 로 boardVO 멤버변수와 연결
            <td><form:input path="title" placeholder="제목을 입력하세요"/> </td>
        </tr>
        <tr>
            <th colspan="2">내용</th>
        </tr>
        <tr>
            // `path` 로 boardVO 멤버변수와 연결
            <td colspan="2"><form:textarea path="content" placeholder="내용을 입력하세요"></form:textarea></td>
        </tr>
.
.
<div class="btnNavi">
    <input type="button" class="saveBtn" value="등록"/>
</div>
.
.
<script>
  $('.saveBtn').on('click',function(){
    var form = document.querySelector('#boardVO');
    form.submit();
  })
</script>
{% endhighlight %}

<br>

### 컨트롤러 - 게시글 등록/수정 
화면단에서 post 방식으로 submit 하면 `form:form` 내 `path`들이 컨트롤러단에서 `@ModelAttribute` 에서 담긴다. <br>
ajax 할때  id 와 value 로 일일이 가져와서 전송 파람을 만들어줬는데 컬럼이 많을경우 `form:form` 태그로 쉬워질 수 있다!

<br>

{% highlight js %}
@PostMapping(value="/board/regist")
public String registBoard(
    ModelMap model,
    @ModelAttribute("boardVO") BoardVO boardVO
    ) throws Exception {
        if(boardVO.getBno() == null) {
            service.insertBoard(boardVO);    
        }else {
            service.modiBoard(boardVO);
        }
    return "redirect:/board/SiteBorn";
}
{% endhighlight %}
<br>

<br><br><br>
_The end_
