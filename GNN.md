# GNN (Graph Neural Networks, 그래프 신경망)

## 1. 개요 (Overview)
GNN(Graph Neural Networks)은 그래프(Graph) 구조의 데이터를 처리하기 위한 [딥러닝](./DLBasic.md) 모델입니다. 소셜 네트워크, 분자 구조, 추천 시스템 등 객체 간의 관계가 중요한 데이터에 사용됩니다.

## 2. 그래프 데이터 구조
- **Node (정점)**: 객체 (예: 사용자, 원자).
- **Edge (간선)**: 객체 간의 관계 (예: 친구 관계, 화학 결합).

## 3. 작동 원리 (Mechanism)
**Message Passing (메시지 전달)**: 각 노드는 연결된 이웃 노드들로부터 정보를 받아 자신의 상태(Embedding)를 업데이트합니다. 이 과정을 반복하면 그래프 전체의 구조적 정보를 학습할 수 있습니다.

## 4. 주요 모델 (Key Models)
- **GCN (Graph Convolutional Networks)**: 이미지의 합성곱(Convolution) 개념을 그래프에 적용하여, 이웃 노드의 정보를 집계(Aggregation)합니다.
- **GAT (Graph Attention Networks)**: [Attention Mechanism](./AttentionMechanism.md)을 적용하여, 이웃 노드 중 더 중요한 노드에 가중치를 두어 정보를 받아들입니다.

## 5. 활용 분야
- **신약 개발**: 분자 구조의 속성 예측.
- **소셜 네트워크 분석**: 가짜 계정 탐지, 커뮤니티 발견.
- **추천 시스템**: 사용자와 아이템 간의 상호작용 그래프 분석.
