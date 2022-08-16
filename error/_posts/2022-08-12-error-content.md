---
layout: post
title: Dynamic Web Module __ requires Java __ or newer
description: >
  Error Log
sitemap: false
hide_last_modified: true
---

Maven Update 이후 프로젝트가 돌아가지 않았다.
원인을 찾아보니 Java Version이 1.8에서 11로 변경돼 있었다.
Version이 맞지 않아 Server에 add/remove가 불가능했다.
1.8로 변경하고 TOMCAT 9를 추가하니 잘 돌아간다.

Version을 항상 확인하자.
그리고 Clean을 습관화 하자.

08/16
Properties에 Maven Java Version이 여전히 11로 설정된다.
추가 해결이 필요하다.