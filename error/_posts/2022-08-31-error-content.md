---
layout: post
title: Returning cached instance of singleton bean 'page-controller'
description: >
  Error Log
sitemap: false
hide_last_modified: true
---

새로운 화면을 추가하는데 오류가 났다.


``Returning cached instance of singleton bean 'page-controller'``


별 문제는 아니었다.


``@Controller("stand-001-controller")``


``@RequestMapping(value = "/business/standd001")``


``public class Stand001Controller {``


@RequestMapping 값에 오타가 있었다. 오타를 조심하자.



**경로 / 어노테이션 제대로 확인하기**

**넘겨주는 파라미터 / 정보 제대로 확인하기**

**sql 공부하기 (2)**

**알고리즘 공부하기**

**1~12월 같은 불변데이터는 하드코딩 처리 가능**