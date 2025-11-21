# Evaluation Metrics (평가 지표)

## 1. 개요 (Overview)
Evaluation Metrics(평가 지표)는 [머신러닝(Machine Learning)](./MLBasic.md) 모델의 성능을 정량적으로 측정하는 기준입니다. 문제의 종류(분류, 회귀 등)에 따라 적절한 지표를 선택해야 합니다.

## 2. 분류(Classification) 지표

### 2.1. Accuracy (정확도)
전체 데이터 중 모델이 맞게 예측한 비율입니다. 데이터 불균형이 심할 경우 신뢰하기 어렵습니다.

### 2.2. Precision & Recall (정밀도와 재현율)
- **Precision**: 모델이 Positive라고 예측한 것 중 실제 Positive인 비율. (스팸 메일 분류에서 중요)
- **Recall**: 실제 Positive인 것 중 모델이 찾은 비율. (암 환자 진단에서 중요)

### 2.3. F1-Score
Precision과 Recall의 조화 평균입니다. 두 지표의 균형을 볼 때 사용합니다.

## 3. 회귀(Regression) 지표

### 3.1. MSE (Mean Squared Error)
예측값과 실제값 차이의 제곱의 평균입니다. 큰 오차에 민감합니다. [손실 함수](./DLBasic.md)로도 많이 사용됩니다.

### 3.2. MAE (Mean Absolute Error)
예측값과 실제값 차이의 절대값의 평균입니다. 직관적인 해석이 가능합니다.

## 4. 생성형 AI 및 기타 지표
- **FID (Fréchet Inception Distance)**: [Generative AI](./GenerativeAI.md)에서 생성된 이미지의 품질과 다양성을 평가합니다.
- **Linear Probing**: [Self-Supervised Learning](./SelfSL.md)에서 학습된 표현(Representation)의 품질을 평가하기 위해, 고정된 인코더 위에 선형 분류기를 붙여 성능을 측정합니다.
