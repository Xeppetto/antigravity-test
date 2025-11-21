# GPT (Generative Pre-trained Transformer)

## 1. 개요 (Overview)
GPT는 OpenAI가 개발한 [NLP](./NLP.md) 모델로, [Transformer](./Transformer.md)의 **디코더(Decoder)** 부분만을 사용하여 텍스트를 생성하는 데 특화되어 있습니다.

## 2. 학습 방법 (Pre-training)
**Autoregressive Language Modeling (자기회귀 언어 모델링)**: 이전 단어들을 보고 다음 단어가 무엇일지 예측하도록 학습합니다. (예: "오늘 날씨가" -> "좋다")
- 단방향(Unidirectional) 문맥만 볼 수 있다는 한계가 있지만, 텍스트 생성 능력은 탁월합니다.

## 3. 발전 과정
- **GPT-1**: 전이 학습의 가능성 증명.
- **GPT-2**: 모델 크기를 키워 놀라운 작문 실력 과시 (Zero-shot learning 가능성).
- **GPT-3**: 1750억 개의 파라미터. 별도의 Fine-tuning 없이 프롬프트(Prompt)만으로 다양한 작업 수행 가능 (Few-shot learning).
- **GPT-4**: 멀티모달(이미지 인식 등) 능력 추가 및 추론 능력 대폭 향상.

## 4. ChatGPT
GPT-3.5/4를 기반으로 대화형 인터페이스와 [RLHF (Reinforcement Learning from Human Feedback)](./ReinforcementLearning.md)를 적용하여, 인간의 지시를 잘 따르고 안전하게 대화하도록 조정한 모델입니다.
