# Instance Segmentation (인스턴스 분할)

## 1. 개요 (Overview)
Instance Segmentation(인스턴스 분할)은 이미지 내의 객체를 픽셀 단위로 분류하되, 같은 클래스(예: 사람)라도 개별 객체(사람 A, 사람 B)를 서로 구별하는 기술입니다.

## 2. 비교
- **[Object Detection](./ObjectDetection.md)**: 객체의 위치를 박스(Bounding Box)로 찾고 분류합니다. (개체 구별 O, 픽셀 단위 X)
- **[Semantic Segmentation](./SemanticSegmentation.md)**: 픽셀 단위로 분류하지만, 같은 클래스의 개체를 구별하지 않습니다. (개체 구별 X, 픽셀 단위 O)
- **Instance Segmentation**: 위 두 가지를 결합했습니다. (개체 구별 O, 픽셀 단위 O)

## 3. 주요 모델
- **Mask R-CNN**: Faster R-CNN(객체 탐지)에 마스크 브랜치(Mask Branch)를 추가하여 픽셀 단위 마스크를 생성합니다.
- **YOLACT**: 실시간 처리가 가능한 1단계(One-stage) 모델입니다.

## 4. 관련 문서
- [Computer Vision](./ComputerVision.md)
- [Object Detection](./ObjectDetection.md)
- [Semantic Segmentation](./SemanticSegmentation.md)
