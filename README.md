# Inception V1
## 다양한 필터 사이즈
### 배경
1. 이미지 안에 타겟의 위치 분포는 다양함
![image](https://user-images.githubusercontent.com/74392995/125406583-f1e7f200-e3f3-11eb-8e83-4dda1b99d47c.png)
### 아이디어
1. 다양한 필터 사이즈(1x1, 3x3, 5x5)를 사용하자! -> 더 "깊게"가 아닌 더 "넓게"
![image](https://user-images.githubusercontent.com/74392995/125408465-e4cc0280-e3f5-11eb-9975-593b0a94bf00.png)
2. 1x1 필터 사용 : 입력 채널의 수를 줄일 수 있으며 cov 연산 후 추가되는 ReLU를 통해 비선형적 특징을 더 추가 가능
![image](https://user-images.githubusercontent.com/74392995/125408812-40968b80-e3f6-11eb-80be-d34bdde74492.png)
## 더 깊은 층
### 배경
1. 층을 깊게 쌓을수록 파라미터 수가 증가해 계산 복잡도가 증가하며 오버피팅의 우려가 생김
2. 층이 깊어질수록 vanishing gradient problem 발생
### 아이디어
1. two auxiliary classifiers : 중간 layer에 auxiliary classifier를 추가하여, 중간중간에 결과를 출력해 추가적인 역전파를 일으켜 gradient가 전달될 수 있게끔 하면서도 정규화 효과가 나타나도록 함
![image](https://user-images.githubusercontent.com/74392995/125410471-df6fb780-e3f7-11eb-8cb3-9bb8196803ad.png)
2. 최종 loss를 계산할 때 모델의 중간 부분의 loss값을 포함
![image](https://user-images.githubusercontent.com/74392995/125410586-ff06e000-e3f7-11eb-846a-df67b0894225.png)
# Inception V2
## 더 작은 필터 사이즈
### 문제점
1. representational bottleneck : 차원을 줄일수록 정보 손실이 커지는 문제 발생
### 아이디어
1. 5x5 convolution을 두개의 3x3 convolution으로 
![image](https://user-images.githubusercontent.com/74392995/125412676-16df6380-e3fa-11eb-9a5d-c664fffe07ff.png)
2. nxn을 1xn과 nx1로 쪼개기
![image](https://user-images.githubusercontent.com/74392995/125414699-fd24bdfa-ecab-4f9a-9da9-1b871df7e1d3.png)
3. nxn을 1xn과 nx1로 쪼개기 + Wider

![image](https://user-images.githubusercontent.com/74392995/125415113-b2775fb5-f6a1-4737-bbe9-c510a1975aeb.png)
# Inception V3
## auxiliary classifiers
### 문제점
1. auxiliary classifiers은 학습초기에 수렴성을 개선시키지 못함
### 아이디어
1. RMSProp optimizer : Momentum optimizer에서 RMSProp optimizer로 바꿈
2. Factorized 7x7 convolutions
3. BatchNorm in the Auxillary Classifiers
4. Label Smoothing : label 을 0또는 1이 아니라 smooth 하게 부여하는 것, 미스라벨링의 오차를 줄여줌
# Inception V4
## auxiliary classifiers
### 문제점
1. 모듈이 너무 복잡해서 형식화(uniform)할 필요가 있음
### 아이디어
![image](https://user-images.githubusercontent.com/74392995/125422217-6b07a81c-9684-4cc1-a949-76924aefd592.png)

