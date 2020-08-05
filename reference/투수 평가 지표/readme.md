**세이버 매트릭스 관련 참고용 사이트**
https://namu.wiki/w/%EC%95%BC%EA%B5%AC/%EA%B8%B0%EB%A1%9D%20%EA%B3%84%EC%82%B0%EB%B2%95?from=%EC%95%BC%EA%B5%AC%EC%9D%98%20%EA%B8%B0%EB%A1%9D%20%EA%B3%84%EC%82%B0%EB%B2%95

http://ko.yagongso.wikidok.net/wt/PageList/Category/5951313c43e5245120b0032f

nc 블로그: 투수/수비지표 계산법
https://blog.ncsoft.com/%EC%95%BC%EA%B5%AC-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B6%84%EC%84%9D-10-%EC%95%BC%EA%B5%AC-%EC%A7%80%ED%91%9C-%EA%B3%84%EC%82%B0%EB%B2%95-%ED%88%AC%EC%88%98-%EC%88%98%EB%B9%84-%EC%A7%80%ED%91%9C/


**1.	ERA (Earned Run Average; 방어율, 평균자책점)** 

: +) ER (Earned Run)=자책점: 투수의 잘못으로 내준 점수

- ERA는 9이닝 당 ER의 비율을 의미. 
- 가장 보편화된 투수 평가 기준이지만, 팀 전체의 문제인 실점을 투수만의 통계량으로 취급하는 모순이 존재.
- ERA = 9 * ER/ IP; 9 * ER/(INN2/3) (개인투수 파일에서 INN2는 이닝 * 3을 나타내므로 잘 계산해야할듯!)
- *ERA는 낮을수록 좋음!*


**2. K/9: 9이닝당 탈삼진 개수** 

: 9이닝 동안의 탈삼진 개수, 9로 표시하는 이유는 9이닝을 기준으로 하기 위함.
- K/9= 9 * K/IP ; 9 * KK/(INN2/3)
- *K/9는 높을수록 좋음!*


**3.	BB/9 : 9이닝당 볼넷 개수 (고의사구 포함)**

: 9이닝 동안 허용한 볼넷의 개수를 뜻함. 투수의 제구력을 평가하는 기준
- BB/9 = 9 * BB/IP ; 9 * BB/(INN2/3)
- *BB/9는 낮을수록 좋음!*

**+) BB/9: (고의사구 제외한 9이닝 당 볼넷 개수)**

- BB/9= 9 * nBB(고의사구 제외한 볼넷 개수)/IP ; = 9 * (BB-IB)/(INN2/3)

**4.	K/BB (볼삼비):**

:탈삼진/볼넷 수
- K/BB = K/BB ; KK/BB
- *높을수록 좋은 지표인듯*

**5.	WHIP (Walks plus Hits devided by Innings Pitched; 이닝 당 출루 허용)**

: 이닝 당 볼넷과 안타를 투수가 내주는 것을 의미하는 통계량. 가장 보편적
- >> 2016~2018 한국프로야구 세이버 메트릭스 지표 분석 에서는 16년과 18년도에는 WHIP이 팀 성적과 높은/통계적으로 상관관계를 보였음을 확인함
- WHIP= (H+BB)/IP ; = (HIT+BB)/(INN2/3)
- *WHIP의 값이 적을수록 좋음!* ; 1.1 이하는 특급 투수 취급

**6.	BABIP (Batting Average on Ballse In Play; 인플레이 타구 피안타율)**

: 인플레이로 이어진 타구에 대한 타율을 계산. 홈런은 제외하고 계산 (홈런은 플레이가 종료된 상황이라고 간주하기 때문.)
- 투수 성적에 운이 얼마나 개입되는지에 대한 척도로 활용
- >>타자와 투수 모두에게 적용이 가능한 지표
- BABIP= (H - HR)/(AB - K - HR + SF); = (HOLD - HR) / (AB - KK - HR + HS?HF)

**7.	DIPS (Defense Independent Pitching Stats)** 

: 투수가 통제할 수 있는 영역인 삼진, 볼넷, 홈런, 데드볼을 갖고 평균 자책점의 형태로 나타낸 것.
- 계수가 너무 복잡한 공식들이 많아서 근사계산 공식인 DICE도 많이 사용. 
- DICE = FIP=  3.00+ (13 * HR + 3 * (BB+HBP) -2 * K)/IP ;  3.00+ (13 * HR + 3 * (BB+HP) -2 * KK)/ (INN2 / 3) 

**8.	FIP (Fielding Independent Pitching; 수비 무관 평균 자책점)**

: DIPS의 개량된 형태, 투수의 미래 성적을 예측하는데 유용하며 평균자책점과 같은 형태로 산출되기 때문에 비교해서 살펴보기가 편함.
- FIP=  C(보통3.1~3.2, 투수지표 논문에선 3.20)+ (13 * HR + 3 * (BB+HBP) -2 * K)/IP ; C(보통3.1~3.2, 3.00)+ (13 * HR + 3 * (BB+HP) -2 * KK)/ (INN2 /3) 
- 여기서 C = ERA_bar – (13 × HR_bar + 3 ×(BB_bar + HBP_bar) – 2 * K_bar ) / IP_bar (각 리그 ERA, HR, ... 의 리그 평균값)
- >> '한국프로야구에서 FIP 계수의 추정' 확인하면 KBO에 맞는 kFIP를 새롭게 제시 
- >> kFIP = C+ (14 × HR + 3 × (BB + HBP) − K) / IP ; C+ (14 × HR + 3 × (BB + HP) − KK) / (INN2 / 3)


------------------***위 지표들의계산 방식은 ‘한국프로야구에서의 투수평가지표’ 의 표를 참고. ***-----------------------


**9. RA9 (Run Allowed Per 9 Innings Pitched; 9이닝당 평균실점)**: -

:투수의 9이닝당 평균 실점
- ERA와 다른 점은 비자책과 자책을 구분하지 않고 모든 실점을 반영한다는 것
- RA9 = 9* R / IP ; = 9 * R/ (INN2 / 3)


**10. HR/9  (Home Runs Allowed Per 9 Innings Pitched;9이닝당 피홈런 개수)**

- HR/9 = 9* HR / IP ; = 9 * HR/ (INN2 / 3)


**11. H/9  (Hits Runs Allowed Per 9 Innings Pitched; 9이닝당 피안타 개수)**

- H/9 = 9* H / IP ; = 9 * HIT/ (INN2 / 3)


**12. OAVG/OOBP/OSLG/OOPS – 피안타율/피출루율/피장타율/피OPS ** 타자 지표와 동일하게 계산

- AVG 피안타율: AVG = H / AB ; = HIT / AB
- OBP 피출루율: OBP= ( H + BB + HBP ) / ( AB + BB + HBP + SF ) ; = ( HIT + BB + HP ) / ( AB + BB + HP + SF ) 
- SLG 피장타율: SLG = ( 1B+ 2 * 2B + 3 * 3B + 4 * HR ) / AB  ; = ( HIT + 2 * H2 + 3 * H3 + 4 * HR ) / AB
- OPS 피출루율+피장타율 : OPS = OBP + SLG


~**13. GO/AO 땅볼/뜬공 **~ 

:땅볼/ 뜬공 데이터 없음....
