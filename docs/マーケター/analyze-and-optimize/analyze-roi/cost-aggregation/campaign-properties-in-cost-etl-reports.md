---
title: コストETLレポートのキャンペーン設定情報
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
  edited_at: '2026-10-28T08:36:40Z'
  id: 360020994977
  locale: ja
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ja/articles/360020994977
---
> **概要：** キャンペーン設定情報の内容と、AppsFlyerのコストETLデータでの表示について説明します。

<div id="about-campaign-properties" />

## キャンペーン設定情報について

キャンペーン設定情報は、キャンペーンの目的、入札方式、入札額など、広告キャンペーンの各種設定を表すディメンションをまとめたものです。これらの設定は通常、アドネットワークの管理画面で確認・編集します。AppsFlyerでは、その設定情報を取得し、他のディメンションと同様にコストETLで確認できるようにしています。

キャンペーン設定情報を使用すると、次のことが可能になります。

* ユーザー獲得チームが行った入札設定の変更をすべて確認できます。
* 入札設定の変更による効果を計測・分析し、意図した効果が得られたかどうかを確認できます。

AppsFlyerのキャンペーン設定情報は、Meta広告とGoogleに対応しています。 AppsFlyerが取得するデータと、媒体ごとの値を共通表記に統一する際の対応関係を、以下で説明します。

<div id="facebook" />

<Accordion title="Meta広告">

AppsFlyerが取得するデータと、Meta広告の値を共通表記に統一する際の対応関係を、以下の表に示します。

<Table>
  <thead>
    <tr>
      <th>
        ディメンション
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        キャンペーンの目的
      </td>
      <td>
        取得元：[campaign.objective](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights)
      </td>
    </tr>
    <tr>
      <td>
        課金モデル
      </td>
      <td>
        取得元：<Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview#opt">adset.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        課金モデルとAppsFlyerの共通表記の対応表
      </td>
      <td>
        | 課金モデル | 共通表記に統一した課金モデル |
        | --- | --- |
        | * {"LINK_CLICKS"}<br />* {"POST_ENGAGEMENT"}<br />* REPLIES<br />* {"LANDING_PAGE_VIEWS"} | CPC |
        | * {"OFFSITE_"} CONVERSIONS<br />* {"DERIVED_EVENTS"}<br />* {"LEAD_GENERATION"} | CPA |
        | APP\_INSTALLS | CPI |
        | VALUE | ROI |
        | * REACH<br />* IMPRESSIONS<br />* SOCIAL\_IMPRESSIONS | CPM |
        | * THRUPLAY<br />* VIDEO\_VIEWS<br />* TWO\_SECOND\_CONTINUOUS\_VIDEO\_VIEWS | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        入札戦略
      </td>
      <td>
        取得元：<Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">adset.bid\_strategy</Anchor>

        広告セットにbid\_strategyがない場合の取得元：<Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">campaign.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyerの共通表記に統一した入札戦略
      </td>
      <td>
        | 入札戦略 | 共通表記に統一した入札戦略 |
        | --- | --- |
        | * {"LOWEST_COST_"} {"WITHOUT_CAP"}<br />* {"COST_CAP"}<br />* {"LOWEST_COST_"} {"WITH_MIN_ROAS"} | Auto bid |
        | TARGET\_COST | Target bid |
        | 上記以外 | Unknown |
      </td>
    </tr>
    <tr>
      <td>
        入札額
      </td>
      <td>
        広告主の通貨での入札額
      </td>
    </tr>
    <tr>
      <td>
        元の入札額
      </td>
      <td>
        取得元：adset.bid\_amount
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="google" />

<Accordion title="Google">

AppsFlyerが取得するデータと、Googleの値を共通表記に統一する際の対応関係を、以下の表に示します。

<Table>
  <thead>
    <tr>
      <th>
        ディメンション
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        キャンペーンの目的
      </td>
      <td>
        取得元：<Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type">campaign.advertising\_channel\_sub\_type</Anchor>

        注意：以下のフィールドに設定される値は、channel\_sub\_typeによって異なります。

        * AC：APP\_CAMPAIGNまたはAPP\_CAMPAIGN\_FOR\_ENGAGEMENT
        * Non-AC：channel\_sub\_typeが上記以外の値の場合
      </td>
    </tr>
    <tr>
      <td>
        課金モデル
      </td>
      <td>
        * ACの場合の取得元：<Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
        * Non-ACの場合の取得元：<Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">campaign.bidding\_strategy\_type</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        課金モデルとAppsFlyerの共通表記の対応表
      </td>
      <td>
        <table><thead><tr><th colspan="2">課金モデル</th><th>共通表記に統一した課金モデル</th></tr></thead><tbody><tr><td rowspan="4"> <span>AC</span><span><br/></span> </td><td><ul><li>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</li><li>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</td><td><span>ROI</span></td></tr><tr><td><ul><li>UNKNOWN</li><li>UNSPECIFIED</li></ul></td><td><span>Other</span></td></tr><tr><td>Non-AC</td><td><ul><li>REACH</li><li>ENHANCED_CPC</li><li>MANUAL_CPC</li><li>PERCENT_CPC</li><li>TARGET_SPEND</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>MANUAL_CPM</li><li>TARGET_CPM</li><li>TARGET_IMPRESSION_SHARE</li></ul></td><td><span>CPM</span></td></tr><tr><td> </td><td>MANUAL_CPV</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSIONS</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION_VALUE</li><li>TARGET_ROAS</li></ul></td><td><span>ROI</span></td></tr><tr><td><span> </span></td><td><ul><li>COMMISSION</li><li>PAGE_ONE_PROMOTED</li><li>TARGET_OUTRANK_SHARE</li><li>UNKNOWN</li><li>UNSPECIFIED</li></ul></td><td><span>Other</span></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        入札戦略
      </td>
      <td>
        * ACの場合の取得元：<Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
        * Non-ACの場合の取得元：<Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">campaign.bidding\_strategy\_type</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyerの共通表記に統一した入札戦略
      </td>
      <td>
        <table><thead><tr><th colspan="2"><font> <span>入札戦略</span> </font></th><th><font> <span>共通表記に統一した入札戦略</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font> <span>AC</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Max bid</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Other</span> </font></td></tr><tr><td rowspan="5"><font> <span>Non-AC</span> </font></td><td><ul><li><font> <span>ENHANCED_CPC</span> </font></li><li><font> <span>MANUAL_CPC</span> </font></li><li><font> <span>MANUAL_CPM</span> </font></li><li><font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Manual bid</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONS</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li><font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Auto bid</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>COMMISSION</span> </font></li><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Other</span> </font></td></tr><tr><td><font> <span>上記以外</span> </font></td><td><font> <span>Unknown</span> </font></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        入札額
      </td>
      <td>
        広告主の通貨での入札額
      </td>
    </tr>
    <tr>
      <td>
        元の入札額
      </td>
      <td>
        取得元：  <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros">campaign.target\_cpa.target\_cpa\_micros</Anchor>
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="snap" />

<Accordion title="Snap">

<Table>
  <thead>
    <tr>
      <th>
        ディメンション
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        キャンペーンの目的
      </td>
      <td>
        取得元：<Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#campaigns">campaign.objective</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        課金モデル
      </td>
      <td>
        取得元：<Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#squad-optimization-goals">adsquad.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        課金モデルとAppsFlyerの共通表記の対応表
      </td>
      <td>
        | 課金モデル | 共通表記に統一した課金モデル |
        | --- | --- |
        | * SWIPES<br />* STORY\_OPENS | CPC |
        | * USES<br />* {"PIXEL_ADD_TO_CART"}<br />* {"PIXEL_PURCHASE"}<br />* {"PIXEL_SIGNUP"}<br />* {"APP_ADD_TO_CART"}<br />* {"APP_PURCHASE"}<br />* {"APP_SIGNUP"} | CPA |
        | APP\_INSTALLS | CPI |
        | * IMPRESSIONS | CPM |
        | * VIDEO\_VIEWS<br />* VIDEO\_VIEWS\_15\_SEC | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        入札戦略
      </td>
      <td>
        取得元：<Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#bid-strategy">adsquad.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyerの共通表記に統一した入札戦略
      </td>
      <td>
        | 入札戦略 | 共通表記に統一した入札戦略 |
        | --- | --- |
        | * MIN\_ROAS<br />* AUTO\_BID | Auto bid |
        | {"LOWEST_COST_"} {"WITH_MAX_BID"} | Max bid |
        | TARGET\_COST | Target bid |
      </td>
    </tr>
    <tr>
      <td>
        入札額
      </td>
      <td>
        広告主の通貨での入札額
      </td>
    </tr>
    <tr>
      <td>
        元の入札額
      </td>
      <td>
        取得元：adsquad.bid\_micro
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="about-campaign-properties=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E8%A8%AD%E5%AE%9A%E6%83%85%E5%A0%B1%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J1PX98QNCZG9Y9PRZQ4ZEEFK=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E8%A8%AD%E5%AE%9A%E6%83%85%E5%A0%B1%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J1PX98QNX2T408GB2WV0RFZH=facebook h_01J1PX98QP22PPG9V84DD5WEM1=google h_01J1PXNDS4V16NQQQGMBND9PAF=snap" />
