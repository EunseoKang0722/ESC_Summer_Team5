# ESC_Summer_Team5
ESC_20Summer_5조
빅콘테스트: KBO 정규시즌 팀별 승률, 타율 및 방어율(평균자책점) 예측

 스포츠투아이에서 제공하는 야구데이터(팀 통산 전적자료, 연도별 전적자료, 팀 및 선수 기록 등)를 활용하여 경진대회 종료 이후, 정규시즌 잔여 경기에 대한 각 팀별 승률, 타율 및 방어율(평균자책점) 예측

## 0810 회의

[NA처리]
선수 한 명 연봉 missing value

[팀전력]
1) 타율 방어율 승률 세 가지 지표를 따로 따로 예측하는게 어떤지
2) 타자는 안빠지고 투수는 순서대로 들어감.
3) 선수전력대신 팀전력을 쓰자는 이야기. 실제 팀전적을 많이 쓴다.
4) 특정 타자와 특성 투수가 만나느냐의 크롤링은 나중에 생각.

[승/패]
1) 기존변수와 파생변수간의 상관관계(Heatmap) 분석 후 상관관계가 높은 기존변수들은 제거 
2) 스케일링 안된 변수들 스케일링
3) 최종변수들을 이용해 FA 등의 방법으로 차원축소 진행.
4) 최종변수들은 비지도학습을 통해 군집분석 진행. -> 범주변수 추가하는 형태로

변수추가 -> PCA -> 분류 -> EDA

지표추가, X변수 예측방법 : 강은서, 최정윤 <br>
상관관계분석 및 스케일링 : 오정헌 <br>
군집분석 : 서경덕 <br>
예측 -> 모든 변수로 예측 : 정권상

~수요일 낮 12시 <br>
~금요일 낮 12시 <br>
~토요일 새벽 4시 <br>
~월요일 밤 7시

* train/test split 할 때 비율생각해야함. 코로나 이후의 경기는 더 많이 경기가 진행되기 때문이다.

[타율/방어율]
타율과 방어율은 팀vs선발투수의 유형을 나눠서 해보겠다는 아이디어.




## [8/17] 회의 기록

[경덕 논의점]
1) (파생변수들 말고) 기존 변수들을  scaling 해서 다시 나눠졌을 때 제대로 될지....?
2) 타자지표는 factor가 의미있게 나눠졌는데, 투수는 그렇지 않다. 어떻게 해야할지...?
 --> factor 개수가 4개라 의미가 없을 수도? 
3) clustering 경계 라인이 직선이 아니라 곡선이라 해석을 어떻게 해야할지. decision boundary를 어떻게 해석?
 --> decision boundary 해석 굳이 필요 없다...
  
[권상 논의점]
-factor 스케일링

[승률 예측 모델] 
- WLS 무승부 제외하고 승패만 고려 or 승/패/무 모두 고려
- 경기별 factor 자체를 예측
- 최근 경기에 대한 가중치를 더 높게
- input 변수를 무엇으로 줄지가 문제 
   (홈팀 여부(=초말여부), 날짜(그당시의 등수), (경기시간?), 상대팀, 최근 5경기의 승패여부(한 경기씩 예측하면서 전적에 추가; LSTM??), 그때까지의 팀전력 데이터(팀타율) )
- 일단은 머신러닝으로 예측 (토요일까지)

[타율 예측 모델]
- 타율 예측 모델 DNN  * *'딥러닝과 통계 모델을 이용한 T-커머스 매출 예측' 참고* *
  ; layer 쌓는 방식을 생각해야.
  ; svd로 희박한 데이터 문제 처리 고민  
   
  
[투수력 예측 모델] 



### 8/17 역할 분담
- 기존변수 스케일링(min-max scaling) + 쳐내기 전 lasso +  상관관계 높은것 제외할 것 뽑기; Y는 무승부 빼기+ 승률예측: 
 --> 2명 은서, 권상
- X 변수 예측팀: 방어율/타율/factor 예측 
 --> 2명: 경덕, 정헌, (정윤)
- 발표 1명 정윤

## ***[8/24 회의 기록]***
- 스케일링: 타자, 투수 지표에 사칙연산 적용하기 이전에 NaN이나 Inf값 미리 0으로 변환
- 타자: PA 예측 후 PA에 일정 비율을 곱하여 잔여 지표 계산
- 투수: INN2 예측 후 INN2에 일정 비율을 곱하여 잔여 지표 계산
- 득점: 팀타자지표 + 상대 팀투수지표 결합하여 예측
- 실점: 팀투수지표 + 실책(팀타자지표) 결합하여 예측
- 승률: 피타고리안 승률 사용하여 예측

### 8/24 역할 분담
- 변수 스케일링: 정윤
- 타자/투수 지표 예측: 권상, 정헌
- 득점/실점 예측: 경덕, 은서

## 9/3 회의기록
### 9/3 역할 분담 (~ SUN) 맞습니까?
day별로 정렬 먼저하고 전체 188개로 하기~.~ 

- 권상 PA, BF: Prophet으로 예측한 결과 업로드
- 경덕 비율: (2019후반기 기준으로 최적의 k 찾기)
- 모델: 19년 후반기 득, 실점예측
정헌 득점모형 - 잘다듬어보도록 <br>
정윤(Bayesian opt) 실점모형 - lightgbm


