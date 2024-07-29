## SQL에서의 Join

관계형 DB는 **`중복 데이터를 피하기 위해`**서 데이터를 여러 개의 테이블로 **`나눠서 저장`**한다.

때문에 분리되어 저장된 데이터를 사용자가 원하는 값으로 도출하기 위해서 **`여러 테이블을 조합해야함`**

이때 사용하는게 Join(조인)이다.

---

## Join의 종류

- INNER JOIN
- LEFT OUTER JOIN
- RIGHT OUTER JOIN
- FULL OUTER JOIN
- CROSS JOIN
- SELF JOIN

### INNER JOIN

교집합으로 **`기준 테이블과 Join 테이블의 중복된 값을 보여준다`**

```sql
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
INNER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
```

### LEFT OUTER JOIN

**`기준 테이블값과 조인 테이블의 중복된 값을 보여준다`**

```sql
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
LEFT OUTER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
```

### RIGHT OUTER JOIN

**`LEFT OUTER JOIN 반대로 오른쪽 테이블 기준으로 JOIN`**

```sql
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
RIGHT OUTER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
```

### FULL OUTER JOIN

**`합집합을 말한다 A와 B 테이블의 모든 데이터가 검색`**

```sql
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
FULL OUTER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
```

### CROSS JOIN

**`모든 경우의 수를 전부 표현해주는 방식`**

A가 3개, B가 4개면 총 12개의 데이터가 검색됨

```sql
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
CROSS JOIN JOIN_TABLE B
```

### SELF JOIN
**`자신과 자신을 조인하는 것`**

하나의 테이블을 여러 번 복사해서 조인한다고 생각하면 편함

**자신이 갖고 있는 컬럼을 다양하게 변형시켜 활용할 때 자주 사용**

```sql
SELECT
A.NAME, B.AGE
FROM EX_TABLE A, EX_TABLE B
```

### INNER JOIN 과 OUTER JOIN 차이점

조인이 되는 키 값을 기준으로 INNER JOIN 경우 교집합, OUTER JOIN 경우 기준 테이블 Key의 집합

INNER JOIN 은 공통된 기본키에 대해서 **둘 다 값이 있는거만 보여주고(NULL 포함 X)**

OUTER JOIN 은 대상이 되는 OUTER에 있는 기본키 기준으로 테이블 합치면서
**반대 쪽에 없는 값은 레코드에 NULL**로 둔다

---