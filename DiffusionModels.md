# Diffusion Models (디퓨전 모델)

## 1. 개요 (Overview)
Diffusion Models(디퓨전 모델)은 데이터에 노이즈를 조금씩 추가하여 완전한 노이즈로 만든 후, 다시 노이즈를 제거해가는 과정을 학습하여 데이터를 생성하는 최신 [생성형 AI](./GenerativeAI.md) 기술입니다. DALL-E 3, Stable Diffusion, Midjourney 등의 기반이 되는 모델입니다.

## 2. 작동 원리 (Mechanism)

### 2.1. Forward Process (Diffusion Process)
원본 이미지에 점진적으로 가우시안 노이즈를 추가하여, 결국에는 완전한 무작위 노이즈로 만듭니다.

### 2.2. Reverse Process (Denoising)
노이즈가 섞인 이미지에서 노이즈가 무엇인지 예측하고 제거하는 신경망(주로 U-Net)을 학습시킵니다. 완전한 노이즈에서 시작하여 이 과정을 반복하면 깨끗한 이미지를 얻을 수 있습니다.

## 3. 장단점
- **장점**: [GAN](./GAN.md)보다 학습이 안정적이며, 생성된 이미지의 다양성과 품질이 매우 뛰어납니다.
- **단점**: 노이즈를 제거하는 과정을 수십~수천 번 반복해야 하므로 생성 속도가 느립니다. (최근에는 이를 가속화하는 연구가 활발합니다.)

## 4. 주요 모델
- **DDPM (Denoising Diffusion Probabilistic Models)**: 디퓨전 모델의 기초를 정립.
- **Stable Diffusion (Latent Diffusion)**: 픽셀 공간이 아닌 잠재 공간(Latent Space)에서 디퓨전을 수행하여 속도와 효율성을 획기적으로 높임.
