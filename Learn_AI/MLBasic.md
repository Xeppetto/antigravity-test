# Machine Learning Basics (머신러닝 기초)

## 1. 개요 (Overview)

### 머신러닝이란?
Machine Learning(머신러닝)은 **데이터로부터 스스로 학습**하여 성능을 향상시키는 기술입니다. 사람이 규칙을 일일이 코딩하지 않아도, 데이터 속의 패턴을 찾아내고 이를 바탕으로 예측이나 결정을 내립니다.

### 전통적 프로그래밍 vs 머신러닝

**전통적 프로그래밍**:
```
규칙(사람이 작성) + 데이터 → 결과
```
예: "만약 이메일에 '당첨'이라는 단어가 있으면 스팸"

**머신러닝**:
```
데이터 + 정답 → 규칙(컴퓨터가 학습)
```
예: 수천 개의 스팸/정상 메일을 보여주면 AI가 스스로 판별 규칙 학습

### 왜 머신러닝이 필요한가?

#### 1. 규칙을 명시하기 어려운 문제
- 고양이 사진 인식: "털이 있고, 귀가 뾰족하고..." → 예외가 너무 많음
- 음성 인식: 각 사람의 발음, 억양, 배경 소음 등 변수가 무한대

#### 2. 규칙이 계속 변하는 문제
- 주식 예측: 시장 환경이 매일 변함
- 추천 시스템: 사용자 취향이 시간에 따라 변함

#### 3. 너무 많은 규칙이 필요한 문제
- 바둑: 경우의 수가 우주의 원자 개수보다 많음

## 2. 핵심 개념 (Key Concepts)

### 2.1. 데이터 (Data)

머신러닝의 **원료**입니다. 데이터의 품질과 양이 모델의 성능을 결정합니다.

#### 구성 요소

**Feature (특징, 입력 변수)**:
예측에 사용되는 입력 데이터입니다.

```
집값 예측 예시:
Feature 1: 집의 크기 (㎡)
Feature 2: 방의 개수
Feature 3: 지하철역까지 거리 (m)
Feature 4: 건축 연도
```

**Label (레이블, 타겟, 정답)**:
예측하고자 하는 값입니다.

```
집값 예측 예시:
Label: 집의 가격 (억 원)
```

**데이터셋 예시**:
| 크기(㎡) | 방 개수 | 역까지 거리 | 건축년도 | **가격(억)** |
|---------|--------|----------|--------|------------|
| 85      | 3      | 500      | 2015   | **5.5**    |
| 120     | 4      | 200      | 2020   | **8.2**    |
| 60      | 2      | 800      | 2010   | **3.8**    |

앞의 4개 열 = Features, 마지막 열 = Label

#### 데이터 분할

```
전체 데이터
  ├─ Training Set (훈련 세트, 70~80%): 모델 학습에 사용
  ├─ Validation Set (검증 세트, 10~15%): 하이퍼파라미터 튜닝
  └─ Test Set (테스트 세트, 10~15%): 최종 성능 평가
```

**왜 분할하나요?**
- 시험 문제로 공부하고 같은 문제로 시험 보면 의미 없음
- Test Set은 "본 적 없는 데이터"로 실제 성능 평가

### 2.2. 모델 (Model)

데이터의 패턴을 학습한 **수학적 함수**입니다.

```
y = f(x)

x: 입력 (Features)
f: 모델 (학습된 함수)
y: 출력 (Prediction, 예측값)
```

**예시**:
```
집값 = f(크기, 방 개수, 역까지 거리, 건축년도)

구체적으로:
집값 = 0.05 × 크기 + 0.3 × 방개수 - 0.0002 × 거리 + 0.01 × 년도 - 15
```

이 함수의 계수들(0.05, 0.3, ...)이 **파라미터**이고, 학습을 통해 최적값을 찾습니다.

### 2.3. 학습 (Training)

모델의 **파라미터를 조정**하여 예측 오차를 최소화하는 과정입니다.

#### 학습 과정

```
1. 초기 파라미터 설정 (랜덤 값)
2. 현재 모델로 예측 수행
3. 예측값과 정답의 차이(Loss) 계산
4. Loss를 줄이는 방향으로 파라미터 업데이트
5. 2~4번을 반복
```

#### Loss Function (손실 함수)

예측값과 실제값의 **차이를 측정**하는 함수입니다.

**회귀 문제 - MSE (Mean Squared Error)**:
```
실제 집값: 5억
예측 집값: 4억
오차 = (5 - 4)² = 1

모든 데이터에 대해 평균:
Loss = (1/n) × Σ(실제값 - 예측값)²
```

**분류 문제 - Cross-Entropy Loss**:
```
실제: 고양이 (확률 1)
예측: [고양이 0.7, 개 0.2, 새 0.1]

Cross-Entropy로 확률 분포 간 차이 측정
```

#### Optimization (최적화)

**Gradient Descent (경사 하강법)**:
손실 함수의 기울기(Gradient)를 계산하여 파라미터를 업데이트합니다.

```
새 파라미터 = 이전 파라미터 - 학습률 × 기울기

예시:
현재 w = 0.5
기울기 = 2 (w를 증가시키면 Loss가 증가)
학습률 = 0.1

새 w = 0.5 - 0.1 × 2 = 0.3 (Loss를 줄이는 방향으로 이동)
```

**시각적 이해**:
```
Loss 함수를 산이라고 생각하면,
경사 하강법은 가장 낮은 곳(최솟값)으로 내려가는 과정입니다.
```

## 3. 학습 유형 (Types of Learning)

### 3.1. Supervised Learning (지도 학습)

**정답이 있는 데이터**로 학습합니다. 가장 널리 사용됩니다.

#### Classification (분류)
데이터를 **정해진 카테고리**로 구분합니다.

**예시**:
- **이진 분류**: 스팸 메일인가? (Yes/No)
- **다중 분류**: 사진 속 동물이 무엇인가? (고양이/개/새/...)

**활용 분야**:
- 이메일 스팸 필터
- 질병 진단 (암인지 아닌지)
- 이미지 인식 (손글씨 숫자 인식)
- 감성 분석 (리뷰가 긍정/부정)

**알고리즘**:
- Logistic Regression
- Decision Tree
- Random Forest
- SVM (Support Vector Machine)
- [Neural Networks](./NeuralNetworks.md)

#### Regression (회귀)
**연속적인 수치 값**을 예측합니다.

**예시**:
- 집값 예측 (3.5억, 5.2억, ...)
- 기온 예측 (25.3도, 28.7도, ...)
- 주가 예측

**활용 분야**:
- 부동산 가격 예측
- 수요 예측 (내일 판매량은?)
- 추천 시스템 (사용자가 이 영화에 줄 평점은?)

**알고리즘**:
- Linear Regression (선형 회귀)
- Polynomial Regression
- Ridge/Lasso Regression
- Neural Networks

### 3.2. Unsupervised Learning (비지도 학습)

**정답 없이** 데이터의 숨겨진 구조나 패턴을 찾습니다.

#### [Clustering (군집화)](./Clustering.md)
유사한 데이터끼리 **자동으로 그룹화**합니다.

**예시**:
- 고객 세분화: 구매 패턴이 비슷한 고객끼리 묶기
- 이미지 압축: 비슷한 색상끼리 묶기
- 문서 분류: 주제가 비슷한 뉴스 기사 묶기

**알고리즘**:
- K-Means
- DBSCAN
- Hierarchical Clustering

#### [Dimensionality Reduction (차원 축소)](./DimensionalityReduction.md)
**데이터의 핵심 정보**만 유지하면서 차원을 줄입니다.

**왜 필요한가?**
- 시각화: 100차원 데이터를 2D로 줄여서 그래프로 표현
- 노이즈 제거: 중요하지 않은 특징 제거
- 계산 속도 향상: 차원이 줄면 연산 빨라짐

**예시**:
- 100개 설문 항목 → 5개 핵심 지표로 요약
- 고해상도 이미지 → 핵심 특징만 추출

**알고리즘**:
- PCA (Principal Component Analysis)
- t-SNE
- UMAP

### 3.3. [Reinforcement Learning (강화 학습)](./ReinforcementLearning.md)

**시행착오를 통해** 보상을 최대화하는 행동을 학습합니다.

#### 구성 요소
```
Agent (에이전트): 학습하는 주체 (예: 게임 AI)
Environment (환경): Agent가 상호작용하는 세계
State (상태): 현재 환경의 상황
Action (행동): Agent가 취할 수 있는 행동
Reward (보상): 행동의 결과로 받는 점수
```

#### 학습 과정
```
1. Agent가 현재 State 관찰
2. Action 선택
3. 환경이 변하고 Reward 받음
4. Reward가 높은 Action을 더 자주 선택하도록 학습
```

**예시**:
- 게임 AI (AlphaGo, 아타리 게임)
- 자율주행 (안전 운전 = 높은 보상)
- 로봇 제어 (목표 도달 = 보상)

### 3.4. [Self-Supervised Learning (자기지도 학습)](./SelfSL.md)

**레이블 없는 데이터**에서 스스로 학습 과제를 만들어 학습합니다.

#### 작동 원리
```
원본 데이터 → 일부 가리기 → 가려진 부분 예측

예시:
"나는 ___을 좋아해" → "___"에 들어갈 단어 예측
```

**왜 중요한가?**
- 레이블 붙이기는 비용이 많이 듦 (사람이 일일이 해야 함)
- 인터넷에는 레이블 없는 데이터가 무한정 존재

**예시**:
- BERT: 문장의 일부 단어를 마스킹하고 맞추기
- MAE: 이미지 일부를 가리고 복원하기
- SimCLR: 같은 이미지의 다른 변형끼리 유사하도록 학습

## 4. 주요 알고리즘 (Algorithms)

### 4.1. Linear Regression (선형 회귀)
가장 기본적인 회귀 알고리즘입니다.

```
y = w1×x1 + w2×x2 + ... + b

집값 = w1×크기 + w2×방개수 + b
```

**장점**: 단순하고 해석하기 쉬움
**단점**: 선형 관계만 표현 가능

### 4.2. Logistic Regression (로지스틱 회귀)
이진 분류를 위한 알고리즘입니다.

```
확률 = sigmoid(w1×x1 + w2×x2 + ... + b)
0.5 이상이면 클래스 1, 미만이면 클래스 0
```

### 4.3. Decision Tree (결정 트리)
의사결정 규칙을 **나무 구조**로 표현합니다.

```
크기 > 80㎡?
├─ Yes → 방개수 > 3?
│         ├─ Yes → 고가
│         └─ No → 중가
└─ No → 저가
```

**장점**: 시각적으로 이해하기 쉬움
**단점**: 과적합(Overfitting)되기 쉬움

### 4.4. Random Forest (랜덤 포레스트)
여러 개의 Decision Tree를 조합한 **앙상블** 방법입니다.

```
트리 1: 고가 예측
트리 2: 중가 예측
트리 3: 고가 예측
...
트리 100: 고가 예측

최종 예측 = 다수결 투표 → 고가
```

**장점**: 과적합이 적고 성능 우수
**단점**: 해석이 어려움

### 4.5. SVM (Support Vector Machine)
데이터를 구분하는 **최적의 경계선**을 찾습니다.

```
두 클래스를 가장 넓은 여백(Margin)으로 분리하는 선 찾기
```

**장점**: 고차원 데이터에 강함
**단점**: 대규모 데이터에는 느림

### 4.6. K-Means Clustering
데이터를 **K개 그룹**으로 나눕니다.

```
1. K개의 중심점을 랜덤 배치
2. 각 데이터를 가장 가까운 중심점에 할당
3. 각 그룹의 평균으로 중심점 업데이트
4. 2~3 반복
```

### 4.7. [Deep Learning (딥러닝)](./DLBasic.md)
인공 신경망을 이용한 고급 머신러닝입니다.

**특징**:
- 수백만~수억 개의 파라미터
- 이미지, 텍스트, 음성 등 복잡한 데이터 처리
- 대규모 데이터와 GPU 필요

## 5. 머신러닝 프로젝트 단계

### 1단계: 문제 정의
```
- 무엇을 예측할 것인가?
- 분류 문제인가, 회귀 문제인가?
- 성공 기준은 무엇인가?
```

### 2단계: 데이터 수집
```
- 어디서 데이터를 구할 것인가?
- 얼마나 많은 데이터가 필요한가?
- 데이터 품질은 괜찮은가?
```

### 3단계: [데이터 전처리](./DataPreprocessing.md)
```
- 결측치 처리
- 이상치 제거
- 정규화/표준화
- Feature 엔지니어링
```

### 4단계: 모델 선택 및 학습
```
- 적절한 알고리즘 선택
- Training/Validation/Test 분할
- 모델 학습
```

### 5단계: [평가](./EvaluationMetrics.md)
```
- Accuracy, Precision, Recall (분류)
- MSE, RMSE, MAE (회귀)
- Test Set으로 최종 성능 측정
```

### 6단계: [튜닝](./HyperparameterTuning.md)
```
- 하이퍼파라미터 조정
- 교차 검증 (Cross-Validation)
- 앙상블 기법 적용
```

### 7단계: 배포 (Deployment)
```
- 실제 서비스에 적용
- 모니터링 및 유지보수
```

## 6. 주요 도전 과제

### 6.1. [Overfitting (과적합)](./OverfittingUnderfitting.md)
훈련 데이터에만 과도하게 맞춰져서 새로운 데이터에는 성능이 나쁜 현상

**해결책**:
- 더 많은 데이터 수집
- [Regularization (정규화)](./Regularization.md)
- 모델 단순화
- [Data Augmentation (데이터 증강)](./DataAugmentation.md)

### 6.2. Underfitting (과소적합)
모델이 너무 단순해서 데이터의 패턴을 제대로 학습하지 못하는 현상

**해결책**:
- 더 복잡한 모델 사용
- Feature 추가
- 학습 시간 늘리기

### 6.3. 불균형 데이터 (Imbalanced Data)
클래스 간 데이터 수 차이가 큰 경우

**예시**: 정상 거래 99%, 사기 거래 1%

**해결책**:
- 오버샘플링 / 언더샘플링
- 클래스 가중치 조정
- SMOTE 기법

## 7. 사전 지식 (Prerequisites)

머신러닝을 제대로 이해하려면 다음 지식이 필요합니다:

### 7.1. 수학 (Mathematics)
- **[Linear Algebra (선형대수)](./LinearAlgebra.md)**:
  - 벡터, 행렬 연산
  - 데이터 표현의 기초

- **[Calculus (미적분)](./Calculus.md)**:
  - 기울기(Gradient), 편미분
  - 모델 최적화의 핵심

- **[Probability & Statistics (확률과 통계)](./ProbabilityStatistics.md)**:
  - 확률 분포, 평균, 분산
  - 불확실성 모델링

### 7.2. 프로그래밍 (Programming)
- **[Python](./PythonForAI.md)**: AI/ML 표준 언어
- **라이브러리**:
  - NumPy: 수치 계산
  - Pandas: 데이터 처리
  - Scikit-learn: 전통적 ML 알고리즘
  - Matplotlib/Seaborn: 시각화

## 8. 실전 팁

### 8.1. 항상 간단한 모델부터 시작
```
Linear Regression → Decision Tree → Random Forest → Neural Network
```
복잡한 모델은 나중에!

### 8.2. 데이터 품질이 가장 중요
```
"Garbage In, Garbage Out"
좋은 데이터 > 복잡한 모델
```

### 8.3. 시각화하기
```
데이터 분포, 학습 곡선, 오차 분석을 그래프로 그려보세요.
숫자만 보면 놓치는 패턴을 발견할 수 있습니다.
```

## 9. 다음 단계

### 머신러닝을 이해했다면:
- **[Deep Learning Basics](./DLBasic.md)**: 신경망의 세계로
- **[Neural Networks](./NeuralNetworks.md)**: 신경망 구조 이해
- **[Optimization Algorithms](./OptimizationAlgorithms.md)**: 학습 최적화
- **[Evaluation Metrics](./EvaluationMetrics.md)**: 모델 평가 방법

### 응용 분야:
- **[Computer Vision](./ComputerVision.md)**: 이미지 처리
- **[NLP](./NLP.md)**: 자연어 처리
- **[Reinforcement Learning](./ReinforcementLearning.md)**: 강화 학습

## 10. 관련 문서
- [Artificial Intelligence (인공지능)](./ArtificialIntelligence.md) - 전체 맥락 이해
- [Deep Learning Basics (딥러닝 기초)](./DLBasic.md) - 머신러닝의 발전된 형태
- [Data Preprocessing (데이터 전처리)](./DataPreprocessing.md) - 학습 전 필수 과정
- [Evaluation Metrics (평가 지표)](./EvaluationMetrics.md) - 모델 성능 측정
- [Overfitting & Underfitting](./OverfittingUnderfitting.md) - 흔한 문제와 해결책
