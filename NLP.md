# Natural Language Processing (NLP, 자연어 처리)

## 1. 개요 (Overview)
Natural Language Processing(NLP, 자연어 처리)은 컴퓨터가 인간의 언어(Natural Language)를 이해하고, 생성하고, 조작할 수 있도록 하는 [인공지능](./ArtificialIntelligence.md)의 한 분야입니다. 번역, 챗봇, 감성 분석 등 다양한 애플리케이션의 기반이 됩니다.

## 2. 주요 과제 (Key Tasks)
- **Text Classification (텍스트 분류)**: 스팸 메일 필터링, 뉴스 카테고리 분류, 감성 분석(긍정/부정).
- **Machine Translation (기계 번역)**: 구글 번역, 파파고와 같이 한 언어를 다른 언어로 변환.
- **Named Entity Recognition (NER, 개체명 인식)**: 텍스트에서 인물, 장소, 조직 등 고유 명사를 찾아 분류.
- **Question Answering (QA, 질의응답)**: 질문에 대한 답을 텍스트에서 찾아주거나 생성.
- **Text Generation (텍스트 생성)**: 소설 쓰기, 기사 요약, 대화 생성.

## 3. 핵심 기술의 발전
1.  **Rule-based**: 문법 규칙을 사람이 직접 코딩 (확장성 낮음).
2.  **Statistical (통계적)**: 단어의 빈도수(TF-IDF) 등을 기반으로 확률적 접근.
3.  **Word Embedding (단어 임베딩)**: Word2Vec, GloVe 등 단어를 벡터로 변환하여 의미를 포착.
4.  **RNN / LSTM**: 순차 데이터 처리에 강점이 있어 NLP의 표준이 됨.
5.  **[Transformer](./Transformer.md)**: [Attention](./AttentionMechanism.md) 메커니즘을 통해 병렬 처리와 장거리 의존성 문제를 해결하며 NLP를 혁신. 현재의 [BERT](./BERT.md), [GPT](./GPT.md)의 기반.
