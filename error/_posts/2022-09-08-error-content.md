---
layout: post
title:  ORA-00001: There is no getter for property named
description: >
  Error Log
sitemap: false
hide_last_modified: true
---


500번 오류가 또 났다.

``There is no getter for property named``

Controller에 어떤 변수 getter가 없다고 뜨는 문제였는데,


sql xml 파일에 ``A.COMPANY_CODE = #{data.companyCode}``라고 써야 하는 것을


``A.COMPANY_CODE = #{companyCode}`` 라고 써서 생긴 오류다.


**경로 / 어노테이션 제대로 확인하기 (2)**

**넘겨주는 파라미터 / 정보 제대로 확인하기**

**sql 공부하기 (2)**

**알고리즘 공부하기**

**1~12월 같은 불변데이터는 하드코딩 처리 가능**