# Loss Functions (손실 함수)

## 1. 개요 (Overview)
Loss Function(손실 함수)은 모델의 예측값($\hat{y}$)과 실제 정답($y$)이 얼마나 차이가 나는지를 수치로 나타내는 함수입니다. Cost Function(비용 함수)이라고도 부릅니다. 학습의 목표는 이 손실 함수의 값을 최소화하는 것입니다.

## 2. 회귀(Regression) 문제용

### 2.1. MSE (Mean Squared Error)
- **수식**: $\frac{1}{n} \sum (y - \hat{y})^2$
- **특징**: 오차를 제곱하므로 큰 오차에 더 큰 페널티를 줍니다. 미분이 가능하여 최적화에 유리합니다.

### 2.2. MAE (Mean Absolute Error)
- **수식**: $\frac{1}{n} \sum |y - \hat{y}|$
- **특징**: 오차의 절댓값을 평균 냅니다. 이상치(Outlier)에 덜 민감합니다.

## 3. 분류(Classification) 문제용

### 3.1. Binary Cross-Entropy
- **용도**: 이진 분류 (예: 스팸/햄, 개/고양이)
- **특징**: 예측 확률과 실제 레이블(0 또는 1) 사이의 정보량 차이를 계산합니다.

### 3.2. Categorical Cross-Entropy
- **용도**: 다중 클래스 분류 (예: 손글씨 숫자 0~9 인식)
- **특징**: [Softmax](./ActivationFunctions.md) 출력값과 원-핫 인코딩된 정답 사이의 오차를 계산합니다.

## 4. 기타
- **Contrastive Loss**: [Contrastive Learning](./ContrastiveLearning.md)에서 사용되며, 비슷한 데이터는 가깝게, 다른 데이터는 멀게 만듭니다.
