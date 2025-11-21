# Knowledge Distillation (지식 증류)

## 1. 개요 (Overview)
Knowledge Distillation(지식 증류)은 크고 복잡한 모델(Teacher Model)이 배운 지식을 작고 가벼운 모델(Student Model)에게 전달하여, 작은 모델의 성능을 높이는 경량화 기술입니다.

## 2. 왜 필요한가?
최신 딥러닝 모델들은 성능은 좋지만 파라미터가 너무 많아(수억~수천억 개), 모바일 기기나 임베디드 시스템에서 실행하기 어렵습니다. 지식 증류를 통해 모델의 크기를 줄이면서도 성능 저하를 최소화할 수 있습니다.

## 3. 작동 원리 (Mechanism)
1.  **Teacher Model**: 이미 학습이 완료된 고성능 모델입니다.
2.  **Student Model**: 학습시키려는 작은 모델입니다.
3.  **Soft Label**: Teacher Model의 출력(Softmax 확률값)은 정답(Hard Label)보다 더 많은 정보를 담고 있습니다. (예: 이 이미지는 '개'일 확률이 90%지만, '고양이'일 확률도 9%나 된다 -> 개와 고양이는 비슷하게 생겼다)
4.  Student Model은 정답뿐만 아니라 Teacher Model의 Soft Label도 흉내 내도록 학습합니다.

## 4. 효과
Student Model은 단순히 정답만 보고 학습할 때보다 훨씬 더 빠르고 정확하게 학습할 수 있습니다.
