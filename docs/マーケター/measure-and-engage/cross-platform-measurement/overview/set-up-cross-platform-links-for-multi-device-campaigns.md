---
title: マルチデバイスキャンペーン向けのクロスプラットフォームリンクの設定
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
  edited_at: '2026-10-14T09:28:02Z'
  id: 6966260647185
  locale: ja
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ja/articles/6966260647185
---
> **概要：** 各プラットフォームでのアプリのインストールを別のプラットフォームの広告閲覧に紐づけて計測する方法について記載しています。たとえば、モバイルアプリのインストールをCTV端末で表示された広告に、コンソールゲームアプリのインストールをモバイルまたはデスクトップ（ウェブ）で表示された広告に、CTVアプリのインストールをモバイルまたはデスクトップ（ウェブ）で表示された広告に、それぞれ成果を紐づけます。

## 概要

AppsFlyerのクロスプラットフォームOneLink（インプレッションURL）を使用すると、あるプラットフォームからのインストールを別のプラットフォームに表示される広告ビューに結び付けることができます。同じ世帯内の複数のインストールは、同じクロスプラットフォーム広告インプレッションに起因する可能性があります。

## クロスプラットフォーム計測用のOneLinkテンプレートの作成

単一のテンプレートは、すべてのプラットフォームでアプリをサポートします（つまり、1つのテンプレートがすべてのプラットフォームで機能します）。

1. クロスプラットフォーム計測用の<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">OneLinkテンプレート</Anchor>を作成または編集します。
2. **クロスプラットフォーム計測**のセクションで、**編集** > **クロスプラットフォームの同等アトリビューション優先度**トグルをオンにします。
3. 関連するプラットフォームのドロップダウンから、関連するアプリを選択します。　**注：** 各アプリは、クロスプラットフォーム計測が有効な1つのOneLinkテンプレートにのみ追加できます。[<Image alt="クロスプラットフォームの計測.png" src="https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png" width="476px" />](https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png)

## クロスプラットフォームのパートナー連携設定

クロスプラットフォームのインプレッションURLを使用してクロスプラットフォーム計測を設定するには、ターゲットアプリごとにパートナー設定を設定します。

> 🚧 **重要！**
>
> OneLinkテンプレートで選択したすべてのターゲットアプリについて、以下の手順を実行してパートナー設定を有効にしてください（[上記のセクション](#クロスプラットフォーム計測用のonelinkテンプレートの作成)を参照）。ターゲットアプリの1つで設定が無効になっている場合、クロスプラットフォームの計測は発生しません。

<div id="h_01K2HBXDWSG3R1WZXT5RB0W48D" />

<Accordion title="ステップ1：パートナー設定のターゲットアプリを選択します">

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動します。
2. 該当の媒体を選択します。
3. **設定**タブで、**アプリ**のドロップダウンボックスからターゲットアプリを選択します。

</Accordion>

<div id="step-2-enable-viewthrough-attribution" />

<Accordion title="ステップ2：ビュースルー計測の有効化">

連携済みパートナーが使用するリンクにおいて、ビュースルー計測を有効にします。

1. 連携タブにて、**インストールのビュースルー計測**をオンにしてください。
2. **連携の保存**をクリックします。

</Accordion>

<div id="step-4-create-an-attribution-link-crossplatform-impression-url" />

<Accordion title="ステップ3：次に、計測リンク（＝クロスプラットフォーム用のインプレッション計測リンク）を作成します。">

連携媒体の<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">計測リンク</Anchor>（クロスプラットフォームインプレッションURL）の作成：

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動し、アドネットワークを選択します。
2. **計測リンク**タブで、計測リンクを作成する際に<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">OneLinkを使用</Anchor>を選択します。
3. クロスプラットフォーム計測の設定を有効にしたOneLink テンプレートを選択してください。
4. **ビュースルー計測**セクションまでスクロールダウンします。[![](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)
5. **クロスプラットフォーム計測**をオンにします。これにより、インプレッション計測リンクに `af_xplatform=true` パラメータが追加され、リンクにクロスプラットフォームの計測機能が付与されます。このパラメーターを追加しないと、URLは通常のインプレッションURLとして機能してしまい、複数のインストールを同じインプレッションに紐付けることはできません。
6. <strong>クロスプラットフォームのビュースルールックバック期間を設定します。</strong>これは、インプレッション計測リンクに `af_xplatform_vt_lookback` パラメータを追加し、アプリインストールがインプレッションに紐付けできる、インプレッション後の時間の長さ（最大24時間）を示します。
7. 必要に応じてほかの計測パラメータを追加します。クロスプラットフォームアプリキャンペーンを特定する命名規則を使用します。 追加できるデータとパラメータの詳細については<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">こちらのページ</Anchor>をご確認ください。サンプルリンク：

   ```http
   https://impressions.onelink.me/{template_id}?pid=__media_source__&af_xplatform=true&af_xplatform_vt_lookback=24h&af_siteid=__CSITE__&c=__ctv_to_mobile__&af_channel=__PLACEMENT__&af_c_id=__CAMPAIGN_ID__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_source_platform=__source_platform__&af_source_device_category=__device_category__&af_ad_type=__CTYPE__&redirect=false
   ```
8. CTVやPC、コンソールのプラットフォーム上で表示する広告に設定するために、アドネットワークへ計測リンクを入稿してください。

> 🚧 **重要！**
>
> オウンドメディアおよび連携外パートナーには、必要に応じてパラメータを追加します。 追加できるデータとパラメータの詳細については<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">こちらのページ</Anchor>をご確認ください。

</Accordion>

<div id="equal-priority-advanced-setting" />

<Accordion title="アドバンス：同等優先度の設定（オプション）">

クロスプラットフォームの計測において、クリックとインプレッションと**同等のアトリビューション優先度**をオプションで割り当てることができます。このアドバンス設定により、AppsFlyerはインプレッション（例えば、CTVやコンソールで）をクリックと同じ計測優先度を持つものとして扱うことができます。詳細については、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#アトリビューション方法の判定優先順位">計測方法の優先順位</Anchor>を参照してください。

**同等の優先度を有効に設定：**

1. クロスプラットフォーム設定セクションで、**クロスプラットフォームの同等アトリビューション優先度**のチェックボックスを選択します。
2. **保存**をクリックしてください。

> 📘 **注意**
>
> クロスプラットフォームの同等アトリビューション優先度を有効にすると、AppsFlyerが他のソースよりも自社の計測を優先する可能性があります。この設定は注意して使用し、全体的な計測戦略に合致する場合のみ使用してください。

</Accordion>

## アドネットワークのリスト

CTV、PC、コンソールのプラットフォームに広告を表示し、クロスプラットフォームアトリビューション（CTVからモバイルアプリなど）をサポートしているアドネットワークの一覧は、 <Anchor target="_blank" href="https://hq1.appsflyer.com/partner-marketplace/explore?integrationLevels=CROSS_PLATFORM">AppsFlyer Partner Marketplace</Anchor>で確認できます。確認するには、AppsFlyerアカウントへのログインが必要になります。

## 特性と制限

| 特性 | 備考 |
| --- | --- |
| <span id="attribution-window"></span>アトリビューション期間 | 1〜72時間の間 - ルックバック期間のパラメータ `af_xplatform_vt_lookback` に依存（デフォルト：24時間） |
| <span id="retargeting"></span>Retargeting | <ul><li>リアトリビューションCV：クロスプラットフォームからモバイルのフローで対応。他のプラットフォームには対応していません。</li><li>リエンゲージメントCV：サポートされておらず、計測対象外です。</li></ul> |
| <span id="attribution-method"></span>アトリビューション方法 | 確率論的モデリングによるビュースルー計測 |
| <span id="household-attribution"></span>世帯アトリビューション | サポートされています。つまり、同じ世帯内の複数のインストールが、同一のクロスプラットフォームの広告インプレッションに紐づく可能性があります。 |
| <span id="reporting"></span>レポート | <ul><li>クロスプラットフォームインストールは、通常のAppsFlyerダッシュボードとレポートで利用できます。<ul><li>集計データ<Anchor target="_blank" href="/marketers/ja/docs/getting-started-with-appsflyer-dashboards">ダッシュボード</Anchor> / <Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">レポート</Anchor></li><li>ローデータ<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">レポート</Anchor></li></ul></li><li>クロスプラットフォームのインプレッションは、アプリレベルのダッシュボードには表示されません。ただし、Data Lockerの <Anchor target="_blank" href="/marketers/ja/docs/data-locker-advertiser-reports#user-journey">クロスプラットフォームエンゲージメントレポート</Anchor>で取得できます。</li><li>クロスプラットフォームキャンペーンを簡単に識別できるパラメータ命名規則を使用してください。</li></ul> |
| <span id="ip-masking"></span>IPマスキング | クロスプラットフォームエンゲージメントのIPマスキングは、アプリレベルの特性であるため、サポートされていません。`ip_masking` が設定されている場合、インストールはクロスプラットフォームのエンゲージメントにアトリビューションされません。 |
| <span id="ctvto-mobile"></span>CTV-to-mobile | CTVからモバイルへの計測フローは、クロスプラットフォームキャンペーンを実施する権限を持つ[連携済みパートナー](/docs/set-up-cross-platform-links-for-multi-device-campaigns#アドネットワークのリスト)のみに提供されます。 |
| <span id="cross-platform-attribution-links-in-mobile-devices"></span>モバイルデバイスにおけるクロスプラットフォーム計測リンク | モバイルデバイスでクロスプラットフォーム計測リンクが表示されると、計測は標準のモバイル確率モデル論理によって決定され、<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#tv-screens">CTV</Anchor>、PC、およびコンソール用に設計されたクロスプラットフォーム計測フローによって決定されるわけではありません。その結果、モバイルインプレッションは、真のクロスプラットフォームインプレッションに対して利用可能な[同等の優先度](#step-3-enable-equal-priority-for-crossplatform-impressions)、[拡張ルックバック期間](#attribution-window)、または[世帯計測](#household-attribution)の対象にはなりません。 |
| <span id="agency-permissions"></span>代理店権限 | 代理店アカウントで「クロスプラットフォームの同等アトリビューション優先度」は設定できません。この設定は、特定のアドネットワークの広告主の設定から適用されます。 |

## 数値の乖離

AppsFlyerとtvScientificではアトリビューションモデルに違いがあります。これにより、tvScientificダッシュボードとAppsFlyerダッシュボードの間に不一致が生じる可能性があります。不一致の理由：

| 要因 | TVScientific | AppsFlyer |
| --- | --- | --- |
| ベースラインのモデル | 共有クレジットアトリビューションモデル | ラストタッチアトリビューションモデル |
| ルックバック期間 | 最大30日間 | 最大72時間 |
| リターゲティング | 新規ユーザー（新規インストール）とリピーター（リエンゲージメント）の両方を計測 | 新規ユーザー（新規インストール）のみ計測 |
| コストの割り当て | 広告配信費用はOS（iOS / Android）に関係なくインプレッションに割り当てられます。 | 広告配信費用は、iOS と Android の別々のシステムのインプレッションに割り当てられます。 |

## よくある質問

<div id="does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on" />

<Accordion title="Q：確率的モデリングによるビュースルーアトリビューションを有効にするには、オンにする必要がありますか？">

A：いいえ。アプリ設定画面の確率的モデリングによるビュースルーアトリビューションを有効にする設定は、クロスプラットフォームのビュースルーアトリビューションを機能させるためにオンにする必要はありません。

</Accordion>

<div id="why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />

<Accordion title="なぜダッシュボードでクロスプラットフォームキャンペーンのインプレッションが表示されないのですか？">

クロスプラットフォームのインプレッションは、アプリレベルのダッシュボードには表示されません。これは、1つのCTVインプレッションが異なるアプリ間で複数のコンバージョンを引き起こす可能性があり、各アプリにインプレッションを正確に割り当てる方法がないためです。<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-data-via-data-locker#レポートの種類および可用性">Data Lockerのクロスプラットフォームエンゲージメントレポート</Anchor>でインプレッションデータにアクセスできます。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01H8V0RV7X8JEVEJ36TJB1X43D=%E6%A6%82%E8%A6%81 step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E8%A8%88%E6%B8%AC%E7%94%A8%E3%81%AEonelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88%E3%81%AE%E4%BD%9C%E6%88%90 h_01HVECG1TZ8B5GH28CZM2186BF=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E8%A8%88%E6%B8%AC%E7%94%A8%E3%81%AEonelink%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88%E3%81%AE%E4%BD%9C%E6%88%90 set-up-crossplatform-attribution=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HVECG1TZSDTP0WBG7XYM509G=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A 01JEKG3V0C75G782RC7CE9DAV2=%E9%87%8D%E8%A6%81 h_01HVECG1TZKNG17STSN5XJAF9C=step-2-enable-viewthrough-attribution step-4-create-an%C2%A0attribution-link%C2%A0crossplatform-impression-url=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ6WP257R9D8A105FR=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ3K1EFA22716K2B9X=%E9%87%8D%E8%A6%81-1 h_01K2HBZKX0EJHSVCXJJ97NMVXZ=equal-priority-advanced-setting equal-priority-impact-note=%E6%B3%A8%E6%84%8F h_01K2HBZKX0ECJPTQMPPXC3JBVC=%E6%B3%A8%E6%84%8F list-of-ad-networks=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E3%83%AA%E3%82%B9%E3%83%88 h_01HVED5DJP78EGF2D8SFJVND1H=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E3%83%AA%E3%82%B9%E3%83%88 traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HVED5DJPFR5XCWYDSYCHMCR6=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 discrepancies=%E6%95%B0%E5%80%A4%E3%81%AE%E4%B9%96%E9%9B%A2 h_01HVED5DJPMP3AQDTN3GM77T2F=%E6%95%B0%E5%80%A4%E3%81%AE%E4%B9%96%E9%9B%A2 faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HVED5DJPBPDSZ0AAY1RG8NEZ=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01K4AC2J63B4MBTDGZHH7ACRCG=does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on why-don%E2%80%99t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard h_01K4AC2J63KBF8X20DMNPW1GTK=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />
