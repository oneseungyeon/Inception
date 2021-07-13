# Inception
## 다양한 필터 사이즈
### 배경
1. 이미지 안에 타겟의 위치 분포는 다양함
![image](https://user-images.githubusercontent.com/74392995/125406583-f1e7f200-e3f3-11eb-8e83-4dda1b99d47c.png)
### 아이디어
1. 다양한 필터 사이즈를 사용하자! -> 더 "깊게"가 아닌 더 "넓게"
![image](https://user-images.githubusercontent.com/74392995/125408465-e4cc0280-e3f5-11eb-9975-593b0a94bf00.png)
2. 1x1 필터 사용 : 입력 채널의 수를 줄일 수 있으면 5x5 필터보다 덜 복잡
![image](https://user-images.githubusercontent.com/74392995/125408812-40968b80-e3f6-11eb-80be-d34bdde74492.png)
## 더 깊은 층
### 배경
1. 층을 깊게 쌓을수록 파라미터 수가 증가해 계산 복잡도가 증가하며 오버피팅의 우려가 생김
### 아이디어
