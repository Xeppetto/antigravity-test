# Linear Algebra (선형대수)

## 1. 개요 (Overview)
Linear Algebra(선형대수)는 벡터(Vector)와 행렬(Matrix)을 다루는 수학의 한 분야로, [머신러닝(Machine Learning)](./MLBasic.md)과 [딥러닝(Deep Learning)](./DLBasic.md)의 언어라고 할 수 있습니다. 데이터의 표현, 변환, 그리고 모델의 연산 과정 대부분이 선형대수를 기반으로 합니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. Vector & Matrix (벡터와 행렬)
- **Scalar (스칼라)**: 하나의 숫자 (0차원 텐서).
- **Vector (벡터)**: 숫자의 배열 (1차원 텐서). 데이터 포인트 하나를 나타낼 때 주로 사용됩니다.
- **Matrix (행렬)**: 숫자의 2차원 배열 (2차원 텐서). 데이터셋 전체나 가중치(Weight)를 나타낼 때 사용됩니다.
- **Tensor (텐서)**: 3차원 이상의 배열로 확장된 개념. (예: RGB 이미지 = 3차원 텐서)

### 2.2. Matrix Operations (행렬 연산)
- **Dot Product (내적)**: 두 벡터의 유사도를 측정하거나, 신경망의 가중치 합을 계산할 때 사용됩니다.
- **Matrix Multiplication (행렬 곱)**: 신경망의 층(Layer)을 통과할 때 입력 데이터와 가중치 행렬 간의 연산에 사용됩니다.

### 2.3. Eigenvalues & Eigenvectors (고유값과 고유벡터)
행렬에 의한 변환 후에도 방향이 변하지 않는 벡터와 그 크기 변화량을 의미합니다. [PCA (Principal Component Analysis)](./MLBasic.md)와 같은 차원 축소 기법의 핵심 원리입니다.

## 3. AI에서의 활용
- **데이터 표현**: 이미지는 픽셀 값들의 행렬로, 텍스트는 임베딩 벡터로 표현됩니다.
- **모델 학습**: 역전파(Backpropagation) 과정에서 기울기(Gradient)를 계산하고 파라미터를 업데이트할 때 행렬 연산이 필수적입니다.
- **[SIGReg](./SIGReg.md)**: 공분산 행렬(Covariance Matrix)의 성질을 이용하여 임베딩의 붕괴를 방지합니다.
