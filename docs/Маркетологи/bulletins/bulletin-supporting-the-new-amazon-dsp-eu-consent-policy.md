---
title: 'Бюллетень: Поддержка новой политики согласия Amazon DSP в ЕС'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-12T09:11:36Z'
  edited_at: '2026-10-19T14:37:57Z'
  id: 45664244736529
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/45664244736529
---
| Раздел | Подробности |
| --- | --- |
| **Что нового** | В рамках применения Закона о цифровых рынках (DMA) Amazon Ads обновляет свою политику согласия для ЕС. AppsFlyer вносит необходимые изменения, чтобы соответствовать требованиям политики Amazon и при этом помочь рекламодателям максимально раскрыть потенциал своих маркетинговых каналов Amazon Ads. |
| **Дата вступления в силу** | <ul><li>Дата вступления в силу на Amazon — 30 июня 2026 г</li><li>Дата начала поддержки на AppsFlyer — 18 мая 2026 года</li></ul> |
| **Что важно знать** | **Соответствующие интеграции и аудитория:** все рекламодатели, чьи приложения интегрированы с Amazon Ads через SRN-интеграцию `amazondsp_int` и которые ведут рекламную деятельность в ЕС (включая Великобританию и Швейцарию).<br /><br />**Необходимые действия** Убедитесь, что вы передаете в AppsFlyer корректные сигналы согласия DMA для любого события (открытие приложения или событие внутри приложения) у пользователей из ЕС, Великобритании или Швейцарии.<br /><br />Сигналы согласия могут быть следующими:<ol><li>**Вручную заполненная форма согласия:** Единственное обязательное поле - это `ad_user_data_enabled` как часть массива заполняемого вручную согласия. Другие поля, требуемые для согласия для Google's DMA, нерелевантны для Amazon.</li><li>**Согласие TCF:** Передайте полную информацию о согласии TCF, сформированную вашим CMP, и убедитесь, что в списке согласованных вендоров указан идентификатор вендора Amazon Ads (`793`).</li><li>**Строки согласия GPP:** Amazon поддерживает строки согласия GPP, но в настоящее время это не поддерживается AppsFlyer.</li></ol>**<span id="h_01KP0FAZ70YDRQ71TDRYFEG120"></span>См. также**<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">Как отправить согласие DMA через SDK в AppsFlyer</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">Как отправить согласие на DMA через S2S от AppsFlyer</Anchor> (поиск по `consent_data`)</li></ul> |