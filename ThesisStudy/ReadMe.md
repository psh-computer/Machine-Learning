# 🤖 SVM from Scratch with PyCharm

Linear Support Vector Machine (SVM)을 외부 머신러닝 라이브러리(scikit-learn) 없이 **Pure NumPy와 경사하강법(Gradient Descent)만을 활용하여 밑바닥부터 직접 구현**한 프로젝트입니다. 

소프트 마진(Soft Margin)과 힌지 손실(Hinge Loss)의 수학적 원리를 코드로 바르게 구현하고, 최적화된 결정 경계(Decision Boundary)와 마진(Margin)을 시각화하여 이론적 동작을 검증합니다.

---

## 📌 핵심 구현 특징
* **Soft Margin SVM 최적화**: 규제 매개변수 $C$를 도입하여 마진 안으로 들어오는 오차를 허용하는 힌지 손실 함수를 목적 함수로 정의했습니다.
* **경사하강법 기반 파라미터 업데이트**: 매 에포크마다 마진 조건($y_i(w \cdot x_i + b) \ge 1$)을 검사하여 조건 충족 여부에 따라 가중치 $w$와 편향 $b$를 다르게 업데이트합니다.
* **시각화 헬퍼 포함**: 2차원 공간 상에서 최적의 초평면(Hyperplane)인 결정 경계선과 서포트 벡터가 위치할 마진선($+1, -1$)을 계산하는 함수를 내장했습니다.
* **Scikit-learn 비교 검증**: 직접 구현한 모델의 예측 정확도를 `sklearn.svm.SVC` 모델과 비교하여 구현의 정확성을 검증합니다.

---

## 📐 수학적 배경 (Mathematical Background)

### 1. 목적 함수 (Objective Function)
Soft Margin SVM은 마진을 최대화하면서 분류 오차를 최소화하기 위해 아래와 같은 비용 함수(Cost Function)를 최소화합니다.
$$J(w, b) = \frac{1}{2} \|w\|^2 + C \sum_{i=1}^{n} \max(0, 1 - y_i(w \cdot x_i + b))$$

### 2. 조건별 가중치 업데이트 규칙 (Gradient Update)
비용 함수를 $w$와 $b$에 대해 각각 편미분하여 경사하강법 규칙을 유도합니다. 학습률(Learning Rate)을 $\eta$라 할 때:

* **Case 1: 올바르게 분류되었고 마진 밖에 있는 경우 ($y_i(w \cdot x_i + b) \ge 1$)**
  $$w \leftarrow w - \eta \cdot (2w)$$
  $$b \leftarrow b - \eta \cdot (0) = b$$
  *(단, 본 코드에서는 수식 제약 조건 변형에 따라 편향 규제 규칙 `b -= lr * (-C * y_i)`를 실험적으로 적용)*

* **Case 2: 잘못 분류되었거나 마진을 침범한 경우 ($y_i(w \cdot x_i + b) < 1$)**
  $$w \leftarrow w - \eta \cdot (2w - C \cdot y_i \cdot x_i)$$
  $$b \leftarrow b - \eta \cdot (-y_i) = b + \eta \cdot y_i$$

---

## 💻 실행 방법 및 환경

### 개발 환경
* **OS**: macOS
* **IDE**: PyCharm
* **Language**: Python 3.x

### 필수 라이브러리 설치
```bash
pip install numpy matplotlib scikit-learn