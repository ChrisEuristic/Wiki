#### 리스트를 numpy Array로 만들기
```python
array = numpy.array([2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31])
```

#### 동일한 값이 채워진 numpy Array 만들기
```python
array = numpy.full(6, 7)
```

#### 모든 값이 0인 Array 만들기 (기본적으로 float)
```python
array1 = numpy.full(6, 0)
# [0 0 0 0 0 0]

array2 = numpy.zeros(6, dtype=int)
# [0 0 0 0 0 0]
```

#### 모든 값이 1인 Array 만들기 (기본적으로 float)
```python
array1 = numpy.full(6, 1)
# [1 1 1 1 1 1]

array2 = numpy.ones(6, dtype=int)
# [1 1 1 1 1 1]
```

#### 랜덤한 값의 Array 만들기
```python
array = numpy.random.random(6)
```

#### 연속된 값이 담긴 Array 만들기
* arange(n, < m, step)
```python
array1 = numpy.arange(6)
# [0 1 2 3 4 5]

array1 = numpy.arange(2, 7)
# [2 3 4 5 6]

array1 = numpy.arange(3, 17, 3)
# [ 3  6  9 12 15]
```

#### 배열 산수
* numpy Array는 배열간 동일 index의 셈을 허용한다.
* numpy Array와 리터럴 상수 계산시 모든 배열의 요소와 계산된다.

#### where 함수 ( 필터 생성용 함수 )
* np.where(boolean Array) 형태로 작성하며, 배열의 모든 요소를 검사하여 True인 index를 numpyArray로 반환함.
```python
array = np.array([2,4,6,8,10])
array % 4 == 0
# [F, T, F, T, F]
filter = np.where(array % 4 == 0)
filter
# [1, 3]
array[filter]
# [4, 8]
```

#### 최대값, 최소값, 평균값, 중앙값, 표준편차, 분산
```python
array = np.array([14, 6, 13, 21, 23, 31, 9, 5])
array.max()
array.min()
array.mean()
np.median(array) # 사용법이 상이함
array.std() # 표준편차
array.var() # 분산
```
