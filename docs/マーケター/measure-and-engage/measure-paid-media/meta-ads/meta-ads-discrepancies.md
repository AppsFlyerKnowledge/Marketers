---
title: Meta広告｜計測値の乖離
metadata:
  keywords:
    - Facebook
    - Advertisers
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
  created_at: '2021-11-09T10:10:54Z'
  edited_at: '2026-10-28T09:16:34Z'
  id: 4410481130641
  locale: ja
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ja/articles/4410481130641
---
> **概要：** Meta広告とAppsFlyerのアトリビューションモデルの違いについて説明します。

<div id="meta-ads-discrepancies-with-appsflyer" />

## Meta広告とAppsFlyerの計測値の乖離

モバイルアプリのユーザー獲得における主要なプラットフォームであるAppsFlyerとMeta広告では、アトリビューションモデルが異なります。そのため、Meta広告とAppsFlyerのダッシュボードに表示される数値に乖離が生じる場合があります。

AppsFlyerはMeta広告と緊密に連携して乖離の縮小に取り組んでいますが、広告主は以下の原因を把握しておく必要があります。

<div id="detect-a-discrepancy-between-appsflyer-and-meta-ads" />

### AppsFlyerとMeta広告の計測値の乖離の確認

Meta広告の**イベントマネージャ**に表示されるイベントと、AppsFlyerのレポートに表示されるイベントを比較します。イベント数が大きく異なる場合は、計測値に乖離が生じている可能性があります。

<div id="differences-in-attribution-models" />

## アトリビューションモデルの違い

<table><thead><tr><th>原因</th><th>Meta広告</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><strong>クリックアトリビューションのルックバック期間</strong></td><td>7日間（<a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">一部のケースではデフォルト値が異なります</a>）。</td><td>1～30日間。 Meta広告に合わせて、必ず7日間に設定してください。</td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><strong>ビュースルーアトリビューションのルックバック期間</strong></td><td>1日（<a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">一部のケースではデフォルト値が異なります</a>）。</td><td>デフォルトは1日ですが、1～48時間の範囲で設定できます（デフォルト値を維持してください）。</td></tr><tr><td><span id="multichannel-sourceattribution"></span> <strong>複数のメディアソースを</strong><br/><strong>考慮したアトリビューション</strong> </td><td>Meta広告は、他のメディアソースの関与にかかわらず、自社の基準でインストールを自社にアトリビューションします。</td><td>AppsFlyerはラストクリックアトリビューションを使用します（AppsFlyerのアトリビューションの詳細は<a href="./appsflyer-attribution-model" title="AppsFlyer Attribution Model" target="_blank">こちら</a>を参照）。</td></tr><tr><td><span id="crossdevice-attribution"></span><strong>クロスデバイスアトリビューション</strong></td><td>Meta広告は、iOS、Android、デスクトップなど、異なるデバイスでクリックとインストールを行ったユーザーもアトリビューションの対象とします。</td><td>AppsFlyerは、同一のデバイスでエンゲージメントとインストールが発生した場合にアトリビューションします。</td></tr><tr><td><span id="different-time-zones"></span><strong>タイムゾーンの違い</strong></td><td>Meta広告のレポートのデフォルトタイムゾーンはPSTです。 AppsFlyerのアプリ設定で指定したアプリのタイムゾーンと一致するように、必ず<a href="https://www.facebook.com/business/help/754049591334898" target="_blank">Meta広告マネージャでタイムゾーンを変更してください</a>。</td><td>AppsFlyerのアプリのデフォルトタイムゾーンはUTC+0です。<a href="./app-settings#localization-time-zone" target="_blank">アプリ設定ページ</a>でアプリのタイムゾーンを変更し、Meta広告マネージャで指定したタイムゾーンと一致させることができます。</td></tr><tr><td><span id="google-install-referrer"></span><strong>インストールリファラ</strong></td><td colspan="2">広告IDのないインストールがGoogle Playインストールリファラ、Facebookインストールリファラ、Instagramインストールリファラを介してMeta広告にアトリビューションされた場合、AppsFlyerはそのインストールをMeta広告に報告しません。このインストールはAppsFlyerには表示され、Meta広告には表示されないため、乖離が生じる場合があります。</td></tr></tbody></table>

<div id="click-through-and-view-through-attribution" />

## クリックスルーアトリビューションとビュースルーアトリビューション

AppsFlyerは、クリックスルーアトリビューションとビュースルーアトリビューションの両方をサポートしています。 Meta広告とAppsFlyerの乖離を最小限に抑えるため、クリックスルーとビュースルーの両方のルックバック期間を、Meta広告のデフォルト値と一致させてください。

Meta広告のクリックスルールックバック期間のデフォルト値は7日間です。[一部のケースではデフォルト値が異なります](https://www.facebook.com/business/help/395050428485124?id=428636648170202)が、Meta広告のデフォルト設定をすべてカバーするため、AppsFlyerのクリックスルールックバック期間は7日間に設定することを推奨します。

AppsFlyerのアトリビューション期間は、Meta広告の設定値に合わせることを推奨します。<Anchor target="_blank" href="https://www.facebook.com/business/help/654970342692714">アトリビューション設定の比較については、Meta for Developersのドキュメントを参照してください。</Anchor>

<Image align="center" alt="image (13).png" src="https://files.readme.io/215d2234aae1ec6b4e1c6ac922915851bf8ab02574a874119d286fa49c64f9ba-25899749062033.png" />

<div id="example" />

> 📄 **例**
>
> アプリcom.greatappについて、AppsFlyer側のMeta広告のクリックルックバック期間を1日、Meta広告側をデフォルトの7日間に設定したとします。 FacebookでGreatappの広告をクリックし、2～7日後に初めてアプリを起動したユーザーは、AppsFlyerではオーガニックユーザーに分類されます。一方、Meta広告はこれらのユーザーを自社の成果として報告します。

<div id="in-app-events-differences" />

## アプリ内イベントの乖離

Meta広告とAppsFlyerに表示されるインストール後のイベント（アプリ内購入など）にも、両プラットフォーム間で乖離が生じる場合があります。以下の表では、主な原因と、乖離を最小限に抑える方法を説明します。

| 原因 | 説明 | AppsFlyerからのヒント |
| --- | --- | --- |
| <span id="different-lifetime-definition"></span>**ユーザーのライフタイムの定義の違い** | Meta広告では、ユーザーのライフタイムは最大7日間と定義されています。そのため、広告クリックから7日を超えて発生したイベントは表示されません。  <br />AppsFlyerでは、Meta広告経由のユーザーのライフタイムは最大180日間と定義されています。 | Meta広告キャンペーン経由のユーザーについて、7日を超えて発生したイベントも含めて価値を評価する場合は、AppsFlyerのデータを使用すると、より広い範囲で把握できます。 |
| <span id="unmapped-events"></span>**イベントがマッピングされていない** | AppsFlyerはSDKからイベントを受信していますが、Meta広告へのマッピングが設定されていないため、送信していません。 | ユーザーの質を評価するうえで重要なアプリ内イベントは、すべて<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-in-app-event-mapping">Meta広告にマッピングしてください</Anchor>。 |
| <span id="unsent-revenue"></span>**収益が送信されていない** | AppsFlyerはSDKのイベントから収益を受信していますが、Meta広告には送信していません。 | 下の画像の購入イベントのように、アプリ内イベントの<strong>［収益を送信］</strong>のチェックボックスが必ずオンになっていることを確認してください。 |
| <span id="missing-event-values-on-facebook"></span>**Meta広告にイベント値が表示されない** | AppsFlyerは、イベントのマッピングに基づき、構造が正しいパラメータと値をMeta広告に送信します。 | イベント値をMeta広告に漏れなくマッピングするため、SDKのアプリ内イベントは<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure">AppsFlyerの推奨する構造</Anchor>に従って設定してください。 |
| <span id="different-event-count"></span>**イベント数の違い** | Facebook（FB）ダッシュボードに表示される特定のアプリ内イベント（購入イベントなど）の件数が、AppsFlyer（AF）ダッシュボードの対応する件数と異なります。 | Facebook（FB）ダッシュボードはアクティビティベースですが、AppsFlyer（AF）のOverview dashboardとイベントダッシュボードはLTVベースです。イベント数を比較する場合は、AppsFlyerのアクティビティベースのダッシュボードを使用してください。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports#about-data-differences-and-discrepancies">LTVとアクティビティの違い</Anchor>を参照してください。 |

<div id="installs-from-re-engagement-campaigns-in-my-ua-dashboard" />

## リエンゲージメントキャンペーンのインストールがUAダッシュボードに表示される理由

リエンゲージメントキャンペーンでは、ユーザーがインストール済みのアプリを開くことがあります（**リエンゲージメント**）。また、同じデバイスに過去のインストール履歴があるとAppsFlyerが認識した場合、そのコンバージョンを**リアトリビューション**として扱うことがあります。

リエンゲージメントキャンペーンでMeta広告が**新規ユーザー**、または初回インストールから<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">**リアトリビューション期間**</Anchor>を**超えた後にインストールしたユーザー**をターゲットにした場合、Meta広告ではリエンゲージメントキャンペーンの成果であっても、AppsFlyerでは**新規ユーザー獲得のインストール**として記録されます。

一方、初回インストールから**設定済みのリアトリビューション期間内**に発生したインストールはリアトリビューションと見なされ、AppsFlyerのリターゲティングページに表示されます。Meta広告では、新規インストールとして表示される場合があります。

<div id="note" />

> 📘 **注意**
>
> Meta広告ではリターゲティングキャンペーンのすべてのインストールが同じ場所に表示されますが、AppsFlyerのダッシュボードではOverview dashboard（新規インストール）とリターゲティングページ（リアトリビューションとリエンゲージメント）に分かれて表示されます。

<div id="cross-device-attribution" />

## クロスデバイスアトリビューション

Meta広告は、クロスデバイスアトリビューションを報告します。そのため、あるプラットフォーム（iOSまたはAndroid）向けのキャンペーンに、別のプラットフォームのインストールが表示される場合があります。

<div id="example-1" />

> 📄 **例**
>
> LindaがAndroidスマートフォンのFacebookでGreatAppのモバイル広告をクリックします。 Meta広告は、このクリックを元のAndroid向けキャンペーン「Android Females」の成果として記録します。 Lindaは、自宅のiPadにGreatAppをインストールすることにします。初回起動時にAppsFlyerがこのiOSインストールの流入元をMeta広告に問い合わせると、Meta広告は「Android Females」キャンペーンと回答します。

<div id="validation-rules-and-protect360" />

## 検証ルールとProtect360

<Anchor target="_blank" href="/marketers/ja/docs/implement-validation-rules-to-prevent-fraud">AppsFlyerの検証ルール</Anchor>を使用しており、Meta広告経由のインストールが拒否された場合、AppsFlyerとMeta広告の結果が異なることがあります。この場合、Meta広告は自社の成果としてインストールを報告しますが、AppsFlyerは同じインストールを拒否します。

同様に、AppsFlyerの不正対策ソリューションであるProtect360を使用している場合も、Meta広告が自社の成果として報告するインストールをAppsFlyerが拒否することがあります。

<div id="example-2" />

> 📄 **例**
>
> GreatAppのUA担当マネージャーであるJeffが、北米のスペイン語話者のみをターゲットにした「SPNA」というキャンペーンを作成します。この条件を検証するため、Jeffはカナダと米国のユーザーのみを受け入れる検証ルールを設定します。
> スペインにいるMeta広告のユーザーが広告をクリックしてアプリをインストールすると、Meta広告は自社の成果として報告します。一方、AppsFlyerは検証ルールを満たさないため、このインストールを拒否します。

<div id="sdk-related-discrepancies" />

## SDKに関連する乖離

広告主が<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-faq#who-needs-facebooks-sdk">AppsFlyer SDKとFacebook SDKの両方を実装するケース</Anchor>があります。これにより、アプリ内イベントに乖離が生じる場合があります。 Meta広告は、両方のSDKから報告されたアプリ内イベントの重複を排除しません。そのため、Meta広告で収益やその他のイベントが正しく報告されない可能性があります。

* Meta広告でのアプリ内イベントの二重報告を避けるには、以下の**いずれか**の方法を使用してください。
  * Facebook SDKでイベントを設定しないようにします。
  * AppsFlyer側で<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-in-app-event-mapping">Meta広告へのアプリ内イベントのマッピング</Anchor>を無効にします。

<div id="meta-probabilistic-modeling-aem-discrepancies-in-ios-apps" />

## iOSアプリにおけるMetaの確率論的モデリング（AEM）による乖離

iOSアプリで合算イベント測定（AEM）を有効にすると、Metaは確率論的モデリングを使ってインストールやアプリ内イベントをアトリビューションする場合があります。 <strong>Metaは、社内レポートとAppsFlyerに共有する情報で、異なるモデリング手法を適用する場合があります。</strong>このモデリング手法の違いにより、Meta広告マネージャとAppsFlyerに表示されるインストール数は、どちらかが多くなる場合も少なくなる場合もあります。具体的には、次のようなケースがあります。

* Metaが内部でコンバージョンを記録していても、対応するAEMのアトリビューション申告をAppsFlyerに送信しない場合があります。
* 広告マネージャに表示されない、モデリングによるコンバージョンについて、MetaがAEMのアトリビューション申告をAppsFlyerに送信する場合があります。

<div data-zendesk-anchors="facebook-ads-discrepancies-with-appsflyer=meta%E5%BA%83%E5%91%8A%E3%81%A8appsflyer%E3%81%AE%E8%A8%88%E6%B8%AC%E5%80%A4%E3%81%AE%E4%B9%96%E9%9B%A2 01H890CZSXPMK0BDMC4202HNYM=meta%E5%BA%83%E5%91%8A%E3%81%A8appsflyer%E3%81%AE%E8%A8%88%E6%B8%AC%E5%80%A4%E3%81%AE%E4%B9%96%E9%9B%A2 detect-a-discrepancy-between-appsflyer-and-facebook=appsflyer%E3%81%A8meta%E5%BA%83%E5%91%8A%E3%81%AE%E8%A8%88%E6%B8%AC%E5%80%A4%E3%81%AE%E4%B9%96%E9%9B%A2%E3%81%AE%E7%A2%BA%E8%AA%8D 01H890CZSXGHVBH21SQA0671JQ=appsflyer%E3%81%A8meta%E5%BA%83%E5%91%8A%E3%81%AE%E8%A8%88%E6%B8%AC%E5%80%A4%E3%81%AE%E4%B9%96%E9%9B%A2%E3%81%AE%E7%A2%BA%E8%AA%8D differences-in-attribution-models=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%A2%E3%83%87%E3%83%AB%E3%81%AE%E9%81%95%E3%81%84 01H890CZSX8M6VGGREYX4W2X37=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%A2%E3%83%87%E3%83%AB%E3%81%AE%E9%81%95%E3%81%84 clickthrough-and-viewthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01H890CZSX40JDGY8P8AQ4CYGS=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01H890CZSXRD7PCZBK52GW7QE9=%E4%BE%8B inapp-events-differences=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E4%B9%96%E9%9B%A2 01H890CZSXKC5JKK9051MC0VY6=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E4%B9%96%E9%9B%A2 installs-from-reengagement-campaigns-in-my-ua-dashboard=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%8Cua%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AB%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%82%8B%E7%90%86%E7%94%B1 01H890CZSYE21K7PBQK4PNMGJR=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%8Cua%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AB%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%82%8B%E7%90%86%E7%94%B1 01H890CZSY7TRCA4NVKSVPY7DB=%E6%B3%A8%E6%84%8F crossdevice-attribution::77a37a1f=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01H890CZSYS8QKEAF6799SBS8J=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01H890CZSY2Z3S6E9R5MYC1CHX=%E4%BE%8B-1 validation-rules-and-protect360=%E6%A4%9C%E8%A8%BC%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%A8protect360 01H890CZSYDHZE4V0ZWTT8V0EJ=%E6%A4%9C%E8%A8%BC%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%A8protect360 01H890CZSYCTQZCAYAZP9TCBBF=%E4%BE%8B-2 sdk-related-discrepancies=sdk%E3%81%AB%E9%96%A2%E9%80%A3%E3%81%99%E3%82%8B%E4%B9%96%E9%9B%A2 01H890CZSYVFPQP0SKNPWMPB1R=sdk%E3%81%AB%E9%96%A2%E9%80%A3%E3%81%99%E3%82%8B%E4%B9%96%E9%9B%A2 meta-probabilistic-modeling-aem-discrepancies-in-ios-apps=ios%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bmeta%E3%81%AE%E7%A2%BA%E7%8E%87%E8%AB%96%E7%9A%84%E3%83%A2%E3%83%87%E3%83%AA%E3%83%B3%E3%82%B0aem%E3%81%AB%E3%82%88%E3%82%8B%E4%B9%96%E9%9B%A2 h_01KA6NEZSRFSAJYZ5C4HJ4SKTQ=ios%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bmeta%E3%81%AE%E7%A2%BA%E7%8E%87%E8%AB%96%E7%9A%84%E3%83%A2%E3%83%87%E3%83%AA%E3%83%B3%E3%82%B0aem%E3%81%AB%E3%82%88%E3%82%8B%E4%B9%96%E9%9B%A2" />
