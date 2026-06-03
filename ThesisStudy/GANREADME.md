# 🎨 Vanilla GAN from Scratch with PyTorch

PyTorch를 활용하여 구조가 가장 직관적이고 표준적인 **Vanilla GAN(Generative Adversarial Networks)**을 구현한 프로젝트입니다. 

**MNIST 손글씨 데이터셋(28x28)**을 학습하여, 무작위 노이즈($z$)로부터 실제 존재하는 것과 유사한 가짜 이미지를 생성하는 모델을 구축하고 이진 교차 엔트로피(BCE Loss)를 통해 적대적 학습을 수행합니다.

---

## 📌 핵심 구현 특징
* **미러 서버 우회 적용**: 널리 알려진 `torchvision.datasets.MNIST` 서버 만료 및 다운로드 오류 문제를 미러링 사이트 주소(`mirrors`) 지정을 통해 우회 해결했습니다.
* **효율적인 기기 할당**: Apple Silicon(M1/M2/M3/M4) 환경에서 최적의 연산 속도를 낼 수 있도록 **MPS(Metal Performance Shaders)** 가속 장치를 지원합니다.
* **기울기 전파 분리 (`.detach()`)**: 판별자(Discriminator)를 학습시키는 단계에서 생성기(Generator)가 만든 이미지의 연산 그래프를 끊어, 불필요한 메모리 소모와 생성기 가중치의 꼬임을 방지했습니다.
* **차원 변형 자동화**: 데이터로더에서 나온 4D 텐서 `[B, 1, 28, 28]` 데이터를 전결합층(Linear Layer) 연산에 맞게 `view(-1, 784)`로 펼치고 다시 복원하는 과정을 구조화했습니다.

---

## 📐 GAN의 수학적 배경 (Mathematical Background)

GAN은 생성기($G$)와 판별자($D$)가 서로를 이기려는 최소극대화(Minimax) 게임을 통해 학습을 진행합니다.

$$\min_G \max_D V(D, G) = \mathbb{E}_{x \sim p_{data}} [\log D(x)] + \mathbb{E}_{z \sim p_z} [\log(1 - D(G(z)))]$$

### 1. 판별자(Discriminator) 최적화
* **목표**: 실제 데이터는 $1$로, 생성기가 만든 가짜 데이터는 $0$으로 분류해야 합니다.
* **손실 함수**: Binary Cross-Entropy (BCE) Loss를 사용하여 아래 오차를 최소화합니다.
  $$\text{Loss}_D = -\log D(x) - \log(1 - D(G(z)))$$

### 2. 생성기(Generator) 최적화
* **목표**: 자기가 만든 이미지 $G(z)$를 판별자가 진짜($1$)라고 믿게 속여야 합니다.
* **손실 함수**: 판별자가 가짜 이미지를 넣었을 때 $1$이 나오도록 유도합니다.
  $$\text{Loss}_G = -\log D(G(z))$$

---

## 💻 실행 방법 및 환경

### 개발 환경
* **OS**: macOS
* **IDE**: PyCharm / Jupyter Notebook
* **Language**: Python 3.12+
* **Framework**: PyTorch

### 필수 라이브러리 설치
```bash
pip install torch torchvision