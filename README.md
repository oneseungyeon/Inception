# Inception V1
## 다양한 필터 사이즈
### 배경
1. 이미지 안에 타겟의 위치 분포는 다양함
![image](https://user-images.githubusercontent.com/74392995/125406583-f1e7f200-e3f3-11eb-8e83-4dda1b99d47c.png)
### 아이디어
1. 다양한 필터 사이즈(1x1, 3x3, 5x5)를 사용하자! -> 더 "깊게"가 아닌 더 "넓게"
![image](https://user-images.githubusercontent.com/74392995/125408465-e4cc0280-e3f5-11eb-9975-593b0a94bf00.png)
2. 1x1 필터 사용 : 입력 채널의 수를 줄일 수 있으며 5x5 필터보다 덜 복잡
![image](https://user-images.githubusercontent.com/74392995/125408812-40968b80-e3f6-11eb-80be-d34bdde74492.png)
## 더 깊은 층
### 배경
1. 층을 깊게 쌓을수록 파라미터 수가 증가해 계산 복잡도가 증가하며 오버피팅의 우려가 생김
2. 층이 깊어질수록 vanishing gradient problem 발생
### 아이디어
1. two auxiliary classifiers
![image](https://user-images.githubusercontent.com/74392995/125410471-df6fb780-e3f7-11eb-8cb3-9bb8196803ad.png)
2. 최종 loss를 계산할 때 모델의 중간 부분의 loss값을 포함
![image](https://user-images.githubusercontent.com/74392995/125410586-ff06e000-e3f7-11eb-846a-df67b0894225.png)
# Inception V2
## 더 작은 필터 사이즈
### 문제점
1. representational bottleneck : 차원을 줄일수록 정보 손실이 커지는 문제
### 아이디어
1.5x5 convolution을 두개의 3x3 convolution으로 
![image](https://user-images.githubusercontent.com/74392995/125412676-16df6380-e3fa-11eb-9a5d-c664fffe07ff.png)
2. nxn을 1xn과 nx1로 쪼개기
![image](https://user-images.githubusercontent.com/74392995/125414699-fd24bdfa-ecab-4f9a-9da9-1b871df7e1d3.png)
3. nxn을 1xn과 nx1로 쪼개기 + Wider
![image](https://user-images.githubusercontent.com/74392995/125414762-c6dfc639-4bf0-4b8c-87d8-bf3214f201f6.png)
# Inception V3
## auxiliary classifiers
### 문제점
1.
### 아이디어
1.
