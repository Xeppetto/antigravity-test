# RNN (Recurrent Neural Networks, 순환 신경망)

## 1. 개요 (Overview)
RNN(Recurrent Neural Networks)은 순서가 있는 데이터(Sequence Data)를 처리하기 위해 고안된 신경망입니다. 이전 시점(Time step)의 출력이 다음 시점의 입력으로 다시 들어가는 "순환(Recurrent)" 구조를 가집니다.

## 2. 특징 (Features)
- **Memory (기억)**: 은닉 상태(Hidden State)라는 내부 메모리를 통해 이전까지의 정보를 기억합니다.
- **Sequence Processing**: 길이가 가변적인 입력(문장, 시계열 데이터)을 처리할 수 있습니다.

## 3. 한계 (Limitations)
- **Vanishing Gradient (기울기 소실)**: 시퀀스가 길어질수록 역전파 과정에서 기울기가 점점 작아져, 앞쪽의 정보를 잊어버리는 장기 의존성(Long-term Dependency) 문제가 발생합니다.

## 4. 발전된 모델 (Advanced Models)

### 4.1. LSTM (Long Short-Term Memory)
- Cell State와 Gate(Input, Forget, Output) 구조를 도입하여 중요한 정보는 오래 기억하고 불필요한 정보는 잊어버리도록 조절합니다. 기울기 소실 문제를 획기적으로 개선했습니다.

### 4.2. GRU (Gated Recurrent Unit)
- LSTM의 구조를 단순화하여 연산 속도를 높이면서도 비슷한 성능을 냅니다.

## 5. 현재의 위상
[Transformer](./Transformer.md)의 등장 이후 NLP 분야에서는 주류에서 밀려났지만, 시계열 예측이나 음성 인식 등에서는 여전히 유용하게 사용됩니다.
