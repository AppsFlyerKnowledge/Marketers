---
title: Использование дэшбордов PBA
metadata:
  keywords:
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-04-21T04:53:54Z'
  edited_at: '2026-08-27T00:03:52Z'
  id: 360007630318
  locale: ru
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ru/articles/360007630318
---
> **Кратко:** Получите максимум от функций дэшборда PBA.

<Image align="center" alt="People-Based Attribution от AppsFlyer_us-en.png" src="https://files.readme.io/d2178dfedb2f67420e66626adbd72dd96ba9edc39fcb0be08648b01656fd2d4b-360010094118.png" />

<div id="pba-dashboards" />

## Дэшборд PBA

Следующие разделы относятся к дэшбордам <Anchor target="_blank" href="/marketers/ru/docs/pba-website-attribution-dashboard">Website Attribution</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/pba-web-assisted-installs">Web-Assisted Installs</Anchor> дашбордов.

<div id="settings" />

## Настройки

<div id="filtering-options" />

<Accordion title="Параметры фильтрации">

Уточняйте результаты на дэшборде PBA с помощью (A) выбора диапазона дат, (B) основных фильтров и (C) дополнительных фильтров, чтобы адаптировать анализ под свои задачи.

<div id="filter-panel-in-pba-dashboards" />

#### Панель фильтров на дэшбордах PBA

<Image align="center" alt="PBAHeader_us-en.png" src="https://files.readme.io/aaa4040b69082c8507c604b530086404080d542b614fd20fcb0d5302221d7586-360019762657.png" />

**Ключ**:

(1) Выбор диапазона дат

(2) Фильтры по умолчанию

(3) Дополнительные фильтры: нажмите +, чтобы выбрать дополнительный фильтр.

**Принципы**

* Панель фильтров одинакова для всех дэшбордов PBA.
* Доступные фильтры различаются в зависимости от дэшборда, как указано в следующей таблице.
* Фильтры с контекстом: некоторые фильтры, как указано в таблице, должны быть связаны с контекстом. Например, на дэшборде Web-Assisted Installs для фильтра гео требуется контекст: либо веб-медиаисточник, либо мобильный медиаисточник. Вы можете задать фильтр гео для каждого из них, настроив два фильтра гео — по одному для каждого контекста.

<div id="available-filter-dimensions-per-dashboard" />

#### Доступные параметры фильтрации для каждого дэшборда

<table><tbody><tr><th>Фильтр</th><th>Описание/значения</th><th>Атрибуция веб-сайтов </th><th>Web-Assisted Installs</th><th>Путь<br/>конверсии</th></tr><tr><td>Выбор диапазона дат</td><td><p>Дата, когда произошло одно из следующих событий конверсии PBA: </p><ul><li>установка приложения</li><li>Веб-конверсия</li><li>Мобильная конверсия</li></ul></td><td><p>Д</p></td><td><p>Д</p></td><td><p>Д</p></td></tr><tr><td>Гео/страна </td><td><p>Список стран/территорий </p></td><td>Д</td><td><span>Да (1)</span></td><td><p><span>Да (2)</span></p></td></tr><tr><td>Максимальное значение счётчика событий</td><td>Органический, смарт-баннер, кастомная ссылка, платный</td><td>--</td><td><span>Д</span></td><td><span>--</span></td></tr><tr><td>Дополнительная причина блокировки</td><td>Реклама, прямой трафик, электронная почта, реферальный трафик, органический поиск, социальные сети</td><td>Д</td><td><span>Д</span></td><td><span>Да (2)</span></td></tr><tr><td>Мобильная платформа</td><td>Android, iOS</td><td>--</td><td><span>Д</span></td><td><span>--</span></td></tr><tr><td>Медиаисточник </td><td><p>Медиаисточник, к которому относится событие<span></span></p></td><td><p>Д</p></td><td><span>Y(1)</span></td><td><span> <font>Да (2)</font> </span></td></tr><tr><td><p>ID аккаунта сети</p></td><td><p>Включает платные, <a href="./owned-media-attribution" target="_blank">собственные</a> и earned</p></td><td><p>Д</p></td><td>Д</td><td>Да (2)</td></tr><tr><td><p>События конверсии</p></td><td><p>Показывает пути, ведущие к событию конверсии, для пути конверсии</p></td><td><p>Д</p></td><td><p>--</p></td><td><p><span>Д</span></p></td></tr><tr><td><p>Длина пути (шаги) </p></td><td><p>Количество шагов в текущем представлении пути конверсии: медиаисточник, медиаканал, тип медиа</p></td><td><p>--</p></td><td><p>--</p></td><td><p>Д</p></td></tr><tr><td><p>Время пути (дни)</p></td><td>Продолжительность конверсии, начиная с первой точки взаимодействия</td><td>--</td><td>--</td><td>Д</td></tr><tr><td colspan="5"><p><strong>(1)</strong> На дэшборде ассистированных установок с веб-каналов вы связываете фильтр с веб-медиаисточником или мобильным медиаисточником. Вы можете установить несколько экземпляров фильтра. Пример кейса</p></td></tr></tbody></table>

</Accordion>

<div id="grouping-options" />

<Accordion title="Параметры группировки">

Параметры группировки доступны на дэшбордах **Web-Assisted Installs** и **Website Attribution**.

Данные на дэшборде группируются, например, по медиаисточнику, устройству или стране. При выборе группы в таблицу результатов добавляется столбец данных. Порядок выбора групп влияет на способ отображения данных.

* Группа по умолчанию: **Медиаисточник/кампания**
* В раскрывающемся списке выберите 1 или несколько вариантов.

<div id="example" />

> 📄 **Пример**
>
> Одна и та же таргетинговая кампания запущена и в Net\_A, и в Net\_B.
>
> **Цель:** Определить, какой медиаисточник более успешен.
>
> **Как?** Сгруппируйте по *медиаисточнику*, затем посмотрите кампанию, которая направлена на ту же целевую аудиторию.

| группа объявлений | Description(Описание) | Web-Assisted Installs | Атрибуция веб-сайтов |
| --- | --- | --- | --- |
| Тип устройства | Включает смартфон, планшет, настольный компьютер, ТВ и другое (нераспознанные устройства) | Д | Д |
| Среда | <ul><li>Используется для различения KPI веб- и мобильных платформ</li><li>Дэшборд Website Attribution: объединяет операционную систему и платформу. Например, Android/Web, iOS/Web, Windows/Web, Linux/Web</li><li>Web-Assisted Installs: iOS, Android, Windows</li></ul> | Д | Н |
| Гео/страна | <ul><li>Просматривайте тенденции трафика и вовлеченности по странам</li><li>Результаты могут напрямую воздействовать на инвестиционные решения в каждой стране</li></ul> | Д | Д |
| Медиа-источник / кампания | **Медиаисточник**<br /><br />Медиаисточник, атрибутированный конверсии<ul><li>Чтобы просмотреть подробные данные кампании, переходите по уровням ее иерархии: кампания> группа объявлений > объявление.</li><li>Доступные уровни иерархии различаются в разных медиаисточниках</li></ul>**Названия кампаний**<ul><li>Доступные названия кампаний на основе параметров URL-адреса.</li><li>Названия кампаний доступны не во всех кейсах.</li></ul> | Д | Д |
| Дополнительная причина блокировки | Реклама, прямой, электронная почта, реферальный, органический поиск, социальные | Н | Д |
| ID аккаунта сети | Включает платные, <Anchor target="_blank" href="/marketers/ru/docs/owned-media-attribution">собственные</Anchor> и заработанные | Н | Д |
| Окно повторного вовлечения |  | Н | Д |

</Accordion>

<div id="other-settings" />

<Accordion title="Другие настройки">

| Параметр | Description(Описание) |
| --- | --- |
| Пакет брендов | Дэшборды PBA содержат данные на уровне brand-bundle. Бандлы состоят из веб-сайта, 1 приложения для Android и 1 приложения для iOS.<ul><li>Вы можете выбирать наборы, если ваши <Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings#часто-задаваемые-вопросы">разрешения</Anchor> позволяют просматривать/редактировать входящие в них приложения.</li><li>Используйте переключатель для перехода между наборами.</li><li><Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings">Создание и редактирование наборов.</Anchor></li></ul> |
| Настройки PBA | <ul><li>Настроить события конверсии</li><li>Изменить настройки бандла</li></ul> |

</Accordion>

<div id="additional-information" />

## Информация

<div id="traits-and-limitations" />

<Accordion title="Спецификации и ограничения">

Дэшборды и отчеты PBA обновляются <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support#eod">ежедневно</Anchor> по часовому поясу UTC.

* Ежедневная обработка охватывает события, полученные в течение предыдущего дня.
* Финализация данных:
  * В случае с Web-Assisted Installs атрибуция сайта в PBA выявляет дополнительные связанные события в течение первых 7 дней после конверсии. Это может изменить медиаисточник, который в итоге будет определен как ответственный за конверсию.
  * В связанных отчетах по необработанным данным поле *final\_data* имеет значение false в течение начального 7-дневного периода.

Дэшборды PBA не поддерживают локальную валюту, поэтому данные отображаются в USD.

</Accordion>

<div data-zendesk-anchors="pba-dashboards=%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4-pba h_01HNJGN4BYRH14QXS4SWQAHR8D=%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4-pba settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HNJGN4BYF8NFYYWHG30RHEJH=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HNJGN4BYSHM9PFYQQ86ZR84X=filtering-options filter-panel-in-pba-dashboards=%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D1%8C-%D1%84%D0%B8%D0%BB%D1%8C%D1%82%D1%80%D0%BE%D0%B2-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B0%D1%85-pba h_01HNJGN4BYVYY2MKK5G3RCS07W=%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D1%8C-%D1%84%D0%B8%D0%BB%D1%8C%D1%82%D1%80%D0%BE%D0%B2-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B0%D1%85-pba filters-and-date-picker=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%84%D0%B8%D0%BB%D1%8C%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%B0%D0%B6%D0%B4%D0%BE%D0%B3%D0%BE-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B0 h_01HNJGN4BZ2KZAK120ZGT3B23W=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%84%D0%B8%D0%BB%D1%8C%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%B0%D0%B6%D0%B4%D0%BE%D0%B3%D0%BE-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B0 h_01HNJGN4BZV94W8W2GBXCZF563=grouping-options 01EDDQYQ8RWQZZTEZY9AVT1M64=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 01EDDQYQ8R5JPZE30ETV70FJVN=other-settings additional-information=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F h_01HNJGN4BZ9BMV7BQRQCKGYSSP=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F h_01HNJGN4BZFMG73SPZ1J4Z7TT5=traits-and-limitations" />
