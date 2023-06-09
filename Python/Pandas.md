### 2차원 리스트, 2차원 numpy Array, pandas Series로 데이터프레임을 만들 수 있다.
```python
list = [['dongwook', 50, 86], ['sineui', 89, 31], ['ikjoong', 68, 91], ['yoonsoo', 88, 75]]
array = np.array(list)
list_of_series = [
    pd.Series(['dongwook', 50, 86]), 
    pd.Series(['sineui', 89, 31]), 
    pd.Series(['ikjoong', 68, 91]), 
    pd.Series(['yoonsoo', 88, 75])
]

# 아래 셋은 모두 동일합니다
df1 = pd.DataFrame(list)
df2 = pd.DataFrame(array)
df3 = pd.DataFrame(series)
```

### 딕셔너리의 리스트로 데이터프레임 만들기
```python
list = [
  {'name': 'A', 'age': 5, 'score': 50},
  {'name': 'B', 'age': 6, 'score': 60},
  {'name': 'C', 'age': 7, 'score': 70}
]
df = pd.DataFrame(list)
```

### 데이터 파일 읽어들이기
```python
pd.read_csv('./파일명.csv')

pd.read_csv('./파일명.csv', index_col = 0)
# 0번째 컬럼을 Row Index로 사용한다는 의미.
```

### 특정 Row, Column 추출하기
```python
data = df.loc[row, column]
# data는 특정 행, 열의 값을 갖는다.
# row와 column 변수의 자리엔 List나 Series 같은 배열이 올 수 있다.
# df.loc[row] 형태 또는 df.loc[row, :] 형태로 작성하면 row로 지정한 행 전체를 반환한다.
# df.loc[:, column] 형태로 column으로 지정한 열 전체를 가져올 수 있다. column은 2nd Arg이므로 1st 자리를 생략할 수 없다.
# 그러나 df['column']의 형태로 지정한 열 전체를 가져올 수 있다.
# 개별 행이나 열은 모두 Series 타입으로 반환된다.
```

### Pandas의 연산 개념
- numpy와 pandas 모두 산술연산자에 반복문으로 대응한다.<br>
- Series = Series + 1의 실제 의미는 아래 for문과 같다.
```python
Series_Temp = Series
for i in range(Series_Temp.size()):
    Series_Temp[i] += 1
Series = Series_Temp
```
- 이는 비교연산 결과 역시 동일하다.
- Series > 0은 boolean Series가 반환된다.

### iloc의 사용
- loc와 동일하게 작용하나 Args 값으로 index 값을 할당하여야 한다.
```python
df.iloc[1, 2]
# 1번 행, 2번 열의 값을 가져온다.

df.iloc[[0, 3], [4, 6]]
# 4번과 6번 열까지만 표시된 0번과 3번 행을 가져온다.
# return type은 DataFrame이 된다.

df.iloc[8: , 0:3]
# 0번부터 3번 열까지만 표시된, 8번부터 마지막 행까지를 가져온다.
```

### 데이터프레임의 값 수정
```python
df.loc[row,column] = new Value
# 특정 위치의 값을 수정

df.loc[row] = [new Value, new Value, new Value, ... ]
# 특정 행의 값 전체를 수정

df[column] = [new Value, new Value, new Value, ... ]
# 특정 열의 값 전체를 수정
```

### 데이터프레임의 값 추가
* 값 수정과 방법은 동일하나 row, column 자리에 newRow, newColumn이 들어가면 된다.

### 데이터프레임의 값 삭제
```python
df.drop(row, axis='index', inplace=True)
# row에 대입한 행이 삭제된다.
# row 값에 List를 넣어 여러 행을 삭제할 수 있다.
# inplace는 현재 객체에 반영할지, 새로운 객체를 만들어 반영할지를 결정한다. True시 현재 객체.

df.drop(column, axis='columns', inplace=False)
# column에 대입한 열이 삭제된다.
# column 값에 List를 넣어 여러 열을 삭제할 수 있다.
# inplace가 False이므로 원본 객체는 손상되지 않고 column 열이 삭제된 새로운 데이터프레임이 반환된다.
```

### 데이터프레임의 컬럼 Rename
```python
df.rename(columns={'oldName1': 'newName1', 'oldName2': 'newName2'}, inplace=True)
# inplace는 현재 객체에 반영할지, 새로운 객체를 만들어 반영할지를 결정한다. True시 현재 객체.
```

### 데이터프레임의 index column에 이름 붙이기
```python
df.index.name = 'newName'
```

### 데이터프레임의 특정 column을 index column으로 만들기(덮어쓰기)
```python
df['newColumn'] = df.index
# newColumn이라는 열을 생성하고 index column의 내용으로 초기화시킨다.

df.set_index('column', inplace=True)
# column이라는 열을 index column으로 만든다.
# 이 명령은 기존 index column이 있는 경우 old index column을 덮어써서 삭제시키기 때문에 반드시 old column을 다른 data column으로 만들어주고 실행해야 한다.
# inplace가 True이므로 원본 객체가 변경된다.
```

### 데이터프레임의 상단, 하단만 출력하기
```python
df.head(int rows)
# 0번부터 rows -1 행까지 출력된다.

df.tail(int rows)
# 마지막번부터 rows 개수만큼 행이 출력된다. (순서가 바뀌진 않는다.)
```

### 데이터프레임의 사이즈
```python
df.shape
# 변수임.
# (x, y) 형태의 값. 3차원 이상인 경우 (x, y, z, ...) 형태로 나타나게 됨.
```

### 데이터프레임의 컬럼 이름
```python
df.columns
# 변수임.
```

### 데이터프레임의 컬럼별 기본정보 확인
```python
df.info()
# 컬럼명, 값 개수, null여부, 데이터타입,
```

### 데이터프레임의 컬럼별 통계 확인
```python
df.describe()
# 컬럼별로 값 개수, 평균, 표준편차, 최소값, 25%, 중위값, 75%, 최대값
```

### 데이터프레임을 정렬하기
```python
df.sort_values()

'''키워드 변수'''
by = 'column'
# 정렬할 기준 column 지정

ascending = boolean
# True: 오름차순, False: 내림차순

inplace = boolean
# True: 현재 데이터프레임 수정, False: 새로운 데이터프레임 생성
```

### Series에서 중복을 제거하여 반환받기
```python
df['column'].unique()
# array([value1, value2, ...])
```

### Series에서 데이터 확인
```python
df['column'].describe()
# count: 값 개수
# unique: 값 이름들
# top: 가장 많이 나온 값
# freq: top의 개수
```

### Series에서 값의 종류와 개수 반환받기
```python
df['column'].value_counts()
# value1 value_count1
# value2 value_count2
# ... ...
```

### 그래프 그리기
```python
plt.plot(df)    # 선 그래프
plt.scatter()   # 산점도
plt.bar()       # 막대 그래프
plt.pie()       # 파이 그래프
plt.hist()      # 히스토그램
plt.title()     # 그래프의 제목 설정
plt.xlabel()    # x축 레이블 설정
plt.ylabel()    # y축 레이블 설정
plt.show()      # 그래프를 보여줌

아래는 흠.... 일반적인 문법은 아님

# 키워드 파라미터
# kind = 'line' 또는 'bar' 또는 'pie'
# kind = 'barh' (가로형 막대 그래프)
# y = 'column' 또는 y = ['column1', 'column2', ... ]
# stacked = boolean(T: 하나로 합쳐진 막대 그래프)
```
