# 시계열 데이터란
- 행과 행에 시간의 순서(흐름)가 있고,
- 🌟 행과 행의 시간간격이 동일한 데이터
- 행과 행 간의 시간의 순서 관계 존재


## 날짜 요소 뽑기

1. 날짜형으로 바꾸기
- **to_datetime**
    - format: 날짜형식을 파이썬에게 알려주는 것
    ```python
    pd.to_datetime(data['A'])
    ```
 2. df[’Date’].dt.날짜요소
    - 날짜 요소
        
        
        | date | YYYY-MM-DD(문자) |
        | --- | --- |
        | year | 연(4자리) |
        | month | 월(숫자) |
        | month_name() | 월(문자) |
        | day | 일(숫자) |
        | time | HH:MM:SS(문자) |
        | hour | 시(숫자) |
        | minute | 분(숫자) |
        | second | 초(숫자) |
        | quarter | 분기(숫자) |
        | day_name() | 요일이름(문자) |
        | week | 주차(숫자) |
        | days_in_month | 월 일수(숫자) |
## shift(), rolling, diff()



### shift()
- 시계열 데이터에서 시간의 흐름 전후로 정보를 이동시킬 때 사용

```python
df['A_lag''] = temp['A'].shift() # default = 1, 어제 데이터
df['A_lag''] = temp['A'].shift(1) # 그저께 데이터
df['A_lag''] = temp['A'].shift(-1) # 내일 데이터
```

### rolling : Moving Area
- 이평선(이동평균값)
- 시간의 흐름에 따라
- 사전 참고 오류(leakag) :
    - 행은 분석 단위, 내일의 매출액 예측(전날 판매 종료 된 후)
    - 1/ 7일 예측하는데 1/6일까지만 정보로 예측하는데 rolling을 하면 1/7 포함해서 평균을 구함

```python
df['A_MA3'] = temp['A'].rolling(3).mean() # 오늘부터 2일전 데이터 평균
df['A_MA3'] = temp['A'].rolling(3).max()
df['A_MA3'] = temp['A'].rolling(3, min_periods = 1).mean() # 값이 하나라도 있으면 만들어 내

```

### .diff() : 차분
- 특정 시접 데이터, 이전 시점 데이터와의 차이 구하기
- 차분 사용 이유?
    1. 주가보다는 등락폭을 예측하는 것이 더 쉬움(변화량을 예측하는 것이 더 쉬움)
    2. 시계열 데이터에서 차분을 사용한다 —> 나중에 찾아보기

```python
df['A_D1'] = temp['A'].diff() # 현재와 전 값을 차이
df['A_D2'] = temp['A'].diff(2) # 현재와 전전 값을 차이
```



<aside>
💡 시계열 데이터일 때 사용 가능 —— (날짜형 데이터가 아님)
sequential(시간의 흐름) 데이터에서만 사용

</aside>
