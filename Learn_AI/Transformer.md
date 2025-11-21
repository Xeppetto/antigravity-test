# Transformer (트랜스포머)

## 1. 개요 (Overview)

### Transformer란?
Transformer는 2017년 Google이 발표한 "**Attention Is All You Need**" 논문에서 제안된 혁명적인 신경망 아키텍처입니다. [RNN](./RNN.md)의 순차 처리 한계를 극복하고, **전적으로 Attention 메커니즘**에만 의존하여 시퀀스 데이터를 처리합니다.

### 왜 혁명적인가?

#### 1. RNN의 한계 극복
**RNN/LSTM의 문제점**:
- 순차적 처리 → 병렬화 불가능 → 학습 느림
- 긴 시퀀스에서 장거리 의존성(Long-range Dependency) 학습 어려움
- 기울기 소실/폭발 문제

**Transformer의 해결책**:
- **병렬 처리 가능** → 모든 단어를 동시에 처리
- **Self-Attention**으로 거리에 관계없이 모든 단어 간 관계 파악
- 학습 속도 수십 배 향상

#### 2. AI 전 분야를 지배
```
NLP: BERT, GPT, T5, LLaMA, Claude
Vision: ViT, Swin Transformer
Multimodal: CLIP, Flamingo, GPT-4o
Audio: Whisper
생성형 AI: ChatGPT, Stable Diffusion, Sora
```

## 2. 핵심 메커니즘 (Key Mechanisms)

### 2.1. [Self-Attention (셀프 어텐션)](./AttentionMechanism.md)

#### 작동 원리
"The **animal** didn't cross the street because **it** was too tired"

**질문**: "it"이 무엇을 가리키는가?

**Self-Attention의 계산**:
```
1. "it"을 Query로 설정
2. 문장의 모든 단어를 Key로 설정
3. Query와 각 Key의 유사도 계산
4. 유사도를 가중치로 하여 Value들을 가중합

결과: "it" ← 높은 어텐션 → "animal" (93%)
       "it" ← 낮은 어텐션 → "street" (5%)
```

#### 수학적 정의

**3가지 벡터**:
- **Query (Q)**: "무엇을 찾고 있는가?"
- **Key (K)**: "나는 무엇을 제공할 수 있는가?"
- **Value (V)**: "실제 정보"

```
Attention(Q, K, V) = softmax(QK^T / √d_k) V

d_k: Key 벡터의 차원 (스케일링 계수)
QK^T: 모든 Query-Key 쌍의 유사도 (내적)
softmax: 유사도를 확률로 변환
V: 가중합할 실제 값
```

#### 시각적 이해
```
입력 문장: [The, animal, didn't, cross, the, street]

Self-Attention Matrix (각 단어가 다른 단어에 얼마나 주목하는가):

        The  animal  didn't  cross  the  street
The     0.3   0.2    0.1    0.1   0.2    0.1
animal  0.1   0.6    0.1    0.1   0.0    0.1
didn't  0.1   0.2    0.4    0.2   0.0    0.1
...

"animal"은 자기 자신에게 60% 주목 (대각선 강함)
```

#### 장점
- **병렬 처리**: 모든 단어를 동시에 계산
- **장거리 의존성**: 문장 길이에 관계없이 모든 관계 파악
- **해석 가능성**: Attention 가중치를 시각화하여 모델이 무엇을 보는지 확인 가능

### 2.2. Multi-Head Attention (멀티 헤드 어텐션)

하나의 Attention만으로는 복잡한 관계를 포착하기 어렵습니다.

#### 개념
**여러 개의 Attention을 병렬로** 수행하여 다양한 관점에서 정보를 포착합니다.

```
Head 1: 주어-동사 관계에 주목
Head 2: 명사-형용사 관계에 주목
Head 3: 대명사-선행사 관계에 주목
...
Head 8: 의미적 유사성에 주목

최종 출력 = Concat(Head1, Head2, ..., Head8) × W_O
```

#### 수학적 정의
```
MultiHead(Q, K, V) = Concat(head1, ..., headh) W^O

where headi = Attention(Q W^Q_i, K W^K_i, V W^V_i)

h: Head 개수 (보통 8 또는 12)
W^Q_i, W^K_i, W^V_i: 각 Head의 가중치 행렬
W^O: 출력 투영 행렬
```

#### 비유
```
단일 Attention = 하나의 눈으로 보기
Multi-Head Attention = 여러 각도에서 동시에 보기 (파리의 겹눈)
```

### 2.3. Positional Encoding (위치 인코딩)

#### 문제
Self-Attention은 **순서 정보가 없습니다**.
```
"나는 사과를 좋아한다" = "좋아한다 사과를 나는"
(Attention만으로는 구분 불가)
```

#### 해결책
각 단어의 **위치 정보를 벡터로 인코딩**하여 입력에 더합니다.

**Sinusoidal Positional Encoding** (원본 Transformer):
```
PE(pos, 2i)   = sin(pos / 10000^(2i/d_model))
PE(pos, 2i+1) = cos(pos / 10000^(2i/d_model))

pos: 단어의 위치 (0, 1, 2, ...)
i: 차원 인덱스
d_model: 임베딩 차원
```

**특징**:
- 각 위치마다 고유한 패턴
- 상대적 거리를 내적으로 계산 가능
- 학습 없이 사용 가능 (고정 함수)

**최근 변형**:
- **Learnable Positional Embedding**: 위치 벡터를 학습 파라미터로
- **Relative Positional Encoding**: 절대 위치 대신 상대 거리 사용
- **RoPE (Rotary Position Embedding)**: LLaMA 등에서 사용

## 3. Transformer 아키텍처 구조

### 3.1. Encoder-Decoder 구조 (원본 Transformer)

```
입력 (Source)                        입력 (Target)
    ↓                                    ↓
Input Embedding                   Output Embedding
    +                                    +
Positional Encoding              Positional Encoding
    ↓                                    ↓
┌─────────────┐                  ┌─────────────┐
│  Encoder    │                  │  Decoder    │
│  ×N layers  │ ────────────────→│  ×N layers  │
│             │   (Cross         │             │
│- Multi-Head │    Attention)    │- Masked     │
│  Attention  │                  │  Multi-Head │
│- FFN        │                  │  Attention  │
│- Residual   │                  │- Cross      │
│- LayerNorm  │                  │  Attention  │
└─────────────┘                  │- FFN        │
                                 └─────────────┘
                                       ↓
                                  Linear + Softmax
                                       ↓
                                  출력 확률
```

### 3.2. Encoder Block 상세

**하나의 Encoder Layer**:
```
입력 (512차원)
    ↓
┌────────────────────────────┐
│ Multi-Head Self-Attention  │ ← 입력끼리 관계 파악
└────────────────────────────┘
    ↓
Add & Norm (Residual Connection + Layer Normalization)
    ↓
┌────────────────────────────┐
│ Feed-Forward Network       │ ← 비선형 변환
│   (FFN)                    │
│   512 → 2048 → 512         │
│   (ReLU in between)        │
└────────────────────────────┘
    ↓
Add & Norm
    ↓
출력 (512차원)
```

**FFN (Position-wise Feed-Forward Network)**:
```
FFN(x) = max(0, xW1 + b1)W2 + b2

각 위치마다 독립적으로 같은 FFN 적용
```

### 3.3. Decoder Block 상세

Encoder와 비슷하지만 **3가지 Attention**:

```
1. Masked Self-Attention: 미래 단어를 보지 못하게 마스킹
   (생성 시 왼쪽 단어만 참고 가능)

2. Cross-Attention (Encoder-Decoder Attention):
   Query: Decoder의 현재 상태
   Key, Value: Encoder의 출력
   → 입력 문장의 어디를 볼지 결정

3. Feed-Forward Network
```

### 3.4. Residual Connection & Layer Normalization

#### Residual Connection (잔차 연결)
```
출력 = LayerNorm(입력 + Sublayer(입력))

Sublayer: Attention 또는 FFN
```

**역할**:
- 기울기 소실 방지
- 깊은 네트워크 학습 가능
- 정보 손실 방지

#### Layer Normalization
각 샘플을 독립적으로 정규화 (평균 0, 분산 1)

```
LayerNorm(x) = γ × (x - μ) / √(σ² + ε) + β

γ, β: 학습 가능한 파라미터
```

**vs Batch Normalization**:
- BN: 배치 전체의 통계 사용 (시퀀스 길이가 다르면 문제)
- LN: 각 샘플의 Feature 차원 통계 사용 (시퀀스 모델에 적합)

## 4. 주요 변형 (Variants)

### 4.1. Encoder-only: [BERT](./BERT.md) 계열

**구조**: Encoder만 사용 (Bidirectional)

**특징**:
- 양방향 문맥 이해 (앞뒤 모두 참고)
- Masked Language Modeling으로 학습
- 문장 전체를 한 번에 입력받음

**용도**:
- 텍스트 분류 (감성 분석, 스팸 탐지)
- 질의응답 (QA)
- Named Entity Recognition (NER)
- 문장 임베딩

**예시 모델**:
- BERT, RoBERTa, ALBERT, DeBERTa

### 4.2. Decoder-only: [GPT](./GPT.md) 계열

**구조**: Decoder만 사용 (Unidirectional, Autoregressive)

**특징**:
- 왼쪽에서 오른쪽으로만 생성 (Causal)
- 다음 단어 예측으로 학습
- 긴 텍스트 생성에 탁월

**용도**:
- 텍스트 생성 (ChatGPT, Claude)
- 대화형 AI
- 코드 생성 (GitHub Copilot)
- 요약, 번역 (Few-shot learning으로)

**예시 모델**:
- GPT, GPT-2, GPT-3, GPT-4, LLaMA, Mistral, Claude

### 4.3. Encoder-Decoder: T5, BART

**구조**: 원본 Transformer와 동일

**특징**:
- 입력과 출력이 다른 형태
- 명시적인 Source-Target 매핑

**용도**:
- 기계 번역 (영어 → 한국어)
- 요약 (긴 글 → 짧은 요약)
- 질의응답 (질문 → 답변)

**예시 모델**:
- T5, BART, mT5, mBART

### 4.4. [Vision Transformer (ViT)](./ViT.md)

이미지를 Transformer로 처리합니다.

**방법**:
```
1. 이미지를 16×16 패치로 분할
2. 각 패치를 선형 변환하여 임베딩
3. Positional Encoding 추가
4. Standard Transformer Encoder 통과
5. [CLS] 토큰으로 분류
```

**특징**:
- CNN 없이 순수 Transformer만 사용
- 대규모 데이터에서 CNN 능가
- [LeJEPA](./LeJEPA.md), [MAE](./SelfSL.md) 등의 백본

## 5. Transformer의 강점과 한계

### 5.1. 강점

#### 1. 병렬 처리
```
RNN: T 시점씩 순차 처리 → T번 반복 필요
Transformer: 모든 시점 동시 처리 → 1번에 끝
```

#### 2. 장거리 의존성
```
문장 길이 1000에서도:
- RNN: 1000번 전파하며 정보 손실
- Transformer: 직접 Attention으로 참조
```

#### 3. 해석 가능성
Attention 가중치를 시각화하여 모델의 판단 근거 확인 가능

#### 4. 전이 학습 (Transfer Learning)
- 대규모 데이터로 사전 학습
- 소량 데이터로 Fine-tuning
- 다양한 과제에 적용

### 5.2. 한계

#### 1. 계산 복잡도
```
Self-Attention 복잡도: O(n²d)

n: 시퀀스 길이
d: 임베딩 차원

시퀀스가 길어지면 메모리와 계산량이 제곱으로 증가
```

**해결 시도**:
- Longformer: Sparse Attention (O(n))
- Linformer: Low-rank 근사
- Flash Attention: 메모리 효율적 구현

#### 2. 귀납적 편향 부족
- CNN: 지역성(Locality), 변환 불변성(Translation Invariance) 내장
- Transformer: 데이터에서 모든 것을 학습해야 함 → 더 많은 데이터 필요

#### 3. 위치 인코딩의 한계
- 외삽(Extrapolation) 어려움: 학습 시보다 긴 시퀀스에 약함
- RoPE, ALiBi 등으로 개선 시도

## 6. 실전 구현 팁

### 6.1. 하이퍼파라미터

**원본 Transformer (Base)**:
```
d_model = 512        # 임베딩 차원
n_heads = 8          # Attention Head 수
d_ff = 2048          # FFN 중간 차원
n_layers = 6         # Encoder/Decoder 층 수
dropout = 0.1
```

**GPT-3 (175B)**:
```
d_model = 12288
n_heads = 96
d_ff = 49152
n_layers = 96
```

### 6.2. 학습 전략

**Warm-up + Decay 스케줄러**:
```
학습률 = d_model^(-0.5) × min(step^(-0.5), step × warmup_steps^(-1.5))

처음엔 천천히 증가 (Warm-up)
이후 점진적 감소
```

**Label Smoothing**:
정답 레이블을 100% 확신하지 않고 약간 부드럽게 (과적합 방지)

### 6.3. 최적화

**Gradient Checkpointing**:
- 중간 활성화를 저장하지 않고 역전파 시 재계산
- 메모리 절약, 속도는 약간 느려짐

**Mixed Precision Training**:
- FP16으로 학습하여 속도 2배, 메모리 절약
- 중요한 부분은 FP32 유지

## 7. Transformer의 역사적 영향

### Before Transformer (2017 이전)
```
NLP: RNN, LSTM, GRU 지배
Vision: CNN 독점
```

### After Transformer (2017 이후)
```
2017: Transformer 발표
2018: BERT (NLP 혁명)
2019: GPT-2 (언어 생성 돌파)
2020: GPT-3 (Few-shot learning), ViT (Vision 진입)
2021: CLIP (Multimodal), AlphaFold2 (단백질 구조)
2022: ChatGPT (대중화), Stable Diffusion (이미지 생성)
2023: GPT-4 (Multimodal), LLaMA (오픈소스 LLM)
2024: Sora (동영상 생성), Claude 3 (장문 이해)
```

**결론**: Transformer는 단순한 모델이 아니라 **AI 패러다임의 전환**

## 8. Transformer와 최신 연구

### 8.1. [JEPA](./JEPA.md) 및 [LeJEPA](./LeJEPA.md)
Vision Transformer를 인코더와 예측기로 사용하여 잠재 공간에서의 예측을 수행합니다.

### 8.2. [Self-Supervised Learning](./SelfSL.md)
- Masked Autoencoding (MAE): 이미지 일부를 마스킹하고 복원
- Contrastive Learning: CLIP, SimCLR

### 8.3. Efficient Transformer
- Sparse Attention
- Linear Attention
- State Space Models (Mamba)

## 9. 관련 문서
- [Attention Mechanism (어텐션 메커니즘)](./AttentionMechanism.md) - Transformer의 핵심 원리
- [BERT (인코더 모델)](./BERT.md) - Encoder-only Transformer
- [GPT (디코더 모델)](./GPT.md) - Decoder-only Transformer
- [ViT (비전 트랜스포머)](./ViT.md) - 이미지에 Transformer 적용
- [Generative AI (생성형 AI)](./GenerativeAI.md) - Transformer 기반 생성 모델
- [Self-Supervised Learning](./SelfSL.md) - Transformer 사전 학습 방법
- [NLP (자연어 처리)](./NLP.md) - Transformer의 주요 응용 분야
