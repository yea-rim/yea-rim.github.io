---
layout: post
title: Kendo ui 개념 정리
description: >
  Kendo ui
sitemap: false
hide_last_modified: true
---

### Kendo ui란?

Kendo IU는 jQuery용 강력한 데이터 시각과 및 편집 구성 요소다. 함께 결합할 수 있는 다양한 기능과 이벤트를 제공한다.

그리드는 다양한 데이터 소스에 바인딩할 수 있으며 페이징, 정렬, 필터링, 그룹화 등의 공통 기능이 내장되어 있다. Aggregate, 고정 열, 가상화 및 무한 스크롤, 상태 관리, SingnalR Hub 바인딩 등과 같은 고급 기능이 포함된다.

``
<div id="example">
    <div id="grid"></div>
    <script>
        $(document).ready(function () {
            $("#grid").kendoGrid({
                dataSource: {
                    type: "odata",
                    transport: {
                        read: "https://demos.telerik.com/kendo-ui/service/Northwind.svc/Customers"
                    },
                    pageSize: 20
                },
                height: 550,
                groupable: true,
                sortable: true,
                pageable: {
                    refresh: true,
                    pageSizes: true,
                    buttonCount: 5
                },
                columns: [{
                    template: "<div class='customer-photo'" +
                    "style='background-image: url(../content/web/Customers/#:data.CustomerID#.jpg);'></div>" +
                    "<div class='customer-name'>#: ContactName #</div>",
                    field: "ContactName",
                    title: "이름",
                    width: 240
                }, {
                    field: "ContactTitle",
                    title: "권한"
                }, {
                    field: "CompanyName",
                    title: "기업명"
                }, {
                    field: "Country",
                  	title: "지역",
                    width: 150
                }]
            });
        });
    </script>
</div>
``

출처 : https://demos.telerik.com/jsp-ui/grid/basic-usage