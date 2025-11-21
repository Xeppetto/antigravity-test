# Probability and Statistics (확률과 통계)

## 1. 개요 (Overview)
Probability(확률)와 Statistics(통계)는 불확실성을 다루는 수학적 도구입니다. [머신러닝(Machine Learning)](./MLBasic.md)은 데이터에 내재된 불확실성 속에서 패턴을 찾아내고 예측을 수행하므로, 확률과 통계는 필수적인 기초 지식입니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. Probability Distribution (확률 분포)
데이터가 어떻게 퍼져 있는지를 나타냅니다.
- **Gaussian Distribution (정규 분포)**: 자연계에서 가장 흔하게 관찰되는 분포. [SIGReg](./SIGReg.md)나 [VAE](./GenerativeAI.md) 등 많은 모델이 데이터가 정규 분포를 따른다고 가정합니다.
- **Bernoulli Distribution (베르누이 분포)**: 동전 던지기와 같이 두 가지 결과만 나오는 분포. 이진 분류(Binary Classification) 문제와 관련이 깊습니다.

### 2.2. Bayes' Theorem (베이즈 정리)
사전 확률(Prior)과 관측된 데이터(Likelihood)를 통해 사후 확률(Posterior)을 갱신하는 방법입니다. 베이지안 네트워크나 나이브 베이즈 분류기의 기초가 됩니다.

### 2.3. Expectation & Variance (기댓값과 분산)
- **Expectation (평균)**: 데이터의 중심 경향성.
- **Variance (분산)**: 데이터가 평균으로부터 얼마나 퍼져 있는지. [Regularization](./Regularization.md)에서 과적합을 막기 위해 분산을 제어하기도 합니다.

## 3. AI에서의 활용
- **Loss Function**: Cross-Entropy Loss는 확률 분포 간의 차이를 최소화하는 것과 같습니다 (Maximum Likelihood Estimation).
- **[Generative AI](./GenerativeAI.md)**: 데이터의 확률 분포를 학습하여 새로운 샘플을 생성합니다.
- **[EBM](./EBM.md)**: 확률 대신 에너지 함수를 사용하여 데이터의 분포를 모델링합니다.
