---
layout: post
title: Failed to parse mapping resource, Error parsing Mapper XML.
description: >
  Error Log
sitemap: false
hide_last_modified: true
---

서버가 무한로딩 걸려서 켜지지도 않고 이상한 오류가 잔뜩 났다.



``Invocation of init method failed; ``

``nested exception is org.springframework.core.NestedIOException: ``

``Failed to parse mapping resource: ``

``Error parsing Mapper XML. ``

``ClassNotFoundException: Cannot find class: ``


한참 보다가 문제를 발견했다.


xml 파일 중 parameterType의 파일명 소문자를 대문자로 오타낸 것을...

정말 한참 찾았다...



**경로 / 어노테이션 제대로 확인하기 (2)**

**넘겨주는 파라미터 / 정보 제대로 확인하기**

**sql 공부하기 (2)**

**알고리즘 공부하기**

**1~12월 같은 불변데이터는 하드코딩 처리 가능**