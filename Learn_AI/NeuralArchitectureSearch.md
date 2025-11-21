# Neural Architecture Search (NAS, 신경망 구조 탐색)

## 1. 개요 (Overview)
Neural Architecture Search(NAS, 신경망 구조 탐색)는 인공지능 모델의 구조(Architecture)를 사람이 직접 설계하지 않고, AI가 자동으로 최적의 구조를 찾아내는 기술입니다. "AI를 만드는 AI"라고도 불립니다.

## 2. 왜 필요한가?
딥러닝 모델의 성능은 레이어의 수, 필터의 크기, 연결 방식 등 구조에 크게 의존합니다. 이를 전문가가 일일이 실험하며 설계하는 것은 많은 시간과 비용이 듭니다. NAS는 이를 자동화하여 효율성을 높입니다.

## 3. 주요 구성 요소
- **Search Space (탐색 공간)**: 탐색할 수 있는 모든 가능한 아키텍처의 집합입니다.
- **Search Strategy (탐색 전략)**: 탐색 공간에서 어떤 아키텍처를 시도해볼지 결정하는 알고리즘입니다.
    - **[Reinforcement Learning](./ReinforcementLearning.md)**: 아키텍처 생성을 에이전트의 행동으로 보고, 성능을 보상으로 하여 학습합니다.
    - **[Evolutionary Algorithms](./EvolutionaryAlgorithms.md)**: 우수한 아키텍처를 교배하고 변이시켜 진화시킵니다.
- **Performance Estimation Strategy (성능 평가 전략)**: 선택된 아키텍처의 성능을 빠르게 예측하거나 측정하는 방법입니다.

## 4. 대표적인 모델
- **AutoML**: 구글의 자동화된 머신러닝 플랫폼.
- **EfficientNet**: NAS를 통해 발견된 효율적인 이미지 분류 모델.

## 5. 관련 문서
- [Optimization Algorithms](./OptimizationAlgorithms.md)
- [Reinforcement Learning](./ReinforcementLearning.md)
