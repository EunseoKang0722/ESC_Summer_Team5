# 파생변수 후보 (타자력예측)
OBP(On Base Percentage; 출루율) <br>
AVG(Average; 타율) <br>
SLG(Slugging Percentage; 장타율) <br>
ISO(Isolated Power; 순장타율)
BABIP(Batting Average on Balls In Play; 인플레이 타구의 비율)
BB/K (Base on Balls per Strike Out; 볼넷/삼진 비율) <br>
RC27(Runs Created 27; 한 경기당 득점생산) <br>
WAR(Wins Above Replacement; 대체선수 대비 승리 기여도)

# 기존변수
## 팀

|컬럼|컬럼명|비고|
|:--:|:--:|:-----------:|
|T_NM|팀명|각 구단의 이름|
|T_ID|팀코드|구단구분을 위한 고유코드값|

## 경기

|컬럼|컬럼명|비고|
|:--:|:--:|:-----------:|
|G_ID|게임키|각 경기 구분 고유 코드 값 YYYYMMDDAABBX|
|GDAY_DS|일자||
|VISIT_KEY|원정팀코드||
|HOME_KEY|홈팀코드||
|HEADER_NO|더블헤더코드||
|GWEEK|요일||
|STADIUM|구장||

## 선수
|컬럼|컬럼명|비고|
|:--:|:--:|:-----------:|
|GYEAR|시즌||
|PCODE|선수코드||
|NAME|선수명||
|T_ID|팀코드|선수 소속팀의 고유 코드 값|
|POSITION|포지션|선수의 포지션|
|AGE_VA|나이||
|MONEY|연봉||


## 등록선수
|컬럼|컬럼명|비고|
|:-------:|:-----:|:-------------------:|
|GDAY_DS|일자|등록/말소 일자|
|T_ID|팀코드||
|P_ID|선수코드||
|ENTER_YN|등록말소|등록말소 여부|

## 팀투수
|컬럼|컬럼명|비고|
|:-------:|:-----:|:-------------------:|
|G_ID|게임키|경기 구분 코드 값|
|GDAY_DS|일자|경기일|
|T_ID|팀코드||
|VS_T_ID|상대팀코드||
|HEADER_NO|더블헤더코드||
|TB_SC|초말|이닝 초/말 구분값|
|CG_CK|완투|완투 여부(0 or 1)|
|WLS|결과|(승W, 패L, 세S, 무D)|
|HOLD|홀드|홀드 여부(0 or 1)|
|INN2|이닝*3|실제투구이닝*3배(정수화 위해)|
|BF|투구 수||
|PA|타자|상대타자 숫자|
|AB|타수|상대타자 타수|
|HIT|안타||
|H2|2루타||
|H3|3루타||
|HR|홈런||
|SB|도루||
|CS|도루실패||
|SH|희타|희생타|
|SF|희비|희생플라이|
|BB|4구||
|IB|고4|고의4구|
|HP|사구|몸에 맞는 볼|
|KK|삼진||
|GD|병살타||
|WP|폭투||
|BK|보크||
|ERR|실책||
|R|실점|총 실점|
|ER|자책점|투수의 책임이 되는 실점|
|P_WHIP_RT|득점권WHIP||
|P2_WHIP_RT|2점차이하WHIP||
|CB_WHIP_RT|345번타자 WHIP||

WHIP(Walks plus Hits divided by innings Pitched): 이닝당 안타+볼넷 허용률
득점권: 주자가 2루 이상(1~2루, 2루, 2~3루, 1~3루, 3루, 만루) 위치해 있는 경우

## 개인타자
|컬럼|컬럼명|비고|
|:-------:|:-----:|:-------------------:|
|G_ID|게임키||
|GDAY_DS|일자||
|T_ID|팀코드||
|VS_T_ID|상대팀코드||
|HEADER_NO|더블헤더코드||
|TB_SC|초말||
|P_ID|선수코드||
|START_CK|선발|선발출장 여부(0 or 1)|
|BAT_ORDER_NO|타순|해당경기 출전타순|
|PA|타자||
|AB|타수||
|RBI|타점||
|RUN|득점||
|HIT|안타||
|H2|2루타||
|H3|3루타||
|HR|홈런||
|SB|도루||
|CS|도루실패||
|SH|희타|희생타|
|SF|희비|희생플라이|
|BB|4구|볼넷|
|IB|고4|고의4구|
|HP|사구|몸에 맞는 볼|
|KK|삼진||
|GD|병살타||
|ERR|실책||
|LOB|잔루|이닝이 끝난 상황에 누 상에 남아있는 주자 수|
|P_HRA_RT|득점권타율||
|P_AB_CN|득점권타수||
|P_HIT_CN|득점권안타||
