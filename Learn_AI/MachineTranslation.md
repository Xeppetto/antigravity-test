# Machine Translation (기계 번역)

## 1. 개요 (Overview)
Machine Translation(기계 번역)은 컴퓨터를 이용하여 한 언어(Source Language)를 다른 언어(Target Language)로 자동 번역하는 기술입니다.

## 2. 발전 과정
1.  **RBMT (Rule-Based)**: 언어학적 규칙과 사전을 이용해 번역합니다. (어색함)
2.  **SMT (Statistical)**: 대량의 병렬 코퍼스(Parallel Corpus)에서 통계적 패턴을 학습합니다.
3.  **NMT (Neural Machine Translation)**: [딥러닝](./DLBasic.md) 모델을 사용하여 문장 전체의 문맥을 이해하고 번역합니다.
    - **Seq2Seq (Encoder-Decoder)**: [RNN](./RNN.md) 기반 구조. 긴 문장에서 성능 저하.
    - **[Attention Mechanism](./AttentionMechanism.md)**: 중요한 단어에 집중하여 긴 문장 문제 해결.
    - **[Transformer](./Transformer.md)**: 현재 NMT의 표준 아키텍처. (예: Google Translate, Papago, DeepL)

## 3. 평가 지표
- **BLEU (Bilingual Evaluation Understudy)**: 기계 번역 결과와 사람이 번역한 결과가 얼마나 유사한지 측정하는 점수입니다.

## 4. 관련 문서
- [NLP](./NLP.md)
- [RNN](./RNN.md)
- [Transformer](./Transformer.md)
