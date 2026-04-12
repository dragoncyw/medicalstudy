# 🏥 Medical Imaging & Medical AI — Undergraduate Education

> 의료영상 및 의료인공지능 기초 교육을 위한 실습 중심 Python Notebook

---

## 📌 Overview

이 프로젝트는 **의료영상(Medical Imaging)**과 **의료 인공지능(Medical AI)**의 기초 개념부터  
실제 실습까지 한 번에 학습할 수 있도록 설계된 교육용 자료입니다.

- 🎓 대상: 의료 AI를 처음 배우는 학부생
- ⏱️ 학습 시간: 약 6~8시간
- 💻 환경: Jupyter Notebook / Google Colab

---

## 📂 Project Structure

```text
├── 의료영상_의료인공지능_기초교육_v2.ipynb
└── README.md
```

---

## 🧠 Contents

### 🔬 Part 1. Medical Imaging Basics
- 의료영상 개념
- 주요 영상 기법 비교 (X-ray, CT, MRI, Ultrasound, PET)
- 의료영상 처리 파이프라인

### 🤖 Part 2. Medical AI Basics
- 의료 데이터 특성
- AI 기반 진단 개념
- 머신러닝 vs 딥러닝

### 💻 Part 3. Hands-on Practice
- OpenCV 기반 영상 처리
- Feature extraction
- 간단한 ML 모델 적용

### 🚀 Part 4. Showcase Project
- CNN 분류 실습
- Transfer Learning 개념 시연
- U-Net 구조 이해

---

## ✅ Colab 실행 가능 여부

이 노트북은 **대체로 Google Colab에서 실행 가능한 구조**입니다.

### 확인한 점
- 외부 로컬 데이터 파일을 직접 읽는 코드가 없음
- 대부분의 셀이 `numpy`, `matplotlib`, `opencv-python`, `scikit-learn` 기반
- TensorFlow가 필요한 셀은 `try/except`로 분리되어 있어, 설치가 안 되어도 앞부분 이론/시각화 셀은 실행 가능
- MNIST 다운로드, ResNet50 가중치 다운로드 등은 인터넷이 연결된 Colab 환경에서 일반적으로 실행 가능

### 주의할 점
- 첫 설치 셀에서 `pip install`을 실행하므로 Colab에서는 1~2분 정도 추가 시간이 걸릴 수 있음
- TensorFlow 관련 셀은 런타임 환경에 따라 다시 설치 또는 런타임 재시작이 필요할 수 있음
- 한글 폰트는 Colab에서 완벽히 동일하게 보장되지 않을 수 있음
- 저장되는 이미지 파일(`.png`)은 Colab 왼쪽 파일 탭에 생성됨

---

## ▶️ Local 실행 방법

### 1. 라이브러리 설치

```bash
pip install numpy pandas matplotlib seaborn opencv-python scikit-learn scipy
```

TensorFlow가 필요하면 추가 설치:

```bash
pip install tensorflow
```

### 2. Jupyter 실행

```bash
jupyter notebook
```

또는

```bash
jupyter lab
```

그 다음 아래 파일을 엽니다:

```text
의료영상_의료인공지능_기초교육_v2.ipynb
```

---

## ▶️ Google Colab 실행 방법

### 방법 1. GitHub에서 바로 열기
1. 이 저장소를 GitHub에 업로드합니다.
2. GitHub에서 `의료영상_의료인공지능_기초교육_v2.ipynb` 파일을 클릭합니다.
3. 상단의 **Open in Colab** 버튼이 보이면 클릭합니다.  
   또는 Colab에서 GitHub 저장소를 직접 열어도 됩니다.

### 방법 2. Colab에 직접 업로드하기
1. [Google Colab](https://colab.research.google.com/) 접속
2. **파일 업로드(Upload notebook)** 선택
3. `의료영상_의료인공지능_기초교육_v2.ipynb` 업로드
4. 위에서부터 순서대로 셀 실행

---

## ⚙️ Colab 권장 실행 순서

### 1. 런타임 설정
- 메뉴: **런타임 → 런타임 유형 변경**
- 가능하면 **GPU** 선택
- CPU만으로도 대부분 실행 가능하나, TensorFlow 실습은 GPU가 더 빠름

### 2. 첫 셀부터 순서대로 실행
가장 안전한 방법은 **위에서 아래로 순서대로 실행**하는 것입니다.

특히 아래 순서를 권장합니다:

1. 환경 설정 셀
2. 공통 import 셀
3. 의료영상 이론 / 시각화 셀
4. 머신러닝 실습 셀
5. TensorFlow 확인 셀
6. CNN / Transfer Learning / U-Net 셀

---

## 🔧 Colab에서 더 안정적으로 실행하려면

기존 노트북 그대로도 실행 가능하지만, Colab에서는 아래처럼 설치 셀을 바꾸면 더 안정적입니다.

### 기본 라이브러리 설치 셀 예시

```python
import sys
import subprocess

packages = [
    "numpy",
    "pandas",
    "matplotlib",
    "seaborn",
    "opencv-python",
    "scikit-learn",
    "scipy"
]

for pkg in packages:
    subprocess.check_call([sys.executable, "-m", "pip", "install", "-q", pkg])

print("기본 라이브러리 설치 완료")
```

### TensorFlow 확인 셀 예시

```python
try:
    import tensorflow as tf
    print("TensorFlow version:", tf.__version__)
except ImportError:
    !pip install -q tensorflow
    import tensorflow as tf
    print("TensorFlow installed:", tf.__version__)
```

---

## 📊 Learning Outcomes

이 자료를 완료하면 다음을 수행할 수 있습니다:

- 의료영상 데이터의 흐름 이해
- 영상 처리 및 시각화 수행
- 머신러닝 / 딥러닝 기본 구조 이해
- CNN, Transfer Learning, U-Net 개념 파악
- 의료 AI 프로젝트의 전체 구조 이해

---

## 📌 Requirements

- Python 기초
- NumPy / Matplotlib 기초
- 딥러닝 입문 수준의 이해가 있으면 더 좋음

---

## 🧑‍🏫 For Educators

이 자료는 다음 용도로 활용 가능합니다:

- 학부 수업 실습 자료
- 의료 AI 입문 강의
- 단기 워크숍 / 부트캠프
- Colab 기반 온라인 실습

---

## 📄 License

Educational use only.
