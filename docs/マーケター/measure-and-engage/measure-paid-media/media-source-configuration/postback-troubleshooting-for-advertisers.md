---
title: 広告主向け：ポストバックに関するトラブルシューティング
metadata:
  keywords:
    - Postback
    - Partner
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2026-10-14T09:34:18Z'
  id: 14272573202833
  locale: ja
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ja/articles/14272573202833
---
> **概要：** 概要： パートナー（広告媒体）がポストバックを受け取らない主な原因と解決策を見つけます。以下の各トピックに目を通し、それらが原因である可能性があるかどうかを確認してください。

<div id="check-the-integration-toggles" />

## 連携トグルの確認

さまざまなトグルが、連携のさまざまな部分を制御します。トグルの状態が、ポストバックを受信しない理由である可能性があります。

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="パートナー連携トグルがオフになっている">

パートナーの有効化

<Image align="center" alt="integration_turned_off.png" src="https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png" />

**連携を有効にする方法：**

1. AppsFlyer管理画面 左メニュー 連携 > **連携済みパートナー**を選択します。
2. パートナーの「統合の管理」アイコンをクリックします。
3. パートナーの有効化トグル

パートナーの有効化

* <span id="1703758710.321359"></span>Roku 開発者管理画面から メールアドレス

</Accordion>

<div id="1703760110.503549" />

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<Accordion title="アプリ内イベントポストバックの設定がオフになっている">

基準となる これは、ポストバックが送信されないことを意味します。

**アプリ内イベントのポストバックをオンにするには：**

1. AppsFlyer管理画面 左メニュー 連携 > **連携済みパートナー**を選択します。
2. パートナーの「統合の管理」アイコンをクリックします。
3. **連携** タブにて、スクロールダウンします。   

   <Image align="center" alt="integration-in_app_event_postbacks_toggle.png" src="https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png" />

</Accordion>

<div id="check-the-event-configuration" />

## イベント設定を確認します。

イベントは、特定のポストバックを送信しないよう設定可能です。

<div id="the-event-wasnt-configured" />

<Accordion title="イベントが設定されていない">

設定したアプリ内イベントのリストにイベントが含まれていることを確認します。設定されていないアプリ内イベントのデータは、ポストバックは送信されません。

<Image align="center" alt="list_of_in_app_events.png" src="https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png" />

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**を選択します。
2. パートナーの「統合の管理」アイコンをクリックします。
3. **連携**タブで、**アプリ内イベントのポストバック**セクションまでスクロールダウンし、ポストバック送信したいイベントが設定されているかどうかを確認します。

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="イベントが正しく設定されていない">

<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#イベントマッピング">イベントマッピング</Anchor>が間違っていないかどうか確認します。AppsFlyer SDKイベント<strong>（モバイルアプリまたはS2S経由でAppsFlyer上で計測したイベント名）が、パートナー側のイベント名（パートナーによって使用される正確なイベント名）と一致することを確認してください。</strong>

<Image align="center" alt="in_app_event_postback_mapping_2.png" src="https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png" />

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="イベントは正しく設定されているが、送信データの条件が設定されている">

イベントに条件が定義されている場合は、その条件に従ってポストバックが送信されます。ポストバック送信を制限する条件があるかどうかを確認します。

<Image align="center" alt="in_app_event_condition__1_.png" src="https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png" />

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="「このパートナーにのみ」のイベントデータをポストバックを送信するように構成されています">

アプリ内イベントの設定が、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバック送信のオプション">**このパートナーのみ**にポストバックを送信するか、**オーガニックを含むすべてのメディアソース**に送信する</Anchor>よう設定されているかどうかを確認します。このパートナーのみに設定されている場合は、アトリビューションされたデータのみがポストバックを取得します。

<Image align="center" alt="in_app_event_sending_options.png" src="https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png" />

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="イベントが設定期間外で発生した">

ポストバックは、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">ポストバック期間</Anchor>の設定に基づいて送信されます。この期間以降のイベントのポストバックはパートナーに送信されませんが、イベントは引き続きAppsFlyerに記録されます。

<Image align="center" alt="in_app_event_postback_window.png" src="https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png" />

<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">SRN</Anchor>の場合、アプリ内イベントのポストバックは 、パートナーのデータ保持期間中のみ送信されます 。

</Accordion>

<div id="the-attribution-link-was-configured-not-to-send-postbacks-for-installs" />

<Accordion title="計測リンクがインストールのポストバックを送信しないように設定されている">

アトリビューションリンクに `af_installpostback=false` パラメータが含まれている場合、インストールは記録されますが、ポストバックはパートナーに送信されません。

**計測リンクを確認するには：**

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**を選択します。

</Accordion>

<div id="privacy-restrictions" />

## プライバシー制限

以下の場合、AppsFlyerはプライバシーの制限によりポストバックを送信しません：

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="パートナー側で高プライバシーポストバックをサポートしていない">

<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">高プライバシーポストバック</Anchor>が有効になっているが、パートナー側で高プライバシーポストバックに対応していない場合、<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks">高度なプライバシーポストバック</Anchor>は受信されません。

<Image align="center" alt="partner_not_supporting_ap_postbacks.png" src="https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png" />

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<div id="the-sdk-was-set-not-to-share-information-with-the-partner" />

<Accordion title="サードパーティプラットフォームでのメディアソースの制限">

<Anchor target="_blank" href="/marketers/ja/docs/discrepancies-between-appsflyer-and-third-party-platforms#サードパーティプラットフォームへのポストバックの制限">一部のメディアソース</Anchor>は、第三者とのデータ共有を制限しています。そのため、このようなメディアソースからのインストールはオーガニックとして送信されます。

</Accordion>

詳細については、以下を参照してください：


<div id="miscellaneous" />

## その他

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="ポストバックは送信されましたが、パートナー側の管理画面に表示されていない">

AppsFlyerはパートナーにポストバックを送信していても、パートナー側の管理画面に表示されない場合があります。そのような場合は、パートナーに連絡してください。

**ポストバックがAppsFlyerから送信されたかどうかを確認するには：**

1. AppsFlyerのサイドメニューから、 レポート > ローデータ出力を選択します。
2. **ポストバック**（インストール、アプリ内イベント、リターゲティングコンバージョン、アプリ内イベントリターゲティング）で関連するレポートを表示します。

postback\_reports.JPG

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="イベントが発生しなかったか、AppsFlyerに送信されなかった">

発生したすべてのイベントは、 <Anchor target="_blank" href="/marketers/ja/docs/activity-dashboard">**アクティビティ** ダッシュボード</Anchor> と <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview?query=raw%20data%20reports">ローデータレポート</Anchor>で確認できます。そこに表示されないイベントは、イベントが発生しなかったか、AppsFlyerに送信されなかったことを意味します。

イベントが SDK で定義されていない可能性があります。この場合、プラットフォームには表示されません。

イベントが発生したと思われる場合は、アクティビティダッシュボードに表示されるかどうかを確認する方法を確認するか、ローデータレポートを取得して確認してください。

**アクティビティダッシュボードを表示するには：**

**ローデータレポートの出力：**

1. AppsFlyerのサイドメニューから、 レポート > ローデータ出力を選択します。
2. **レポートの作成**をクリックします。
3. 取得したいレポートタイプを選択します。
4. 日付範囲と必要な項目を選択し、 作成をクリックします 。
5. レポートをダウンロードして、イベントを探してください。

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="タイムゾーンの違い">

AppsFlyerプラットフォームとパートナーのプラットフォームのタイムゾーンの違いにより、ポストバックの受信に不一致が生じる場合があります。AppsFlyerのダッシュボードとレポートは、選択したタイムゾーンに従って表示されます。

**AppsFlyerでアプリのタイムゾーンを表示するには：**

1. **AppsFlyer管理画面左メニュー** **設定** > アプリ設定へ移動します。
2. **ローカリゼーション**セクションのタイムゾーンを確認します。

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="SRN媒体のデータで広告ID (IDFA/GAID) が取得できていない">

<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">SRNには</Anchor>、AppsFlyerがインストール、アプリ起動、アプリ内イベントのポストバックを送信しない特定のケースがいくつかあります。

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<Accordion title="サードパーティプラットフォームでのメディアソースの制限">

<Anchor target="_blank" href="/marketers/ja/docs/discrepancies-between-appsflyer-and-third-party-platforms#サードパーティプラットフォームへのポストバックの制限">一部のメディアソース</Anchor>は、第三者とのデータ共有を制限しています。AppsFlyerは、 これらのメディアソースを通じて取得したユーザーレベルのデータを、第三者のプラットフォームやサービスと共有することはできません。 そのため、このようなメディアソースからのインストールはオーガニックとして送信されます。Meta広告が第三者のプラットフォームとデータを共有することはありません。

</Accordion>

<div id="advanced-privacy-postbacks" />

<Accordion title="高プライバシーポストバック">

ポストバックは<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks">高度なプライバシーテンプレート</Anchor>に従って送信されます。

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> <Anchor target="_blank" href="/partners/ja/docs/postback-troubleshooting-for-ad-networks">アドネットワークのポストバックに関するトラブルシューティング</Anchor>

<div data-zendesk-anchors="activation-toggles=%E9%80%A3%E6%90%BA%E3%83%88%E3%82%B0%E3%83%AB%E3%81%AE%E7%A2%BA%E8%AA%8D h_01H9FT385FY1QJC6M2YVMZF2NC=%E9%80%A3%E6%90%BA%E3%83%88%E3%82%B0%E3%83%AB%E3%81%AE%E7%A2%BA%E8%AA%8D h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E8%A8%AD%E5%AE%9A%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%97%E3%81%BE%E3%81%99 h_01H9FT385FW71JV2KKZ22TP6TN=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E8%A8%AD%E5%AE%9A%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%97%E3%81%BE%E3%81%99 h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window h_01H9FT385GDDV1D6X69JQWPN02=the-attribution-link-was-configured-not-to-send-postbacks-for-installs privacy-restrictions=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E5%88%B6%E9%99%90 h_01H9FT385G84E2A1J64VWG8H4Z=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E5%88%B6%E9%99%90 h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms miscellaneous=%E3%81%9D%E3%81%AE%E4%BB%96 h_01H9FT385GSWRPKEHKJ4HXCX01=%E3%81%9D%E3%81%AE%E4%BB%96 h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01JK86ZFXJGPVYJCAAVAY6F4YD=advanced-privacy-postbacks h_01HE7R6G699RG30ZSSQF02AK5Y=%E5%8F%82%E7%85%A7" />
