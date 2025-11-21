# ViT (Vision Transformer)

## 1. 개요 (Overview)
ViT(Vision Transformer)는 2020년 구글이 발표한 모델로, [NLP](./NLP.md)에서 성공한 [Transformer](./Transformer.md) 아키텍처를 거의 수정 없이 이미지 처리에 적용하여 [CNN](./CNN.md)을 뛰어넘는 성능을 달성했습니다.

## 2. 작동 원리 (Mechanism)
1.  **Patch Partitioning**: 이미지를 고정된 크기(예: 16x16)의 패치(Patch)로 잘게 쪼갭니다. 각 패치를 NLP의 단어(Token)처럼 취급합니다.
2.  **Linear Embedding**: 각 패치를 1차원 벡터로 변환(Flatten)하고 선형 투영(Linear Projection)을 합니다.
3.  **Positional Embedding**: 패치의 위치 정보를 더해줍니다.
4.  **Transformer Encoder**: 패치들의 시퀀스를 Transformer에 넣어 전체 이미지의 문맥(Global Context)을 학습합니다.
5.  **Classification**: 특수 토큰([CLS])의 출력을 이용하여 이미지를 분류합니다.

## 3. 특징
- **Inductive Bias가 적음**: CNN처럼 지역적 특징(Locality)이나 평행 이동 불변성(Translation Invariance)을 가정하지 않습니다. 따라서 데이터가 적을 때는 CNN보다 성능이 낮지만, 대규모 데이터(JFT-300M 등)로 학습하면 CNN을 압도합니다.
- **[LeJEPA](./LeJEPA.md)** 등 최신 비전 모델의 백본(Backbone)으로 널리 사용됩니다.
