# Batch Normalization (배치 정규화)

## 1. 개요 (Overview)
Batch Normalization(배치 정규화)은 신경망의 각 층(Layer)에 들어가는 입력의 분포를 정규화(평균 0, 분산 1)하여 학습을 안정화하고 가속화하는 기법입니다. 2015년에 제안되어 딥러닝의 표준 테크닉이 되었습니다.

## 2. 왜 필요한가? (Internal Covariate Shift)
학습이 진행되면서 앞쪽 층의 파라미터가 바뀌면, 뒤쪽 층으로 들어오는 입력의 분포도 계속 바뀝니다. 이를 **Internal Covariate Shift(내부 공변량 변화)**라고 합니다. 이 때문에 뒤쪽 층은 계속해서 새로운 분포에 적응해야 하므로 학습이 불안정하고 느려집니다.

## 3. 동작 원리 (Mechanism)
1.  **Normalization**: 미니 배치(Mini-batch) 단위로 평균과 분산을 계산하여 입력을 정규화합니다.
2.  **Scale and Shift**: 정규화된 값에 학습 가능한 파라미터인 $\gamma$(스케일)와 $\beta$(이동)를 적용하여, 데이터가 가질 수 있는 표현력을 유지합니다.

## 4. 장점 (Benefits)
- **학습 속도 향상**: 더 큰 학습률(Learning Rate)을 사용할 수 있습니다.
- **초기화 의존성 감소**: 가중치 초기화에 덜 민감해집니다.
- **Regularization 효과**: 미니 배치마다 평균/분산이 조금씩 달라지므로 약간의 노이즈가 추가되어, [Dropout](./Regularization.md)과 유사한 규제 효과를 냅니다.
