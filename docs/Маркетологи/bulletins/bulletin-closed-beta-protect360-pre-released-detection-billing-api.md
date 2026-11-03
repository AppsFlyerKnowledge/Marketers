---
title: >-
  Бюллетень: функция раннего обнаружения Protect360 для Billing API доступна в
  закрытой бете.
metadata:
  keywords:
    - Marketers
    - Protect360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2024-08-05T16:11:54Z'
  edited_at: '2026-10-19T14:40:51Z'
  id: 27286254350481
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/27286254350481
---
| **Что нового** | Protect360 теперь учитывает данные предрелизного обнаружения фрода. Данные дополнительного обнаружения вычитаются из вашего пакета (в AppsFlyer). Это связано с тем, что оно отражает нелегитимные конверсии, которые не следует включать в пакет. |
| --- | --- |
| **Дата выпуска [Бета]** | Июль, 2024 |
| **Что важно знать** | <ul><li>Данные предварительного обнаружения будут доступны в **Управление аккаунтом** -> **Отчет об использовании** -> **Источник конверсии** -> **Предварительное обнаружение**</li><li>Предварительное обнаружение агрегируется и разделяется на неорганические и органические конверсии.</li><li>Предрелизное обнаружение будет обновляться ежедневно. Тем не менее, окончательные расчеты будут предоставлены 10 числа следующего месяца.</li><li>Предрелизное обнаружение не отображается партнерам и, следовательно, не применяется для проведения сверок с партнерами.</li><li>Данные предрелизного обнаружения доступны с 1 июля 2024 года.</li></ul> |
| **Влияние** | Предрелизные обнаружения можно найти в вашем отчете об использовании. Это предрелизное обнаружение снизило ваши затраты, возвращая обнаруженное мошенничество в ваш пакет.<br /><br />Предрелизные обнаружения отражают дополнительные конверсии, которые следует вычесть из пакета AppsFlyer. |
| **Информация** | Ниже приведены скриншоты, показывающие отчет об использовании с фильтром предрелизного обнаружения и визуализацией данных.<br /><br />**<span id="usage-report-showing-where-to-find-the-filter"></span>Отчет об использовании - показывает, где найти фильтр.**<br /><br />![Usage_protect1.jpg](https://files.readme.io/efdbb5f45e800a762c7c1acca6798845b70c81ce79330123fef90a1909b51b61-27361610892561.jpg)<br /><br />**<span id="billable-report-filtered-to-show-only-deduction-due-to-protect360-prereleased-detection-therefore-in-minus"></span>Отчёт по тарификации — только вычеты по предрелизному обнаружению Protect360 (отображаются со знаком минус).**<br /><br />![Usage_protect2.jpg](https://files.readme.io/0f5a8caef0d223878f8aee8bcc409313ec69cdef517f91cc0fe68ab8dc0abe16-27361550181905.jpg)<br /><br />**<span id="pie-chart-reflecting-the-total-billable-conversions-breakdown-after-the-deduction-of-the-prereleased-detection"></span>Круговая диаграмма, отражающая общую разбивку оплачиваемых конверсий после вычета предрелизного обнаружения.**<br /><br />![Usage_protect3.jpg](https://files.readme.io/4c327a495a21a16f7b03e6aaa216e79601b8ab31c29a9e1abf48381d345e6bc4-27361610894225.jpg) |

<div data-zendesk-anchors="h_01J4RBNRXRME4HVFBD793PYRPQ=usage-report-showing-where-to-find-the-filter h_01J4RBNWQ8B4XZA5CW9AX1F5C2=billable-report-filtered-to-show-only-deduction-due-to-protect360-prereleased-detection-therefore-in-minus h_01J4RBQWNBFDFZRSFHSBVDS89S=pie-chart-reflecting-the-total-billable-conversions-breakdown-after-the-deduction-of-the-prereleased-detection" />
