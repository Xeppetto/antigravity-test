# Speech Recognition (음성 인식)

## 1. 개요 (Overview)
Speech Recognition(음성 인식)은 사람이 말하는 음성 언어를 컴퓨터가 해석하여 텍스트 데이터로 변환하는 기술입니다. STT(Speech-to-Text) 또는 ASR(Automatic Speech Recognition)이라고도 불립니다.

## 2. 주요 과정 (Process)
1.  **Feature Extraction (특징 추출)**: 음성 신호에서 잡음을 제거하고, MFCC(Mel-Frequency Cepstral Coefficients)와 같은 특징 벡터를 추출합니다.
2.  **Acoustic Model (음향 모델)**: 추출된 특징이 어떤 음소(Phoneme)에 해당하는지 확률적으로 계산합니다.
3.  **Language Model (언어 모델)**: 단어들의 순서와 문맥을 고려하여 가장 자연스러운 문장을 만듭니다.
4.  **Decoding**: 음향 모델과 언어 모델의 결과를 종합하여 최종 텍스트를 출력합니다.

## 3. 주요 모델 (Key Models)
- **HMM (Hidden Markov Model)**: 과거의 통계 기반 모델.
- **CTC (Connectionist Temporal Classification)**: [RNN](./RNN.md) 기반의 딥러닝 모델로, 입력과 출력의 길이가 달라도 학습이 가능하게 했습니다.
- **Listen, Attend and Spell (LAS)**: [Attention Mechanism](./AttentionMechanism.md)을 적용한 Seq2Seq 모델.
- **Whisper**: OpenAI가 개발한 대규모 음성 인식 모델로, 다국어 인식 및 번역 성능이 뛰어납니다.
