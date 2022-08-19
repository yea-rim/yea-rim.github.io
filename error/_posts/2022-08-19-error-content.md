---
layout: post
title: sql xml 파일 경로 오류
description: >
  Error Log
sitemap: false
hide_last_modified: true
---

Tomcat 연결에 오류가 뜬다.

``Server Tomcat v9.0 Server at localhost was unable to start within 45 seconds. If the server requires more time, try increasing the timeout in the server editor.``

메이븐 업데이트, 서버 클린, 프로젝트 클린을 해봐도 소용 없다.
그래서 오류 콘솔을 분석했다.

``Cannot find class: nested exception is org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'sqlSessionFactory' defined in file``

root context에 잘못 넣었나 찾아봤지만 아니었다.
그래서 xml 코드를 확인했다.

``resultType=""``

아니나 다를까 resultType 경로를 잘못 적었다.
잘못 적어서 경로를 찾지 못했다는 오류가 뜬 것이다.

### 경로 / 어노테이션 제대로 확인하기