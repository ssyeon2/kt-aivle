# 데이터 분석
**CRISP-DM**
- 업무 이해(문제 정의, 정보 도출) -> 데이터 이해 -> 모델링을 위한 데이터 구조 준비(전처리) -> 모델링 -> 평가(학습, 검증) -> 배포
- 예측을 통해 비즈니스 문제 해결(수익, 가치 창출)

# 데이터 전처리
### ① 데이터 구조 만들기 - 데이터 분석
- 행 : 분석단위
- 열 : 정보, 변수

### ② 모델링을 위한 전처리 - ML, DL 모델링
- 모든 셀은 값이 있어야
- 모든 값은 숫자
- 필요치, 숫자의 범위 맞춰야

Nan : Not a number
NA : Not Available


## 1. 단변량 분석
|  | 그래프 | 통계량 |
| --- | --- | --- |
| 양적 데이터 | 히스토그램, kdeplot, 박스플롯 | max, min, mean, std, 사분위수 |
| 질적 데이터 | bar plot | 범주별 빈도수, 비율 |

## 2. 이변량 분석
|  | 시각화 | 수치화 | 시각화 | 수치화 |
| --- | --- | --- | --- | --- |
| 연속형 | scatter | 상과분석 | barplt, histogram, Density plot |     |
| 범주형 | sns.barplot | t검정, 분산분석 | mosaic | 카이제곱검정 |
