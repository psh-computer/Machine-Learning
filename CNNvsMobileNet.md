# Machine-Learning
# CNN vs MobileNet Efficiency Analysis

이 프로젝트는 일반 합성곱 블록과 Depthwise Separable Convolution 블록을 구현해 구조를 비교합니다. 현재 노트북은 두 블록의 출력 형태를 확인하는 초기 단계이며, 성능 비교 실험과 측정 결과는 아직 포함하지 않습니다.

## 1. Background
- Standard Convolution: 공간 정보와 채널 정보를 동시에 처리하여 연산량이 많음.
- MobileNet (Depthwise Separable Conv): - Depthwise: 각 채널별로 공간 정보 추출
  - Pointwise: 채널 간 정보 조합 및 차원 조절.

## 2. Next experiment
To support an efficiency claim, use the same input shape and hardware for both blocks, report parameter counts and repeated inference timings, and evaluate accuracy in a defined classification task. Include the device, warm-up policy, number of timing runs, and variability. The current notebook does not yet provide these measurements.
