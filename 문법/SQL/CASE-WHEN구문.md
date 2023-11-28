### 기본 구조

```sql
CASE
  WHEN 조건1 THEN 결과1
  WHEN 조건2 THEN 결과2
  …
  ELSE 결과
END AS 컬럼명
```

#### 예제
![image](https://github.com/minahLim/CodingTest/assets/146914181/c3faec7f-e1f1-4844-aaa5-affe4319bd29)

<br> 이미지 출처: [프로그래머스 문제중]조건에 부합하는 중고거래 상태 조회하기
```sql
SELECT BOARD_ID, WRITER_ID, TITLE, PRICE,
    CASE
        WHEN STATUS = 'SALE' THEN '판매중'
        WHEN STATUS = 'RESERVED' THEN '예약중'
        WHEN STATUS = 'DONE' THEN '거래완료'
        ELSE 'NO INFO'
    END AS STATUS
FROM USED_GOODS_BOARD 
WHERE CREATED_DATE > '2022-10-04' AND CREATED_DATE < '2022-10-06'
ORDER BY BOARD_ID DESC;
```
