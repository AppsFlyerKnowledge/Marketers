---
title: Google Ads（AdWords）｜コストと広告収益
metadata:
  keywords:
    - Advertisers
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-20T10:01:42Z'
  edited_at: '2026-10-28T09:15:15Z'
  id: 4417309205521
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/4417309205521
---
> **At a glance:** AppsFlyerでGoogle Adsのコストと広告収益データの取得を有効にします。

## コスト、クリック数、インプレッション

コスト連携では、以下の集計データを提供します：

* キャンペーン、広告セット、国／地域、チャネルレベルのコストデータ。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークコスト連携に関する表</Anchor>を参照してください。  
  **注意：** コストデータの取得には、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>の契約が必要です。
* クリック、インプレッションに関するデータ、及びキーワードやキャンペーン名、広告セットなどの補足データ。

> 📘 **Note**
>
> * MCCアカウントにも対応しています。
> * Google Adsでは、1つのキャンペーンの対象をiOSまたはAndroidのいずれか一方のアプリに設定してください。両方のアプリを対象とするキャンペーンでは、AppsFlyerでアプリ別にコストを分けられず、両アプリの合計コストが表示されます。
> * Google Ads APIの仕様により、現在事前登録キャンペーンにおいてコスト、クリック、インプレッションデータはご利用いただけません。

AppsFlyer管理画面内でGoogle Adsのコスト、クリック、インプレッションを表示するには、Google Ads設定ページ経由で接続が必要です。接続が完了すると、AppsFlyerでは、既存の全てのキャンペーンにおけるGoogle Adsのコスト、クリック、インプレッションを照会し始めます。

詳細：<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">Google Adsコスト連携設定</Anchor>

Googleのクリックとビューの定義についてご参照ください。

詳細：<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6163740">Google Ads - 制限事項</Anchor>

**設定が完了後、数時間以内にデータが受信されます**。

> 👍 **Tip**
>
> 正しいGoogle Adsアカウントでログインしているかどうかは、Google Ads管理画面の右上に表示されるメールアドレスで確認できます。
>
> Google AdsアカウントがMCCアカウントのサブアカウントである場合、右上のIDはMCCのIDであり、 サブアカウントのIDは左上隅にあります。
>
> 正しいアカウントにログインしていない場合は、アカウントからログアウトして、別のGoogleアカウントのメールアドレスで再度ログインします。

### コストデータ連携状況

コスト（および広告収益）連携状況ダッシュボード、または各アドネットワークのダッシュボードで、<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と、AppsFlyerが対応するコストデータを最後に取得できた日時を確認できます。 

Google Adsでは、複数のアカウントを同期して、コストデータを取得することができます。同期されたアカウントごとに、AppsFlyerにはコスト連携のステータス（連携状況）と、一致するコストデータを最後に取得できた日時が表示されます。

### Googleのコスト同期の停止

**Googleコストの同期を停止するには、Googleアカウントの接続を削除します：**

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">コストタブを開き、アカウントの［アクション］列にカーソルを合わせて［接続を削除］をクリックします。</Anchor> 削除すると、AppsFlyerによるコストの取得が停止します。接続を削除しても過去のデータには影響しません。

## Google Adsでの広告収益の記録

Google Ads（AdWords）の広告収益連携は、2020年11月30日に廃止されました。広告収益データを取得するには、AdWordsをご利用のお客様は<Anchor target="_blank" href="/marketers/ja/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>への移行が必要です。

<Accordion title="よくある質問">

**Q.** コストデータが表示されない場合は？

**A.** データが表示されない理由はいくつか考えられます：

* ログイン時に、正しいGoogleアカウントを使用していることを必ず確認してください。  
  誤ったGoogleアカウントでログインすると、コストデータは取得・表示されません。このような場合は、Googleアプリの権限からアプリを削除して、正しいアカウントでログインする必要があります。そのためには、次のステップを実行してください：
  1. 次のURLをクリックします：<Anchor target="_blank" href="https://myaccount.google.com/permissions">https://myaccount.google.com/permissions</Anchor>
  2. Google側でAppsFlyer Costを削除し、再度ログインします。
* 代理店のコスト連携が有効でも、ログインした代理店ユーザーに該当するGoogle Adsのお客様IDへのアクセス権がないと、コストを取得できない場合があります。これにより、広告主には不完全なコストデータが表示されます。

  ［コスト］タブでログインする代理店ユーザーが、［連携］タブで設定したGoogle Adsのお客様IDにアクセスできることを確認してください。

  <Image alt="" src="https://files.readme.io/2d17b3dad78e02c76253f30db0c15c18eb837b531becabc07ccad274258c2c61-49938966132753.png" width="457px" />
* iOS検索キャンペーンやAndroidランディングページキャンペーンでスペースや特殊文字を使用すると、コストデータとクリックデータの照合に問題が生じ、コストがレポートに表示されなくなる場合があります。
* コストの取得開始後に代理店がコスト連携を無効にしても、広告主側のコスト連携が有効であれば、代理店が連携を無効にした日以降のデータのみ広告主に紐づきます。

**Q.** 地域別のクリックデータはどこに表示されますか？

**A.** Googleから取得する地域別クリックデータが、一部に限られる場合があります。その場合、AppsFlyerは地域情報を含まないGoogleの他のデータソースから、不足しているクリック情報を補完します。したがって、地域別にグループ化すると、Googleのキャンペーンからのクリック合計数が、別のグループ区分のクリック合計数と一致しないことがあります。

</Accordion>

<Accordion title="機能と制限事項">

| 項目 | 補足 |
| --- | --- |
| アクティブ / 非アクティブなキャンペーン | Google Ads連携は、以下の場合、**非アクティブキャンペーン**（AppsFlyerでインストールやコンバージョンが記録されていないキャンペーン）のコストデータ（コスト、クリック数、インプレッション数）をサポートします：<ul><li>インストール向けアプリキャンペーン（ACIキャンペーンタイプ）</li><li>エンゲージメント向けアプリキャンペーン（ACEキャンペーンタイプ）</li><li>事前登録用アプリキャンペーン（ACPREキャンペーンタイプ）</li></ul>これらのアプリキャンペーンでは、AppsFlyerはアトリビューションデータに合わせてコストデータをチャネル別に分類します。例：ACI\_Display、ACI\_Youtube、ACI\_Search<br /><br />非ACIおよび非ACEキャンペーンの場合、AppsFlyerは**アクティブなキャンペーン**のみのコストデータ（コスト、クリック、インプレッション）をレポートします。 つまり、少なくとも1つのコンバージョンまたはインストールがAppsFlyerに記録されているキャンペーンです。コストデータは、コンバージョン／インストールの7日間の期間についてレポートされます。 |
| Performance Maxキャンペーン | Performance Maxキャンペーンは、国 / 地域別のコストデータの内訳をサポートしていません。 |

</Accordion>

**関連記事**

* iOS 14関連の考慮事項については、<Anchor target="_blank" href="/marketers/ja/docs/get-skan-postback-data-from-google-ads">Google AdsにおけるSKAdNetworkとAppsFlyerの相互運用性</Anchor>をご参照ください。

<div data-zendesk-anchors="cost-clicks-and-impressions=%E3%82%B3%E3%82%B9%E3%83%88%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E6%95%B0%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 h_01HDP2SMHJ26S1BCER3KKZ8H14=%E3%82%B3%E3%82%B9%E3%83%88%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E6%95%B0%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 cost-data-sync-status=%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E9%80%A3%E6%90%BA%E7%8A%B6%E6%B3%81 h_01HDP2SMHJT8Z6DP7BHC0Y5RRN=%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E9%80%A3%E6%90%BA%E7%8A%B6%E6%B3%81 stopping-google-cost-sync=google%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E5%90%8C%E6%9C%9F%E3%81%AE%E5%81%9C%E6%AD%A2 h_01HDP2SMHJPEDKKZF9SBXW56KG=google%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E5%90%8C%E6%9C%9F%E3%81%AE%E5%81%9C%E6%AD%A2 recording-ad-revenue-with-google-ads=google-ads%E3%81%A7%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E8%A8%98%E9%8C%B2 h_01HDP2SMHKC9TSZZZPFFNK8TPH=google-ads%E3%81%A7%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E8%A8%98%E9%8C%B2" />
