# Data Preprocessing (데이터 전처리)

## 1. 개요 (Overview)
Data Preprocessing(데이터 전처리)은 수집한 원시 데이터(Raw Data)를 [머신러닝(Machine Learning)](./MLBasic.md) 모델이 학습하기 좋은 형태로 가공하는 과정입니다. "Garbage In, Garbage Out"이라는 말처럼, 데이터의 품질이 모델의 성능을 좌우합니다.

## 2. 주요 기법 (Key Techniques)

### 2.1. Data Cleaning (데이터 정제)
- **결측치(Missing Values) 처리**: 비어 있는 값을 평균/중앙값으로 채우거나 해당 행을 삭제합니다.
- **이상치(Outliers) 제거**: 통계적으로 정상 범위를 벗어나는 값을 찾아 제거하거나 보정합니다.

### 2.2. Normalization & Standardization (정규화 및 표준화)
데이터의 스케일(단위)을 맞추는 과정입니다.
- **Min-Max Scaling**: 값을 0과 1 사이로 변환합니다.
- **Standardization (Z-score)**: 평균이 0, 분산이 1이 되도록 변환합니다. 학습 안정성을 높이는 데 중요합니다.

### 2.3. Encoding (인코딩)
컴퓨터가 이해할 수 없는 문자열(카테고리) 데이터를 숫자로 변환합니다.
- **One-Hot Encoding**: 각 카테고리를 0과 1로 이루어진 벡터로 표현합니다. (예: [1, 0, 0], [0, 1, 0])
- **Label Encoding**: 각 카테고리에 고유한 정수를 부여합니다.

## 3. AI에서의 중요성
- 데이터 전처리가 잘 되어야 모델이 더 빠르고 정확하게 수렴합니다.
- [Data Augmentation](./DataAugmentation.md)은 전처리 단계 이후, 학습 시 실시간으로 적용되기도 합니다.
