# Time Series Analysis (시계열 분석)

## 1. 개요 (Overview)
Time Series Analysis(시계열 분석)는 시간의 흐름에 따라 순차적으로 관측된 데이터(주가, 날씨, 웹사이트 트래픽 등)를 분석하고 미래를 예측하는 기술입니다.

## 2. 주요 특징
- **Trend (추세)**: 장기적으로 상승하거나 하락하는 경향.
- **Seasonality (계절성)**: 특정 주기(요일, 월, 계절)로 반복되는 패턴.
- **Noise (노이즈)**: 설명할 수 없는 무작위 변동.

## 3. 주요 모델 (Key Models)

### 3.1. 통계적 방법
- **ARIMA (AutoRegressive Integrated Moving Average)**: 과거의 데이터와 오차를 이용하여 현재를 설명하는 고전적인 모델입니다. 데이터가 정상성(Stationarity)을 가져야 합니다.
- **Prophet**: 페이스북이 개발한 모델로, 계절성과 휴일 효과 등을 직관적으로 반영할 수 있어 실무에서 많이 쓰입니다.

### 3.2. 딥러닝 방법
- **[RNN](./RNN.md) / LSTM**: 시퀀스 데이터 처리에 강점이 있어 시계열 예측에 자연스럽게 적용됩니다.
- **[Transformer](./Transformer.md)**: 최근에는 Time-Series Transformer 등이 등장하여 긴 시계열 데이터의 패턴을 효과적으로 학습하고 있습니다.
