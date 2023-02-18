# 데이터 프레임
## 집계
```python
groupby('집계별', as_index = False)['컬럼'].함수()
```

## 변경
1. 열 추가, 삭제
```python
# 열 삭제
df.drop('변수', axis = 1, inplace = True)
# 열 추가
df['열 이름'] = df['A'] + df['B']
```

2. 값 변경
* 조건 변경(.loc)
```python
df.loc[조건, '컬럼'] = 값
df.loc[조건]['컬럼'] = 값

# np.where
np.where(조건, 참값, 거짓값)

# map
df['행'].map({'기존값': '변경값'})

# 숫자 -> 범주
pd.cut(['A'], bins, labels)
```

## 결합
* pd.concat(): 
    * 구조를 맞춰서 결합
    * 구조가 같은 경우 이내 위 붙이기
   ```python
   # join = 'inner', 'outer'
   # axis = 1(가로 합치기), axis = 0(가로 합치기)
   pd.concat([df1, df2], join = 'inner', axis = 1)


* merge():
    * 값을 맞춰서 결합
    * key 값을 설정하여 옆으로
    * 옆으로 합치는 경우만 존재 
   ```python
   # 'inner', 'outer', 'right', 'left
   pd.merge(df1, df2, how = 'inner', on = key)
