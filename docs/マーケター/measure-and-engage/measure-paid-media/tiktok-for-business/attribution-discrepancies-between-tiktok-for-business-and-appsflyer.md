---
title: TikTok for BusinessとAppsFlyerの乖離
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-10-30T07:45:29Z'
  edited_at: '2026-10-14T09:31:00Z'
  id: 19733501619473
  locale: ja
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ja/articles/19733501619473
---
> **概要：** TikTok for BusinessとAppsFlyerのアトリビューションモデルの違いについて理解しましょう。

## 概要

モバイルユーザー獲得エコシステムの2大プレーヤーであるTikTok for BusinessとAppsFlyerは、それぞれ異なるアトリビューションモデルを使用しています。このため、TikTok for BusinessとAppsFlyerダッシュボードの数値に不一致が生じる可能性があります。これらの不一致を最小限に抑えるためにTikTok for Businessと密接に連携していますが、両者の数値を分析する際に広告主は潜在的な原因を把握しておく必要があります。

## アトリビューションモデルの違い

以下の表は、TikTok広告マネージャーとAppsFlyerダッシュボード間の不一致の可能性がある理由を説明します：

<table><thead><tr><th>原因</th><th>TikTok広告マネージャー</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>クリックスルー：ルックバック期間</strong></p></td><td><p>デフォルトの期間は7日です。しかし、AndroidアプリやTikTokのセルフアトリビューション（TikTokアドバンスSRN）に移行したアプリでは、異なる設定が可能です。</p></td><td><p>デフォルトの期間は7日です。期間は1日から30日の間で設定できます。必ずTikTokのアトリビューション期間と同じ期間を設定してください。</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>ビュースルー：ルックバック期間</strong></p></td><td><p>デフォルトの期間は1日です。しかし、AndroidアプリやTikTokのセルフアトリビューション（TikTokアドバンスSRN）に移行したアプリでは、異なる設定が可能です。</p></td><td><p>デフォルトの期間は1日です。期間は1時間から48時間の間で設定できます。必ずTikTokのアトリビューション期間と同じ期間を設定してください。</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>マルチチャネルソースアトリビューション</strong></p></td><td><p>TikTokは他のメディアソースとは無関係にインストールを自己アトリビューションします。</p></td><td><p>AppsFlyerはラストクリックアトリビューションを使用します（詳細：<a href="./appsflyer-attribution-model" target="_blank">AppsFlyerの計測モデルについて</a>）。</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>クロスデバイスアトリビューション</strong></p></td><td><p>TikTokは、iOS、Android、デスクトップなど、異なるデバイスを使用してエンゲージメントとインストールの両方を行うユーザーを対象としています。</p></td><td><p>AppsFlyerは、エンゲージメントとインストールの両方を同一デバイスで実行したユーザーをアトリビューションします。</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>異なるタイムゾーン</strong></p></td><td><p><a href="https://ads.tiktok.com/help/article/time-zone" target="_blank">TikTokのタイムゾーン</a>（日付範囲の横に表示されます）は変更できません。広告アカウント作成時に設定されます。</p></td><td><p>AppsFlyerのデフォルトのアプリタイムゾーンはUTC+0です。TikTokイベントマネージャーに設定されたタイムゾーンに合わせるには、<a href="./app-settings#localization-time-zone" target="_blank">アプリ設定画面</a>でアプリのタイムゾーンを変更してください。</p></td></tr><tr><td><span id="ios-attribution"></span><p><strong>iOSアトリビューション</strong></p></td><td><p>iOSアプリに関しては、TikTok広告マネージャーにはSKANアトリビューションの結果のみが表示されます。</p></td><td><p>iOSアプリにおいて、AppsFlyerはSKANアトリビューションの結果を表示し、SRNおよびアドバンスSRNのAppsFlyerアトリビューション結果と重複排除されたSSOTデータを含めた情報を提供します。SKANデータのみが両プラットフォームで一致することが期待されます。 </p></td></tr><tr><td><span id="in-app-event-attribution-periods"></span><p><strong>アプリ内イベントのアトリビューション期間</strong></p></td><td colspan="2"><p>各プラットフォームのアトリビューションは、インストール時からの期間に基づいて異なる場合があります。</p></td></tr><tr><td><span id="day-1-90"></span><p>1日目〜90日目</p></td><td colspan="2"><p>アトリビューションの矛盾はありません。両方のプラットフォームがアプリ内イベントをインストールに紐付けます。</p></td></tr><tr><td><span id="day-91-180"></span><p>91日目〜180日目</p></td><td rowspan="2"><p>90日以降、アプリ内イベントはTikTokでサポートされなくなります。</p></td><td><div><div><div>AppsFlyerは、アプリ内イベントをインストールに紐付けます。</div></div></div></td></tr><tr><td><span id="day-180"></span><p>180日目以降</p></td><td><div><div><div> <a href="./user-level-data-retention#パートナー別のデータ保持期間" target="_blank">TikTokのデータ保持ポリシー</a>により、アプリ内イベントはオーガニックとして紐付けられます。</div></div></div></td></tr></tbody></table>

## インストールの違い

場合によっては、TikTok for BusinessにはAppsFlyerが拒否したインストールや、新規インストールとしてカウントされないインストールが含まれることがあります。

### リエンゲージメントキャンペーン

リエンゲージメントキャンペーンは、ユーザーが既にインストール済みのアプリを起動させるための施策です（**リエンゲージメントCV**）。AppsFlyerが同じデバイスでのアプリの以前のインストールを認識した場合、そのコンバージョンは**リアトリビューションCV**と計上されます。

ユーザーがTikTok for Businessのリエンゲージメントキャンペーンを通じて初めてアプリをインストールした場合、そのユーザーはAppsFlyerに**新規ユーザー獲得インストール**として記録されます。さらに、ユーザーが初期インストール後の指定された<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>後にアプリをインストールした場合も、新規獲得と見なされます。

一方で、最初のインストールに続く**設定されたリアトリビューション期間**内で発生するインストールは、リアトリビューションとして分類されます。これらのインストールは、AppsFlyerのリターゲティングページに表示されます。ただし、TikTok for Businessでは新規インストールと見なされる可能性があります。

### 検証ルールとProtect360を使用する際のインストール拒否

<Anchor target="_blank" href="/marketers/ja/docs/implement-validation-rules-to-prevent-fraud">検証ルール</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide">Protect360</Anchor>は、特定のインストールを拒否（ブロック）することで保護を提供するAppsFlyerの機能です。これらの機能を使用すると、TikTok for Business発の拒否されたインストールはAppsFlyerによってブロックされ、TikTok for Businessはそれらのインストールを自己報告します。

> 📄 **例**
>
> GreatAppのユーザー獲得マネージャーであるJeffは、北アメリカのスペイン語話者のみをターゲットにしたSPNAというキャンペーンを作成しました。これを検証するために、Jeffはカナダとアメリカのユーザーのみを受け入れる検証ルールを設定します。
> スペインのTikTok for Businessユーザーがアプリをクリックしてインストールした場合、TikTok for Businessはそのインストールを自己報告しますが、AppsFlyerは検証ルールを通過しないインストールを拒否します。

## 乖離を減少させる

アトリビューションモデルの違いがあるものの、場合によっては不一致を軽減できることがあります。

### クリックスルーとビュースルー計測

AppsFlyerは、クリックスルーおよびビュースルーのアトリビューションをサポートしています。TikTok for BusinessとAppsFlyer間での不一致を減らすためには、クリックスルーとビュースルーの両方のルックバック期間がTikTok for Businessで定義されたものと一致していることを確認してください。

> 📄 **例**
>
> TikTok for Businessのクリックスルールックバック期間がアプリ`com.greatapp`に対してAppsFlyerでは1日に設定されている一方、TikTok for Businessではデフォルト値である7日に設定されていると仮定します。TikTokでGreatappの広告をクリックしたユーザーが2〜7日後に初めてアプリを起動すると、AppsFlyerではオーガニックユーザーとしてカウントされ、一方でTikTok for Businessではそのユーザーを自己レポート（アトリビューション）します。

### アプリ内イベントのアトリビューション

プラットフォーム間の違いは、インストール後のイベント（例：アプリ内購入）がTikTok for BusinessおよびAppsFlyerに表示される場面でも現れる場合があります。以下の表では、これらの違いの最も一般的な理由と、その不一致を減少させる方法についてアドバイスします：

| 原因 | 説明 | AppsFlyerのヒント |
| --- | --- | --- |
| <span id="selfattribution"></span>**セルフアトリビューション** | TikTokはインストールとイベントを常に自社のキャンペーンにアトリビューションさせるのに対し、AppsFlyerはそれらを獲得ソースへアトリビューションします。このようなイベントは、AppsFlyer内ではTikTokによるアシストとして表示されます。 | TikTokのアトリビューションコンバージョンのローデータと、TikTokがアシストしたローデータを合わせて処理します。 |
| <span id="unmapped-events"></span>**マッピングされていないイベント** | AppsFlyerはSDK由来のイベントを取得しますが、それらがTikTok for Businessにマッピングされていないため、送信されません。 | ユーザーの質を示すアプリ内イベントを必ず<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#アプリ内イベントのポストバック">TikTok for Businessにマッピング</Anchor>してください。 |
| <span id="unsent-revenue"></span>**未送信の収益** | AppsFlyerはSDK由来のイベントから収益を得ますが、それらがTikTok for Businessへ送信されていません。 | <Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#アプリ内イベントのポストバック">TikTok for Businessアプリ内イベントをマッピングする</Anchor>際に必ず収益を含めてください。 |
| <span id="missing-event-values-on-tiktok"></span>**TikTok for Businessでイベント値が欠けている場合** | AppsFlyerは、正しい構造があれば、イベントマッピングの一環としてパラメーターと値をTikTok for Businessに送信します。 | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure">AppsFlyerの推奨構造</Anchor>に基づいてSDKのアプリ内イベントを実装し、TikTok for Businessとの連携設定画面でイベントの値を完全にマッピングしてください。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HFXTVVZNJQJFAAR1F3HW1D5M=%E6%A6%82%E8%A6%81 differences-in-attribution-models=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%A2%E3%83%87%E3%83%AB%E3%81%AE%E9%81%95%E3%81%84 h_01HFXTVVZN79JX9E5PTXMPB8BS=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%A2%E3%83%87%E3%83%AB%E3%81%AE%E9%81%95%E3%81%84 differences-in-installs=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E9%81%95%E3%81%84 h_01HFXTVVZNDQKNW85BBWR0PE2Z=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E9%81%95%E3%81%84 reengagement-campaigns=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_01HFXTVVZNA1R59KCA41H2YSBJ=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 rejected-installs-when-using-validation-rules-and-protect360=%E6%A4%9C%E8%A8%BC%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%A8protect360%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E9%9A%9B%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E6%8B%92%E5%90%A6 h_01HFXTVVZNJVFHE0W5DTP5PDCG=%E6%A4%9C%E8%A8%BC%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%A8protect360%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E9%9A%9B%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E6%8B%92%E5%90%A6 01H890CZSYCTQZCAYAZP9TCBBF=%E4%BE%8B minimizing-discrepancies=%E4%B9%96%E9%9B%A2%E3%82%92%E6%B8%9B%E5%B0%91%E3%81%95%E3%81%9B%E3%82%8B h_01HFXTVVZNW9GZB8QYMR1KTNMN=%E4%B9%96%E9%9B%A2%E3%82%92%E6%B8%9B%E5%B0%91%E3%81%95%E3%81%9B%E3%82%8B clickthrough-and-viewthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%81%A8%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC h_01HFXTVVZNN45WY997DK9K8WA4=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%81%A8%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC h_01HFRQMF6HTT84J4EDFXZMK7CP=%E4%BE%8B-1 inapp-event-attribution=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HFXTVVZNG7TKQVY1229X594G=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3" />
