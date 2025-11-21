# Multi-Agent Reinforcement Learning (MARL, 다중 에이전트 강화 학습)

## 1. 개요 (Overview)
Multi-Agent Reinforcement Learning(MARL)은 여러 개의 에이전트(Agent)가 공통의 환경(Environment)에서 상호작용하며 학습하는 [강화 학습](./ReinforcementLearning.md) 분야입니다.

## 2. 특징 및 챌린지
- **Non-stationarity (비정상성)**: 내가 가만히 있어도 다른 에이전트가 학습하고 행동을 바꾸면 환경이 변한 것처럼 느껴집니다. 이로 인해 학습이 불안정해집니다.
- **Cooperation vs Competition**: 에이전트들이 서로 협력해야 할 수도(예: 축구 로봇), 경쟁해야 할 수도(예: 스타크래프트) 있습니다.

## 3. 주요 알고리즘
- **Independent Q-Learning (IQL)**: 다른 에이전트를 환경의 일부로 취급하고 각자 학습합니다.
- **QMIX / VDN**: 협력적 환경에서 각 에이전트의 가치 함수를 결합하여 전체의 가치를 최대화합니다.
- **MADDPG**: Actor-Critic 기반으로, 학습할 때는 다른 에이전트의 정보를 모두 보고(Centralized Training), 실행할 때는 각자 행동(Decentralized Execution)합니다.

## 4. 관련 문서
- [Reinforcement Learning](./ReinforcementLearning.md)
- [Swarm Intelligence](./SwarmIntelligence.md)
