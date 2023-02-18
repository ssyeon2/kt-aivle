# 데이터 시각화
- 요약이 가능
- 정보 손실과 해석의 결과가 달라짐

## matplotlib
```
plt.plot('A', 'B', data = data) # 기본 라인 차트
plt.show()

# x축 값 기울기 조정
plt.xticks(rotation = 30)
plt.xlabel('-')
plt.ylabel('_')
plt.title()
```

### subplot
- 여러 그래프 나눠서 그리기
```
plt.subplot()
plt.plot()
```


## seabron
- 추가 패키지
### density plot
```
sns.kdeplot(x='A', data=data)
plt.show()
```
### barplot
```
sns.barplot(x='A', y='B', data = data)
plt.show()
```
