# Recommender Systems (추천 시스템)

## 1. 개요 (Overview)
Recommender Systems(추천 시스템)은 사용자(User)의 선호도나 과거 행동 데이터를 분석하여, 사용자가 좋아할 만한 아이템(Item)을 예측하고 제안하는 AI 시스템입니다. 넷플릭스, 유튜브, 아마존 등의 핵심 기술입니다.

## 2. 주요 기법 (Key Techniques)

### 2.1. Content-based Filtering (콘텐츠 기반 필터링)
사용자가 과거에 좋아했던 아이템과 비슷한 특성(장르, 감독, 키워드 등)을 가진 아이템을 추천합니다.
- 장점: 다른 사용자의 데이터가 필요 없습니다.
- 단점: 사용자가 경험하지 않은 새로운 분야의 아이템을 추천하기 어렵습니다.

### 2.2. Collaborative Filtering (협업 필터링)
비슷한 취향을 가진 다른 사용자들의 데이터를 활용합니다. "당신과 비슷한 사람들이 이 상품도 샀습니다" 방식입니다.
- **Matrix Factorization (행렬 분해)**: 사용자-아이템 행렬을 두 개의 저차원 행렬로 분해하여 빈 칸(평점)을 예측합니다.

### 2.3. Hybrid Systems
두 가지 방식을 결합하여 서로의 단점을 보완합니다.

### 2.4. Deep Learning based
최근에는 [Autoencoders](./Autoencoders.md)나 [RNN](./RNN.md) 등을 활용하여 사용자의 복잡한 시퀀스 패턴을 학습하는 방식이 사용됩니다. (예: YouTube 알고리즘)
