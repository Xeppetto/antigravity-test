# Domain Adaptation (도메인 적응)

## 1. 개요 (Overview)
Domain Adaptation(도메인 적응)은 특정 도메인(Source Domain)에서 학습된 모델을, 데이터 분포가 다른 새로운 도메인(Target Domain)에서도 잘 동작하도록 만드는 [전이 학습(Transfer Learning)](./TransferLearning.md)의 한 분야입니다.

## 2. 예시
- **Source Domain**: 낮에 찍은 자율주행 도로 이미지 (레이블 있음)
- **Target Domain**: 밤에 찍은 자율주행 도로 이미지 (레이블 없음)
- 낮 데이터로 학습한 모델은 밤 데이터에서 성능이 떨어지므로, 도메인 적응을 통해 밤 데이터에도 적응시킵니다.

## 3. 주요 기법
- **Adversarial Training**: [GAN](./GAN.md)의 아이디어를 활용하여, 특징 추출기(Feature Extractor)가 도메인(낮/밤)을 구분할 수 없는 공통된 특징을 추출하도록 학습합니다. (예: DANN)
- **Discrepancy Minimization**: 두 도메인 간의 분포 차이(MMD 등)를 최소화하도록 학습합니다.

## 4. 관련 문서
- [Transfer Learning](./TransferLearning.md)
- [GAN](./GAN.md)
