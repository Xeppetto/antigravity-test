# Attention Mechanism (어텐션 메커니즘)

## 1. 개요 (Overview)
Attention Mechanism(어텐션 메커니즘)은 인간이 무언가를 볼 때 중요한 부분에 집중(Attention)하는 것과 유사하게, 모델이 입력 데이터의 특정 부분에 가중치를 더 두어 정보를 처리하는 기법입니다.

## 2. 등장 배경
기존의 [RNN](./RNN.md) 기반 번역 모델(Seq2Seq)은 긴 문장을 하나의 고정된 벡터로 압축해야 했기 때문에 정보 손실이 발생했습니다. Attention은 "번역할 때마다 원문(Source)의 어느 단어를 봐야 하는가?"라는 질문에서 출발했습니다.

## 3. 작동 원리 (Mechanism)
1.  **Query (Q)**: 현재 시점에서 필요한 정보가 무엇인지 묻는 벡터.
2.  **Key (K)**: 정보의 색인(Index) 역할을 하는 벡터.
3.  **Value (V)**: 실제 정보가 담긴 벡터.
4.  **Score 계산**: Q와 K의 유사도(내적 등)를 계산하여 Attention Score를 구합니다.
5.  **Weighted Sum**: Score를 확률로 변환(Softmax)한 후, V와 곱해서 더합니다. 즉, 중요한 정보(V)를 더 많이 가져옵니다.

## 4. Self-Attention
[Transformer](./Transformer.md)의 핵심 기술로, Q, K, V가 모두 같은 입력에서 나옵니다. 문장 내의 단어들이 서로 어떤 관계가 있는지(문맥)를 파악하는 데 탁월합니다.
