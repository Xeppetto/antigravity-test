# Ensemble Learning (앙상블 학습)

## 1. 개요 (Overview)
Ensemble Learning(앙상블 학습)은 여러 개의 [머신러닝](./MLBasic.md) 모델을 결합하여, 단일 모델보다 더 좋은 성능을 내는 기법입니다. "집단 지성"을 활용하는 것과 같습니다.

## 2. 주요 기법 (Key Techniques)

### 2.1. Bagging (Bootstrap Aggregating)
데이터를 복원 추출(Bootstrap)하여 여러 개의 학습 데이터셋을 만들고, 각 데이터셋으로 모델을 학습시킨 후 결과를 합칩니다(Aggregating).
- **Random Forest**: 여러 개의 Decision Tree를 Bagging 방식으로 결합한 모델. 과적합을 잘 방지하고 성능이 뛰어납니다.

### 2.2. Boosting
여러 모델을 순차적으로 학습시키되, 이전 모델이 틀린 데이터에 가중치를 더 주어 다음 모델이 학습하게 합니다. 오답 노트에 집중하는 방식입니다.
- **XGBoost / LightGBM / CatBoost**: Gradient Boosting 알고리즘을 효율적으로 구현한 라이브러리들로, 정형 데이터(Tabular Data) 분석 대회(Kaggle 등)를 휩쓸고 있습니다.

### 2.3. Stacking
여러 모델의 예측값을 다시 새로운 모델(Meta-learner)의 입력으로 사용하여 최종 예측을 수행합니다.

## 3. 장점
단일 모델의 편향(Bias)이나 분산(Variance)을 줄여주어 일반화 성능이 매우 높습니다.
