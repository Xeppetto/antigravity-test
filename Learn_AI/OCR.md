# OCR (Optical Character Recognition, 광학 문자 인식)

## 1. 개요 (Overview)
OCR(Optical Character Recognition, 광학 문자 인식)은 이미지나 스캔된 문서에서 텍스트를 감지하고, 이를 컴퓨터가 편집 가능한 텍스트 데이터로 변환하는 기술입니다.

## 2. 주요 단계 (Process)
1.  **Text Detection (문자 탐지)**: 이미지 내에서 글자가 있는 영역(Bounding Box)을 찾습니다. (예: EAST, CRAFT)
2.  **Text Recognition (문자 인식)**: 잘라낸 영역의 이미지를 텍스트로 변환합니다. (예: CRNN)

## 3. 주요 모델
- **CRNN (Convolutional Recurrent Neural Network)**: [CNN](./CNN.md)으로 특징을 추출하고, [RNN](./RNN.md)으로 시퀀스를 읽은 뒤, CTC Loss로 학습하는 구조입니다.
- **Transformer-based**: 최근에는 [Transformer](./Transformer.md)를 활용하여 더 높은 정확도를 달성하고 있습니다. (예: TrOCR)

## 4. 응용 분야
- 명함 인식, 영수증 스캔
- 번호판 인식 (LPR)
- 고문서 디지털화

## 5. 관련 문서
- [Computer Vision](./ComputerVision.md)
- [CNN](./CNN.md)
- [RNN](./RNN.md)
