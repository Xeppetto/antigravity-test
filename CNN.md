# CNN (Convolutional Neural Networks, 합성곱 신경망)

## 1. 개요 (Overview)
CNN(Convolutional Neural Networks)은 주로 이미지나 비디오 같은 격자(Grid) 구조의 데이터를 처리하는 데 특화된 [딥러닝](./DLBasic.md) 아키텍처입니다. 인간의 시각 피질 구조에서 영감을 받아 만들어졌습니다.

## 2. 핵심 구조 (Key Components)

### 2.1. Convolutional Layer (합성곱 층)
- **Filter (Kernel)**: 작은 크기(예: 3x3)의 필터가 이미지를 훑고 지나가며(Sliding Window) 특징을 추출합니다.
- **Feature Map**: 필터를 통과하여 나온 결과물로, 이미지의 특정 패턴(Edge, Texture 등)이 어디에 있는지를 나타냅니다.
- **Parameter Sharing**: 같은 필터를 이미지 전체에 사용하므로 학습할 파라미터 수가 획기적으로 줄어듭니다.

### 2.2. Pooling Layer (풀링 층)
- Feature Map의 크기를 줄여서(Downsampling) 연산량을 감소시키고, 이미지의 작은 위치 변화에 강건(Invariant)하게 만듭니다.
- **Max Pooling**: 특정 영역에서 가장 큰 값만 남깁니다.

### 2.3. Fully Connected Layer (전결합 층)
- 추출된 특징들을 1차원으로 펼쳐서(Flatten) 최종 분류를 수행합니다.

## 3. 주요 모델
- **LeNet-5 (1998)**: 최초의 성공적인 CNN, 손글씨 숫자 인식.
- **AlexNet (2012)**: 딥러닝 붐을 일으킨 모델, GPU 활용.
- **VGGNet**: 3x3 필터만 사용하여 깊이를 깊게 쌓음.
- **ResNet**: Residual Connection(잔차 연결)을 도입하여 100층 이상의 깊은 망 학습 가능.
