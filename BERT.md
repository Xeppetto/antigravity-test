# BERT (Bidirectional Encoder Representations from Transformers)

## 1. 개요 (Overview)
BERT는 2018년 구글이 발표한 [NLP](./NLP.md) 모델로, [Transformer](./Transformer.md)의 **인코더(Encoder)** 부분만을 사용하여 문맥을 양방향(Bidirectional)으로 이해하는 데 특화되어 있습니다.

## 2. 학습 방법 (Pre-training)

### 2.1. MLM (Masked Language Modeling)
문장의 중간에 있는 단어를 가리고(Mask), 앞뒤 문맥을 보고 그 단어가 무엇인지 맞추도록 학습합니다. 이를 통해 단어의 양방향 문맥을 파악합니다. (예: "나는 [MASK]를 먹었다" -> "사과")

### 2.2. NSP (Next Sentence Prediction)
두 문장이 주어졌을 때, 두 번째 문장이 첫 번째 문장의 바로 다음에 오는 문장인지 아닌지를 맞춥니다. 문장 간의 관계를 학습합니다.

## 3. 활용 (Fine-tuning)
사전 학습된 BERT 위에 얇은 레이어를 하나 추가하여, 분류, 질의응답(QA), 개체명 인식(NER) 등 다양한 다운스트림 태스크에 적용(Fine-tuning)합니다. NLP의 성능을 한 단계 끌어올린 기념비적인 모델입니다.
