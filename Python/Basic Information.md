# 연산자

### 식별 연산자
* is : 두 객체의 주소를 비교하여 bool 타입으로 반환. (예: a is b)

### 멤버 연산자
* in : List, Tuple, Dict에서 특정 값의 존재 여부를 bool 타입으로 반환.
* not in : in의 부정.


<br><br>

# List

### 개요
* [요소1, 요소2, 요소3, ...] 형태로 구성.
* Static 언어들과 달리 각 요소의 타입을 일치시키지 않아도 유효함.
* 변수나 리터럴에 대괄호를 씌워 리스트로 변환 가능.


<br><br>

# Tuple

### 개요
* (요소1, 요소2, 요소3, ...) 형태로 구성.
* 요소를 수정할 수 없음. 요소의 요소, 즉 하위 레벨 요소는 수정 가능.
* 변수나 리터럴에 소괄호를 씌워 튜플로 변환 가능.
* 소괄호 내 여러 변수를 배치하여 튜플 값을 일반 변수로 언패킹 가능.


<br><br>

# Dictionary

### 개요
* {키1: 값1, 키2: 값2, ...} 형태로 구성.
* 키는 수정 불가, 값은 수정 가능.
* Dict 변수[신규 키] = 신규 값 형태로 데이터 추가 가능.


<br><br>

# 문자열 포매팅

### % 연산자 방식
* print("%d는 %.1f와 같다." %(a, b))

### format 메소드 방식
```python
print("나는 {}이고 {}입니다.".format("사람",str))

# 순서 정해주기
print("나는 {0}이고 {1}입니다.".format("사람",str))

# 세부 포매팅
print("나는 {0}이고 {1:.1f}입니다.".format("사람",10.532))
```

### f-String 방식
```python
print(f"나는 {job}이고 {name}라고 합니다. 키는 {height:.1f}cm 입니다.")
```



<br><br>

# Class
### 정의 방법
```python
class 클래스명:
  클래스변수 = 값
  
  def __init__(self, arg):
    self.클래스변수 = "생성자"
    print("생성자 호출")
    
  def 인스턴스메서드(self, arg):
    print("메소드 호출")
```

### 인스턴스 생성
```python
  인스턴스변수 = 클래스명(args)
```

### 클래스 변수(Static Var)
```python
class 클래스명:
  변수 = 0

  def 함수():
    클래스명.변수 = 값
    
클래스명.변수 = 값
```

### 클래스 메소드(Static Method)
```python
class 클래스명:
  @classmethod
  def 클래스메소드():
    print("@classmethod 데코레이터로 클래스 메소드를 정의")

클래스명.클래스메소드()
```

### Private 변수 정의 방법
```python
class 클래스명:
  def __init__(self, 변수):
    self.__변수 = 변수
```

### 상속
```python
class 부모클래스:
  def 부모함수():
  
class 자식클래스(부모클래스):
  def 자식함수():
    super().__init__(args)
    super().함수()

# super()의 리턴값이 부모클래스(is Not Instance).
```

### 다중상속
```python
class 자식클래스(부모클래스1, 부모클래스2):

인스턴스 = 자식클래스()
인스턴스.부모클래스1에선언된메소드()
인스턴스.부모클래스2에선언된메소드()
```

### 추상 클래스
* 추상 메소드를 가진 클래스
* import abstractmethod 필수
```python
from abc모듈 import ABC클래스, abstractmethod

class 클래스명(ABC클래스):
  @abstractmethod
  def 추상메소드():
    pass
```
