# VAE (Variational Autoencoder, 변이형 오토인코더)

## 1. 개요 (Overview)
VAE(Variational Autoencoder)는 데이터를 잠재 공간(Latent Space)의 확률 분포로 매핑하여 새로운 데이터를 생성하는 [생성형 AI](./GenerativeAI.md) 모델입니다.

## 2. 구조 (Structure)
- **Encoder**: 입력 데이터를 잠재 공간의 확률 분포(평균 $\mu$, 분산 $\sigma$)로 변환합니다.
- **Sampling**: 분포에서 잠재 벡터(Latent Vector, $z$)를 샘플링합니다.
- **Decoder**: 샘플링된 $z$를 다시 원래의 데이터로 복원합니다.

## 3. 특징
- **확률적 생성**: 같은 입력이라도 샘플링 과정 때문에 매번 조금씩 다른 결과가 나올 수 있습니다.
- **연속적인 잠재 공간**: 잠재 공간이 부드럽게 이어져 있어, 두 데이터 사이의 중간 형태(Interpolation)를 자연스럽게 생성할 수 있습니다.

## 4. GAN과의 비교
- [GAN](./GAN.md)보다 이미지가 다소 흐릿(Blurry)하게 생성되는 경향이 있지만, 학습이 훨씬 안정적이고 수학적 토대가 탄탄합니다.
