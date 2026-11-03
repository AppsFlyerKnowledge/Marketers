---
title: オーディエンスのユーザー識別子ポリシー
metadata:
  keywords:
    - IDFA
    - Audiences
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-12-23T15:39:55Z'
  edited_at: '2026-10-14T09:20:21Z'
  id: 360016791118
  locale: ja
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ja/articles/360016791118
---
> **概要：** ユーザー識別子ポリシーを設定して、オーディエンスがパートナーと共有するデータを**アカウントレベル**で管理できるようにしましょう。

## 概要

オーディエンスを定義すると、 AppsFlyer Audiencesは、そのオーディエンスのメンバーの識別子を、選択した<Anchor target="_blank" href="/marketers/ja/docs/audiences-partner-connections">広告パートナー</Anchor>に送信します。これにより、これらのユーザーのみに広告を配信できるようになります。

iOS 14.5のプライバシー要件やその他のユーザープライバシー考慮事項にコンプライアンスするために、Audiencesはどの識別子をパートナーと共有するかを自在に管理できます：

* アカウントレベルで
* パートナー接続レベルで

この記事では、アカウントレベルでのユーザー識別子ポリシーの管理方法を解説します。パートナー接続レベルで共有される識別子の管理について詳しくは、オーディエンスガイドの<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#manage-connections">接続の管理</Anchor>セクションを参照してください。

## ユーザー識別子

このセクションでは、パートナーと共有可能な識別子について説明します。

<div id="shared-identifiers" />

<Accordion title="共有識別子">

デフォルトでは、Audiencesは次の識別子をパートナーと共有します。

* **iOS：** IDFA（iOS 14.5以降、ユーザーがこの識別子の共有を許可した場合にのみ利用可能）
* **Android：** GAID

一部の広告パートナーは、次の識別子もサポートしています：

* メールアドレス（ハッシュ化）
* 電話番号（ハッシュ化）
* OAIDとIMEI（どちらもGoogle Play以外のAndroidストアに適用）

その他の識別子は、自社の内部プロセス（CRMやアナリティクス）に有効な場合があります：

* CUID
* IDFV（iOSにのみ関連）

追加情報（AppsFlyerで特定の識別子を使用する要件を含む）については、以下の識別子表を参照してください。

</Accordion>

<div id="identifiers-table" />

<Accordion title="識別子のテーブル">

<table><thead><tr><th>識別子</th><th>OS</th><th>デフォルトで共有されるか？</th><th>使用条件／<br/>注記<br/><br/> </th></tr></thead><tbody><tr><td>IDFA</td><td>iOS</td><td>注記を参照<br/>（右）</td><td>デフォルトでは、<a href="./audiences-user-identifier-policy#ios">ATTステータス： 承認済みまたは未決定</a>のユーザーのみ共有されます。 </td></tr><tr><td>GAID</td><td>Android</td><td>はい</td><td>なし</td></tr><tr><td>OAID</td><td>Android<br/>（Google Play以外）</td><td>いいえ</td><td> AppsFlyer SDKの<a href="./android-oaid-implementation-in-the-sdk" target="_blank">実装が必要</a> </td></tr><tr><td>IMEI</td><td>Android<br/>（Google Play以外）</td><td>いいえ</td><td> AppsFlyer SDKの<a href="./android-oaid-implementation-in-the-sdk" target="_blank">実装が必要</a> </td></tr><tr><td>CUID</td><td>iOS<br/>Android</td><td>いいえ</td><td><ul><li>広告主によって生成され、<a href="./customer-user-id-field-cuid" target="_blank">AppsFlyer APIまたはSDKを使用してAppsFlyer</a>にレポートされます。</li><li>広告パートナーと共有されませんが、社内の目的には役立つ場合があります。</li><li> <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">追加識別子利用規約</a>に基づきます。 </li></ul></td></tr><tr><td>IDFV</td><td>iOS</td><td>いいえ</td><td><ul><li>広告パートナーと共有されませんが、社内の目的には役立つ場合があります。</li><li> <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">追加識別子利用規約</a>に基づきます。 </li></ul></td></tr><tr><td>メールアドレス（ハッシュ化）</td><td>iOS<br/>Android</td><td>いいえ</td><td rowspan="2"><ul><li> AppsFlyer SDKまたはS2SモバイルAPI経由で<a href="./audiences-configure-additional-identifiers-for-partner-audience-creation" target="_blank">実装する必要</a>があります</li><li>SHA256ハッシュで暗号化する必要があります。</li><li> <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">追加識別子利用規約</a>に基づきます。 </li></ul></td></tr><tr><td>電話番号（ハッシュ化）</td><td>iOS<br/>Android</td><td>いいえ</td></tr></tbody></table>

</Accordion>

## アカウントレベルのユーザー識別子ポリシー設定

ユーザー識別子ポリシーは管理者ユーザーのみが設定できます。

**ポリシーを設定または変更するには、次の手順に従ってください：**

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。
2. 右上隅にある設定 (歯車) アイコンをクリックします。
3. **ユーザー識別子ポリシー**の画面にて、自社のプライバシーポシリーに準拠する設定を選択してください。
   * IDFA、GAID、OAID、IMEI 以外の識別子の共有を許可する選択をした場合は、まず[Additional Identifiers Terms of Use](https://support.appsflyer.com/hc/article_attachments/360017900558)（追加識別子の利用規約）を確認し同意する必要があります。
   * 既存のパートナー接続によってアップロードされた識別子を許可しない場合、これらの識別子のアップロードを停止するかどうかを確認する通知が表示されます。
4. **保存**をクリックしてください。

IDFA ポリシーの変更は、AppleのiOS 14.5のリリースから有効になります。ユーザー識別子ポリシーに対するその他のすべての変更は、パートナーへの次のアップロードから有効になります。

## プライバシー規制

このセクションでは、ユーザー識別子の共有方法に影響するプライバシー規制について説明します。

<div id="ios" />

<Accordion title="iOS">

バージョン14.5以降、iOSでは、広告目的（App Tracking Transparency）でのIDFAデバイス識別子の共有を許可／禁止するオプションを全てのアプリでユーザーに提供する必要があります。このオプション（ATT同意ダイアログ）をユーザーが見て応答したかどうかで、<Anchor target="_blank" href="/marketers/ja/docs/att-implications-ios-14-and-deprecation-of-lat">ATTステータス</Anchor>が決まります。

iOS における識別子共有のためのオーディエンスポリシーオプションは、ユーザーの最新の ATT ステータスに基づいています。共有オプションは次のとおりです：

| ユーザーポリシーオプション | 対応するATTステータス |
| --- | --- |
| アップロードしない | この識別子はパートナーにアップロードされません |
| ATTステータス：承認のみ | 最新のATTステータスが **authorized** または **af\_authorized** の場合、識別子がアップロードされます。 |
| ATT ステータス：承認済みまたは未決定 | 最新のATT ステータスが **authorized**、**af\_authorized**、**not\_determined**、または **af\_unavailable**の場合、識別子がアップロードされます。  <br />  <br />*Apple のiOS 14.5リリース以降のIDFAのデフォルトオプション* |
| 常にアップロード | 識別子はATTステータスに関係なくアップロードされます。アプリの利用規約に準拠していることを確認してください。  <br />  <br />*IDFAではこのオプションは利用できません* |

**注記：** Audiencesでは、新規ユーザーがATT同意ダイアログを確認し応答するまで、彼らのATTステータスを <strong>not determined（未決定）</strong>と見なします。

ATTステータスの詳細な定義については、以下を参照してください：

* <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">Apple ATTステータスの定義</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/att-implications-ios-14-and-deprecation-of-lat#attの値">AppsFlyer ATTステータスの定義</Anchor>（af\_authorized、af\_unavailable）

さらに、欧州経済領域（EEA）のすべてのユーザーは、Google による[デジタル市場法（DMA）](/docs/audiences-user-identifier-policy#eu-digital-markets-act)の施行の対象となります。

</Accordion>

<div id="android" />

<Accordion title="Android">

欧州経済領域（EEA）のAndroidユーザーは、Google による[デジタル市場法（DMA）](/docs/audiences-user-identifier-policy#eu-digital-markets-act)の施行の対象となります。

</Accordion>

<div id="eu-digital-markets-act" />

<Accordion title="EUデジタル市場法">

Googleは、2024年3月6日のデジタル市場法（DMA）の施行の一環として、EUユーザーの同意ポリシーを更新しました。Google公式アプリアトリビューションパートナーとして、AppsFlyerは、広告主がGoogle広告のマーケティングチャネルから最大限の価値を引き出せるようにしながら、ポリシー要件をサポートするために必要な変更を行っています。<Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">詳細はこちら</Anchor>

**変更によりオーディエンスにどのような影響があるか：**

* **新しいAppsFlyer SDK**  
  最新のAppsFlyer SDKは、<Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">欧州経済領域（EEA）</Anchor>のアプリ所有者からユーザー同意を収集し、そのデータをGoogleと共有できるようにします。AppsFlyerで作成されたオーディエンス（カスタムオーディエンスや推奨オーディエンスなど）は、SDKから収集された同意情報を自動的に Audiences と共有し、その後Googleと共有されます。最新のSDKに更新すると、このプロセスは自動的に実行されます。
* **Googleに接続しているオーディエンス**
  * **同意が得られた場合** - AppsFlyerは、情報をGoogleと共有することに同意したEEAユーザーのデバイスを送信します。
  * **同意が拒否された場合** - AppsFlyerは、Googleと情報を共有することに同意しなかったEEAユーザーのデバイスを送信しません。
  * **同意が不明な場合** - AppsFlyerは、同意の付与も拒否も行っていないEEAユーザーのデバイスを「未指定」として送信します。Googleは、これらを自社のオーディエンスに含めることはおそらくないでしょう。  

    詳細については、Googleの<Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">FAQ</Anchor>をご覧ください。
* **既存のオーディエンス**  
  2024年3月6日以前にGoogle内で既にオーディエンスの一部であったすべてのデバイスは影響を受けず、引き続きオーディエンスの一部です。既存のオーディエンスに追加された新しいオーディエンスまたは新しいEEAデバイスのみが、同意を得てGoogleにアップロードされます。
* **オーディエンスアップロードサイズ**  
  同意を許可または拒否するユーザーの数に応じて、推定および実際のアップロードサイズが影響を受ける可能性があります。
* #### **オーディエンスのインポート**

  * **標準オーディエンスのインポート** - AppsFlyerは、AppsFlyer SDKから収集した同意データを追加し、同意されていないデバイスや指定されていないデバイスをオーディエンスから削除してから、Googleに送信します。
  * **「現状のまま」のオーディエンスをインポートする** - <Anchor target="_blank" href="/marketers/ja/docs/audiences-import-audience-segments-from-internal-systems#import-a-csv-file">CSV</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/audiences-import-audience-segments-from-internal-systems#use-the-import-audience-api">API</Anchor>経由で「現状のまま」のオーディエンスをインポートする場合は、さらに2つの同意フィールドを追加する必要があります。これらのフィールドは次のとおりです：

| AppsFlyerフィールド(1) | Googleフィールド(2) | 値 | フィールドの説明 |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true/false | ユーザーがGoogleに自分のデータをパーソナライズ広告利用することに同意したか？ |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true/false | ユーザーが自分のデータをGoogleに送信することに同意したか？ |

同意フィールドに価値が入力されていない場合は、「未指定」としてGoogleに送信されます。

> 📘 **注記**
>
> Googleによるデジタル市場法（DMA）の施行は、AndroidとiOSプラットフォームの両方に適用されます。

</Accordion>

<div data-zendesk-anchors="background=%E6%A6%82%E8%A6%81 h_01HKA2FS9VBCSV8FP8FH79H4R0=%E6%A6%82%E8%A6%81 user-identifiers=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E8%AD%98%E5%88%A5%E5%AD%90 h_01HKA2FS9VSVJD54R14GC7G0P4=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E8%AD%98%E5%88%A5%E5%AD%90 h_01HNZH99Z8NA9607VHSYH5XVW0=shared-identifiers h_01HKA2FS9V1KBK9BJAJ63FP6CV=identifiers-table setting-accountlevel-user-identifier-policy=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%83%AC%E3%83%99%E3%83%AB%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E8%AD%98%E5%88%A5%E5%AD%90%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BC%E8%A8%AD%E5%AE%9A h_01HKA2FS9WNGGRP3NX5NKV15SK=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%83%AC%E3%83%99%E3%83%AB%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E8%AD%98%E5%88%A5%E5%AD%90%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BC%E8%A8%AD%E5%AE%9A user-identifier-policy-options=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E8%A6%8F%E5%88%B6 h_01HKA2FS9W5NSKKRK2VCZARG15=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E8%A6%8F%E5%88%B6 h_01HNZJ1ET6F87AHHVQK17QHZDD=ios h_01HNZJ1ET67JQQCPYSM3H6Y9VW=android h_01HNZN8MWETDCMGWKJ0MMM8JK4=eu-digital-markets-act importing-audiences=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%AE%E3%82%A4%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%88 h_01HPGV1GYT8DW0GYWTC031TNVH=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%AE%E3%82%A4%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%88 h_01HNZEAJT00KKEBDPR7FD0TJNR=%E6%B3%A8%E8%A8%98" />
