# SQL_BASIC 5주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_5th_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**5주차 과제는 문제 풀이를 중심으로**, 강의에서 제시된 예제 문제 중 **3 문제 이상을 선택하여 직접 풀어본 뒤**, 강의 영상의 풀이와 비교해 **틀린 부분, 맞은 부분, 새롭게 배운 개념**을 구체적으로 정리해주세요. (적어도 4문제는 정리해야 합니다.) 완성된 과제는 Gihub에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀(수행 인증샷은 필수입니다.)** 



## SQL_BASIC_5th

### 섹션 5. 데이터 탐색 - 변환

### 4-4. 날짜 및 시간 데이터 이해하기(2) (EXTRACT, DATETIME_TRUNC, PARSE_DATETIME, FROMAT_DATETIME)

### 4-5. 시간 데이터 연습문제 1~2번

### 4-5. 시간 데이터 연습문제 3~5번

### 4-6. 조건문 (CASE WHEN, IF)

### 4-7. 조건문 연습 문제

### 4-8. 정리

### 4-9. BigQuery 공식 문서 확인하는 법

(강의에서 연습문제가 많아서 따로 프로그래머스 문제 과제는 없습니다.)



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | ✅         |
| 4주차 | 섹션 **3-4** ~ **4-4** | ✅         |
| 5주차 | 섹션 **4-4** ~ **4-9** | ✅         |
| 6주차 | 섹션 **5-1** ~ **5-7** | 🍽️         |
| 7주차 | 섹션 **6-1** ~ **6-6** | 🍽️         |

<br>



<!-- 여기까진 그대로 둬 주세요-->

---

# 4-4. 날짜 및 시간 데이터 이해하기(2) (EXTRACT, DATETIME_TRUNC, PARSE_DATETIME, FROMAT_DATETIME)

~~~
✅ 학습 목표 :
* 날짜 및 시간 데이터에 대해서 더 자세히 설명할 수 있다. 
* CURRENT_TIME, EXTRACT, DATETIME_TRUNC, PARSE_DATETIME, FROMAT_DATETIME 을 설명할 수 있다. 
~~~

1. 날짜 및 시간 데이터 타입 파악하기
DATE : 날짜만 저장 <br>
DATETIME : 날짜 + 시간 저장 <br>
TIMESTAMP : 날짜 + 시간 저장하지만 UTC 기준으로 처리되는 타입 <br>
UTC : 세계 표준시 <br>
Millisecond : 1초의 1000분의 1, 즉 천분의 1초 <br> 
TIMESTAMP 는 UTC 기준이라 한국 시간과 비교하면 9시간 차이 남<br>
DATETIME 은 타임존 개념이 없어서, 한국 기준으로 보면 그대로 한국 시간처럼 사용 가능<br>
TIMESTAMP와 DATETIME 차이 <br> 
TIMESTAMP<br> 
UTC 기준<br> 
타임존 영향을 받음<br> 
한국 시간으로 보면 보통 9시간 차이 고려 필요<br> 
DATETIME<br> 
타임존 정보 없음<br> 
그냥 보이는 날짜와 시간을 그대로 저장<br> 
한국 기준 데이터 다룰 때는 더 직관적임<br> 



# 4-6. 조건문(CASE WHEN, IF)

~~~
✅ 학습 목표 :
* 조건문 함수의 기능을 이해하고, 설명할 수 있다. 
~~~

조건문: 특정 조건이 충족되면 그에 맞는 값을 반환하는 문법. 데이터를 분류하거나 새로운 컬럼을 만들 때 자주 사용함. <br> 
<br> 
CASE WHEN<br> 
여러 조건을 순서대로 확인해서 결과를 반환하는 방식<br> 
조건이 여러 개일 때 사용하기 좋음<br> 
<br> 
SELECT<br> 
  CASE<br> 
    WHEN 조건1 THEN 결과1<br> 
    WHEN 조건2 THEN 결과2<br> 
    ELSE 그 외 조건일 경우 결과<br> 
  END AS 새로운_컬럼_이름<br> 
<br> 


IF<br> 
조건이 참인지 거짓인지에 따라 두 가지 값 중 하나를 반환하는 방식<br> 
조건이 하나일 때 간단하게 사용 가능<br> 

IF(조건문, True일 때의 값, False일 때의 값) AS 새로운_컬럼_이름<br> 
<br> 
둘 다 조건에 따라 값을 다르게 보여주고 싶을 때 사용하고
주로 새로운 컬럼 생성, 데이터 분류, 범주화 작업에 활용함.



 # 4-5. 시간 데이터 연습문제 & 4-7. 조건문 연습 문제

~~~
✅ 학습 목표 :
* 4-5, 4-7 각각에서 두 문제 이상 (최소 4문제) 푼 내용 정리하기
~~~

✅ 학습 목표 :
* 4-5, 4-7 각각에서 두 문제 이상 (최소 4문제) 푼 내용 정리하기
#1

SELECT <br>
COUNT(*)<br>
FROM(<br>
SELECT<br>
id,<br>
catch_date,<br>
DATE(DATETIME(catch_datetime, "Asia/Seoul")) As catch_datetime_kr_date
FROM basic.trainer_pokemon<br>
)<br>
WHERE<br>
catch_date != catch_datetime_kr_date<br>
## 같지 않은 경우 141 <br>
## 같은 경우 238<br>

<br>
SELECT<br>
COUNT(DISTINCT id) AS cnt<br>
FROM basic.trainer_pokemon<br>
WHERE<br>
EXTRACT(YEAR FROM DATETIME(catch_datetime, "Asia/Seoul")) = 2023<br>
AND EXTRACT(MONTH FROM DATETIME(catch_datetime, "Asia/Seoul")) = 1<br>
<br>
#2
<br>
-- SELECT<br>
-- -- id,<br>
-- -- battle_datetime,<br>
-- -- DATETIME(battle_timestamp,"Asia/Seoul") AS battle_timestamp_kr<br>
-- COUNTIF(battle_datetime = DATETIME(battle_timestamp, "Asia/Seoul"))<br>AS battle_datetime_same_battle_timestamp_kr,<br>
-- COUNTIF(battle_datetime != DATETIME(battle_timestamp, "Asia/Seoul")) AS battle_datetime_same_battle_timestamp_kr<br>
-- FROM basic.battle<br>
<br>
SELECT<br>
COUNT(DISTINCT id) AS battle_cnt<br>
FROM basic.battle<br>
WHERE<br>
EXTRACT (HOUR FROM battle_datetime) >= 6<br>
AND EXTRACT (HOUR FROM battle_datetime) <= 18<br>
<br>
#3
SELECT<br>
-- *, <br>
id,<br>
kor_name,<br>
speed,<br>
IF(speed>=70, "빠름", "느림") AS Speed_category<br>
FROM basic.pokemon<br>
<br>
#4
SELECT<br>
id,<br>
kor_name,<br>
type1,<br>
CASE<br>
WHEN type1 = "Water" THEN "물"<br>
WHEN type1 = "Fire" THEN "불"<br>
WHEN type1 = "Electric" THEN "전기"<br>
ELSE "기타"<br>
END AS type1_Korean<br>
FROM basic.pokemon<br>





<br>

<br>

---

# 확인문제

## 문제 1

> **🧚Q. 광윤이는 카페 주문 로그 데이터(order_log)를 분석하여, '오전(0시-11시)'과 '오후(12시-23시)'의 주문 건수를 집계하려고 합니다. 광윤이가 작성한 다음 SQL 쿼리 중 문법적으로 틀렸거나 의도한 결과가 나오지 않는 것을 모두 골라보세요. (복수 선택 가능)**

~~~sql
1. SELECT 
   IF(EXTRACT(HOUR FROM order_time) < 12, '오전', '오후') AS time_type,
   COUNT(*)
   FROM order_log
   GROUP BY time_type;

2. SELECT 
   DATETIME_TRUNC(order_time, HOUR) AS truncated_hour,
   COUNT(*)
   FROM order_log
   WHERE order_time BETWEEN '2021-01-01' AND '2021-12-31'
   GROUP BY order_time;

3. SELECT 
   FORMAT_DATETIME(order_time, '%H') AS order_hour,
   COUNT(*)
   FROM order_log
   GROUP BY 1;

4. SELECT 
    CASE 
      WHEN EXTRACT(HOUR FROM order_time) BETWEEN 0 AND 11 THEN '오전'
      ELSE '오후'
    AS time_group,
    COUNT(*)
   FROM order_log
   GROUP BY time_group;
~~~

<!-- 틀린쿼리에 대한 오류의 원인도 같이 작성해주세요. 문제에서 제공된 order_time 컬럼은 DATETIME type의 데이터를 가지고 있다고 가정합니다. -->

~~~
2번 4번
:  order_time, HOUR 으로 SELECT 진행 하였는데 GROUP BY에서는 order_time을 사용하고 있어 오류,  EMD이 없어서 오류 
~~~



## 문제 2

> **🧚Q. 예운이는 포켓몬 타입에 따라 설명을 부여하는 쿼리를 작성했습니다. type 1 컬럼의 값에 따라 조건을 분기했으며, 다음 SQL 쿼리를 실행했습니다.**

~~~sql
SELECT name,
       CASE 
         WHEN type1 = 'Fire' THEN 'Hot'
         WHEN type1 = 'Water' THEN 'Cool'
         ELSE 'Normal'
       END AS type_description
FROM pokemon;
~~~

> **다음 중 type_description의 결과가 'Normal'로 출력될 포켓몬은?**

| **name**   | **type1** |
| ---------- | --------- |
| Pikachu    | Electric  |
| Charmander | Fire      |
| Squirtle   | Water     |
| Bulbasaur  | Grass     |

<!-- 근거와 함께 답을 작성해주세요 -->

~~~
Pikachu, Bulbasaur
~~~



<br>

### 🎉 수고하셨습니다.