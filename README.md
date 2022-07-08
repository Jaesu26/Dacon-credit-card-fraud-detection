# Dacon-credit-card-fraud-detection
데이콘 신용카드 사기 거래 탐지 AI 경진대회

`비지도 학습`을 통해 신용카드 사기 거래를 탐지하는 AI 모델을 만들자

## 변수 선택

정상 데이터의 분포와 사기 데이터의 분포가 비슷한 경우 Class를 구분하기 힘들 것으로 판단하여 둘의 분포가 다른 변수만 선택했고 다음과 같다

선택한 변수: 'V1', 'V3', 'V4', 'V5', 'V7', 'V9', 'V10', 'V11', 'V12', 'V14', 'V16', 'V17', 'V18'  

## 이상치 탐지 모델

이상치 탐지 모델로 `EllipticEnvelope`, `IsolationForest`, `OneClassSVM`, `multivariate_normal`, `LocalOutlierFactor`, `AutoEncoder`를 사용해봤고 `EllipticEnvelope` 모델의 성능이 가장 좋았다

- 하이퍼파라미터에 따른 `EllipticEnvelope` 모델의 성능

|support_fraction|contamination|valid F1-score|public F1-score|
|:-:|:-:|:-:|:-:|
|0.6|0.001159|0.92365|0.92769|
|0.6|0.001194|0.91658|0.93053|
