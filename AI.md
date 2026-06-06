**:white_check_mark: PyTorch란?**  
- 딥러닝 신경망 구축을 위한 오픈소스 프레임워크  
- Torch 머신러닝 라이브러리 + Python API를 결합  
- 쉽고 직관적인 문법을 제공하며, 동적 연산이 가능  

**:white_check_mark: PyTorch vs TensorFlow 비교**  
| 항목 | PyTorch | TensorFlow |
| :---: | :---: | :---: |
| 개발사 | Meta (Pytorch Foundation) | Google |
| 주요 사용처 | 연구, 학계 | 산업, 제품 배포 |
| 장점 | 사전 학습 모델과 문서가 많음 | Google 서비스와 통합 용이 |

**:white_check_mark: PyTorch 저장소 및 사용자 현황**  
- GitHub 및 Hugging Face에서 활발하게 사용됨  
- 연구 커뮤니티에서 선호되며, TensorFlow보다 학습 용이성에서 강점  

**:white_check_mark: PyTorch 사용법**  
**:closed_book: 텐서 (Tensor)**  
- PyTorch의 핵심 데이터 구조  
- NumPy 배열과 유사하지만 GPU 가속이 가능  

**:closed_book: PyTorch 자료형**  
- torch.FloatTensor → 32비트 실수형 텐서  
- torch.IntTensor → 32비트 정수형 텐서  
- torch.cuda.FloatTensor → GPU 가속된 실수형 텐서  

:book: 요약 정리  
- PyTorch는 **컴퓨터 비전, 자연어 처리, 강화 학습** 등 다양한 AI 분야에서 활용되는 딥러닝 프레임워크  
- TensorFlow와 비교했을 때, PyTorch는 동적 연산과 문법이 더 직관적  
- Hugging Face와 같은 플랫폼에서 사전 학습 모델을 쉽게 활용 가능
```
https://huggingface.co/
```
- 텐서(Tensor)는 PyTorch의 핵심 자료형이며, GPU 가속 지원

**:white_check_mark: 경사하강법 (Gradient Descent)**   
:bulb: 손실(Loss)을 최소화하기 위해 파라미터를 조정하는 알고리즘  
- 모델이 **손실이 줄어드는 방향(기울기의 음의 방향)** 으로 이동하며 학습  

**:small_blue_diamond: 핵심 절차**  
1. 예측 계산 → `Yp = W * X + B`  
2. 손실 계산 → `(Yp - Y)²` 평균(MSE)  
3. 경사 계산 → `loss.backward()` (자동미분)  
4. 파라미터 수정 → `W -= lr * W.grad`  
5. 경사 초기화 → `optimizer.zero_grad()`  

**:gear: Optimizer (최적화 함수)**  
- torch.optim.SGD, Adam 등으로 파라미터 자동 업데이트  
- Momentum 사용 시 빠르고 안정적인 수렴  
- 학습률(lr) 조절이 핵심: 너무 크면 발산, 너무 작으면 수렴 지연  

**:white_check_mark: 오차역전파(Backpropagation)**  
- 신경망 학습의 핵심 알고리즘으로, 손실(loss)을 최소화하기 위해 가중치를 조정하는 과정  
- 미분을 이용해 오차를 역으로 전달하여 가중치를 업데이트함  


**:white_check_mark: 활성화 함수(Activation Function)**  
- 뉴런의 출력을 결정하는 함수로, 비선형성을 추가하여 신경망이 복잡한 패턴을 학습할 수 있도록 함  
- 주요 활성화 함수:  
  ◦ **ReLU(Rectified Linear Unit)**: 기울기 소실 문제 해결, 대부분의 딥러닝 모델에서 사용  
  ◦ **Sigmoid**: 0 ~ 1 사이 값 출력, 이진 분류 문제에 사용됨  
  ◦ **Tanh**: -1 ~ 1 사이 값 출력, Sigmoid보다 성능이 좋지만 깊은 신경망에서는 기울기 소실 가능  

**:white_check_mark: 손실 함수 (Loss Function)**  
- 개별 샘플(데이터 한 개)에 대한 오차를 계산하는 함수  
- 모델이 예측한 값과 실제 값 사이의 차이를 측정  

**:white_check_mark: 비용 함수 (Cost Function)**  
- 손실 함수의 평균값을 계산하여 전체 모델 성능을 평가하는 함수  
- 손실 함수가 하나의 샘플을 기준으로 한다면, 비용 함수는 전체 데이터셋을 기준으로 함  

**:white_check_mark: 차이점**  
- **손실 함수**는 개별 데이터 포인트의 오차를 측정  
- **비용 함수**는 데이터 전체에 대한 평균 손실을 계산하여 최적화  

**:white_check_mark: 선형 회귀 (Linear Regression)**  
- 독립 변수(x)와 종속 변수(y) 사이의 **직선 관계**를 모델링하는 회귀 방법  
- **독립변수는 입력값이나 원인/ 종속변수는 결과물(target)**  
- 수식 : y = w x + b 형태  

**:white_check_mark: 다항 회귀 (Polynomial Regression)**  
- 선형 회귀로 설명할 수 없는 **비선형 데이터**를 모델링
- 다항식의 형태로 변형하여 더 복잡한 관계를 학습
- 너무 높은 차수를 사용하면 **과적합(Overfitting)** 발생 가능
- 수식 : y = w₁x + w₂x² + … + b (2차 이상의 다항식 형태)  

**<참고>**  
이진 분류(Binary Classification)는 데이터를 두 가지 범주(예: 0/1, True/False)로 나누는 대표적인 머신러닝 기법입니다. 🤖  
대표적인 알고리즘으로는 **로지스틱 회귀(Logistic Regression), SVM, 시그모이드 기반 모델** 등이 있습니다.  
또한, 분류 모델의 성능을 평가하기 위해  
**Confusion Matrix, Accuracy, Precision, Recall, F1-score, ROC Curve**와 같은 다양한 지표를 활용합니다. :bar_chart:  
특히 중요한 점은, **모델 자체도 중요하지만 문제의 목적과 상황에 따라 적절한 평가 지표를 선택하는 것**입니다. :point_up:  
예를 들어, 오류를 줄이는 것이 중요한지, 놓치는 것을 줄이는 것이 중요한지에 따라 핵심 지표가 달라질 수 있습니다.  

**:pushpin: CNN(Convolutional Neural Network)**  
**:closed_book:CNN이란?**  
- 이미지, 영상 인식에 특화된 딥러닝 모델  
- 패턴과 공간적 구조를 효과적으로 학습  

**:book:주요 구성 요소**  
- 합성곱 층(Convolutional Layer)  
  ◦ 필터(커널)를 사용해 특징 추출  
  ◦ 중요한 시각적 패턴 감지 (예: 가장자리, 윤곽)  

- 풀링 층(Pooling Layer)  
  ◦ 특징 맵 크기 축소 (다운샘플링)  
  ◦ 연산량 감소 및 중요한 정보 유지 (예: 최대 풀링)  

- 완전 연결 층(Fully Connected Layer, FC)  
  ◦ 최종 분류 작업 수행  
  ◦ Flatten을 거쳐 1차원 형태로 변환 후 출력  

- 활성화 함수(Activation Function)  
  ◦ 비선형성을 추가하여 복잡한 패턴 학습  
  ◦ 주로 ReLU(Rectified Linear Unit) 사용  

- 손실 함수(Loss Function) & 옵티마이저(Optimizer)  
  ◦ 예측 값과 실제 값 차이를 줄이기 위해 사용  
  ◦ 분류 문제에서는 주로 Cross-Entropy Loss 활용  

**:white_check_mark: 최적화 알고리즘 (Optimization Algorithm)**  
신경망 학습 과정에서 가중치(W)와 편향(b)를 업데이트하여 손실을 최소화하는 방법입니다.  

**:small_blue_diamond: 대표적인 최적화 알고리즘**
• 경사 하강법 (Gradient Descent)  
 → 전체 데이터를 기반으로 한 번에 업데이트 (안정적이지만 느림)  
• 확률적 경사 하강법 (SGD)  
 → 샘플 단위로 업데이트 (빠르지만 진동 가능성 있음)  
• 모멘텀 (Momentum)  
 → 이전 업데이트를 반영하여 학습 속도 개선  
• Adam (Adaptive Moment Estimation)  
 → Momentum + RMSprop 결합  
 → 학습률 자동 조정으로 빠르고 안정적인 학습 가능 (가장 많이 사용)  

**:closed_book: Pooling Layer**  
-> CNN(Convolutional Neural Network)에서 Pooling Layer는 특징을 추출하고 차원을 축소하는 역할을 합니다.  
- Max Pooling: 각 필터 영역에서 최댓값을 추출  
- Global Average Pooling: 전체 필터에서 평균을 계산하여 크기를 줄임  
- Adaptive Average Pooling: 입력 크기에 관계없이 고정된 크기의 출력을 생성  

**:closed_book:사전 학습(Pre-trained)된 CNN 모델**  
**:book: 이미지 분류 vs 객체 검출 (Image Classification vs Object Detection)**  
- 이미지 분류(Image Classification): 이미지 내에서 무엇이 있는지 식별  
- 객체 검출(Object Detection): 이미지에서 여러 객체를 찾아 위치까지 식별  

**:book: LSVRC (Large Scale Visual Recognition Challenge)**  
- Imagenet 챌린지에서 CNN 모델들이 평가됨  
- CNN의 성능을 높이기 위한 주요 기능  
  ◦ ReLU (Rectified Linear Unit) 활성화 함수 사용
  ◦ Dropout 적용하여 과적합 방지
  ◦ Max Pooling 활용
  ◦ 데이터 증강 (Data Augmentation) 기법 적용
  ◦ 딥러닝을 활용한 성능 개선

**:closed_book: CNN의 발전 과정**  
**:book: LeNet (1989)**  
- 필기체 인식 모델  
- AT&T 벨연구소에서 개발됨  
- 기본적인 CNN 구조의 기초가 된 모델  

**:book: AlexNet (2012)**  
- 이미지넷(Imagenet) 대회에서 우승한 모델  
- 기존 네트워크보다 훨씬 깊은 구조로 CNN을 대중화함  
- 주요 특징  
  ◦ **Tanh → ReLU** 활성화 함수 변경 (학습 속도 개선)
  ◦ **Dropout**을 적용하여 과적합 방지
  ◦ **Average Pooling → Max Pooling** 변경 (성능 향상)
  ◦ **데이터 증강(Data Augmentation)** 활용
  ◦ **Local Response Normalization(LRN)** 사용
  ◦ **Kernel size**: (96, 3, 11, 11)  

**:book: GoogLeNet (2014)**  
- **기본 아키텍처**: 기존 CNN보다 깊은 모델  
- **Naive Inception**: Inception 구조의 초기 버전  
- **Inception Module**: 여러 크기의 필터를 병렬로 적용하여 특징을 더욱 효과적으로 추출  
- **Auxiliary Classifier**: 중간 레이어에서 보조적인 분류기를 추가하여 학습 안정화  
- **Global Average Pooling**: 전체 레이어에서 평균을 계산하여 최종 출력을 만듦  

- ResNet(Residual Network)은 딥러닝 신경망이 깊어질수록 발생하는 성능 저하(기울기 소실 문제)를 해결하기 위해 고안된 CNN 모델
ResNet의 필요성 (기울기 소실 문제)
- 역전파 시, 기울기(Gradient)가 계속 작아져 가중치 업데이트가 제대로 되지 않음 (기울기 소실 문제)

- ResNet의 핵심: Residual Block (잔차 블록)  
  **:bulb: 기존 신경망과 차이점:**  
    ◦ 일반적인 CNN은 입력 → 합성곱 → 활성화 함수 → 출력의 방식으로 진행됨  
    ◦ ResNet은 입력 → 변환(합성곱+ReLU) → 출력뿐만 아니라, 입력을 그대로 더하는 Skip Connection을 추가  

- ResNet vs CNN  
| 모델 | 주요특징 | 학습 가능 깊이 | 성능 |
| :--- | :--- | :--- | :--- |
| 기본 CNN | 단순한 합성곱 + 풀링 구조 | 깊어질수록 저하 | 기본 이미지 분류 |
| VGGNET | 깊은 CNN구조 (16~19층) | 깊음, 파라미터 많음 | 속도 느림 |
| ResNet | Skip Connection 사용 | 수백 개 층 가능 | 빠르고 높은 성능 |  

**📌 전이 학습 (Transfer Learning)**  
전이 학습은 **기존에 학습된 모델(사전 학습된 모델, Pre-trained Model)의 가중치를 그대로 가져와 새로운 데이터셋에 적용하는 기법**,  
데이터가 부족할 때 강력한 모델을 빠르게 학습가능  

**:white_check_mark: 전이 학습 과정**  
1. 사전 학습된 모델 로드  
2. 기존 네트워크의 가중치를 유지한 채 새로운 데이터셋에 적용  
3. 출력층(분류기)만 변경하여 새로운 데이터에 맞게 학습  

**:white_check_mark: 장점**  
1. 학습 데이터가 적어도 높은 성능  
2. 학습 속도가 빠르고 계산 비용 절감  

**:white_check_mark: 전이 학습 적용 예시**  
**자연어 처리(NLP)**: BERT, GPT 등의 모델을 활용하여 챗봇 구축  

**📌 파인 튜닝 (Fine-tuning)**  
파인 튜닝(Fine-tuning)은 **전이 학습에서 일부 레이어의 가중치를 업데이트하여 특정 데이터셋에 맞게 미세 조정하는 방법**,  
기본적인 특징은 유지하면서, 새로운 데이터에 맞게 모델을 더 정교하게 학습  

**:white_check_mark: 파인 튜닝 과정**  
1. 사전 학습된 모델 로드  
2. 일부 층의 가중치만 업데이트하도록 설정  
3. 새로운 데이터셋으로 학습

**:white_check_mark: 장점**  
1. 모델을 완전히 처음부터 학습할 필요 없이, 기존 가중치를 활용하면서도 최적화 가능  
2. 도메인(특정 문제)에 맞게 더욱 정밀한 성능을 기대  

**:white_check_mark: 파인 튜닝 적용 예시**  
**의료 영상 분석**: 일반적인 이미지 분류 모델을 CT/MRI 분석에 맞게 조정  

**:pushpin: OpenCV**  
OpenCV(Open Source Computer Vision Library)는 오픈소스 컴퓨터 비전 및 영상 처리 라이브러리.  
다양한 프로그래밍 언어(C++, Python 등)에서 지원되며, 실시간 영상 처리 기능을 제공함.  

- 화소(Pixel)란?  
디지털 이미지는 작은 정사각형 셀(픽셀)들의 집합으로 구성됨.  
각 픽셀은 색상 정보를 저장하며, 해상도가 높을수록 더 많은 픽셀을 포함함.  

- 색상공간
RGB (Red, Green, Blue)  
BGR (Blue, Green, Red) → OpenCV 기본 사용  
HSV (Hue, Saturation, Value) → 색상 기반 처리에 유리  
Grayscale (흑백) → 밝기 값(0~255)만 저장  

- 픽셀 값과 색상 표현  
컬러 이미지 (RGB, BGR): 픽셀당 3개 값 (예: R=255, G=0, B=0 → 빨간색)  
흑백 이미지 (Grayscale): 픽셀당 1개 값 (예: 0 → 검정, 255 → 흰색)  

- OpenCV의 주요 기능  

**:book: 이미지 처리**  
  - 이미지 읽기/쓰기 (`cv2.imread()`, `cv2.imwrite()`)  
  - 색상 변환 (`cv2.cvtColor()`)  
  - 이미지 필터링 (`cv2.GaussianBlur()`, cv2.medianBlur()`)  
  - 히스토그램 분석 (`cv2.calcHist()`)

**:book:  영상 처리**  
  - 동영상 프레임 처리 (`cv2.VideoCapture(`)  
  - 배경 제거 및 모션 감지  
  - 엣지 검출 (`cv2.Canny()`)  

**:book: 객체 검출**  
  - 얼굴 및 눈 검출 (`cv2.CascadeClassifier()`)
  - YOLO, Faster R-CNN과 연계한 객체 검출
  - 딥러닝 기반 이미지 인식 (`DNN` 모듈 활용)

**:book: 영상 변환 및 기하학 연산**  
  - 이미지 크기 변경 (cv2.resize())  
  - 회전 (cv2.rotate())  
  - 변형 (cv2.warpAffine(), cv2.warpPerspective())  

**:closed_book: 색 공간 변환**  
```
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)  # 흑백 변환
hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)  # HSV 변환

# BGR → GRAY, HSV, LAB 등 다양한 색공간 변환 가능
```

**:white_check_mark: 객체 검출 기본 개념**  
- **객체 검출(Object Detection)**  
  ◦ 영상/이미지 안에서 관심 있는 **물체의 위치 + 영역** 찾기  
  ◦ 분류(Classification)는 “무엇인지”만, 검출은 “어디에 있는지”까지  
- **접근 방식**  
  ◦ 전통적 방식: 에지, 코너, 특징점, 템플릿 매칭, 컨투어 등  
  ◦ 딥러닝 방식: YOLO, SSD, Faster R-CNN 등  

**:white_check_mark: 에지 기반 검출**  
- **에지(Edge)**  
  ◦ 밝기가 급격히 변하는 부분 → 물체의 윤곽선에 해당  
- **Canny 에지 검출**  
  ◦ 노이즈 제거(블러) → 그래디언트 계산 → 비최대 억제 → 히스테리시스 임계값  
- **컨투어(Contour) 활용**  
  ◦ 에지로부터 외곽 윤곽선(contour)을 추출  
  ◦ 윤곽선을 기반으로 객체를 감싸는 직사각형 또는 회전된 최소 박스를 계산  
  ◦ 단순한 물체(사각형 박스, 물체 영역 검출)에 활용  

**:white_check_mark: 코너 & 특징점 기반 검출**  
**:small_blue_diamond: 해리스 코너(Harris Corner) 검출**  
- 코너(Corner)  
  ◦ x, y 방향으로 모두 밝기 변화가 큰 지점  
  ◦ ⇒ **물체 특징을 잘 대표**하는 포인트 → 움직임 추적, 매칭에 유리  
- 아이디어 요약  
  ◦ 작은 윈도우를 움직이며 **밝기 변화량(에너지)** 계산  
  ◦ 윈도우를 어느 방향으로 움직여도 변화가 크면 → 코너  

:small_blue_diamond: Shi-Tomasi (Good Features to Track)  
- 해리스와 유사한 구조, 다만 **코너 품질 평가 방식** 개선  

**:white_check_mark: 객체 검출 흐름 예시 :gear:**  
- ① 그레이스케일 변환 + 블러로 노이즈 완화  
- ② Canny 에지 + 컨투어로 대략적인 물체 영역 찾기  
- ③ 영역 안/전체 이미지에서 Harris / Shi-Tomasi로 특징점(코너) 추출  
- ④ 특징점 매칭, 추적, 템플릿 매칭 등과 결합해 객체 검출/추적  

**:book: Mean Shift 알고리즘**  
- 개념: 히스토그램의 중심이 어디로 이동해야 밀도가 높은지를 계산하는 방식  
  ◦ 대상의 색 분포 기반으로 추적  
  ◦ 대상 크기 변화는 반영 불가  

**:book: RGB 기반 Mean Shift**  
- 색상 공간에서 히스토그램(분포)을 계산하여 유사한 색상 영역으로 이동  
- HSV 또는 YCrCb 컬러 공간이 더 일반적으로 사용되기도 함  

**:book: Camshift 알고리즘 (Continuously Adaptive Mean Shift)**  
- MeanShift의 확장 버전  
- 대상 크기, 방향 변화도 자동으로 추적  
- 얼굴 인식, 손 추적 등에서 활용  

**:book: Optical Flow (광류)**  
- 물체의 이동 방향과 속도를 추정하는 기법  
- 연속된 프레임 간의 픽셀 움직임을 계산  

**:book: Lucas-Kanade Optical Flow**  
- Optical Flow의 대표 알고리즘  
- 일정 영역 내에서 픽셀 변화량이 일정하다는 가정  
- 연산량이 적고 빠름, but 큰 움직임엔 약함  

**:book: Dense Optical Flow (Farneback 알고리즘)**  
- 모든 픽셀에 대해 이동 벡터를 계산  
- 전체 영상 흐름 분석에 유용  

**:book: Polar 좌표 변환 (각도 + 크기 표현)**  
- Optical flow 결과를 벡터(방향/크기)로 표현하기 위해 사용  
- `cv2.cartToPolar()` 함수로 구현 가능  

**:book: RAFT (Recurrent All-Pairs Field Transforms)**
- 최신 Optical Flow 모델 중 하나  
- 모든 픽셀 쌍 간의 거리와 연관성을 반복적으로 계산  
- 높은 정확도와 성능 (deep learning 기반)  

**:white_check_mark:GAN (Generative Adversarial Network)**  
- 생성자(Generator)와 판별자(Discriminator) 두 네트워크가 경쟁하며 학습  
- Generator: 가짜 데이터를 만들어 실제처럼 보이게 함  
- Discriminator: 입력된 데이터가 진짜인지 가짜인지 판별  
- 두 모델이 서로 경쟁하면서 발전 → 점점 더 정교한 데이터 생성 가능  
- 주요 활용: 이미지 생성, 스타일 변환, 데이터 보강 등  

**:heavy_check_mark:학습 목표:**  
- 생성자는 판별자를 속이는 것이 목표  
- 판별자는 생성자의 가짜 데이터를 잘 걸러내는 것이 목표  


**:white_check_mark:DCGAN (Deep Convolutional GAN)**  
- GAN에 합성곱 신경망(CNN)을 적용한 구조  
- 기존 GAN의 불안정한 학습 문제를 개선  
  ◦ 주요 특징:Fully connected layer 대신 Convolutional layer 사용  
  ◦ Generator에서 Transposed Convolution(역합성곱) 사용하여 이미지 크기 확대  
  ◦ Batch Normalization 적극 활용  
  ◦ ReLU, LeakyReLU 활성화 함수 사용  
  ◦ Pooling layer 제거  
- 더 안정적이고 고품질의 이미지 생성 가능  
- 주요 활용: 얼굴 생성, 침실 이미지 생성 등  

**:white_check_mark:VAE (Variational Autoencoder)**  
- GAN과 다른 방식의 생성 모델 (적대적 학습 X)  
  ◦ 구조:Encoder: 입력 데이터를 잠재 공간(latent space)으로 압축  
  ◦ Decoder: 잠재 공간에서 데이터를 복원/생성  
  ◦ 핵심 개념:잠재 공간을 확률 분포(주로 정규분포)로 모델링  
  ◦ 입력을 평균(μ)과 분산(σ)으로 인코딩  
  ◦ Reparameterization trick을 통해 역전파 가능  
- 손실 함수: Reconstruction Loss + KL Divergence  
  ◦ Reconstruction Loss: 원본과 복원 이미지의 차이  
  ◦ KL Divergence: 잠재 분포가 정규분포에 가까워지도록 규제  
- 장점: 학습이 안정적이고, 잠재 공간이 연속적이어서 보간(interpolation) 가능  
- 단점: GAN보다 생성 이미지가 흐릿한 경향  
- 주요 활용: 이미지 생성, 이상 탐지, 데이터 압축 등  

**:closed_book: Neural Radiance Fields (NeRF)**  
- 정의: 3D 장면의 외관을 신경망으로 학습하여, 새로운 시점에서 해당 장면을 렌더링할 수 있는 딥러닝 기반의 기술  
- 입력: 위치 (𝑥, 𝑦, 𝑧)와 시선 방향 (𝜃, 𝜙)  
- 출력: 색상(RGB)과 밀도(σ)  
- 특징: 카메라 여러 뷰에서 학습한 장면을, 보지 않은 각도에서도 사실적으로 재구성 가능  
- NeRF는 Volumetric rendering을 기반으로 하며, 입력 위치를 주기적으로 변환하는 Positional Encoding 기법도 사용합니다 (→ 고주파 세부묘사 학습 가능)  

**:closed_book: 3D Mesh & Polygon Modelling**  
- **3D Mesh**: 삼각형 기반의 표면 표현 방식  
- **Polygon modelling**: 3D 물체를 면 단위로 구성하는 방식  
- CAD, 게임 그래픽, 3D 스캔 등에서 사용  
- Mesh는 **명시적 표면 표현**/ NeRF는 **암묵적 함수 표현** → surface가 아닌 volume을 모델링  

**:closed_book: NeRF Architecture**  
- 구성 요소  
  ◦ **Positional Encoding**: MLP의 한계를 보완해 고주파 함수 표현 가능, 위치를 고차원으로 사영하여 표현력 향상  
  ◦ **Hierarchical Sampling**: coarse → fine sampling을 통해 효율적 렌더링 수행  

**:closed_book: Volume Rendering**  
- **NeRF의 핵심 과정**  
- **Ray 방향**으로 샘플을 추출하고, 해당 위치의 RGB/σ를 조합해 픽셀 색 계산  
- 투과율 T(t), 가중치, 누적 함수 등을 수학적으로 사용  

**:closed_book: Pinhole Camera Model**  
- 카메라 모델로, 3D 세계의 점을 2D 평면에 투영  
- 투영 식  
  ◦ x = fX/Z,  y = fY/Z  
  ◦ **f: focal length, Z: depth**  

**:closed_book: Ray Generation (TinyNeRF 예시)**  
- 픽셀마다 ray를 생성하여 3D 공간에 발사  
- 각 ray의 origin과 direction이 필요  
- NeRF 학습 시, ray 단위로 데이터를 구성  

**:closed_book: Gaussian Splatting**  
- **NeRF의 실시간성 한계**를 보완하기 위한 **속도 중심의 대안**  
- **3D Gaussian 분포**로 장면을 표현하고, 화면에 splat(퍼뜨리기) 방식으로 빠르게 렌더링  
- 복잡한 scene도 수천 개의 3D Gaussian으로 압축 표현  
- Neural Field보다 훨씬 빠르며 실시간 애플리케이션에 적합  
- 빠르고, 압축 가능하며, 품질도 우수  

**:closed_book: Multivariate Gaussian PDF**  
- Gaussian Splatting에 사용되는 **3D Gaussian 분포의 수학적 모델링**  
- 위치, 크기, 방향성(공분산) 등을 포함한 확률 밀도 기반 표현  

**:closed_book: Structure from Motion (SfM)**  
- 여러 시점의 사진에서 카메라 위치와 3D 구조 복원  
- NeRF의 데이터 수집/사전 처리 단계에서 활용됨 (카메라 포즈 추정)  

**:closed_book: XAI란?**  
설명 가능한 AI (XAI, Explainable AI)는 인공지능 모델의 예측 결과나 의사 결정 과정을 **사람이 이해할 수 있도록 설명**해주는 기술 또는 접근 방식  
기존의 AI 모델, 특히 딥러닝 모델은 "블랙박스"처럼 작동하여, 그 내부 결정 과정이 복잡하고 불투명하여 **왜 그런 결정을 내렸는지** 이해하기 어려운 경우가 다수 존재  
-> XAI는 이러한 문제를 해결하려는 접근 방식  

**:closed_book: XAI의 주요 목표**  
- **투명성**: AI가 어떤 기준으로 결정을 내렸는지 설명할 수 있어야 함  
- **신뢰성**: 사용자가 AI의 예측이나 결정을 신뢰할 수 있도록 함  
- **공정성**: AI 모델의 결정을 공정하고 편향 없이 이해할 수 있게 만듦  
- **책임성**: 모델이 잘못된 결정을 내릴 경우, 그 원인과 책임을 명확히 할 수 있어야 함  

**:closed_book: XAI의 종류**  
- **CAM (Class Activation Mapping)**: 모델이 예측을 내릴 때 중요한 이미지 부분을 시각화하여 설명  
- **Saliency Map**: 모델 예측에 중요한 특징을 강조하여, 각 입력 특성이 얼마나 중요한지 보여줌  
- **Integrated Gradients**: 각 특성이 예측에 미친 영향을 기울기를 통해 통합하여 계산하는 방법  
- **DeepLift**: 기준값과 비교하여 각 특성의 기여도를 계산하여 예측을 설명  

**:closed_book: 주요 기법**  
**:book: 모델에 독립적인 기법 (Model-agnostic)**  
　◦ LIME: 특정 예측 결과를 설명하기 위해 간단한 선형모델 근사  
　◦ SHAP: 각 특성이 결과에 얼마나 영향을 주었는지 수치화  
**:book: 모델 내부 기반 기법 (Model-specific)**  
　◦ Grad-CAM: CNN 모델의 이미지 분류 시, 주목한 영역 시각화  
　◦ Attention 시각화: Transformer 모델이 어떤 토큰에 집중했는지 시각적으로 확인  

**:closed_book: LLM 기반의 XAI 기법**  
- 대규모 언어 모델(LLM, 예: GPT, Claude, Gemini 등)을 활용하여 보다 직관적인 xai 가능성  
    ◦ 자연어 설명 생성 : LLM이 예측 결과에 대해 사람이 이해할 수 있는 설명문을 직접 생성  
    ◦ Chain-of-Thought 유도 : 판단 과정을 명시적으로 드러내도록 유도하여 투명성 확보  
    ◦ 질문-응답 기반 해석 : 사용자가 "왜 이 결과인가요?"라고 질문하면, LLM이 근거를 생성  
    ◦ Multimodal 해석 : 이미지+텍스트 복합 입력에 대한 해석까지 가능 (예: GPT-4V, Gemini 등)  

**:closed_book: XAI의 도전 과제**  
- **복잡한 모델**: 딥러닝처럼 복잡한 모델은 여전히 설명하기 어려운 경향이 있음, 모델이 예측을 내리는 방식을 간단히 설명하는 것은 여전히 쉽지 않음  
- **설명 가능성과 성능의 트레이드오프**: 해석 가능한 모델은 때때로 성능이 낮을 수 있기 때문에, 설명 가능성과 모델 성능 간의 균형을 맞추는 것이 풀어야 할 숙제  

**:closed_book: 객체 검출(Object Detection)이란?**  
- 이미지에서 객체를 찾아 위치(Bounding Box)를 지정하고, 해당 객체를 분류하는 작업  
- 컴퓨터 비전 분야의 핵심 기술 중 하나로, 자율주행, 의료 영상 분석, 보안 시스템 등에 활용  

**:closed_book: 객체 검출 모델 분류**
**:book: Two-Stage Detector (R-CNN 계열)**  
- R-CNN (2014)  
- Fast R-CNN  
- Faster R-CNN  
- Mask R-CNN (Instance Segmentation 포함)  
-> **Two-Stage Detector**: 객체의 후보 영역(Region Proposal)을 먼저 찾고, 분류 및 박스 조정 수행  

**:book: One-Stage Detector (YOLO, SSD 계열)**  
- YOLO (You Only Look Once) 시리즈  
- SSD (Single Shot Multibox Detector) 시리즈  
- RetinaNet  
-> **One-Stage Detector**: CNN 기반으로 객체 위치를 바로 예측. 빠르지만 정확도가 낮을 수 있음  
  
**:closed_book: R-CNN의 단계**  
1. **Region Proposal (후보 영역 생성)**  
- 이미지를 작은 영역으로 나눈 후, 특정 영역을 선택하는 방식  
- Selective Search 기법 사용 (Graph-based segmentation → Region Merging → 후보 영역 선택)
2. **Feature Extraction (특징 추출)**  
- AlexNet (2012)을 사용하여 PASCAL VOC 데이터셋에서 사전 학습 후 특징 벡터 생성  
3. **SVM을 이용한 객체 분류**  
- CNN에서 추출한 특징을 SVM(Support Vector Machine)을 사용하여 객체 분류 수행  
4. **Bounding Box Regression**  
- 객체 위치(Bounding Box)를 보정하는 추가적인 회귀 모델 사용  

**:closed_book: Faster R-CNN 단계**  
**:book: RPN (Region Proposal Network)**  
- 기존 Selective Search 대신 CNN 기반의 Region Proposal 생성  
- Anchor Boxes를 활용하여 다양한 크기의 객체를 탐색  
- Bounding Box 좌표를 조정하여 최적화
  
**1. Anchor Target Generation**  
- 여러 크기의 Anchor Box를 생성하여 객체 위치 예측
- 
**2. GT(Ground Truth) 박스와 IOU(Intersection Over Union) 계산**  
- 실제 객체의 위치와 예측된 Anchor Box 간의 IOU 값을 계산하여 최적의 박스를 선택
- 
**3. Proposal 생성**  
- 최적화된 후보 영역을 선별하여 객체 검출 수행  






