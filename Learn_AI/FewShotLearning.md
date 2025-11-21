# Few-Shot Learning (퓨샷 학습)

## 1. 개요 (Overview)
Few-Shot Learning(퓨샷 학습)은 아주 적은 수(Few)의 예제(Shot)만으로 새로운 클래스를 학습하고 분류하는 기술입니다. 사람의 학습 능력(한두 번 보면 아는 것)을 모방합니다.

## 2. 용어 (Terminology)
- **N-way K-shot**: N개의 클래스에 대해 각각 K개의 예제가 주어지는 상황입니다. (예: 5-way 1-shot = 5개 클래스 각각 사진 1장씩)
- **Support Set**: 학습에 사용되는 소량의 예제 데이터셋.
- **Query Set**: 테스트할 데이터셋.

## 3. 주요 접근법
- **Metric-based**: 데이터 간의 거리(유사도)를 학습합니다. (예: Siamese Network, Prototypical Network)
- **Optimization-based**: 적은 데이터로도 빠르게 최적화될 수 있는 초기 파라미터를 찾습니다. (예: MAML)

## 4. 관련 문서
- [Zero-shot Learning](./ZeroShotLearning.md)
- [Meta Learning](./MetaLearning.md)
