---
title: Параметры кампаний в ETL-отчетах о расходах
metadata:
  keywords:
    - cost
    - Advertisers
    - Xpend
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2021-06-02T17:21:22Z'
  edited_at: '2026-10-21T13:57:34Z'
  id: 360020994977
  locale: ru-ru
  section: Cost aggregation
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/ru/articles/360020994977-Campaign-properties-in-cost-ETL-reports
---
> **Краткий обзор**. Узнайте о свойствах кампании и о том, как они отображаются в данных о расходах ETL в AppsFlyer.

<div id="about-campaign-properties" />

## О свойствах кампании

Свойства кампании — это особая группа параметров, которые представляют собой различные настройки рекламной кампании, включая цель кампании, тип ставки и сумму ставки. Эти параметры вы обычно просматриваете и редактируете на дэшборде рекламной сети, но AppsFlyer извлекает измерения свойств кампании и делает данные доступными в Cost ETL, чтобы вы могли просмотреть их так же, как и другие измерения.

С помощью данных о свойствах кампании вы можете:

- Просматривать все изменения ставок, сделанные вашей командой UA.
- Измерять и анализировать эффективность изменения ставки и то, оказало ли оно желаемый эффект.

Данные AppsFlyer о свойствах кампании доступны для Meta Ads и Google. В последующих разделах вы узнаете, какие данные извлекает AppsFlyer, как они стандартизируются и сопоставляются с каждой рекламной сетью.

<div id="facebook" />

<Accordion title="Meta ads">

В таблице ниже вы узнаете, какие данные извлекает AppsFlyer, как они стандартизируются и сопоставляются с Meta Ads.

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
        Извлекается из: [campaign.objective](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights)
      </td>
    </tr>
    <tr>
      <td>
        Модель затрат
      </td>
      <td>
        Извлекается из: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview#opt">adset.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Сопоставление нормализованной модели затрат AppsFlyer
      </td>
      <td>
        | Модель затрат | Нормализованная модель затрат |
        | --- | --- |
        | * {"LINK_CLICKS"}<br />* {"POST_ENGAGEMENT"}<br />* REPLIES<br />* {"LANDING_PAGE_VIEWS"} | CPC |
        | * {"OFFSITE_"} CONVERSIONS<br />* {"DERIVED_EVENTS"}<br />* {"LEAD_GENERATION"} | CPA |
        | APP\_INSTALLS | CPI |
        | VALUE | ROI |
        | * REACH<br />* IMPRESSIONS<br />* SOCIAL\_IMPRESSIONS | CPM |
        | * THRUPLAY<br />* VIDEO\_VIEWS<br />* TWO\_SECOND\_CONTINUOUS\_VIDEO\_VIEWS | CPCV |
      <ul><li>Линия</li><li>POST_ENGLISH</li><li>ОТМЕНЫ</li><li>PLAYLIST_PLAYLIST_SHOP</li></ul> | CPC |
| <ul><li>ВЫПОЛНЕНИЕ_ УПРАВЛЕНИЙ</li><li>PLAYLIST_DESC</li><li>LEAD_GENERATION</li></ul> | CPA |
        | APP\_INSTALLS | CPI |
        | VALUE | ROI |
| <ul><li>ПОСМОТРЕТЬ</li><li>Импрессанты</li><li>IAL_PLAYLIST_BUTTON</li></ul> | CPM |
| <ul><li>ИСПОЛЬЗОВАТЬ</li><li>VIDEO_VIEWS</li><li>TWO_SECOND_CONTINUUS_VIDEO</li></ul> | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Стратегия определения ставки
      </td>
      <td>
        Извлекается из: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">adset.bid\_strategy</Anchor><br /><br />Если на уровне adset нет предложений\_strategy то: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">campaign.advertising\_channel\_sub\_type</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Нормализованная стратегия определения ставок AppsFlyer
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
        Параметр
      </td>
      <td>
        Сумма ставки в валюте рекламодателя
      </td>
    </tr>
    <tr>
      <td>
        Параметр
      </td>
      <td>
        Извлекается из: </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="google" />

<Accordion title="Google">

В таблице ниже вы узнаете, какие данные извлекает AppsFlyer, как они стандартизируются и сопоставляются с Google.

<table><thead><tr><th><font> <span>Параметр</span> </font></th><th><span> <font>Описание</font> </span></th></tr></thead><tbody><tr><td><span> <font> <span>цель кампании</span> </font> </span></td><td><p><font> <span>Извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type" target="_blank">campaign.advertising_channel_sub_type</a></span> </font></p><p><font> <span>Примечание: население следующих полей зависит от канала_под_тип:</span> </font></p><ul><li><font> <span>Рекламная кампания: APP_CAMPAIGN или APP_CAMPAIGN_FOR_ENGAGEMENT</span> </font></li><li><font> <span>Не AC: Каждое другое значение для channel_sub_type</span> </font></li></ul></td></tr><tr><td><span> <font>Стоимость модели</font> </span></td><td><ul><li><span>Для рекламной кампании извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>Для не-AC-кампаний извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td>    Примечание: заполнение следующих полей зависит от channel\_sub\_type:

    * Рекламная кампания: APP\_CAMPAIGN или APP\_CAMPAIGN\_FOR\_ENGAGEMENT
    * Не рекламная кампания: Любое другое значение для channel\_sub\_type
  </td>
</tr>
<tr>
  <td>
    Модель затрат
  </td>
  <td>
    * Для рекламной кампании извлекается из: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
    * Для не рекламной кампании извлекается из: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">campaign.bidding\_strategy\_type</Anchor>
  </td>
</tr>
<tr>
  <td>
    Сопоставление нормализованной модели затрат AppsFlyer
  </td>
  <td>
    <table><thead><tr><th colspan="2">Модель затрат</th><th>Нормализованная модель затрат</th></tr></thead><tbody><tr><td rowspan="4"> <span>Рекламная кампания</span><span></span><br/> </td><td><ul><li>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</li><li>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</td><td><span>ROI</span></td></tr><tr><td><ul><li>UNKNOWN</li><li>UNSPECIFIED</li></ul></td><td><span>Другое</span></td></tr><tr><td>Не рекламная кампания</td><td><ul><li>REACH</li><li>ENHANCED_CPC</li><li>MANUAL_CPC</li><li>PERCENT_CPC</li><li>TARGET_SPEND</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>MANUAL_CPM</li><li>TARGET_CPM</li><li>TARGET_IMPRESSION_SHARE</li></ul></td><td><span>CPM</span></td></tr><tr><td> </td><td>MANUAL_CPV</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSIONS</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION_VALUE</li><li>TARGET_ROAS</li></ul></td><td><span>ROI</span></td></tr><tr><td><span> </span></td><td><ul><li>COMMISSION</li><li>PAGE_ONE_PROMOTED</li><li>TARGET_OUTRANK_SHARE</li><li>UNKNOWN</li><li>UNSPECIFIED</li></ul></td><td><span>Другое</span></td></tr></tbody></table>
  </td>
</tr>
<tr>
  <td>
    Стратегия определения ставки
  </td>
  <td>
    * Для рекламной кампании извлекается из: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
    * Для не рекламной кампании извлекается из: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">campaign.bidding\_strategy\_type</Anchor>
  </td>
</tr>
<tr>
  <td>
    Нормализованная стратегия определения ставок AppsFlyer
  </td>
  <td>
    <table><thead><tr><th colspan="2"><font> <span>Стратегия определения ставки</span> </font></th><th><font> <span>Нормализованная стратегия определения ставок</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font> <span>Рекламная кампания</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Максимальная ставка</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Целевая ставка</span> </font></td></tr><tr><td><ul><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Другое</span> </font></td></tr><tr><td rowspan="5"><font> <span>Не рекламная кампания</span> </font></td><td><ul><li><font> <span>ENHANCED_CPC</span> </font></li><li><font> <span>MANUAL_CPC</span> </font></li><li><font> <span>MANUAL_CPM</span> </font></li><li><font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Ручная ставка</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONS</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li><font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Автоматическая ставка</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Целевая ставка</span> </font></td></tr><tr><td><ul><li><font> <span>COMMISSION</span> </font></li><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Другое</span> </font></td></tr><tr><td><font> <span>Все остальное</span> </font></td><td><font> <span>Неизвестно</span> </font></td></tr></tbody></table>
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
    Извлекается из:  <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros">campaign.target\_cpa.target\_cpa\_micros</Anchor>
  </td>
</tr></td><td><table><thead><tr><th colspan="2">
        Модель затрат
      </th><th>
        Описание
      </th></tr></thead><tbody><tr><td rowspan="4"><span>AC</span><span><br/></span></td><td><ul><li>OPTIMIZ_INSTALLS_TITLE</li><li>OPTIMIZE_IN_APP_CONVERSIONS</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_IN_APP_CONVERSIONS</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_POPUP_TITLE</td><td><span>ROI</span></td></tr><tr><td><ul><li>НЕИЗВЕСТНО</li><li>СПЕЦИФИКАЦИЯ</li></ul></td><td><span>Другое</span></td></tr><tr><td>Non-AC</td><td><ul><li>ПОСМОТРЕТЬ</li><li>Закрыть CPC</li><li>MANUAL_CPC</li><li>Контрагент</li><li>Порыв торговли</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>MANUAL_CPM</li><li>TARGET_CPM</li><li>TARGET_IMPRESSION_SHARE</li></ul></td><td><span>CPM</span></td></tr><tr><td> </td><td>MANUAL_CPV</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZ_CONVERSIONS</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION_VALIDATE</li><li>TARGET_ROAS</li></ul></td><td><span>ROI</span></td></tr><tr><td><span> </span></td><td><ul><li>Комиссар</li><li>PAGE_ONE_PROMOD</li><li>TARGET_OUTRANK_SHARE</li><li>НЕИЗВЕСТНО</li><li>СПЕЦИФИКАЦИЯ</li></ul></td><td><span>Другое</span></td></tr></tbody></table></td></tr><tr><td><span> <font>Стратегия Ставки</font> </span></td><td><ul><li><span>Для рекламной кампании извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>Для не-AC-кампаний извлекается из: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td>    Если на уровне группы объявлений нет параметра bid\_strategy, то: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">campaign.bid\_strategy</Anchor>
  </td>
</tr>
<tr>
  <td>
    Стратегия назначения ставок, стандартизированная AppsFlyer
  </td>
  <td>
    | Стратегия назначения ставки | Нормализованная стратегия назначения ставок |
    | --- | --- |
    | * {"LOWEST_COST_"} {"WITHOUT_CAP"}<br />* {"COST_CAP"}<br />* {"LOWEST_COST_"} {"WITH_MIN_ROAS"} | Автоматическая ставка |
    | TARGET\_COST | Целевая ставка |
    | Другое | Неизвестно |
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
    Извлекается из: adset.bid\_amount
  </td>
</tr></td><td><table><thead><tr><th colspan="2"><font> <span>Стратегия Ставки</span> </font></th><th><font> <span>Нормированная стратегия предложений</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font> <span>AC</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Макс. ставка</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Другое</span> </font></td></tr><tr><td rowspan="5"><font> <span>Non-AC</span> </font></td><td><ul><li><font> <span>ENHANCED_CPC</span> </font></li><li><font> <span>MANUAL_CPC</span> </font></li><li><font> <span>MANUAL_CPM</span> </font></li><li><font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Ручная цена</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONS</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li><font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Auto bid</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>КОМИССИЯ</span> </font></li><li><font> <span>НЕИЗВЕСТНО</span> </font></li><li><font> <span>НЕ УКАЗАНО</span> </font></li></ul></td><td><font> <span>Другое</span> </font></td></tr><tr><td><font> <span>Все остальное</span> </font></td><td><font> <span>Неизвестное</span> </font></td></tr></tbody></table></td></tr><tr><td><span> <font>Сумма ставки</font> </span></td><td><span> <font>Сумма покупки в валюте рекламодателя</font> </span></td></tr><tr><td><span> <font>Оригинальная сумма</font> </span></td><td><span> <font>извлечено из: </font> </span> <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros" target="_blank">кампании.target_cpa.target_cpa_micros</a></td></tr></tbody></table>

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
        Извлекается из: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#campaigns">campaign.objective</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Параметр
      </td>
      <td>
        Извлекается из: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#squad-optimization-goals">adsquad.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Сопоставление нормализованной модели затрат AppsFlyer
      </td>
      <td>
        | Модель затрат | Нормализованная модель затрат |
        | --- | --- |
        | * SWIPES<br />* STORY\_OPENS | CPC |
        | * USES<br />* {"PIXEL_ADD_TO_CART"}<br />* {"PIXEL_PURCHASE"}<br />* {"PIXEL_SIGNUP"}<br />* {"APP_ADD_TO_CART"}<br />* {"APP_PURCHASE"}<br />* {"APP_SIGNUP"} | CPA |
        | APP\_INSTALLS | CPI |
        | * IMPRESSIONS | CPM |
        | * VIDEO\_VIEWS<br />* VIDEO\_VIEWS\_15\_SEC | CPCV |
      <ul><li>ПЕРЕВОДЫ</li><li>Оформление</li></ul> | CPC |
| <ul><li>ИСПОЛЬЗОВАНИЯ</li><li>SHARE_PLAYLIST</li><li>PARTY_BTN</li><li>PARTY_BTN</li><li>Добавить карту</li><li>APP_PURCHASE</li><li>PLAYLIST</li></ul> | CPA |
        | APP\_INSTALLS | CPI |
| <ul><li>Импрессанты</li></ul> | CPM |
| <ul><li>VIDEO_VIEWS</li><li>VIDEO VIEWS_15_SEC</li></ul> | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Стратегия определения ставки
      </td>
      <td>
        Извлекается из: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#bid-strategy">adsquad.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        | Стратегия определения ставки | Нормализованная стратегия определения ставок |
        | --- | --- |
        | * MIN\_ROAS<br />* AUTO\_BID | Автоматическая ставка |
        | LOWEST\_COST\_WITH\_MAX\_BID | Максимальная ставка |
        | TARGET\_COST | Целевая ставка |
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
        Цель кампании
      </td>
    </tr>
    <tr>
      <td>
        Исходная сумма ставки
      </td>
      <td>
        Извлекается из: adsquad.bid\_micro
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="about-campaign-properties=%D0%BE-%D1%81%D0%B2%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01J1PX98QNCZG9Y9PRZQ4ZEEFK=%D0%BE-%D1%81%D0%B2%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01J1PX98QNX2T408GB2WV0RFZH=facebook h_01J1PX98QP22PPG9V84DD5WEM1=google h_01J1PXNDS4V16NQQQGMBND9PAF=snap" />
