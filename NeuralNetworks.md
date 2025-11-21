# Neural Networks (신경망)

## 1. 개요 (Overview)
Neural Networks(신경망)는 인간 뇌의 신경 세포(Neuron)가 신호를 주고받는 방식을 모방한 수학적 모델입니다. [Deep Learning](./DLBasic.md)의 가장 기본이 되는 구성 요소이며, 입력 데이터로부터 패턴을 학습하여 예측이나 분류를 수행합니다.

## 2. 구조 (Structure)

### 2.1. Perceptron (퍼셉트론)
가장 단순한 형태의 신경망으로, 하나의 뉴런으로 구성됩니다.
- **입력(Input)**: $x_1, x_2, ..., x_n$
- **가중치(Weight)**: $w_1, w_2, ..., w_n$ (각 입력의 중요도)
- **편향(Bias)**: $b$ (뉴런의 활성화 임계값 조절)
- **출력(Output)**: $y = f(\sum (w_i x_i) + b)$ ($f$는 [활성화 함수](./ActivationFunctions.md))

### 2.2. MLP (Multi-Layer Perceptron)
여러 개의 퍼셉트론을 층(Layer)으로 쌓아 만든 구조입니다.
- **Input Layer (입력층)**: 데이터를 받아들이는 층.
- **Hidden Layer (은닉층)**: 입력층과 출력층 사이에 있는 층으로, 데이터의 복잡한 특징을 추출합니다. 은닉층이 2개 이상이면 "Deep" Neural Network라고 부릅니다.
- **Output Layer (출력층)**: 최종 결과를 출력하는 층.

## 3. 동작 원리 (Mechanism)

### 3.1. Forward Propagation (순전파)
입력 데이터가 각 층의 뉴런을 통과하며 가중치와 연산되고, 활성화 함수를 거쳐 출력층까지 전달되는 과정입니다.

### 3.2. Learning (학습)
순전파를 통해 얻은 예측값과 실제 정답 사이의 오차([Loss](./LossFunctions.md))를 줄이기 위해 가중치와 편향을 수정하는 과정입니다. 이 과정에서 [Backpropagation](./Backpropagation.md) 알고리즘이 사용됩니다.
