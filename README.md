# 데이콘 신용카드 사기 거래 탐지 AI 경진대회

`비지도 학습`을 통해 신용카드 사기 거래를 탐지하는 AI 모델을 만들자

최종 순위: [208 / 740]

대회 링크: https://dacon.io/competitions/official/235930/overview/description

## 변수 선택

정상 데이터의 분포와 사기 데이터의 분포가 비슷한 경우 Class를 구분하기 힘들 것으로 판단하여 둘의 분포가 다른 변수만 선택했다

선택한 변수: 'V1', 'V3', 'V4', 'V5', 'V7', 'V9', 'V10', 'V11', 'V12', 'V14', 'V16', 'V17', 'V18'  

## 이상치 탐지 모델

이상치 탐지 모델로 `EllipticEnvelope`, `IsolationForest`, `OneClassSVM`, `multivariate_normal`, `LocalOutlierFactor`, `AutoEncoder`를 사용해봤고 `EllipticEnvelope` 모델의 성능이 가장 좋았다

- 하이퍼파라미터에 따른 `EllipticEnvelope` 모델의 성능

|assume_centered|support_fraction|contamination|valid fraud count|test fraud count|valid F1-score|public F1-score|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|False|0.6|0.001054|26|303|0.89275|0.92482|
|False|0.6|0.001089|26|309|0.89275|0.92769|
|False|0.6|0.001159|29|316|0.92365|0.92769|
|False|0.6|0.001179|30|318|0.91658|0.92769|
|False|0.6|0.001194|30|322|0.91658|0.93053|
|False|0.6|0.001229|30|323|0.91658|0.93053|
|False|0.6|0.001265|30|326|0.91658|0.92629|
|True |0.9|0.001054|25|293|0.88170|0.91217|
|True |0.9|0.001194|28|322|0.91371|0.92346|
|True |0.9|0.001335|30|333|0.91658|0.91932|
