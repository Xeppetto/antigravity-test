# Semantic Segmentation (의미론적 분할)

## 1. 개요 (Overview)
Semantic Segmentation(의미론적 분할)은 이미지의 **모든 픽셀(Pixel)**을 특정 클래스(예: 사람, 도로, 자동차)로 분류하는 [컴퓨터 비전](./ComputerVision.md) 기술입니다. [Object Detection](./ObjectDetection.md)보다 훨씬 정밀한 이해가 가능합니다.

## 2. 특징
- 같은 클래스에 속하는 객체들은 구분하지 않습니다. (예: 사람 A와 사람 B를 모두 '사람'으로 표시)
- **Instance Segmentation**: 같은 클래스라도 개별 객체를 구분하는 더 발전된 기술입니다. (Mask R-CNN 등)

## 3. 주요 모델 (Key Models)

### 3.1. FCN (Fully Convolutional Networks)
기존 CNN의 마지막 전결합 층(Fully Connected Layer)을 합성곱 층으로 대체하여, 이미지의 위치 정보를 유지하면서 픽셀 단위 예측을 가능하게 했습니다.

### 3.2. U-Net
의료 영상 분석을 위해 제안된 모델입니다.
- **Encoder (Contracting Path)**: 이미지의 특징을 추출하며 크기를 줄입니다.
- **Decoder (Expanding Path)**: 줄어든 크기를 다시 원래대로 복원합니다.
- **Skip Connection**: 인코더의 고해상도 특징을 디코더로 직접 전달하여 경계선을 정교하게 복원합니다. 'U'자 모양의 구조를 가집니다.

### 3.3. DeepLab
Atrous Convolution(Dilated Convolution)을 사용하여 해상도 손실 없이 넓은 영역(Receptive Field)을 보게 하여 성능을 높였습니다.
