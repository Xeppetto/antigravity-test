# Backpropagation (역전파)

## 1. 개요 (Overview)
Backpropagation(역전파)은 신경망을 학습시키는 핵심 알고리즘입니다. 출력층에서 발생한 오차(Error)를 입력층 방향으로 거꾸로 전파(Propagate)시키면서, 각 뉴런의 가중치(Weight)가 오차에 얼마나 기여했는지를 계산하고 수정합니다.

## 2. 원리 (Mechanism)

### 2.1. Chain Rule (연쇄 법칙)
역전파는 [미적분(Calculus)](./Calculus.md)의 연쇄 법칙을 기반으로 합니다.
- 합성 함수의 미분은 각 구성 함수의 미분의 곱으로 표현할 수 있습니다.
- $\frac{\partial L}{\partial w} = \frac{\partial L}{\partial y} \cdot \frac{\partial y}{\partial z} \cdot \frac{\partial z}{\partial w}$
    - $L$: 손실(Loss)
    - $w$: 가중치(Weight)
    - $y$: 출력(Output)
    - $z$: 가중 합(Weighted Sum)

### 2.2. 과정 (Process)
1.  **Forward Pass**: 입력 데이터를 넣어 예측값을 구하고, 손실 함수를 통해 오차를 계산합니다.
2.  **Backward Pass**:
    - 출력층에서 시작하여 각 층의 기울기(Gradient)를 계산합니다.
    - 연쇄 법칙을 이용해 이전 층의 기울기를 구합니다.
3.  **Update**: 계산된 기울기와 학습률(Learning Rate)을 사용하여 가중치를 업데이트합니다. ($w_{new} = w_{old} - \eta \cdot \frac{\partial L}{\partial w}$)

## 3. 중요성
역전파 알고리즘 덕분에 수많은 층을 가진 깊은 신경망(Deep Neural Network)의 파라미터를 효율적으로 학습시킬 수 있게 되었습니다. 이는 딥러닝 혁명의 기반이 되었습니다.
