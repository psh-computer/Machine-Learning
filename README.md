# Machine-Learning
# CNN vs MobileNet Efficiency Analysis

이 프로젝트는 일반적인 Convolution 연산과 MobileNet의 핵심인 Depthwise Separable Convolution의 효율성을 비교 분석합니다.

## 1. Background
- Standard Convolution: 공간 정보와 채널 정보를 동시에 처리하여 연산량이 많음.
- MobileNet (Depthwise Separable Conv): - Depthwise: 각 채널별로 공간 정보 추출
  - Pointwise: 채널 간 정보 조합 및 차원 조절.

## 2. Key Objectives
- 동일한 구조에서 연산 방식만 바꿨을 때의 Parameter 수 비교.
- 모델별 Inference Time(추론 속도) 측정.
- Accuracy 성능 유지 여부 확인.
# Machine-Learning
