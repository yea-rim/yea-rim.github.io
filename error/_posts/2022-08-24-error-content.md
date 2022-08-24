---
layout: post
title: java.sql.SQLException:부적합한 열 인덱스
description: >
  Error Log
sitemap: false
hide_last_modified: true
---

KindoUI에서 부서를 선택하면 부서에 따른 정보가 오른쪽에 출력돼야 하는데 오류가 뜬다.

``ERROR [jdbc.audit] 13. PreparedStatement.setNull(4, 12)``

해결하는 중이다.

보통 이 경우 값이 잘못 주어졌거나, insert문에서 발생하는 오류라는데 아직 잘 모르겠다.

jsp에서 kendo ui 활용 시 파라미터를 제대로 설정하지 않아 생긴 오류였다.

``				// 조회``
``				read: {``
``					contentType: "application/json",``
``					type: "POST",``
``					url:"<c:url value='/business/oprtn001/read1'/>",``
``					data: function() {``
``						var objs = {};``
``						objs.searchnm = $("#oprtn001_search_nm").val();``
``						objs.searchcd = $("#oprtn001_search_cd").val();``
``						return objs;``
``					},``

### 경로 / 어노테이션 제대로 확인하기