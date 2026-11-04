---
title: AppsFlyerとサードパーティプラットフォームのデータの差異
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-10-16T08:59:17Z'
  edited_at: '2026-10-28T09:04:24Z'
  id: 19384888063249
  locale: ja
  section: Integrate 3rd-party platforms
  section_id: 6551084534545
  url: https://support.appsflyer.com/hc/ja/articles/19384888063249
---
> **At a glance:** AppsFlyerとサードパーティプラットフォームで、アトリビューションに差異が生じる原因を説明します。

<div id="overview" />

## 概要

メディアソースのデータ共有ポリシーにより、ユーザー単位の<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">データが、分析・マーケティングなどのサードパーティプラットフォームにすべて共有されるわけではありません</Anchor>。このため、サードパーティプラットフォームに表示されるデータとAppsFlyerのデータでは、アトリビューションに差異が生じることがあります。

> 📘 **Note**
>
> **注意**
>
> AppsFlyerの集計データと分析データは、制限なく利用できます。

<div id="postback-restrictions-on-third-party-platforms" />

## サードパーティプラットフォームへのポストバックの制限

サードパーティプラットフォームへのポストバック送信には、メディアソースによって異なる制限が設けられています。ポストバックは、まったく送信されない場合、計測元の情報を含めずに送信される場合、制限なく送信される場合があります。

<div id="types-of-postback-restrictions" />

#### ポストバックの制限の種類

<div id="no-postbacks-sent" />

<Accordion title="ポストバックを送信しない場合">

<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">この表</Anchor>に記載されている、メディアソースが共有を制限しているローデータイベントのポストバックは、サードパーティプラットフォームには送信されません。これらのイベントのポストバックを受信できないため、サードパーティプラットフォームでは、AppsFlyerよりも計測された成果の件数が少なくなります。

</Accordion>

<div id="postbacks-with-no-attribution" />

<Accordion title="計測元の情報を含めずにポストバックを送信する場合">

共有が制限されたローデータイベント以外のイベントでも、以下のアドネットワークは、サードパーティプラットフォームへのポストバック共有時にメディアソースの情報を除外するよう求めています。 AppsFlyerは、**元のメディアソースをオーガニックに置き換える**ことで対応します。これらのイベントのポストバックには、元のメディアソースとの紐付け情報が含まれません。そのため、サードパーティプラットフォームでは、AppsFlyerよりも該当メディアソースの成果として計測される件数が少なくなります。

* Amazon
* Meta ads
* Pinterest
* Snapchat（<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">利用規約</Anchor>）
* X Ads
* Bing
* Yahoo（Oath: Ad Platforms／Yahoo Gemini）

> 📘 **Note**
>
> **注意**
>
> Meta広告では、広告主がAdvanced Mobile Measurement（AMM）規約に同意しているかどうかで、ポストバックの動作が異なります。
>
> * **AMM規約に未同意の場合：** <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#install-referrer-android-only">インストールリファラで計測された</Anchor>インストールのポストバックのみを送信します。ポストバックにアトリビューションデータは含まれません。
> * **AMM規約に同意している場合：** <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#アトリビューション方法">すべてのアトリビューション方式</Anchor>で計測されたインストールのポストバックを送信します。ただし、ポストバックにアトリビューションデータは含まれません。すべてのポストバックは、計測元の情報がない（オーガニックの）データとしてサードパーティプラットフォームに送信されます。

</Accordion>

<div id="regular-postbacks" />

<Accordion title="通常のポストバック">

共有が制限されておらず、メディアソースの情報も除外されないその他のイベントは、通常のポストバックとして送信されます。集計イベントも含まれます。

</Accordion>

<table><colgroup><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th colspan="6">ポストバックの制限は、以下を含む、AppsFlyerと連携しているすべてのサードパーティプラットフォームに適用されます。</th></tr></thead><tbody><tr><td><span id="airship"></span>Airship</td><td>Amplitude</td><td>Batch</td><td>Braze</td><td>CleverTap</td><td>Cloud</td></tr><tr><td><span id="convertro"></span>Convertro</td><td>deltaDNA</td><td>Eulerian</td><td>GameAnalytics</td><td>IBM UBX</td><td>Insider</td></tr><tr><td><span id="itunes"></span>iTunes</td><td>Kahuna</td><td>Leanplum</td><td>Liquid</td><td>Localytics</td><td>Luna labs</td></tr><tr><td><span id="Medialyzer"></span>Medialyzer</td><td>Mixpanel</td><td>MoEngage</td><td>mParticle</td><td>OneSignal</td><td>Rocketbox</td></tr><tr><td><span id="salesforce"></span>Salesforce</td><td>Marketing</td><td>MobilePush</td><td>Segment</td><td>Spoteffects</td><td>Swrve</td></tr><tr><td><span id="tapcart"></span>Tapcart</td><td>Tealium</td><td>WebEngage</td><td>Winclap Analytics</td><td>Google Analytics 4</td><td> </td></tr></tbody></table>

<div id="examples-of-discrepancies" />

## データの差異の例

<div id="example-1" />

<Accordion title="Mixpanelへのローデータ共有の制限">

<Tabs>
<Tab title="AMM規約に未同意の場合">

> 📘 **Note**
>
> **例1**
>
> 広告主がMeta広告で広告を配信しています。また、アプリ内のユーザー行動や操作を詳しく把握するため、Mixpanelも利用しています。広告主が、先月のMeta広告経由のインストール数を確認します。
>
>
>
> | AppsFlyerでの表示 | Mixpanelでの表示 |
> | --- | --- |
> | Meta広告の成果として計測されたインストールが100件表示されます。<br /><br />そのうち30件は、`gp_referrer`パラメータを使って計測されています。これらのイベントは共有が制限されていないため、ローデータレポートに表示されます。 | オーガニックインストールが30件だけ表示されます。<br /><br />共有が制限されている70件のイベントについては、Mixpanelにポストバックが送信されません。 `gp_referrer`パラメータを使って計測された30件のインストールのポストバックは、オーガニックとして送信されます。 |

</Tab>

<Tab title="AMM規約に同意している場合">

> 📘 **Note**
>
> **例1**
>
> 広告主がMeta広告で広告を配信しており、AMM規約に同意しています。また、アプリ内のユーザー行動や操作を詳しく把握するため、Mixpanelも利用しています。広告主が、先月のMeta広告経由のインストール数を確認します。
>
>
>
> | AppsFlyerでの表示 | Mixpanelでの表示 |
> | --- | --- |
> | Meta広告の成果として計測されたインストールが100件表示されます。<br /><br />インストールのローデータレポートには、gp\_referrer方式で計測された分だけでなく、100件すべてのインストールが含まれます。 | オーガニックインストールが100件表示されます。<br /><br />AMM規約に同意しているため、Mixpanelは100件すべてのインストールのポストバックを受信します。ただし、いずれのポストバックにもアトリビューションデータが含まれないため、すべてのインストールがオーガニックとして表示されます。 |

</Tab>
</Tabs>

</Accordion>

<div id="example-2" />

<Accordion title="MoEngageへのローデータ共有の制限">

> 📘 **Note**
>
> **例2**
>
> 広告主がPinterestで広告を配信しています。また、顧客エンゲージメントを分析するため、MoEngageも利用しています。広告主は、先月、Pinterestの成果として計測された「ウィッシュリストへの追加」イベントの件数を確認します。
>
>
>
> | AppsFlyerでの表示 | MoEngageでの表示 |
> | --- | --- |
> | Pinterestの成果として計測された「ウィッシュリストへの追加」イベントが97件表示されます。 | Pinterestの成果として計測された「ウィッシュリストへの追加」イベントは表示されません。 Pinterestのクリックスルーおよびビュースルーのイベントは共有が制限されているため、MoEngageはそのポストバックを受信しません。 |

</Accordion>

<div id="example-3" />

<Accordion title="Airshipへの共有の制限">

> 📘 **Note**
>
> **例3**
>
> 広告主がBingで広告を配信しています。また、モバイルアプリのユーザージャーニーを最適化するため、Airshipも利用しています。広告主は、先月、Bingの成果として計測された購入イベントの件数を確認します。
>
>
>
> | AppsFlyerでの表示 | Airshipでの表示 |
> | --- | --- |
> | Bingの成果として計測された購入イベントが35件表示されます。 | オーガニックの購入イベントが84件表示されます。そのうち35件はBing経由ですが、オーガニックとして表示されるため、Bing経由であることは分かりません。 |

</Accordion>

> 📘 **Note**
>
> **関連情報**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#よくある質問">ローデータの内容に関する制限</Anchor>のよくある質問。

<div data-zendesk-anchors="Overview=%E6%A6%82%E8%A6%81 h_01HCVTKD7ZH991A8JF7XCNNE91=%E6%A6%82%E8%A6%81 postback-restrictions=%E3%82%B5%E3%83%BC%E3%83%89%E3%83%91%E3%83%BC%E3%83%86%E3%82%A3%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%B8%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E5%88%B6%E9%99%90 h_01HDDR9JG5303R38QCAB2ZF6CW=%E3%82%B5%E3%83%BC%E3%83%89%E3%83%91%E3%83%BC%E3%83%86%E3%82%A3%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%B8%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E5%88%B6%E9%99%90 types-of-postback-restrictions=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E5%88%B6%E9%99%90%E3%81%AE%E7%A8%AE%E9%A1%9E h_01HE05EXEFJF6SGYTKZ78FPP7Z=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E5%88%B6%E9%99%90%E3%81%AE%E7%A8%AE%E9%A1%9E h_01HDDRVF8J36N3J9AB3YRD8TZP=no-postbacks-sent h_01HDDRVF8JP2FWCA7PH58TZDBY=postbacks-with-no-attribution h_01HDDRVF8J9QRWN8MCKXRV0J3M=regular-postbacks examples=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%B7%AE%E7%95%B0%E3%81%AE%E4%BE%8B h_01HCW4HS35ZTAEWPXB9JKCR725=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%B7%AE%E7%95%B0%E3%81%AE%E4%BE%8B h_01HDDS499QJTX5RJY6CR98BDFB=example-1 h_01HDDS499QG48D1AFR3Z59J1HP=example-2 h_01KQZ0Q440XSG96Q3W65RYVYAG=example-3" />
