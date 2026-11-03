---
title: Настройка кроссплатформенных ссылок для мультидевайсных кампаний
metadata:
  keywords:
    - Attribution
    - Advertisers
    - CTV
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-06-19T07:02:43Z'
  edited_at: '2026-09-17T00:20:27Z'
  id: 6966260647185
  locale: ru
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ru/articles/6966260647185
---
> Краткий обзор: Как продвигать, атрибутировать и измерять установки приложений на платформах по просмотрам рекламы на других платформах. Например, атрибутировать установки мобильного приложения к рекламе, просмотренной на устройствах CTV, установки приложения для игровой консоли к рекламе, просмотренной на мобильных устройствах или на настольных компьютерах (в вебе), установки приложения CTV к рекламе, просмотренной на мобильных устройствах или на настольных компьютерах (в вебе).

## Обзор

С помощью кроссплатформенных ссылок атрибуции от AppsFlyer (URL показов) вы можете атрибутировать установки на одной платформе к рекламе, просмотренной на другой платформе. Несколько установок в одном домохозяйстве могут быть атрибутированы одному и тому же кроссплатформенному показу рекламы.

### Как работает логика атрибуции?

* Показы в AppsFlyer определяются по идентификатору шаблона OneLink и назначаются каждой платформе, заданной в шаблоне.
* Установки определяются по приложению и платформе.
* Логика сопоставления: показы на уровне шаблона сопоставляются с конкретным запуском приложения с помощью вероятностной атрибуции. Можно сопоставить любой вариант приложения в группе.

## Создание шаблона OneLink для кроссплатформенной атрибуции

Один шаблон поддерживает ваше приложение на нескольких платформах (это означает, что один шаблон работает на всех платформах). В шаблоне вы объединяете все варианты вашего приложения для разных платформ (мобильных, CTV, настольных компьютеров, консолей).

1. Создайте или отредактируйте <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">шаблон OneLink</Anchor> для кроссплатформенной атрибуции.
2. В разделе**Кроссплатформенная атрибуция**нажмите кнопку **Редактировать ->Включить кроссплатформенную атрибуцию.**
3. В раскрывающемся списке соответствующих платформ выберите соответствующее приложение. **Примечание**: Каждое приложение можно добавить только в один шаблон OneLink с включенной кросс-платформенной атрибуцией. [<Image alt="Кроссплатформенная атрибуция" src="https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png" width="476px" />](https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png)

## Настройка интеграции партнёров для кроссплатформенной атрибуции

Чтобы настроить кроссплатформенную атрибуцию с использованием URL-адресов кроссплатформенных показов, настройте интеграцию партнёра для каждого целевого приложения.

> 🚧 **Важно!**
>
> Убедитесь, что вы включили интеграцию партнёра, выполнив шаги ниже для всех целевых приложений, которые вы выбрали в шаблоне OneLink (см. [раздел выше](#создание-шаблона-onelink-для-кроссплатформенной-атрибуции)). Если интеграция отключена для одного из целевых приложений, кроссплатформенная атрибуция не произойдет.

<div id="h_01K2HBXDWSG3R1WZXT5RB0W48D" />

<Accordion title="1. Выберите целевое приложение интеграции партнёра">

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Интеграции партнеров** > **Активные интеграции**
2. Выберите интегрированного партнёра.
3. На вкладке **Интеграция** выберите целевое приложение из выпадающего списка **Приложение**.

</Accordion>

<div id="step-2-enable-viewthrough-attribution" />

<Accordion title="Шаг 2: Включите атрибуцию по просмотрам">

Для ссылок, которые будут использоваться интегрированными партнёрами, необходимо включить атрибуцию по просмотрам.

1. На вкладке**Интеграция**включите опцию **Установить атрибуцию по просмотрам**.
2. Нажмите **Сохранить интеграцию**.

</Accordion>

<div id="step-4-create-an-attribution-link-crossplatform-impression-url" />

<Accordion title="3. Создайте ссылку атрибуции (кросс-платформенный URL-адрес для показов):">

Как создать <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">ссылку атрибуции</Anchor> (кросс-платформенный URL-адрес для показов) для интегрированных сетей:

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Интеграции партнеров** > **Активные интеграции** и выберите интегрированного партнера.
2. На вкладке **Ссылка атрибуции** при создании<Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">ссылки OneLink</Anchor> выберите Использовать OneLink.
3. Выберите шаблон OneLink, который вы создали для кроссплатформенной атрибуции.
4. Прокрутите вниз до опции **Атрибуция по просмотрам**.[![](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)
5. Включите опцию **Кроссплатформенная атрибуция**.`af_xplatform=true` Это добавляет`af_xplatform=true`параметр ссылки атрибуции показа и предоставляет ссылке возможности кроссплатформенной атрибуции. Без этого параметра URL функционирует как обычный URL-адрес показов, который не может атрибутировать несколько установок одному показу.
6. **Настройте `af_xplatform_vt_lookback`Окно кроссплатформенной атрибуции по просмотрамaf\_xplatform\_vt\_lookback. **Таким образом можно добавить к ссылке атрибуции просмотров параметр** `af_xplatform_vt_lookback` и указать количество часов (до 72) после показа, в течение которых установка приложения может быть атрибутирована показу.**
7. При необходимости, добавьте любые дополнительные параметры атрибуции. Используйте соглашения об именовании, которые идентифицируют вашу кроссплатформенную кампанию приложений. <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее</Anchor> о параметрах, которые можно добавить для получения дополнительных данных и метрик. Пример ссылки:

   ```http
   https://impressions.onelink.me/{template_id}?pid=__media_source__&af_xplatform=true&af_xplatform_vt_lookback=24h&af_siteid=__CSITE__&c=__ctv_to_mobile__&af_channel=__PLACEMENT__&af_c_id=__CAMPAIGN_ID__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_source_platform=__source_platform__&af_source_device_category=__device_category__&af_ad_type=__CTYPE__&redirect=false
   ```
8. Передайте ссылку в рекламную сеть для размещения за рекламой, показанной на платформах CTV, ПК или консолей.

> 🚧 **Важно!**
>
> Для собственных медиа и неинтегрированных партнёров нужно добавить необходимые параметры.  <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее</Anchor> о параметрах, которые можно добавить для получения дополнительных данных и метрик.

</Accordion>

<div id="equal-priority-advanced-setting" />

<Accordion title="Advanced (Расширенные настройки): Настройка равного приоритета (необязательно)">

Вы можете по желанию назначить **равный приоритет** для кликов и показов в рамках кроссплатформенной атрибуции. Эта расширенная настройка позволяет AppsFlyer рассматривать показы (например, для CTV и консолей) как имеющие такой же приоритет атрибуции, как и клики. Дополнительные сведения см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#приоритеты-методов-атрибуции-водопад-атрибуции">Приоритеты метода атрибуции</Anchor>.

**Как включить равный приоритет:**

1. В разделе настроек кроссплатформенной атрибуции выставьте флажок **Равный приоритет**.
2. Нажмите **Сохранить**.

> 📘 **Примечание**
>
> Включение равного приоритета может привести к тому, что AppsFlyer будет придавать приоритет своей собственной атрибуции над другими источниками. Используйте эту настройку с осторожностью и только если она соответствует вашей общей стратегии атрибуции.

</Accordion>

## Характеристики и ограничения

| Специфика | Замечания |
| --- | --- |
| <span id="attribution-window"></span>Окно атрибуции | От 1 до 72 часов, в зависимости от параметра окна атрибуции `af_xplatform_vt_lookback` (по умолчанию 24 часа). |
| <span id="retargeting"></span>Обязательный | <ul><li>Реатрибуция: Поддерживается для межплатформенного перехода на мобильное приложение. Не для других платформ.</li><li>Повторное вовлечение: Не поддерживается</li></ul> |
| <span id="attribution-method"></span>Метод атрибуции | Атрибуция по просмотрам с помощью вероятностного моделирования |
| <span id="household-attribution"></span>Атрибуция домохозяйств | поддерживается. То есть несколько установок в одном домохозяйстве могут быть атрибутированы одному и тому же показу рекламы на разных платформах. |
| <span id="reporting"></span>Отчётность | <ul><li>Кросс-платформенные установки доступны в обычных дэшбордах и отчётах AppsFlyer:<ul><li>Агрегированные данные <Anchor target="_blank" href="/marketers/ru/docs/getting-started-with-appsflyer-dashboards">на дэшборах</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/aggregated-and-analytics-reporting-overview">в отчётах</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview">Отчёты</Anchor> по сырым данным</li></ul></li><li>Кроссплатформенные показы не отображаются на дэшбордах на уровне приложений. Однако они доступны в отчёте <Anchor target="_blank" href="/marketers/ru/docs/data-locker-advertiser-reports#user-journey">Кросс-платформенные интеракции</Anchor> через Data Locker.</li><li>Убедитесь, что вы используете принятые обозначения параметров, которые легко идентифицируют вашу кроссплатформенную кампанию.</li></ul> |
| <span id="ip-masking"></span>Маскирование IP-адресов | Маскировка IP-адресов для кросcплатформенных интеракций не поддерживается, поскольку это свойство уровня приложений. Если настроен параметр `ip_masking`, установка не будет атрибутирована к кроссплатформенной интеракции. |
| <span id="ctvto-mobile"></span>CTV-to-mobile | Потоки атрибуции CTV-to-mobile доступны только [интегрированным партнёрам](/docs/set-up-cross-platform-links-for-multi-device-campaigns#list-of-ad-networks), имеющим разрешение на проведение кроссплатформенных кампаний. |
| <span id="cross-platform-attribution-links-in-mobile-devices"></span>Кроссплатформенные ссылки атрибуции на мобильных устройствах | При просмотре кроссплатформенной ссылки атрибуции на мобильном устройстве атрибуция определяется стандартной логикой вероятностного моделирования для мобильных устройств, а не кроссплатформенным потоком атрибуции, разработанным для <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#tv-screens">CTV</Anchor>, ПК и консолей. Следовательно, мобильные показы не будут иметь права на [равный приоритет](#step-3-enable-equal-priority-for-crossplatform-impressions), [расширенное окно атрибуции](#attribution-window) или [атрибуцию домохозяйств](#household-attribution), которые доступны для настоящих кроссплатформенных показов. |
| <span id="agency-permissions"></span>Разрешения агентства | Агентства не могут менять положение переключателя «Кроссплатформенный равный приоритет атрибуции» со своей стороны. Эта конфигурация напрямую переносится из настроек рекламодателя для конкретной рекламной сети. |

## Расхождения

AppsFlyer и tvScientific отличаются своими моделями атрибуции. Это может привести к расхождениям между данными на дэшбордах tvScientific и AppsFlyer. Причины расхождений см. в таблице ниже:

| Причина | tvScientific | AppsFlyer: |
| --- | --- | --- |
| Базовая модель | Модель атрибуции по общим заслугам | Модель атрибуции по последнему взаимодействию |
| Окна атрибуции | До 30 дней | До 72 часов |
| Обязательный | Атрибуция как новых пользователей (установки), так и возвращающихся пользователей (повторные вовлечения) | Атрибуция только новых пользователей (установок) |
| Присвоение затрат | Затраты присваиваются показу независимо от операционной системы | Затраты присваиваются показу отдельно для iOS и Android |

## Часто задаваемые вопросы

<div id="does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on" />

<Accordion title="Нужно ли включать переключатель Активировать атрибуцию по просмотрам с помощью вероятностного моделирования?">

Нет. Чтобы работала кроссплатформенная атрибуция по просмотрам, переключатель Активировать атрибуцию по просмотрам с помощью вероятностного моделирования в настройках вашего приложения включать не нужно.

</Accordion>

<div id="why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />

<Accordion title="Почему я не вижу показов для моих кросс-платформенных кампаний на дэшборде?">

<Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-data-via-data-locker#типы-отчётов-и-доступность">Кроссплатформенные показы</Anchor> не отображаются на дэшбордах на уровне приложений. Это связано с тем, что один показ на CTV может привести к нескольким конверсиям в разных приложениях, и нет точного способа распределения показов между приложениями. Вы можете получить доступ к данным о показах в отчёте <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-data-via-data-locker#типы-отчётов-и-доступность">Кросс-платформенные взаимодействия в Data Locker</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 01H8V0RV7X8JEVEJ36TJB1X43D=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 app-group-vs-individual-app-%E2%80%93-attribution-logic=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%BB%D0%BE%D0%B3%D0%B8%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01KANVNVCY6JFTJ1SVK3DGM54C=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%BB%D0%BE%D0%B3%D0%B8%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%88%D0%B0%D0%B1%D0%BB%D0%BE%D0%BD%D0%B0-onelink-%D0%B4%D0%BB%D1%8F-%D0%BA%D1%80%D0%BE%D1%81%D1%81%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HVECG1TZ8B5GH28CZM2186BF=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%88%D0%B0%D0%B1%D0%BB%D0%BE%D0%BD%D0%B0-onelink-%D0%B4%D0%BB%D1%8F-%D0%BA%D1%80%D0%BE%D1%81%D1%81%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 set-up-crossplatform-attribution=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%BE%D0%B2-%D0%B4%D0%BB%D1%8F-%D0%BA%D1%80%D0%BE%D1%81%D1%81%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HVECG1TZSDTP0WBG7XYM509G=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%BE%D0%B2-%D0%B4%D0%BB%D1%8F-%D0%BA%D1%80%D0%BE%D1%81%D1%81%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01JEKG3V0C75G782RC7CE9DAV2=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01HVECG1TZKNG17STSN5XJAF9C=step-2-enable-viewthrough-attribution step-4-create-an%C2%A0attribution-link%C2%A0crossplatform-impression-url=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ6WP257R9D8A105FR=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ3K1EFA22716K2B9X=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE-1 h_01K2HBZKX0EJHSVCXJJ97NMVXZ=equal-priority-advanced-setting equal-priority-impact-note=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01K2HBZKX0ECJPTQMPPXC3JBVC=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HVED5DJPFR5XCWYDSYCHMCR6=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F discrepancies=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HVED5DJPMP3AQDTN3GM77T2F=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F faq=%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HVED5DJPBPDSZ0AAY1RG8NEZ=%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01K4AC2J63B4MBTDGZHH7ACRCG=does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on why-don%E2%80%99t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard h_01K4AC2J63KBF8X20DMNPW1GTK=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />
