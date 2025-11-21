# Prompt Engineering (프롬프트 엔지니어링)

## 1. 개요 (Overview)
Prompt Engineering(프롬프트 엔지니어링)은 [GPT](./GPT.md)와 같은 거대 언어 모델(LLM)로부터 원하는 최상의 결과를 얻어내기 위해 입력(Prompt)을 최적화하는 기술입니다. 모델의 파라미터를 수정하지 않고도 성능을 끌어올릴 수 있습니다.

## 2. 주요 기법 (Key Techniques)

### 2.1. Zero-shot / One-shot / Few-shot Prompting
- **Zero-shot**: 예시 없이 바로 지시만 내립니다.
- **Few-shot**: 몇 가지 예시(입력-출력 쌍)를 보여주어 모델이 패턴을 파악하게 합니다. 성능이 크게 향상됩니다.

### 2.2. CoT (Chain-of-Thought)
모델에게 "단계별로 생각해보라(Let's think step by step)"고 지시하여, 복잡한 추론 과정을 거치게 합니다. 수학 문제나 논리적 문제 해결에 매우 효과적입니다.

### 2.3. Role Playing (페르소나 부여)
"너는 세계적인 AI 전문가야"와 같이 역할을 부여하면, 해당 역할에 맞는 톤과 깊이 있는 답변을 생성합니다.

## 3. 중요성
LLM이 보편화되면서 프롬프트 엔지니어링은 AI를 효과적으로 활용하기 위한 필수 역량이 되고 있습니다.
