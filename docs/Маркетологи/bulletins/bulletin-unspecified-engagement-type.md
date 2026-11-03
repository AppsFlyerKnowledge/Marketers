---
title: 'Бюллетень: неуказанный тип вовлечения'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-12-09T15:17:50Z'
  edited_at: '2026-10-19T14:38:32Z'
  id: 30795194720785
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/30795194720785
---
| Что нового? | Чтобы стандартизировать отчетность, когда `engagement_type` отсутствует или не совпадает, мы вводим `click_unspecified` или `impression_unspecified`в качестве значений по умолчанию в отчетах о сырых данных и дэшбордах. |
| --- | --- |
| Каково воздействие | **Конверсии**:  <br />Начиная с даты вступления изменений в силу, `engagement_type` больше не будет отражаться в отчетности как пустое значение, а по умолчанию будет принимать значение `click_unspecified` или `impression_unspecified` в зависимости от типа касания (то есть клик или показ).  <br />  <br />**События в приложении и сессии**:  <br />Новые значения будут применяться только к событиям в приложении и сессиям, атрибутированным конверсиям, зарегистрированным после даты вступления изменений в силу. События, атрибутированные конверсиям, зарегистрированным до даты вступления изменений в силу, останутся без изменений. |
| Дата вступления в силу | Декабрь 9,2024 г. |
| Что вам нужно знать | Всю информацию по EET можно найти в базе знаний:<ul><li><Anchor target="_blank" href="/marketers/ru/docs/about-enriched-engagement-types">Обогащенные типы вовлечения</Anchor></li><li><Anchor target="_blank" href="/partners/ru/docs/enriched-engagement-types-guide-for-ad-networks">Руководство по обогащенным типам вовлечения для партнеров</Anchor></li></ul>С информацией о непосредственном воздействии внедрения EET можно ознакомиться в бюллетене:<ul><li><Anchor target="_blank" href="/marketers/ru/docs/bulletin-enhanced-engagement-types-visibility">Видимость обогащенных типов вовлечения</Anchor></li></ul> |