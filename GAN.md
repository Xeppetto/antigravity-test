# GAN (Generative Adversarial Networks, 생성적 적대 신경망)

## 1. 개요 (Overview)
GAN(Generative Adversarial Networks)은 두 개의 신경망이 서로 경쟁(Adversarial)하면서 학습하는 [생성형 AI](./GenerativeAI.md) 모델입니다. 2014년 Ian Goodfellow가 제안했습니다.

## 2. 구조 (Structure)
경찰과 위조지폐범의 관계에 비유됩니다.
- **Generator (생성자)**: 랜덤 노이즈로부터 가짜 데이터를 생성하여 Discriminator를 속이려 합니다. (위조지폐범)
- **Discriminator (판별자)**: 입력된 데이터가 진짜인지 가짜인지 구별하려 합니다. (경찰)

## 3. 학습 과정 (Training Process)
1.  Discriminator는 진짜 데이터와 Generator가 만든 가짜 데이터를 구분하도록 학습합니다.
2.  Generator는 Discriminator가 "진짜"라고 판별하도록 더 정교한 가짜 데이터를 만들도록 학습합니다.
3.  이 과정을 반복하면 Generator는 진짜와 구별할 수 없는 데이터를 생성하게 됩니다.

## 4. 장단점
- **장점**: 매우 선명하고 사실적인 이미지를 생성할 수 있습니다.
- **단점**: 학습이 매우 불안정하고(Mode Collapse), 수렴하기 어렵습니다.

## 5. 주요 변형
- **DCGAN**: CNN 구조를 도입하여 안정성을 높임.
- **StyleGAN**: 고해상도 얼굴 생성에 탁월한 성능.
- **CycleGAN**: 짝이 없는(Unpaired) 이미지 간의 스타일 변환 (예: 말 $\leftrightarrow$ 얼룩말).
