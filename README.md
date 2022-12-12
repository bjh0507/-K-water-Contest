# [2022 제2회 K-water AI 경진대회] 상수도 수요예측 AI 알고리즘
![image](https://user-images.githubusercontent.com/90167432/205447766-187fc487-6a78-41dd-9f74-fb03ad615792.png)

- 주최측 : 수자원공사 k-water
- 참여 TASK : TASK1(경상북도 김천시 율곡동 배수지별 유량 적산차 예측)
- 참여 인원 : 4명
- 시작일 : 2022년 11월 24일 ~

## 데이터 전처리
- train 데이터

![image](https://user-images.githubusercontent.com/90167432/206382966-9cae60b4-b254-49b8-a783-4567480e1678.png)

- test 데이터

![image](https://user-images.githubusercontent.com/90167432/206383013-0a04af21-094c-4fab-9429-9705b6c9e868.png)

- 정답 label 데이터

![image](https://user-images.githubusercontent.com/90167432/206383102-8d1bfc3c-dae7-4060-ac04-52a0ace2cbd3.png)
  - 이상치로 인해 모델 학습이 제대로 이뤄지지 않아 이상치에 해당하는 적산차 값을 삭제 대신 직전 값으로 대치 (시계열 데이터이기 때문에 마음대로 삭제하면 안된다고 판단)

## 모델
1. LSTM : 배지혜

2. GRU : 강지아

3. LightGBM : 이준형 


## 최종 모델
- LSTM
  - input size : (50,9) 행렬
    - 이전 50개 행을 토대로 학습을 진행, 예측 수행
  - hidden layer 수 : 2개
    - 활성화 함수 : relu 사용
  - mae값 : 93
