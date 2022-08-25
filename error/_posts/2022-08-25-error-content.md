---
layout: post
title: java.sql.SQLException:부적합한 열 인덱스
description: >
  Error Log
sitemap: false
hide_last_modified: true
---

오늘은 출근하자마자 다음과 같은 오류가 났다.

``java.sql.SQLSyntaxErrorException: ORA-00909: 인수의 개수가 부적합합니다``
``nested exception is java.sql.SQLException: ORA-12899: 열에 대한 값이 너무 큼``

문제는 sql.xml에 있었다.

``AND A.PLAN_YM LIKE CONCAT(#{data.planYm, jdbcType=VARCHAR}, '%')`` [ERROR]

이렇게 써야 하는 것을 아래처럼 적어서 오류가 났다.

``AND A.PLAN_YM LIKE CONCAT(#{data.planYm, jdbcType=VARCHAR} | '%')``

sql 구문 공부를 더 해야겠다.
동적 쿼리 Like문 게시글을 보고 활용했던 건데 불가능한 것 같다.

### 경로 / 어노테이션 제대로 확인하기
#### 넘겨주는 파라미터 / 정보 제대로 확인하기
#### sql 공부하기