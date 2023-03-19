# 위젯별 기능, 속성

### 기본 구조 위젯
```dart
MateriallApp(); // 구글 스타일
CupertinoApp(); // iOS 스타일
```

### 기본 구조 위젯 프로퍼티

```dart
home: // 홈 화면
```

### 화면 분할 위젯 및 프로퍼티

```dart
/* 상단 앱바, 중단 바디, 하단 네비게이션바로 삼분할 */
Scaffold(
  appBar: ,
  body: ,
  bottomNavigationBar: ,
),
```

### 앱바 및 프로퍼티

```dart
AppBar(),
BottomAppBar(),
```

### 컨테이너 및 프로퍼티

```dart
Container(
  width: 100,
  height: 100,
  color: Colors.blue,
  margin: EdgeInsets.fromLTRB(left, top, right, bottom), // 각 방향 int값만큼 외측여백
  padding: EdgeInsets.all(int),                          // int값만큼 내측여백
  decoration: BoxDecoration(                             // 테두리 등 기타 박스 속성
    border: ,
    boxShadow: ,
    borderRadius: ,
  ),
),
```
