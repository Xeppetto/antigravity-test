# Object Detection (객체 탐지)

## 1. 개요 (Overview)
Object Detection(객체 탐지)은 이미지 내에 존재하는 객체들의 **위치(Bounding Box)**를 찾고, 각 객체의 **종류(Class)**를 분류하는 [컴퓨터 비전](./ComputerVision.md) 기술입니다. 자율주행 자동차, CCTV 감시 시스템 등에 필수적입니다.

## 2. 주요 개념
- **Bounding Box**: 객체를 감싸는 직사각형 박스 (x, y, width, height).
- **IoU (Intersection over Union)**: 예측한 박스와 실제 정답 박스가 얼마나 겹치는지를 나타내는 지표.

## 3. 주요 모델 (Key Models)

### 3.1. Two-Stage Detectors
객체의 위치를 먼저 찾고(Region Proposal), 그 영역을 분류하는 방식입니다. 정확도가 높지만 속도가 느립니다.
- **R-CNN 계열**: R-CNN -> Fast R-CNN -> Faster R-CNN (End-to-End 학습 가능).

### 3.2. One-Stage Detectors
위치 탐색과 분류를 한 번에 수행합니다. 속도가 매우 빨라 실시간 처리에 적합합니다.
- **YOLO (You Only Look Once)**: 이미지를 그리드로 나누고 각 셀에서 바로 박스와 클래스를 예측합니다.
- **SSD (Single Shot MultiBox Detector)**: 다양한 크기의 Feature Map을 사용하여 여러 크기의 객체를 잘 탐지합니다.
