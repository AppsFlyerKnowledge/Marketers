---
title: 'Бюллетень: поддержка DMA в отчетах о сырых данных'
metadata:
  keywords:
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2024-05-29T16:52:12Z'
  edited_at: '2026-10-19T14:39:07Z'
  id: 25485269115793
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/25485269115793
---
| **Что нового** | В AppsFlyer в инструменты сырых данных добавляются следующие поля согласия DMA:<ul><li>**gdpr\_applies:** Указывает, подпадает ли пользователь под юрисдикцию DMA (true) или нет (false).</li><li>**ad\_user\_data\_enabled**: Указывает, дал ли пользователь согласие на то, чтобы Google использовал данные пользователя для измерения и персонализированной рекламы (true) или нет (false).</li><li>**ad\_personalization\_enabled**: Указывает, дал ли пользователь согласие на то, чтобы Google использовал его пользовательские данные для персонализированной рекламы (true), или нет (false).</li><li>**raw\_consent\_data**: Возвращает объект JSON с полными сырыми данными о согласии, отправленными рекламодателем в AppsFlyer. Информация, отправленная в этом объекте, затем используется для заполнения трех полей выше.<ul><li>Это поле недоступно в экспорте сырых данных и Pull API</li></ul></li></ul> |
| --- | --- |
| **Дата вступления в силу** | <ul><li>Страница экспорта сырых данных и Pull API — June 3rd, 2024</li><li>Push API и Data Locker — Oct 14, 2024</li></ul> |
| **Где** | <ul><li>Страница экспорта необработанных данных</li><li>Pull API</li><li>push</li><li>Datalocker</li></ul> |
| **Кому следует знать об этом** | <ul><li>Рекламодатели и агентства, которые используют страницу экспорта сырых данных, Push API, Pull API и Data Locker для экспорта сырых данных (на уровне событий) из AppsFlyer.</li></ul> |
| **Как это влияет на вас** | <ul><li>Настройте свою схему и все остальные процессы, связанные с потреблением данных.</li><li>Убедитесь, что новые поля не нарушают вашу схему для Push API и Data Locker.</li></ul> |
| **Дополнительная информация** | Ознакомьтесь с нашей статьёй <Anchor target="_blank" href="/marketers/ru/docs/support-google-eu-consent-policy">«Поддержка политики Google в отношении согласия пользователей из ЕС»</Anchor>. |