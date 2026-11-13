---
title: Свойства кампании в ценовых ETL отчетах
metadata:
  keywords:
    - стоимость
    - Клиенты
    - Xpend
    - Маркетеры
    - ROI360
x-zendesk:
  category: Маркетеры
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Маркетеры
    - ROI360
  created_at: '2021-06-02T17:21:22Z'
  edited_at: '2025-04-05T11:08:21Z'
  id: 360020994977
  locale: ru-ru
  section: Агрегация затрат
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/ru/articles/360020994977-Campaign-properties-in-cost-ETL-reports
---
> **На взгляд:** Узнайте о свойствах кампаний и о том, как они отображаются в данных о ценах AppsFlyer стоимости.

<div id="about-campaign-properties" />

## О свойствах кампании

Свойства кампании – это специальная группа измерений, которая отражает различные параметры рекламной кампании, включая цель кампании, тип ставки и сумму ставки. Это настройки, которые вы обычно просматриваете и редактируете в вашей панели администрирования сети, Но AppsFlyer тянет размеры свойств кампании и делает данные доступными в секции Cost ETL, так же, как вы просматриваете другие измерения.

С данными свойств кампании можно:

- Посмотреть все изменения в ставке, сделанные вашей командой UA.
- Измерение и анализ эффективности изменения в заявке и то, имеет ли оно предполагаемый эффект.

Данные о свойствах кампаний AppsFlyer доступны для мета рекламы и Google. Посмотрите, какие данные притягивает AppFlyer и как он нормализован и сопоставлен с каждой рекламной сетью, в следующих разделах.

<div id="facebook" />

<Accordion title="Meta ads">

Посмотрите, какие данные притягивают AppsFlyer и как он стандартизирован и сопоставлен с мета-объявлениями в следующей таблице.

<Table>
  <thead>
    <tr>
      <th>
        Параметр
      </th>
      <th>
        Описание
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Цель кампании
      </td>
      <td>
        извлечено из: [campaign.objective](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights)
      </td>
    </tr>
    <tr>
      <td>
        Стоимость модели
      </td>
      <td>
        извлечено из: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview#opt">adset.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer нормализованная модель затрат
      </td>
      <td>
        | Стоимость модели | Нормализованная стоимость |
        | --- | --- |
| <ul><li>Линия</li><li>POST_ENGLISH</li><li>ОТМЕНЫ</li><li>PLAYLIST_PLAYLIST_SHOP</li></ul> | CPC |
| <ul><li>ВЫПОЛНЕНИЕ_ УПРАВЛЕНИЙ</li><li>PLAYLIST_DESC</li><li>LEAD_GENERATION</li></ul> | CPA |
        | APP\_INSTALLS | CPI |
        | VALUE | ROI |
| <ul><li>ПОСМОТРЕТЬ</li><li>Импрессанты</li><li>IAL_PLAYLIST_BUTTON</li></ul> | CPM |
| <ul><li>ИСПОЛЬЗОВАТЬ</li><li>VIDEO_VIEWS</li><li>TWO_SECOND_CONTINUUS_VIDEO</li></ul> | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Стратегия назначения ставок
      </td>
      <td>
        извлечено из: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">adset.bid\_strategy</Anchor><br /><br />Если на уровне adset нет предложений\_strategy то: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">предложение\_стратегия</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer нормализовала стратегию ставок
      </td>
      <td>
        | Стратегия покупки | Нормализованная стратегия торгов |
        | --- | --- |
| <ul><li>{"LOWEST_COST_"} WITHOUT_CAP</li><li>ЗАТРАТ_CAP</li><li>{"LOWEST_COST_"} WITH_MIN_ROAS</li></ul> | Автоматическая ставка |
        | TARGET\_COST | Целевая ставка |
        | Все остальное | Неизвестное |
      </td>
    </tr>
    <tr>
      <td>
        Сумма ставки
      </td>
      <td>
        Сумма ставки в валюте рекламодателя
      </td>
    </tr>
    <tr>
      <td>
        Исходная сумма ставки
      </td>
      <td>
        Выключено из: adset.bid\_amount
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="google" />

<Accordion title="Google">

Посмотрите, какие данные притягивает AppsFlyer и как он стандартизирован и сопоставлен с Google, в следующей таблице.

<table><thead><tr><th><font> <span>Параметр</span> </font></th><th><span> <font>Описание</font> </span></th></tr></thead><tbody><tr><td><span> <font> <span>цель кампании</span> </font> </span></td><td><p><font> <span>Извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type" target="_blank">campaign.advertising_channel_sub_type</a></span> </font></p><p><font> <span>Примечание: население следующих полей зависит от канала_под_тип:</span> </font></p><ul><li><font> <span>Рекламная кампания: APP_CAMPAIGN или APP_CAMPAIGN_FOR_ENGAGEMENT</span> </font></li><li><font> <span>Не AC: Каждое другое значение для channel_sub_type</span> </font></li></ul></td></tr><tr><td><span> <font>Стоимость модели</font> </span></td><td><ul><li><span>Для рекламной кампании извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>Для не-AC-кампаний извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td><span> <span>AppsFlyer нормализованная модель затрат</span> </span></td><td><table><thead><tr><th colspan="2">Себестоимость модели</th><th>Нормализованная модель затрат</th></tr></thead><tbody><tr><td rowspan="4"><span>AC</span><span><br/></span></td><td><ul><li>OPTIMIZ_INSTALLS_TITLE</li><li>OPTIMIZE_IN_APP_CONVERSIONS</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_IN_APP_CONVERSIONS</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_POPUP_TITLE</td><td><span>ROI</span></td></tr><tr><td><ul><li>НЕИЗВЕСТНО</li><li>СПЕЦИФИКАЦИЯ</li></ul></td><td><span>Другое</span></td></tr><tr><td>Non-AC</td><td><ul><li>ПОСМОТРЕТЬ</li><li>Закрыть CPC</li><li>MANUAL_CPC</li><li>Контрагент</li><li>Порыв торговли</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>MANUAL_CPM</li><li>TARGET_CPM</li><li>TARGET_IMPRESSION_SHARE</li></ul></td><td><span>CPM</span></td></tr><tr><td> </td><td>MANUAL_CPV</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZ_CONVERSIONS</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION_VALIDATE</li><li>TARGET_ROAS</li></ul></td><td><span>ROI</span></td></tr><tr><td><span> </span></td><td><ul><li>Комиссар</li><li>PAGE_ONE_PROMOD</li><li>TARGET_OUTRANK_SHARE</li><li>НЕИЗВЕСТНО</li><li>СПЕЦИФИКАЦИЯ</li></ul></td><td><span>Другое</span></td></tr></tbody></table></td></tr><tr><td><span> <font>Стратегия Ставки</font> </span></td><td><ul><li><span>Для рекламной кампании извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>Для не-AC-кампаний извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td><font> <span>AppsFlyer нормализовала стратегию цен</span> </font></td><td><table><thead><tr><th colspan="2"><font> <span>Стратегия Ставки</span> </font></th><th><font> <span>Нормированная стратегия предложений</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font> <span>AC</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Макс. ставка</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Другое</span> </font></td></tr><tr><td rowspan="5"><font> <span>Non-AC</span> </font></td><td><ul><li><font> <span>ENHANCED_CPC</span> </font></li><li><font> <span>MANUAL_CPC</span> </font></li><li><font> <span>MANUAL_CPM</span> </font></li><li><font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Ручная цена</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONS</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li><font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Auto bid</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>КОМИССИЯ</span> </font></li><li><font> <span>НЕИЗВЕСТНО</span> </font></li><li><font> <span>НЕ УКАЗАНО</span> </font></li></ul></td><td><font> <span>Другое</span> </font></td></tr><tr><td><font> <span>Все остальное</span> </font></td><td><font> <span>Неизвестное</span> </font></td></tr></tbody></table></td></tr><tr><td><span> <font>Сумма ставки</font> </span></td><td><span> <font>Сумма покупки в валюте рекламодателя</font> </span></td></tr><tr><td><span> <font>Оригинальная сумма</font> </span></td><td><span> <font>извлечено из: </font> </span> <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros" target="_blank">кампании.target_cpa.target_cpa_micros</a></td></tr></tbody></table>

</Accordion>

<div id="snap" />

<Accordion title="Snap">

<Table>
  <thead>
    <tr>
      <th>
        Параметр
      </th>
      <th>
        Описание
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Цель кампании
      </td>
      <td>
        извлечено из: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#campaigns">цель кампании</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Стоимость модели
      </td>
      <td>
        извлечено из: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#squad-optimization-goals">adsquad.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer нормализованная модель затрат
      </td>
      <td>
        | Стоимость модели | Нормализованная стоимость |
        | --- | --- |
| <ul><li>ПЕРЕВОДЫ</li><li>Оформление</li></ul> | CPC |
| <ul><li>ИСПОЛЬЗОВАНИЯ</li><li>SHARE_PLAYLIST</li><li>PARTY_BTN</li><li>PARTY_BTN</li><li>Добавить карту</li><li>APP_PURCHASE</li><li>PLAYLIST</li></ul> | CPA |
        | APP\_INSTALLS | CPI |
| <ul><li>Импрессанты</li></ul> | CPM |
| <ul><li>VIDEO_VIEWS</li><li>VIDEO VIEWS_15_SEC</li></ul> | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Стратегия назначения ставок
      </td>
      <td>
        извлечено из: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#bid-strategy">adsquad.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer нормализовала стратегию ставок
      </td>
      <td>
        | Стратегия покупки | Нормализованная стратегия торгов |
        | --- | --- |
| <ul><li>MIN_ROAS</li><li>AUTO_BID</li></ul> | Auto bid |
        | {"LOWEST_COST_"} {"WITH_MAX_BID"} | Max bid |
        | TARGET\_COST | Target bid |
      </td>
    </tr>
    <tr>
      <td>
        Сумма ставки
      </td>
      <td>
        Сумма ставки в валюте рекламодателя
      </td>
    </tr>
    <tr>
      <td>
        Исходная сумма ставки
      </td>
      <td>
        Извлечено из: adsquad.bid\_micro
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="h_01J1PX98QNCZG9Y9PRZQ4ZEEFK=about-campaign-properties h_01J1PX98QNX2T408GB2WV0RFZH=facebook h_01J1PX98QP22PPG9V84DD5WEM1=google h_01J1PXNDS4V16NQQQGMBND9PAF=snap" />
