# SQL_BASIC 2주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_2nd_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**2주차 과제**는 1주차 과제처럼 SQL의 필요성이나 느낀점 위주가 아닌, **실제 강의 내용을 바탕으로 개념을 정리하고 학습한 내용을 집중적으로 기록**해주세요. 완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요. 

**👀(수행 인증샷은 필수입니다.)** 

## SQL_BASIC_2nd

### 섹션 3. 데이터 탐색 - 조건, 추출, 요약

### 2-3. 데이터 탐색 (SELECT, FROM, WHERE)

### 2-4. SELECT 연습문제

### 2-5. 집계 (Group By + Having + Sum/Count)



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | 🍽️         |
| 4주차 | 섹션 **3-4** ~ **4-4** | 🍽️         |
| 5주차 | 섹션 **4-4** ~ **4-9** | 🍽️         |
| 6주차 | 섹션 **5-1** ~ **5-7** | 🍽️         |
| 7주차 | 섹션 **6-1** ~ **6-6** | 🍽️         |

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념정리 

## 2-3. 데이터 탐색 (SELECT, FROM, WHERE)

~~~
✅ 학습 목표 :
* SQL 쿼리 구조를 이해할 수 있다. 
* SELECT, FROM, WHERE의 핵심 문법을 설명할 수 있다. 
~~~

SELECT  

-- * EXCEPT(eng_name) #eng_name 은 제외하고 출력됨

-- id AS pokemon_id, AS는 별칭을 지어줄 때 사용한다. 

kor_name,

type1,

total

-- id AS "pokemon_id" 
#컬럼 이름에 따옴표를 넣는 경우 : 자주하는 실수 => 따옴표 없이 기록 

FROM `basic.pokemon` 

WHERE

 type1 = "Fire"

## my-project-bigquery-489616 : 프로젝트 id

## basic : dataset

## pokemon : table

## < 프로젝트 id > <데이터셋> <테이블>

## 프로젝트 id는 꼭 명시할 필요는 없을 수도 있음.(프로젝트가 단일이라면)

## 프로젝트를 여러개 사용한다면 명시하는 것이 좋음 => 쿼리를 실행할 때 어떤 프로젝트인지 확인하는  과정이 존재.

## 프로젝트 명시 => 불편

## 프로젝트를 제외하고 사용해도 괜찮긴 함. (여러 프로젝트를 쓸 때는 명시해야한다.)

## 프로젝트 id를 제외하고 작성할 때는 ''가 없어도 괜찮음. 

## 데이터를 활용하고 싶은 목적이 있어야, 어떤 컬럼을 선택할지 알 수 있게됨. 

## 가독성 있는 쿼리는 중요하다.

## 쿼리를 잘 읽을 수 있으려면 잘 작성해야 함. => 협업할 때 특히 중요 => 이후 강의에서 다룸.

## ; 세미콜론 , 쿼리문이 끝났다. 



## 2-5. 집계 (Group By / HAVING / SUM,COUNT)

~~~
✅ 학습 목표 :
* 데이터를 집계하고 그룹화하는 방법을 설명할 수 있다.
* GROUP BY, HAVING, ORDER BY, 집계함수(SUM/COUNT 등)을 활용하는 방법을 설명할 수 있다.
* having과 where의 차이에 대해서 설명할 수 있다.
~~~

집계와 그룹화
:모아서 계산한다. 

GROUP BY
:같은 값끼리 모아서 그룹화한다. 

SELECT
집계할_컬럼1,
집계함수
FROM Table
GROUP BY
집계할_컬럼1

SELECT
type1,
AVG(attack) AS avg_attack,
Count(id) AS cnt
FROM pokemon
GROUP BY type1

DISTINT:별개의 
여러 값 중에 Unique한 것만 보고 싶은 경우 사용 / 중복제거

HAVING: 그룹화한 결과에 조건을 걸어 원하는 그룹만 남김.

ORDER BY: 결과를 특정 열 기준으로 오름차순 또는 내림차순 정렬.

집계함수(SUM/COUNT 등): 여러 행의 값을 하나로 요약해 계산. 


HAVING과 WHERE의 차이: WHERE는 그룹화 전 행을 필터링하고, HAVING은 그룹화 후 그룹을 필터링한다.




# 2️⃣ 학습 인증란

![alt text](image.png)




<br><br>



---

# 3️⃣ 확인문제

## 문제 1

> **🧚Q. 포켓몬 마스터 진아는 포켓몬 데이터 조회하는 SQL문에 재미를 느껴서 혼자서 데이터를 조회하는 쿼리문을 짰습니다. 하지만 세 가지의 오류로 다음 코드가 실행이 안된다고 하는데, 각 오류의 위치와 이유를 설명하고, 올바른 쿼리문으로 수정해보세요.**

~~~sql
# 진아의 SQL Query문 
SELECT name. type
FROM pokemon;
WHERE type = Electric;
~~~
SELECT name. type
→ name과 type 사이 구분자는 .이 아니라 ,를 써야 한다.
→ 여러 열을 조회할 때는 name, type처럼 적어야 한다.

FROM pokemon;
→ 세미콜론 ;이 들어가서 쿼리가 여기서 끝나버린다.
→ WHERE절은 FROM 뒤에 같은 문장 안에서 이어져야 한다.

WHERE type = Electric;
→ 문자열 값 Electric은 작은따옴표로 감싸야 한다.
→ SQL에서는 문자 비교를 할 때 'Electric'처럼 써야 한다.


~~~
SELECT name, type
FROM pokemon
WHERE type = 'Electric';
~~~



## 문제 2

> **🧚Q. 앞서 SQL Query의 오류를 해결한 진아는 기분 좋게 이번에는 포켓몬 데이터에서 타입별 평균 공격력이 60 이상인 타입만 조회하려는 쿼리를 작성하려고 했습니다. 하지만 이번에도 실수를 하여 쿼리문이 실행되지 않거나 잘못된 결과가 나오고 있는데, 쿼리에서 잘못된 부분이 무엇인지 설명하고, 올바르게 수정한 쿼리를 작성해보세요.**

~~~sql
SELECT type, AVG(attack) AS avg_attack
FROM pokemon
WHERE AVG(attack) >= 60
GROUP BY type;
~~~

잘못된 부분: WHERE AVG(attack) >= 60
WHERE는 그룹화 전에 각 행에 조건을 거는 구문이라서
AVG() 같은 집계함수 결과에는 사용할 수 없음.
그룹별 집계 결과에 조건을 줄 때는 HAVING을 써야 함.

~~~
SELECT type, AVG(attack) AS avg_attack
FROM pokemon
GROUP BY type
HAVING AVG(attack) >= 60;
~~~



### 🎉 수고하셨습니다.
