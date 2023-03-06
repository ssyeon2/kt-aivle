# VIF
* 다른 독립 변수에 의존적인 변수를 제거
* 주성분 분석(변수 추출)
* 범주형 데이터 사용 불가
* 제거한 경우 결정계수가 유지되면 변수를 제거하는 것으로 결정
* 회귀 모델



## VIF 확인
* $VIF_i=\frac{1}{1-R_i^2}$
* x, y 분리 후 확인
* vif 가 4에서 5를 넘어가는 경우 다중공선성이 있다고 판단
* Min-Max Scaling 한 후에 확인

```python

from statsmodels.stats.outliers_influence import variance_inflation_factor
vif = pd.DataFrame()
vif['feature'] = x.columns
vif['vif_factor'] = [variance_inflation_factor(x.values, i) for i in range(x.shape[1])

# VIF 기준으로 정렬

vif.sort_values(by='vif_factor', ascending=False, inplace=True)
vif.reset_index(drop=True, inplace=True)
```
