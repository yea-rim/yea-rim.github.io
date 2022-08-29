---
layout: post
title: Kendo UI 파라미터 전달
description: >
  Error Log
sitemap: false
hide_last_modified: true
---

여전히 planYM에 NULL 값이 들어가는 문제를 해결 중이다.


NOT NULL이 걸려 있는 planYM에서 오류가 나는 것은 파라미터 값을 제대로 받아오지 못해서다.


그렇다면 전달은 어디서부터 막힌 걸까? 어디까지는 전달되는 걸까?


logger를 붙여서 확인해보자.


==> 확인 결과 처음부터 들어갈 리가 없는 설계였다.

``		for (Oprtn001VO plan : list) {``
``			for (int i = 1; i <= 12; i++) {``
``				plan.setPlanMonth(String.valueOf(i));``
``				plan.setPlanAmt(plan.setMonthAmt(i));``
``				oprtn001Mapper.insertPlan(plan);``
``			}``
``		}``

그래서 insert할 때 planMonth를 1부터 12까지 직접 넣고,


planAmt를 VO에 따로 넣은 setMonthAmt()로 처리했다. 코드는 다음과 같다.

``	public double setMonthAmt(int i) {``
``		if (i == 1) {``
``			return this.planAmt01;``
``		} else if (i == 2) {``
``			return this.planAmt02;``
``		} else if (i == 3) {``
``			return this.planAmt03;``
``		} else if (i == 4) {``
``			return this.planAmt04;``
``		} else if (i == 5) {``
``			return this.planAmt05;``
``		} else if (i == 6) {``
``			return this.planAmt06;``
``		} else if (i == 7) {``
``			return this.planAmt07;``
``		} else if (i == 8) {``
``			return this.planAmt08;``
``		} else if (i == 9) {``
``			return this.planAmt09;``
``		} else if (i == 10) {``
``			return this.planAmt10;``
``		} else if (i == 11) {``
``			return this.planAmt11;``
``		} else if (i == 12) {``
``			return this.planAmt12;``
``		} else {``
``			return 0;``
``		}``
``	}``

반환된 monthAmt를 INSERT 시 넣어주면 된다.


그리고 planMonth 처리는 sql 구문으로 처리했다.

``CONCAT(#{planYear, jdbcType=VARCHAR}, LPAD(#{planMonth, jdbcType=VARCHAR}, 2, '0'))``

#### 경로 / 어노테이션 제대로 확인하기
#### 넘겨주는 파라미터 / 정보 제대로 확인하기
#### sql 공부하기 (2)
#### 알고리즘 공부하기
#### 1~12월 같은 불변데이터는 하드코딩 처리 가능