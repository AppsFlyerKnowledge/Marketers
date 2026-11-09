---
title: GMPユースケース：CMP360でのサードパーティによるトラフィック計測
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-03-03T12:42:31Z'
  edited_at: '2026-10-14T09:35:42Z'
  id: 360018228758
  locale: ja
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/ja/articles/360018228758
---
> **概要**：

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />


Google Marketing Platform (GMP)は、広告と分析を連携することで、質の高い顧客とのつながりを作り、より深いインサイトを得て、より良いマーケティング結果を導くことができます。


#### ステップ1:

#### ステップ2:

1. 2. 注： 計測リンクには、報告する実際のメディアソースが含まれている必要があります。これは、GMPではなく、サードパーティメディアソースである必要があります。例えば、サードパーティメディアソースがRocketfuelの場合、pid=doubleclick\_int ではなく、pid=rocketfuel\_int を使用してください。<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">詳細はこちら</Anchor>を参照してください。

      **計測リンクの例：**

      <Tabs>
      <Tab title="iOS">

      ```http
      https://app.appsflyer.com/com.example?pid=rocketfuel_int&c=campaign_name
      &advertising_id=13******-****-****-****-54**********
      ```

      </Tab>
      </Tabs>

   3. AppsFlyer計測リンクをCM360リンクに追加：  

      <Tabs>
      <Tab title="iOS">

      ```http
      https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
      dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
      ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
      &c=campaign_name&advertising_id=13******-****-****-****-54**********
      ```

      </Tab>
      </Tabs>

### 計測リンクを使用する

計測リンクを取得したら、目的の媒体に広告を掲載する際には必ずそのリンクを使用してください。