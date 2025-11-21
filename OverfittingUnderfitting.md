# Overfitting & Underfitting (과적합과 과소적합)

## 1. 개요 (Overview)
머신러닝 모델 학습의 목표는 학습 데이터뿐만 아니라, 보지 못한 새로운 데이터에 대해서도 잘 작동하는 **일반화(Generalization)** 능력을 갖추는 것입니다. 이 과정에서 발생할 수 있는 두 가지 대표적인 문제가 Overfitting(과적합)과 Underfitting(과소적합)입니다.

## 2. Overfitting (과적합)
모델이 학습 데이터에 너무 지나치게 맞춰져서, 새로운 데이터에 대한 예측 성능이 떨어지는 현상입니다. 마치 시험 공부를 할 때 문제집의 답을 달달 외워서, 조금만 변형된 문제가 나와도 틀리는 것과 같습니다.
- **원인**: 모델이 너무 복잡하거나, 학습 데이터가 너무 적거나, 학습을 너무 오래 시켰을 때 발생합니다.
- **증상**: 학습 데이터에 대한 오차(Training Loss)는 매우 낮지만, 검증 데이터에 대한 오차(Validation Loss)는 높습니다.
- **해결**: [Regularization](./Regularization.md), [Data Augmentation](./DataAugmentation.md), 더 많은 데이터 수집.

## 3. Underfitting (과소적합)
모델이 학습 데이터의 패턴조차 제대로 학습하지 못해서, 학습 데이터와 새로운 데이터 모두에서 성능이 낮은 현상입니다.
- **원인**: 모델이 너무 단순하거나, 학습 시간이 부족할 때 발생합니다.
- **증상**: Training Loss와 Validation Loss 모두 높습니다.
- **해결**: 더 복잡한 모델 사용, 학습 시간 늘리기.

## 4. Bias-Variance Tradeoff (편향-분산 트레이드오프)
- **Bias (편향)**: 모델의 예측값이 정답과 얼마나 떨어져 있는가. (높으면 Underfitting)
- **Variance (분산)**: 데이터가 바뀔 때 모델의 예측값이 얼마나 변동하는가. (높으면 Overfitting)
- 편향과 분산은 일반적으로 반비례 관계에 있어, 둘 사이의 적절한 균형을 찾는 것이 중요합니다.
