# Autoencoders (오토인코더)

## 1. 개요 (Overview)
Autoencoder는 입력 데이터를 압축(Encoding)했다가 다시 복원(Decoding)하는 과정을 통해 데이터의 효율적인 표현(Representation)을 학습하는 [비지도 학습](./MLBasic.md) 신경망입니다.

## 2. 구조 (Structure)
- **Encoder**: 입력 $x$를 저차원의 잠재 벡터 $z$로 압축합니다. ($z$는 Bottleneck이라고도 함)
- **Decoder**: 잠재 벡터 $z$를 다시 원래 차원의 $\hat{x}$로 복원합니다.
- **Loss Function**: 입력 $x$와 복원된 $\hat{x}$ 사이의 차이(Reconstruction Loss)를 최소화합니다.

## 3. 활용 (Applications)
- **Dimensionality Reduction**: PCA의 비선형 버전처럼 작동하여 데이터를 압축합니다.
- **Denoising**: 입력에 노이즈를 섞고 원본을 복원하도록 학습시키면, 노이즈 제거 모델이 됩니다 (Denoising Autoencoder).
- **Anomaly Detection**: 정상 데이터로만 학습시킨 후, 비정상 데이터가 들어오면 복원 오차가 커지는 것을 이용하여 이상치를 탐지합니다.
- **Generative Models**: [VAE](./VAE.md)의 기초가 됩니다.
