---
title: Определение местоположения пользователя
metadata:
  keywords:
    - IPs
    - Advertisers
    - Agencies
    - Ad Networks
    - ip
    - digital element
    - zip
    - dim
    - zip code
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2019-01-29T12:52:11Z'
  edited_at: '2025-08-14T20:34:37Z'
  id: 360000847378
  locale: ru
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ru/articles/360000847378
---
> **Краткий обзор:** Местоположение пользователя определяется с помощью IP-адреса устройства, который сопоставляется с общим местоположением пользователя (город, штат, страна и т. д.). Местоположение пользователя влияет на выбор креативов, стоимость кампании, вовлечение и качество пользователей.

<Image align="center" alt="5888ResolveIpAddress_us-en.png" src="https://files.readme.io/166e48fb0bb90b627bc51e29b53a556b71939749ab3e5eadff7d6edf0f0dfd25-360011758517.png" />

<div id="determining-user-location" />

## Определение местоположения пользователя

В AppsFlyer сообщается о действиях пользователя на устройстве. Действия (события) содержат различные поля данных, в том числе IP-адрес устройства.

В некоторых случаях истинный IP-адрес устройства маскируется VPN, механизмом, таким как iOS 15 Private Relay, или прокси-серверами SKAN. Следовательно, преобразование IP-адреса в геолокацию, описанное в этой статье, может быть неправильным или вводящим в заблуждение. AppsFlyer не может это контролировать.

IP-адрес преобразуется в AppsFlyer в информацию о геолокации с использованием данных, предоставленных компанией <Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor> — мировым лидером в области IP-локации.

* Информация о геолокации может включать:
  * Территория (страна): Коды по ISO 3166 (alpha-2) или EU (Европа) или AS (Азия), если информация о конкретной территории недоступна.
  * Город: Это может коррелировать с районом в городе, не будучи напрямую связанным с фактическими границами города.
  * DMA (обозначенная рыночная зона), регионы или географические области для просмотра телевидения, измеряемые компанией <Anchor target="_blank" href="https://www.nielsen.com/us/en/solutions/nielsen-global-connect/">Nielsen</Anchor>. <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012539677">Коды метро в файле CSV.</Anchor>
  * Регион: Географический регион или континент.
  * Штат или провинция: Смотрите таблицу <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012615238">локализованных названий штатов в файле CSV</Anchor>. В этой таблице мы используем поле region. Он состоит из 3 букв или цифр.
  * Почтовый индекс.
* IP-адреса для таблиц геолокации обновляются через регулярные промежутки времени, обычно еженедельно.

**Пример: Преобразование IP-адреса в геолокацию**![IPTables_us-en.png](https://files.readme.io/0d7d4d4190face77e18476bdb9e47fdd26ed62ab91cd641f76f728d9a7c8d005-360011787798.png)

<div id="note-regarding-the-united-kingdom-uk" />

> 📘 **Примечание о Великобритании (UK)**
>
> <Image align="center" alt="blobid0.png" src="https://files.readme.io/33ed45ea49e3308e17a237400ea6c6e9d33c495a9c83197041fdae282f9c65a4-360006637538.png" width="62px" />
>
> * В платформе Великобритания обозначается кодом UK.
> * Код ISO 3166 для Великобритании — GB. Код UK зарезервирован, но не выделен в ISO, для Великобритании.

<div id="location-discrepancies" />

### Расхождения в местоположении

В некоторых случаях могут быть различия в производном местоположении пользователей между AppsFlyer и другими платформами, даже если другая платформа использует Digital Element для преобразования IP-адресов. Возможными причинами несоответствия местоположения являются:

* **Обновление базы данных:** чтобы обеспечить быструю атрибуцию, AppsFlyer преобразует IP-адреса в данные о местоположении внутри компании. AppsFlyer получает глобальную карту из Digital Element периодически, а не в режиме реального времени. Если AppsFlyer и другая платформа получают данные от Digital Element в разное время, это может объяснить различия.
* **Изменения у интернет-провайдера:** Базы данных Digital Element быстро меняются по мере того, как интернет-провайдеры (ISP) меняют свои IP-сопоставления.
* **Различные планы/методы:** Digital Element предлагает различные пакетные планы в зависимости от требуемого уровня детализации. Другие платформы, использующие другие пакеты Digital Element или другие методы определения идентификатора устройства, могут предоставлять другие результаты.
* **Прокси или VPN:** Если пользователь использует VPN или прокси, то мы не узнаем истинный IP-адрес пользователя. Геолокация будет соответствовать адресу VPN/прокси.
* **Подробнее**: <Anchor target="_blank" href="https://www.digitalelement.com/blog/the-tricky-science-behind-ip-geolocation/">Непростая задача геолокации IP-адресов</Anchor>

<div data-zendesk-anchors="determining-user-location=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%81%D1%82%D0%BE%D0%BF%D0%BE%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F h_01HDP1SA5YV96YMPPFGN9H6RGE=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%81%D1%82%D0%BE%D0%BF%D0%BE%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F h_01HDP1SA5YR7JWDHX2BNXXTKT9=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BE-%D0%B2%D0%B5%D0%BB%D0%B8%D0%BA%D0%BE%D0%B1%D1%80%D0%B8%D1%82%D0%B0%D0%BD%D0%B8%D0%B8-uk location-discrepancies=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%BC%D0%B5%D1%81%D1%82%D0%BE%D0%BF%D0%BE%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HDP1SA5YNA9N4P9AD4RHWS0J=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%BC%D0%B5%D1%81%D1%82%D0%BE%D0%BF%D0%BE%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8" />
