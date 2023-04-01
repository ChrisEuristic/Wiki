#### 2차원 리스트, 2차원 numpy Array, pandas Series로 데이터프레임을 만들 수 있다.
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

#### 딕셔너리의 리스트로 데이터프레임 만들기
```python
list = [
  {'name': 'A', 'age': 5, 'score': 50},
  {'name': 'B', 'age': 6, 'score': 60},
  {'name': 'C', 'age': 7, 'score': 70}
]
df = pd.DataFrame(list)
```
