---
title: TikTok for BusinessとのSKAN連携
metadata:
  keywords:
    - Advertisers
    - ios14
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-03-14T12:05:58Z'
  edited_at: '2026-10-29T04:33:45Z'
  id: 360018499098
  locale: ja
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ja/articles/360018499098
---
> **概要：** SKAN連携を有効にすると、TikTokからAppsFlyerへSKANポストバックを共有し、AppsFlyerからTikTokへコンバージョン値の計測マッピングを共有できます。

## SKAN連携｜AppsFlyer &lt;-> TikTok

複数のアドネットワークパートナーと連携する場合は、AppsFlyerで設定することをおすすめします。これにより、AppsFlyer上でSKANのパフォーマンス指標をコストなどの指標とあわせて確認できます。

### TikTokとのSKAN連携でできること

この連携により、AppsFlyerで設定したSKANのコンバージョン値のマッピングを、AppsFlyerとTikTokで共有できます。これにより、両方のプラットフォームでパフォーマンス指標を確認できます。TikTok for Businessとの連携（従来の連携または<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup">アドバンスSRN</Anchor>連携）を有効にすると、AppsFlyerからTikTokへ最適化に使用するイベントが提供されます。TikTokが対応している項目は、<Anchor target="_blank" href="/marketers/ja/docs/skan-integrated-partners-list">データ拡充項目の一覧</Anchor>を参照してください。

### TikTok for Businessの設定に関するガイダンス

TikTok for Businessのキャンペーンを設定する際は、TikTokの<Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10000858">iOS 14の影響と対応に関するガイダンス</Anchor>を参照し、次の点を確認してください。

* <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">AppsFlyer SDK</Anchor>が最新であることを確認してください。
* TikTok for Businessで広告を配信するアプリごとに、[TikTokアプリIDを設定](https://ads.tiktok.com/help/article?aid=10001060)してください。
  * TikTokアプリIDは、TikTok Ads Managerで生成される一意のコードです。TikTokはこのIDを使用して、広告主がそのアプリを所有していることを確認します。
  * 必須ではありませんが、すべてのアプリのアプリIDを入力することをおすすめします。  
    これにより、TikTok for Businessのデータをより適切に管理し、追加のプロダクトも利用できるようになります。
  * **複数のTikTokアプリIDを追加するには、次の手順を行います。**
    1. 1つ目のTikTokアプリIDを入力します。
    2. **Enter**キーを押します。
    3. 次のTikTokアプリIDを入力します。
  * TikTokアプリIDを設定しても、AppsFlyerのデータには影響しません。
  * 詳しくは、[iOS 14でのTikTokアプリIDの要件](https://ads.tiktok.com/help/article?aid=10001070)を参照してください。
* bytedanceglobal\_intとtiktokglobal\_intの[コンバージョンイベントのマッピングを完了](/docs/skan-interoperation-with-tiktok-for-business#3)してください。
* キャンペーンの制限と、アカウントやキャンペーンの統合に関するガイダンスを確認してください。

SKANの設定や戦略については、TikTok for Businessのアカウントマネージャーと直接相談してください。

TikTokは、SKANを使用した次の機能に対応しています。

* コンバージョン計測APIによる計測と最適化
* TikTok for BusinessでのiOS 14専用キャンペーンのレポート

### iOS 14専用キャンペーンの上限

SKAN APIの制約により、TikTok for BusinessでiOS 14専用キャンペーンを作成する際は、次の上限が適用されます。対象は、アプリインストール広告と、アプリの新規ユーザー獲得を目的としたダイナミック商品広告です。

* ​iOSアプリでは、キャンペーンは15件まで、各キャンペーンの広告グループは5件までです。
* iOS 14専用キャンペーンには、次の制限もあります。
  * 複数の広告アカウントから作成できますが、有効なキャンペーンの総数は15件までです。
  * 上限の15件には、対象となるすべての目的のキャンペーンが含まれます。上限に達した場合は、既存のキャンペーンを一時停止、オフ、または削除してから、枠が空くまで少なくとも72時間待つ必要があります。その後、新しいキャンペーンを開始できます。

### 連携の有効化

連携を有効にするには、AppsFlyerとTikTok for Businessの両方の管理画面で設定します。アプリ自体での連携設定や変更は不要です。

**AppsFlyerのSKANとTikTok for Businessの連携を有効にするには、次の手順を行います。**

| ステップ | 作業 | 詳細 |
| --- | --- | --- |
| <span id="1"></span>1 | アプリの前提条件 | <ul><li>最新のAppsFlyer SDKをアプリに実装します。</li></ul> |
| <span id="2"></span>2 | SKAN設定の確認 | AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKANソリューション</Anchor>を設定し、有効にします。<br /><br />**SKAN設定を表示するには、次の手順を行います。**<ol><li>AppsFlyerで、［**設定**］>［**SKAN Conversion Studio**］に移動します。</li><li>オプション（⋮）をクリックし、［**SKAN計測**］がオンになっていることを確認します。<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>使用する計測モードを選択します。<br />詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>を参照してください。</li><li>設定したイベント名を、表記を変えずに正確に控えておきます。次のステップで使用します。</li></ol> |
| <span id="3"></span>3 | アプリ内イベントのマッピング | TikTok for Businessのアプリ内イベントのマッピングを確認し、必要に応じて変更します。<br /><br />**アプリ内イベントのマッピングを確認・設定するには、次の手順を行います。**<ol><li>AppsFlyerで、［**設定**］>［**アクティブな連携**］に移動します。</li><li>［**TikTok for Business**］を検索して選択します。</li><li>［**連携**］タブで、<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Businessとの連携が有効になっており、設定が完了していることを確認</Anchor>します。</li><li>［**アプリ内イベントポストバック**］セクションで、次の設定を行います。<ol><li>［必須］［**アプリ内イベントポストバック**］がオフの場合は、オンにします。</li><li><Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>で設定したアプリ内イベントが、TikTok for Businessのイベント名または<Anchor target="_blank" href="/marketers/ja/docs/skan-cv-decode-map-your-cv-to-events">カスタムコンバージョンマップ</Anchor>内のイベントにマッピングされていることを確認します。<br />**注意：**`af_skad_revenue`をTikTokの`Purchase`イベントにマッピングするのは、SKANのコンバージョン値の設定ルールで収益全体を計測する場合のみです。<br />[![](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)</li></ol></li><li>［**連携を保存**］をクリックします。</li></ol> |

> 📄 **関連記事**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">AppsFlyerのSKANソリューションガイド</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-tiktok=skan%E9%80%A3%E6%90%BAappsflyer---tiktok h_01HDNYZ0CT1MGCRSSP3MXTJK5V=skan%E9%80%A3%E6%90%BAappsflyer---tiktok scope-of-skan-interoperability-with-tiktok=tiktok%E3%81%A8%E3%81%AEskan%E9%80%A3%E6%90%BA%E3%81%A7%E3%81%A7%E3%81%8D%E3%82%8B%E3%81%93%E3%81%A8 h_01HDNYZ0CT5NZHDHDBDSCFG911=tiktok%E3%81%A8%E3%81%AEskan%E9%80%A3%E6%90%BA%E3%81%A7%E3%81%A7%E3%81%8D%E3%82%8B%E3%81%93%E3%81%A8 tiktok-for-business-guidance=tiktok-for-business%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%AC%E3%82%A4%E3%83%80%E3%83%B3%E3%82%B9 01HR1TPFCSXRGYC610AR7KMTS5=tiktok-for-business%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%AC%E3%82%A4%E3%83%80%E3%83%B3%E3%82%B9 campaign-limits-for-dedicated-ios-14-campaigns=ios-14%E5%B0%82%E7%94%A8%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%B8%8A%E9%99%90 h_01HDNYZ0CT7RNDAEWYKBHS6PET=ios-14%E5%B0%82%E7%94%A8%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%B8%8A%E9%99%90 enabling-interoperation=%E9%80%A3%E6%90%BA%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HDNYZ0CTJGY3GPC9F907NEPT=%E9%80%A3%E6%90%BA%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HDNZ1BW5EBP0JCX84MTYPQ6K=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />
