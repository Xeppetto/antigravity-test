# Dimensionality Reduction (차원 축소)

## 1. 개요 (Overview)
Dimensionality Reduction(차원 축소)은 데이터의 중요한 정보(구조, 패턴)는 유지하면서 피처(Feature)의 개수(차원)를 줄이는 기법입니다.

## 2. 왜 필요한가? (Curse of Dimensionality)
차원이 늘어날수록 데이터 공간이 기하급수적으로 넓어져서 데이터가 희소(Sparse)해집니다. 이로 인해 거리 계산이 무의미해지고 모델 학습이 어려워지는 **차원의 저주** 문제를 해결하기 위해 사용합니다. 또한 시각화(2D, 3D)를 위해서도 필요합니다.

## 3. 주요 기법 (Key Techniques)

### 3.1. PCA (Principal Component Analysis, 주성분 분석)
데이터의 분산(Variance)을 가장 잘 보존하는 새로운 축(주성분)을 찾아 데이터를 투영합니다. [선형대수](./LinearAlgebra.md)의 고유값 분해를 이용합니다.

### 3.2. t-SNE (t-Distributed Stochastic Neighbor Embedding)
고차원 공간에서 가까운 이웃 간의 거리를 저차원에서도 유지하도록 확률 분포를 이용해 변환합니다. 주로 데이터 시각화에 사용됩니다.

### 3.3. UMAP (Uniform Manifold Approximation and Projection)
t-SNE보다 빠르고, 데이터의 전역적인 구조(Global Structure)도 더 잘 보존하는 최신 기법입니다.

## 4. 활용
- [Data Preprocessing](./DataPreprocessing.md) 단계에서 노이즈 제거 및 연산량 감소를 위해 사용됩니다.
