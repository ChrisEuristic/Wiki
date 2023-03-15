# EL 태그
### JSTL Import

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
