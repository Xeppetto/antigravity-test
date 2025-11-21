# Calculus (미적분)

## 1. 개요 (Overview)
Calculus(미적분), 특히 미분(Differentiation)은 [머신러닝(Machine Learning)](./MLBasic.md) 모델을 학습시키는 [최적화(Optimization)](./OptimizationAlgorithms.md) 과정의 핵심입니다. 변화율을 이해하고 함수의 최솟값이나 최댓값을 찾는 데 사용됩니다.

## 2. 핵심 개념 (Key Concepts)

### 2.1. Derivative (미분/도함수)
함수의 입력이 아주 조금 변할 때 출력이 얼마나 변하는지(기울기)를 나타냅니다.

### 2.2. Partial Derivative (편미분)
변수가 여러 개인 함수에서, 하나의 변수만 변화시키고 나머지는 상수로 취급하여 미분하는 것입니다. 딥러닝 모델은 수백만 개의 파라미터를 가지므로, 각 파라미터에 대해 편미분을 수행합니다.

### 2.3. Gradient (기울기 벡터)
모든 변수에 대한 편미분 값을 모은 벡터입니다. 함수의 값이 가장 가파르게 증가하는 방향을 가리킵니다.

### 2.4. Chain Rule (연쇄 법칙)
합성 함수의 미분을 계산하는 공식입니다. 딥러닝의 **역전파(Backpropagation)** 알고리즘은 이 연쇄 법칙을 반복적으로 적용하여 입력층까지의 기울기를 계산하는 과정입니다.

## 3. AI에서의 활용
- **Gradient Descent (경사 하강법)**: 손실 함수(Loss Function)의 기울기(Gradient)를 구하고, 그 반대 방향으로 파라미터를 업데이트하여 손실을 최소화합니다.
- **Activation Function**: ReLU, Sigmoid 등의 활성화 함수도 미분 가능해야(혹은 구간별로 미분 가능해야) 역전파가 가능합니다.
