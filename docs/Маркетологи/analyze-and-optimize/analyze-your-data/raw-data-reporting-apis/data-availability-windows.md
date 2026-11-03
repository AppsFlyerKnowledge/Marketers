---
title: Окна доступности данных
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2022-01-04T03:33:13Z'
  edited_at: '2026-08-18T00:05:25Z'
  id: 4415473374865
  locale: ru
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/ru/articles/4415473374865
---
> **Краткий обзор:** Доступность данных зависит от типа отчёта и заданного окна доступности.

## Окна доступности данных

* Термины **окно доступности** и **хранение данных** означают разные понятия. <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">Хранение данных</Anchor> относится к периоду хранения сырых данных на наших серверах и является более длительным, чем окно доступности.
* Продолжительность окна зависит от пакета подписки.
* В этой статье речь не идет о <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers">Data Locker</Anchor>.

### Окно доступности данных

Окно доступности ограничивает данные, предоставляемые Pull API и страницей экспорта агрегированных данных. Продолжительность окна зависит от типа отчета, как подробно показано в следующей таблице.

| Тип события отчета | Примеры типов отчётов | Окно доступности по умолчанию |
| --- | --- | --- |
| Атрибуция | Органические установки, неорганические установки, конверсии ретаргетинга, удаления. | 60 из последних 90 дней |
| События внутри приложения | Органические события в приложении, неорганические события в приложении, ретаргетинг событий в приложении | 31 за последние 90 дней. |

### Окно доступности агрегированных данных

Окно доступности ограничивает объём сырых данных, доступных через Pull API и на странице выгрузки сырых данных. Продолжительность окна зависит от типа отчета, как подробно показано в следующей таблице.

| Отчет | Период доступности |
| --- | --- |
| Агрегированные отчеты | 25 месяцев (2 года + 1 месяц), <Anchor target="_blank" href="/marketers/ru/docs/bulletin-aggregated-ltv-data-availability">начиная с первой установки приложения</Anchor> |

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/report-generation-quotas-rate-limitations">Квоты на генерацию отчётов</Anchor>

<div data-zendesk-anchors="data-availability-windows=%D0%BE%D0%BA%D0%BD%D0%B0-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HE0FT9CNECNKYMVX9ZJJ9DNV=%D0%BE%D0%BA%D0%BD%D0%B0-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 raw-data-availability-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HE0FT9CNS4N1GD1AYRBSRWPF=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 aggregated-data-availability-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HE0FT9CPW91ASDH9MEW083ZH=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B0%D0%B3%D1%80%D0%B5%D0%B3%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HE7S7VH4PC6FQAYKP6A0G4YY=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
