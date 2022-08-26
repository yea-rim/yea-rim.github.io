---
layout: post
title: ReflectionException:There is no getter for property named
description: >
  Error Log
sitemap: false
hide_last_modified: true
---

오늘도 출근하자마자 오류가 났다.

``nested exception is org.apache.ibatis.reflection.ReflectionException: There is no getter for property named``


planYear의 getter가 VO에 없어서 생긴 문제인데,


planYear와 planMonth를 CONCAT으로 연결해 planYM으로 받아오기 때문에 무심코 누락했다.


getter setter까지 넣어주고 나니 planYM에 NULL 값이 들어갔다는 오류가 났다.

#### 경로 / 어노테이션 제대로 확인하기
#### 넘겨주는 파라미터 / 정보 제대로 확인하기
#### sql 공부하기