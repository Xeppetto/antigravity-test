# Meta Learning (메타 러닝)

## 1. 개요 (Overview)
Meta Learning(메타 러닝)은 "학습하는 법을 학습(Learning to Learn)"하는 기법입니다. 새로운 태스크를 마주했을 때, 적은 데이터와 적은 학습 횟수만으로도 빠르게 적응하는 모델을 만드는 것이 목표입니다.

## 2. 핵심 아이디어
일반적인 딥러닝이 "개와 고양이 분류하기"라는 특정 태스크를 잘하도록 학습한다면, 메타 러닝은 "새로운 분류 문제가 주어졌을 때 빠르게 학습하는 능력" 자체를 기릅니다.

## 3. 주요 접근법 (Approaches)

### 3.1. Metric-based (거리 기반)
데이터 간의 거리(유사도)를 학습합니다. 새로운 데이터가 들어오면 기존 데이터들과 비교하여 가장 가까운 클래스로 분류합니다.
- **Siamese Networks**, **Prototypical Networks**

### 3.2. Model-based (모델 기반)
적은 데이터로도 파라미터를 빠르게 업데이트할 수 있는 별도의 신경망(Memory 등)을 사용합니다.
- **MANN (Memory-Augmented Neural Networks)**

### 3.3. Optimization-based (최적화 기반)
모델의 초기 파라미터를 최적화하여, 몇 번의 학습(Gradient Step)만으로도 새로운 태스크에 빠르게 수렴하도록 만듭니다.
- **MAML (Model-Agnostic Meta-Learning)**: 가장 대표적인 알고리즘입니다.
