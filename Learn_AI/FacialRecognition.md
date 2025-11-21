# Facial Recognition (안면 인식)

## 1. 개요 (Overview)
Facial Recognition(안면 인식)은 이미지나 비디오에서 사람의 얼굴을 탐지하고, 누구인지 식별하거나 검증하는 [컴퓨터 비전](./ComputerVision.md) 기술입니다.

## 2. 주요 태스크
- **Face Detection**: 이미지에서 얼굴이 어디에 있는지 찾습니다.
- **Face Verification (1:1)**: "이 사람이 등록된 사용자가 맞는가?"를 확인합니다. (예: 스마트폰 잠금 해제)
- **Face Identification (1:N)**: "이 사람은 등록된 N명 중 누구인가?"를 식별합니다. (예: 범죄자 검색)

## 3. 주요 기술
- **FaceNet**: 얼굴 이미지를 유클리드 공간의 벡터로 변환(Embedding)합니다. 같은 사람의 얼굴은 가깝게, 다른 사람의 얼굴은 멀게 매핑합니다. (Triplet Loss 사용)
- **ArcFace**: 각도(Angle) 기반의 마진(Margin)을 사용하여 클래스 간의 분리력을 높인 손실 함수를 사용합니다.

## 4. 관련 문서
- [Computer Vision](./ComputerVision.md)
- [Deep Learning Basics](./DLBasic.md)
