# Continual Learning (지속 학습)

## 1. 개요 (Overview)
Continual Learning(지속 학습)은 모델이 새로운 데이터를 학습할 때, 이전에 학습한 지식을 잊어버리지 않고(Catastrophic Forgetting 방지) 계속해서 지식을 축적해 나가는 학습 방법입니다. Lifelong Learning이라고도 합니다.

## 2. 문제점: Catastrophic Forgetting (파국적 망각)
일반적인 신경망은 새로운 태스크(Task B)를 학습하면, 기존 태스크(Task A)에 최적화된 가중치가 덮어씌워져 Task A의 성능이 급격히 떨어지는 현상이 발생합니다.

## 3. 주요 접근법
- **Replay (리플레이)**: 이전 데이터의 일부를 저장해두거나(Experience Replay), 생성 모델로 이전 데이터를 생성하여(Generative Replay) 새로운 데이터와 함께 학습합니다.
- **Regularization (정규화)**: 이전 태스크에서 중요했던 가중치가 크게 변하지 않도록 손실 함수에 제약(Penalty)을 둡니다. (예: EWC)
- **Parameter Isolation (파라미터 격리)**: 태스크별로 모델의 다른 부분을 사용하거나, 용량을 늘려갑니다.

## 4. 관련 문서
- [Transfer Learning](./TransferLearning.md)
- [Regularization](./Regularization.md)
