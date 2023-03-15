# EL 태그
### JSTL 기본 라이브러리 Import

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

### 객체(자바빈즈) 선언

```jsp
<jsp:useBean id="객체 변수명" class="패키지.클래스명" scope="내장객체 영역" />
```

### JSTL 변수 선언

```jsp
<c:set var="변수명" value="값" scope="내장객체 영역" />
```

### JSTL 변수 삭제

```jsp
<c:remove var="변수명" scope="내장객체 영역" />
```

### if문

```jsp
<c:if test="조건" var="boolean 조건의 결과값"/>
  <!-- 실행문 -->
</c:if>
```

### choose문, when문, otherwise문

```jsp
<c:choose> <!-- switch문 -->
  <c:when test="조건1"><!-- case문 --></c:when>
  <c:when test="조건2"><!-- case문 --></c:when>
  <c:when test="조건3"><!-- case문 --></c:when>
  <c:otherwise><!-- default문 --></c:otherwise>
</c:choose>
```

### forEach문 - 기본형

```jsp
/* for 기본형 */
<c:forEach begin="시작값" end="끝값" step="스텝" var="변수명" varStatus="본 For문 객체명">
  <!-- 실행문 -->
</c:forEach>
```

### forEach문 - 향상형, varStatus Property

```jsp
/* forEach형 */
<c:forEach items="배열, 리스트, 맵 객체" var="변수명" varStatus="본 For문 객체명">
  <!-- 실행문 -->
  varStatus객체명.count    <!-- 반복횟수를 셈 -->
  varStatus객체명.index    <!-- 현재 인덱스를 반환 -->
  varStatus객체명.current  <!-- 현재 값을 반환 -->
  varStatus객체명.first    <!-- 첫 반복문인가? true : false -->
  varStatus객체명.last     <!-- 마지막 반복문인가? true : false -->
</c:forEach>
```

### forTokens문

```jsp
<!-- 문자열을 구분자로 분리, 배열로 만들어 for loop -->
<c:forTokens items="문자열" delims="문자열 구분자" var="변수명">
  <!-- 실행문 -->
</c:forTokens>
```

<br /><br />

# JSTL 국제화(Formatting)
### JSTL 국제화(Formatting) 라이브러리 Import

```jsp
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>
```

### 숫자 포맷 설정

```jsp
<!-- 콤마 있는 숫자 -->
<fmt:formatNumber value="값" />

<!-- 콤마 없는 숫자 -->
<fmt:formatNumber value="값" groupingUsed="false"/>

<!-- 통화 포맷 -->
<fmt:formatNumber value="값" type="currency" var="포맷팅 후 값 변수"/>

<!-- 백분율 포맷 -->
<fmt:formatNumber value="값" type="percent" var="포맷팅 후 값 변수"/>
```

### String to int

```jsp
<!-- 실수 표현 -->
<fmt:parseNumber value="문자열 값" pattern="000,000,000.00" var="변환된 숫자값"/>

<!-- 정수 표현 -->
<fmt:parseNumber value="문자열 값" integerOnly="true" var="변환된 숫자값"/>
```

### 날짜 / 시간 포맷 설정

```jsp
<!-- 0000년 0월 0일 0요일 -->
<fmt:formatDate value="날짜값(Date 객체)" type="date" dateStyle="full" />

<!-- 00. 0. 0. -->
<fmt:formatDate value="날짜값(Date 객체)" type="date" dateStyle="short" />

<!-- 0000년 0월 0일 -->
<fmt:formatDate value="날짜값(Date 객체)" type="date" dateStyle="long" />

<!-- 0000. 0. 0. -->
<fmt:formatDate value="날짜값(Date 객체)" type="date" dateStyle="default" />

<!-- AM/PM 0시 0분 0초 Locale -->
<fmt:formatDate value="날짜값(Date 객체)" type="time" timeStyle="full" />

<!-- AM/PM 0:0 -->
<fmt:formatDate value="날짜값(Date 객체)" type="time" timeStyle="short" />

<!-- AM/PM 0시 0분 0초 Locale(약어) -->
<fmt:formatDate value="날짜값(Date 객체)" type="time" timeStyle="long" />

<!-- AM/PM 0:0:0 -->
<fmt:formatDate value="날짜값(Date 객체)" type="time" timeStyle="default" />

<!-- 0000년 0월 0일 0요일 AM/PM 0시 0분 0초 Locale -->
<fmt:formatDate value="날짜값(Date 객체)" type="both" dateStyle="full" timeStyle="full"/><br />

<!-- 0000-00-00 00:00:00 -->
<fmt:formatDate value="날짜값(Date 객체)" type="both" pattern="yyyy-MM-dd hh:mm:ss" />
```

### 타임존 설정

```jsp
<!-- 그리니치 표준시 -->
<fmt:timeZone value="GMT"></fmt:timeZone>

<!-- 서울 -->
<fmt:timeZone value="Asia/seoul"></fmt:timeZone>

<!-- 시카고 -->
<fmt:timeZone value="America/Chicago"></fmt:timeZone>
```

### 로케일 설정

```jsp
<fmt:setLocale value="언어_국가코드" />
<!--
  한국 : ko_kr
  일본 : ja_JP
  미국 : en_US
-->
```
