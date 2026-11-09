---
title: Meta広告｜よくある質問
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
  created_at: '2021-11-09T10:04:49Z'
  edited_at: '2026-10-28T09:16:37Z'
  id: 4410472805649
  locale: ja
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ja/articles/4410472805649
---
> **概要：** AppsFlyerでのMeta広告の利用に関するよくある質問と回答を紹介します。

<div id="meta-ads-faq" />

## Meta広告に関するよくある質問

<div id="i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard" />

<Accordion title="Meta広告キャンペーンのクリック数がAppsFlyerのダッシュボードに表示されません">

デフォルトでは、Meta広告はコンバージョンとエンゲージメントのデータのみを送信します。ただし、簡単な設定で<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta広告キャンペーンのクリック、インプレッション、コストのデータ</Anchor>も取得できます。

</Accordion>

<div id="can-appsflyer-show-the-campaign-level-and-ad-groups" />

<Accordion title="AppsFlyerでキャンペーンや広告グループ単位のデータを確認できますか？">

はい。 AppsFlyerでは個々の広告単位でも表示できるため、Meta広告のデータをキャンペーン、広告グループ、広告の3階層で掘り下げて確認できます。

</Accordion>

<div id="is-facebook-data-shown-in-realtime" />

<Accordion title="Meta広告のデータはリアルタイムで表示されますか？">

はい。すべてのインストールと、その後のアプリ内イベントはリアルタイムで表示されます。ただし、AppsFlyerがMeta広告から集計形式で取得するクリック、インプレッション、コストのデータは、数時間ごとに定期的に届きます。

</Accordion>

<div id="when-can-i-see-a-new-campaigns-data-on-appsflyer" />

<Accordion title="新しいキャンペーンのデータは、いつAppsFlyerに表示されますか？">

Meta広告の新しい広告、広告セット、キャンペーンのデータを表示するには、少なくとも1件のインストールが発生する必要があります。

たとえば、新しい広告で100クリックが発生しても、インストールが0件の場合、AppsFlyerのダッシュボードやデータには表示されません。一方、クリックとインストールがそれぞれ1件だけの広告でも、AppsFlyerに表示されます。

</Accordion>

<div id="how-can-i-get-more-installs-from-facebook" />

<Accordion title="Meta広告からのインストールを増やす方法はありますか？">

Meta広告のリターゲティングを有効にすると、追加費用なしで、ユーザー獲得キャンペーンのインストール数が最大100%増加する可能性があります。  
どのような仕組みですか？<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#what-is-srn-mistargeting">こちら</Anchor>を参照してください。

</Accordion>

<div id="how-can-i-get-device-level" />

<Accordion title="Google PlayとMetaのインストールリファラを使って、Androidのデバイスレベルのインストールデータを取得するにはどうすればよいですか？">

#### Google Play Install Referrer API

Google Play Install Referrer APIを使用すると、広告主はGoogle Playストア経由のインストールについて、キャンペーン情報などのアトリビューションデータを取得できます。このAPIを<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">アプリに実装する</Anchor>と、インストール後の初回起動時にリファラデータが渡されます。必要な復号キーを登録すると、AppsFlyerのローデータレポートで、マッチタイプが`gp_referrer`のアトリビューション項目を利用できます。

<div id="meta-install-referrer" />

#### Metaインストールリファラ

Metaインストールリファラは、デバイスのローカルストレージに保存された追加のキャンペーンメタデータを提供します。このデータには、[AppsFlyer SDK](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer)を介してアクセスできます。クリックとインプレッションの両方を含む、より豊富なデータを提供し、複数のセッションにまたがる場合もあるため、Google Playインストールリファラを補完します。 Metaインストールリファラによるアトリビューションでは、`fb_referrer`（Facebook）や`ig_referrer`（Instagram）などのマッチタイプを使用します。

<div id="campaign-attribution-fields" />

#### キャンペーンのアトリビューション項目

* 広告ID
* 広告名
* 広告セットID
* 広告セット名
* キャンペーンID
* キャンペーン名
* アカウントID
* チャネル

<div id="sdk-and-setup-notes" />

#### SDKと設定に関する注意事項

* Google Playのリファラデータを取得するには、AppsFlyer SDK V5.4.0以降が必要です。
* Metaインストールリファラを利用するには、SDKが正しく設定されている必要があります。実装の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">こちらのお知らせ</Anchor>を参照してください。

<div id="submitting-the-decryption-key" />

#### 復号キーの登録

どちらのリファラも、Meta開発者アカウントで取得できる復号キーが必要です。キーはアプリごとに一度登録するだけで構いません。登録手順は以下のとおりです。

1. Metaの開発者ポータルにログインします。
2. <strong>［マイアプリ］</strong>に移動し、対象のアプリを選択します。
3. <strong>［設定］>［ベーシック］</strong>に移動し、［Install Referrer decryption key］を探します。
4. AppsFlyerで、<strong>［連携］>［連携済みパートナー］>［Meta広告］</strong>に移動します。
5. <strong>［インストールリファラ復号キー］</strong>欄にキーを貼り付け、保存します。

</Accordion>

<div id="do-you-make-facebook-raw-data-available-to-agencies" />

<Accordion title="Meta広告のローデータを代理店に提供していますか？">

いいえ。 Metaの利用規約では代理店は第三者と見なされるため、Meta広告のローデータを代理店に提供することは認められていません。

</Accordion>

<div id="i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports" />

<Accordion title="インストールとアプリ内イベントのレポートに、Meta広告のローデータが表示されません">

デフォルトでは、Meta広告は、制限のないアトリビューション情報を含むデバイスレベルのデータ配布を認めていません。ただし、MetaのAdvanced Mobile Measurement（AMM）利用規約に同意すると、Meta広告のデバイスレベルのアトリビューションデータに制限なくアクセスできます。 <Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">Meta広告のデバイスレベルのデータの有効化</Anchor>を参照してください。

</Accordion>

<div id="any-specific-columns-for-facebook-in-appsflyers-performance-reports" />

<Accordion title="AppsFlyerのパフォーマンスレポートには、Meta広告専用の列がありますか？">

はい。パフォーマンスレポートの列構成は、選択したメディアソースの組み合わせにかかわらず固定されており、キャンペーン単位までの情報が表示されます。  
ただし、Meta広告のみを対象にパフォーマンスレポートをダウンロードすると、AppsFlyerが4つの列を追加し、個々の広告単位までの情報を表示します。追加される列は、Adset Name、Adset ID、Adgroup Name（個々の広告の名前）、Adgroup IDです。

<Image align="center" alt="" src="https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png" />

</Accordion>

<div id="can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer" />

<Accordion title="Metaのキャンペーン管理パートナーを利用し、AppsFlyerで成果を計測できますか？">

はい。 AppsFlyerは、数十社のMetaキャンペーン管理パートナーと連携しています。ダッシュボードの［連携済みパートナー］ページから、これらのパートナーのアトリビューションを設定できます。

Metaキャンペーン管理パートナーとのアトリビューション設定の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/configuring-meta-campaign-management-partners">こちら</Anchor>を参照してください。

</Accordion>

<div id="what-should-i-do-when-i-receive-the-following-warning" />

<Accordion title="以下の警告が表示された場合はどうすればよいですか？">

<Image align="center" alt="" src="https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png" />

* FacebookアプリIDが正しいことと、そのFacebookアプリIDに地域や年齢の制限が設定されていないかを確認してください。
* すでにアトリビューションが機能している場合、アプリはMeta開発者ポータルで公開済みであるため、このエラーメッセージは無視して構いません。

</Accordion>

<div id="what-happens-with-different-lookback-windows-than-on-facebook" />

<Accordion title="Meta広告とは異なるルックバック期間を設定するとどうなりますか？">

Meta広告のルックバック期間の上限およびデフォルト値は、クリックが7日間、ビューが1日です。

AppsFlyerでこれより短い期間を設定すると、AppsFlyer上でMeta広告にアトリビューションされる件数は減少します。逆に、AppsFlyerでこれより長い期間を設定すると、AppsFlyer側のアトリビューション件数がMeta側よりも多くなります。

そのため、乖離を最小限に抑えるには、AppsFlyer側のMeta広告のルックバック期間を、クリックは7日間、ビューは1日に設定することを推奨します。

</Accordion>

<div id="what-are-the-facebook-api-parameters" />

<Accordion title="Meta APIのパラメータは何ですか？">

一部のAppsFlyer APIでは、後方互換性を維持するため、Metaのパラメータ名がダッシュボードの表示名と異なります。以下の表を参照してください。

| コンバージョンデータ | AppsFlyerのローデータ | Meta |
| --- | --- | --- |
| campaign | campaign | campaign\_group\_name |
| campaign\_id | キャンペーンID | campaign\_group\_id |
| adgroup | 広告 | adgroup\_name |
| adgroup\_id | 広告ID | adgroup\_id |
| adset | 広告セット | campaign\_name |
| adset\_id | 広告セットID | campaign\_id |
| agency | パートナー | N/A |
| is\_fb | メディアソース | is\_fb |
| af\_channel | チャネル | publisher\_platform |
| af\_siteid | サイトID | `publisher_platform`の値が`facebook`以外の場合はpublisher\_platform、それ以外の場合は`null`。 |

</Accordion>

<div id="how-long-do-you-keep-facebook-s-userlevel-data" />

<Accordion title="Meta広告のユーザーレベルのデータは、どのくらいの期間保持されますか？">

Meta広告は、アトリビューションプロバイダーに対し、インストールから6か月後にユーザーレベルのデータを削除するよう求めています。そのため、これらのユーザーがアプリのインストールから6か月後に行ったイベントは、オーガニックとしてカウントされます。  
過去の集計データは変わりません。  
これは、Meta広告のすべてのチャネル（Facebookアプリ、Instagram、Messenger、AudienceNetwork）に適用されます。

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-meta-ads" />

<Accordion title="Meta広告は、iOSのユニバーサルリンクとAndroidのアプリリンクに対応していますか？">

iOSのユニバーサルリンクとAndroidのアプリリンクはサポートされており、Meta広告で使用できます。詳細は、<Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">Metaヘルプセンター</Anchor>を参照してください。

* カタログを使用しない静的広告では、iOSのユニバーサルリンクとAndroidのアプリリンクは、遷移先として<strong>［アプリ］</strong>を選択したキャンペーンでのみサポートされます。
* ダイナミック広告では、[こちら](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads)の説明に従って、iOSのユニバーサルリンク、Androidのアプリリンク、URIスキームを使用できます。

**注意：** iOSのユニバーサルリンクとAndroidのアプリリンクは、有料広告でのみサポートされます。

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content" />

<Accordion title="Metaの広告以外のコンテンツでも、iOSのユニバーサルリンクとAndroidのアプリリンクはサポートされていますか？">

iOSのユニバーサルリンクとAndroidのアプリリンクは、有料広告でのみサポートされます。ソーシャルアプリの広告以外のコンテンツでは、ユーザーをリダイレクトまたはディープリンクで誘導するために、ソーシャルアプリ向けランディングページやURIスキームの設定が必要になる場合があります。

</Accordion>

<div id="aem-attribution-is-not-working" />

<Accordion title="AEMによるアトリビューションが機能しません">

<strong>［拡張データ共有］</strong>がオンになっているにもかかわらずMeta広告へのアトリビューションが発生しない場合は、共有しているイベントがMetaの利用要件を満たしているか確認してください。 [Metaのドキュメント](https://www.facebook.com/business/help/716239976391518?id=1877298665783613)を参照してください。

</Accordion>

<div id="can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads" />

<Accordion title="ダイナミック商品広告で、アプリの起動やディープリンクにOneLinkを使用できますか？">

はい。アプリリンク、ユニバーサルリンク、URIスキームのいずれかを設定したOneLinkは、ダイナミック商品広告で使用できます。ダイナミック広告に使用するカタログのデータフィードで、**applink.ios\_url**と**applink.android\_url**の各フィールドにOneLinkを指定できます。

</Accordion>

<div id="conversion-events-are-not-sent-to-meta-ads" />

<Accordion title="コンバージョンイベントがMeta広告に送信されません">

アトリビューションが含まれないZeroパッケージを利用している可能性があります。

</Accordion>

<div id="can-i-use-get" />

<Accordion title="Get Conversion Data（GCD）でMetaのコンバージョンデータを取得できますか？">

<strong>はい。</strong>アプリの設定とAMMの同意状況に応じて、引き続き**GCD**でMetaのコンバージョンデータを取得できます。

* **Facebook SDKをアプリに実装している場合：**

  <Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#deferred-deep-linking">ディファードディープリンク（DDL）のドキュメント</Anchor>で説明されているとおり、DDLデータを取得し、GCDを介して利用できます。
* **Facebook SDKをアプリに実装していない場合：**

  <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#meta-ads">Advanced Mobile Measurement（AMM）に同意している</Anchor>場合は、GCDで**キャンペーン名、広告セット名、広告名**を取得できます。この場合、取得した値を使って、独自の**ディープリンク処理**を実装できます。

<div id="note" />

> 📘 **注意**
>
> Metaのデータ共有ポリシーにより、GCDで取得できる情報の詳細度が変わる場合があります。取得できるキャンペーンレベルのデータを最大限に利用するため、AMMへの同意が完了していることを確認してください。

</Accordion>

<div id="meta-ads-cost-faq" />

## Meta広告のコストに関するよくある質問

<div id="getting-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="AppsFlyerのダッシュボードでのMeta広告のコストデータの取得">

AppsFlyerは、過去7日間に1件以上のインストールが発生したMeta広告キャンペーンから、広告費データ（クリックとインプレッションを含む）を取得します。

Meta広告キャンペーンが複数のプラットフォーム（Android、iOS、デスクトップなど）にまたがる場合、ダッシュボードのコストはプラットフォーム別に表示され、その金額はMeta広告が算出します。

<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta広告のクリック、インプレッション、コストの取得</Anchor>を参照してください。

</Accordion>

<div id="facebook-cost-example" />

<Accordion title="Meta広告のコストの例">

ある広告主がMeta広告でキャンペーンを実施しています。 AppsFlyerでは、次のように表示されます。

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/a1aa5847db5c0b873b34b1d4de43ade7d4109608371e05a84342122e56d0ce08-4411031032081.png" />

コスト情報は、Meta広告からAppsFlyerに提供されます。**インストール**数は、AppsFlyerが自社のアトリビューションルールに従って算出します。そのため、通常、Meta広告とAppsFlyerで算出されるeCPIは異なります。

</Accordion>

<div id="i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="過去のMeta広告のコストデータがAppsFlyerのダッシュボードに表示されません">

前述のMeta広告管理者アカウントで初めてログインすると、AppsFlyerは既存のキャンペーンについて、最大7日前までさかのぼってMeta広告のコストデータを取得します。それ以前のコストデータは取得できません。

その後の同期でも、AppsFlyerは過去7日間のデータを取得します。つまり、過去7日間に1件以上のコンバージョンが発生したすべてのキャンペーンについて、コスト、クリック、インプレッションのデータが収集されます。

</Accordion>

<div id="can-i-stop-cost-data-sync" />

<Accordion title="コストデータの同期を停止できますか？">

Meta広告とのコストデータの同期を停止するには、<Anchor target="_blank" href="https://www.facebook.com/help/405094243235242">Meta広告アカウントの［ビジネス統合］からAppsFlyerを削除してください</Anchor>。

</Accordion>

<div id="cost-data-was-fine-for-a-few-months-but-it-stopped-displaying" />

<Accordion title="数か月間はコストデータが表示されていましたが、表示されなくなりました">

Meta広告が、コストデータの取得権限を数か月ごとにリセットする場合があります。ダッシュボードにコストデータが表示されなくなった場合は、Meta広告の管理者アカウントで再度ログインしてください。

Meta広告の管理者がパスワードを変更した場合も、再度ログインする必要があります。

</Accordion>

<div id="i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer" />

<Accordion title="5分前にFacebook広告をクリックしました。 AppsFlyerにクリックが表示されないのはなぜですか？">

AppsFlyerは、クリック、インプレッション、コストの集計データをMeta広告から数時間ごとに取得します。そのため、これらのデータがAppsFlyerのダッシュボードに表示されるまで、数時間かかる場合があります。

</Accordion>

<div id="can-i-get-raw-data-on-clicks-and-impressions-from-facebook" />

<Accordion title="Meta広告のクリックやインプレッションのローデータを取得できますか？">

AppsFlyerはMeta広告からクリックとインプレッションの集計データのみを取得するため、すべてのクリックやインプレッションのローデータを取得することはできません。ローデータレポートで取得できるのは、インストールにつながったクリックとインプレッションのみです。

</Accordion>

<div id="are-there-limitations-of-facebook-cost-data-by-geo" />

<Accordion title="地域別のMeta広告のコストデータには制限がありますか？">

AppsFlyerのダッシュボードで地域を絞り込むと、Meta広告のコストデータの合計と内訳を確認できます。

このデータは、Meta広告の「モバイルアプリインストールキャンペーン」でのみ利用できます。

また、地域別のコストデータは、単一のプラットフォームを対象とするキャンペーンでのみ利用できます。つまり、Android向けとiOS向けの広告セットが同じキャンペーンに含まれる場合、地域別のコストデータは取得できません。**コストデータを漏れなく取得するには、プラットフォームごとにキャンペーンを分けてください**。

</Accordion>

<div id="what-are-the-limitations-of-facebook-cost-data-in-master-api" />

<Accordion title="Master APIで取得するMeta広告のコストデータには、どのような制限がありますか？">

Meta広告は、<Anchor target="_blank" href="/marketers/ja/docs/master-api-user-acquisition-metrics-via-api">Master APIレポート</Anchor>でコストデータを地域とチャネルの両方で同時にグループ化することに対応していません。

コストデータを漏れなく含むレポートを作成するには、いずれか一方のディメンションのみでグループ化してください。

</Accordion>

<div id="the-total-cost-doesnt-match" />

<Accordion title="MetaとAppsFlyerでコストの合計が一致しないのはなぜですか？">

Meta広告とAppsFlyerでは、アトリビューションモデルが異なります。この違いにより、Meta広告のコストデータに次のような乖離が生じる場合があります。

* **Meta広告のクロスデバイスアトリビューション：** あるプラットフォーム（iOSまたはAndroid）向けのキャンペーンに、別のプラットフォームのインストールとそのコストが表示される場合があります。
* **Meta広告のモバイル以外を対象としたキャンペーン：** リンククリックキャンペーンなどでは、デスクトップのユーザーが後からモバイルアプリをインストールすることがあります。こうしたクロスデバイスキャンペーンのコストは、AppsFlyerには表示されません。ただし、リンクをクリックしたデバイスとアプリをインストールしたデバイスが同じ場合は、コストデータを取得します。  
  たとえば、Facebookのユーザーがデスクトップで広告をクリックし、広告主のランディングページに移動します。その1週間後、同じユーザーがiPhoneに広告主のiOSアプリをインストールします。このインストールはアトリビューションされ、AppsFlyerのダッシュボードに表示されますが、クロスプラットフォームで発生したこのインストールのコストは表示されません。
* **過去7日間に成果が0件のキャンペーン**：AppsFlyerは、過去7日間にインストールまたはコンバージョンが発生したキャンペーンのコストのみを同期します。 Meta広告のコスト連携を設定したばかりの場合、それ以前に7日間を超えて稼働していなかったキャンペーンのコストは表示されません。
* **削除またはアーカイブされた広告**：これらの広告のコストはMetaからAppsFlyerには報告されませんが、Metaのダッシュボードには反映されます。そのため、キャンペーン単位でデータを比較すると、MetaとAppsFlyerのレポート間で乖離が生じる場合があります。

</Accordion>

<div id="why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical" />

<Accordion title="コストの合計が同じなのに、AppsFlyerとMeta広告でeCPIが異なるのはなぜですか？">

インストール単価は、コストの合計をインストール数で割って算出します。 <Anchor target="_blank" href="/marketers/ja/docs/meta-ads-discrepancies">AppsFlyerとMeta広告ではインストールのカウント方法が異なる</Anchor>ため、通常、両者のeCPIも異なります。

</Accordion>

<div id="why-doesnt-cost-data-include-data-from-all-campaigns" />

<Accordion title="コストデータにすべてのキャンペーンが含まれないのはなぜですか？">

前述のMeta広告へのログインを行ったユーザーに、一部の実施中キャンペーンへのアクセス権がない場合、キャンペーン自体はAppsFlyerのダッシュボードに表示されても、コスト、クリック、インプレッションのデータの一部が欠落します。

**注意：** Metaビジネスマネージャで複数のユーザーにキャンペーンの運用権限があっても、Meta広告へのログインを行う必要があるのは1人だけです。

</Accordion>

<div id="is-facebook-cost-data-displayed-for-retargeting-campaigns" />

<Accordion title="リターゲティングキャンペーンのMeta広告のコストデータは表示されますか？">

リターゲティングキャンペーンのコストとROIのデータは、<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">コホートレポート</Anchor>の**統合**ビューで確認できます。

</Accordion>

<div id="why-does-the-facebook-cost-configuration-window-close-before-login" />

<Accordion title="Meta広告のコスト設定ウィンドウが、ログインする前に閉じるのはなぜですか？">

設定を行っているブラウザですでにMeta広告にログインしている場合、その認証情報を使って自動的に接続します。すでにAppsFlyerにアクセス権を付与している場合は、追加の操作が不要なため、ウィンドウが閉じます。

</Accordion>

<div id="why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store" />

<Accordion title="Amazonアプリストアのアプリでコストデータに乖離が生じるのはなぜですか？">

AppsFlyerとは異なり、Meta広告は、Androidアプリと、AndroidをベースとするAmazonアプリのコストデータを区別しません。そのため、Amazonユーザーのコストデータが、本来のAmazon向けキャンペーンではなく、他のAndroidユーザー向けキャンペーンに割り当てられる場合があります。

</Accordion>

<div id="how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked" />

<Accordion title="以前のMeta広告アカウントが連携されている状態で、新しい広告アカウントのコストデータを連携するにはどうすればよいですか？">

新しい広告アカウントに切り替えたい場合、以前のアカウントがAppsFlyerのMeta広告コスト連携に接続されていれば、Meta広告側でその接続を解除してから、AppsFlyerで新しい広告アカウントを接続する必要があります。

1. Meta広告で<strong>［設定］</strong>><strong>［ビジネス統合］</strong>に移動します。
2. <strong>［アクティブ］</strong>タブで、AppsFlyerの連携を削除します。  

   <Image align="center" alt="" src="https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png" />
3. AppsFlyerのダッシュボードに移動し、新しい広告アカウントのコストを接続します。

</Accordion>

<div id="facebook-sdk-faq" />

## Facebook SDKに関するよくある質問

<div id="who-needs-facebooks-sdk" />

<Accordion title="Facebook SDKが必要なのはどのような場合ですか？">

AppsFlyer SDKを導入する前から、Facebook SDKをアプリに実装している場合もあります。実装していない場合も、AppsFlyer SDKに加えてFacebook SDKが必要かどうか疑問に思うかもしれません。また、両方が必要な場合、二重報告を発生させずに併用できるのでしょうか。

以下の用途では、Facebook SDKは必要ありません。

* **ユーザー獲得**：通常、AppsFlyer SDKだけで、Meta広告経由のユーザーのエンゲージメント、インストール、セッション、インストール後のイベントを含む、モバイルユーザー獲得のアトリビューションに対応できます。
* **ディープリンク**：リンクのクリック時にアプリを開き、特定のアプリ内ページや機能にユーザーを誘導するには、Facebook SDKを使用せずにOneLinkを利用できます。この用途には、iOSのユニバーサルリンク、Androidのアプリリンク、URIスキームを使用できます。詳細は、<Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">Metaヘルプセンター</Anchor>を参照してください。  

  **注意：**  
  カタログを使用しない静的広告では、iOSのユニバーサルリンクとAndroidのアプリリンクは、遷移先として<strong>［アプリ］</strong>を選択したキャンペーンでのみサポートされます。  
  たとえば、Metaの認知度キャンペーンでは遷移先に<strong>［アプリ］</strong>を選択できないため、iOSのユニバーサルリンクとAndroidのアプリリンクはサポートされません。  

  ダイナミック広告では、[こちら](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads)の説明に従って、iOSのユニバーサルリンク、Androidのアプリリンク、URIスキームを使用できます。  

  Meta広告はOneLink URLの情報を取得し、その情報を基にMeta広告用のアプリリンクを作成して、アプリの起動とアプリ内へのディープリンクを行います。

以下の用途では、AppsFlyer SDKに加えてFacebook SDKが必要です。

* **ディファードディープリンク**：  
  Meta広告のDDL値は、コンバージョンデータでは取得できません。このデータの取得にはMetaとの調整が必要であり、通常はFacebook SDKが必要です。
* **ダイナミック商品広告キャンペーンのデータ**：ダイナミック商品広告のデータは、Facebook SDKからのみ取得できます。
* **Meta広告のその他の機能**：認証、広告マネタイズ、ソーシャルシェア、ユーザー招待など、アトリビューション以外の用途でFacebook SDKが必要になる場合があります。

<div id="note-1" />

> 📘 **注意**
>
> ディープリンクとディファードディープリンクに関する上記の説明と推奨事項は、Meta広告のデモ・プレビューツールを使用した詳細なテストに基づいています。これらのツールは、実際に配信される広告とは異なる仕組みを使用します。

</Accordion>

<div id="avoiding-duplicates-with-facebook-sdk" />

<Accordion title="Facebook SDKとの併用時の重複の回避">

アプリに<Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#faq_593792547454717">AppsFlyer SDKとFacebook SDKの両方を実装している</Anchor>場合、インストールとアプリ内イベントはFacebook SDKから報告され、さらにAppsFlyerからもMeta広告のサーバーにポストバックで報告されます。この二重報告を回避するには、どうすればよいですか？

* **インストール**については、Metaが重複を排除します。そのため、**重複は発生せず**、各インストールは1回だけカウントされます。
* **アプリ内イベント**については、Meta広告が重複を排除しないため、二重カウントや不正確なレポートにつながる可能性があります。 Meta広告でのこうした重複を避けるには、以下のいずれかを検討してください。
  * Facebook SDKでイベントを設定しないようにします。
  * Androidの場合は、AppsFlyer側で<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-in-app-event-mapping">Meta広告へのアプリ内イベントのマッピング</Anchor>を無効にします。  
    iOS 14.5以降でSKANアトリビューションを有効にするには、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-interoperation-with-meta-ads#in-app-event-mapping">Meta広告へのアプリ内イベントのマッピング</Anchor>が必要です。

</Accordion>

<div id="meta-ads-attribution-faq" />

## Meta広告のアトリビューションに関するよくある質問

<div id="attributing-agencies-with-facebook" />

<Accordion title="Meta広告での代理店へのアトリビューション">

代理店やMetaキャンペーン管理パートナーは、AppsFlyer上で、広告主に代わってMeta広告キャンペーンを運用し、アトリビューションを行えます。また、広告主自身が運用するMeta広告キャンペーンと並行して実施することもできます。代理店のキャンペーンを代理店にアトリビューションするには、キャンペーン名の先頭に必ず代理店名を付ける必要があります。

iOS 14ユーザーについては、特定の広告アカウントでキャンペーンを運用できる代理店は**1社のみ**です。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-interoperation-with-meta-ads#skan連携--appsflyer---meta-ads">Meta広告とAppsFlyerのSKAdNetwork連携</Anchor>を参照してください。

代理店とMeta広告のインストールアトリビューションについては、<Anchor target="_blank" href="/partners/ja/docs/about-agency-accounts#srn-構成">こちら</Anchor>を参照してください。

また、**代理店はMeta広告のルックバック期間やリターゲティング設定を変更できません**。変更が必要な場合は、広告主に対応を依頼する必要があります。

さらに、代理店はMeta広告に送信されるアプリ内イベントポストバックも変更できません。これは、代理店が獲得したとは限らない、Meta広告にアトリビューションされていないインストールも含め、すべてのインストール情報を受信することをMeta広告が要件としているためです。

以下の画像は、代理店がMeta広告キャンペーンを管理できるようにするために、広告主が設定する必要のある項目を示しています。

<Image align="center" alt="advertiser-vs-agency-facebook-int-new.png" src="https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png" />

</Accordion>

<div id="attribution-for-facebook-for-outofstore-android-apps" />

<Accordion title="Google Play以外のストアで配信するAndroidアプリのMeta広告アトリビューション">

Meta広告では、BaiduなどのGoogle Play以外のストアで配信するAndroidアプリについて、モバイルアプリインストールキャンペーンを作成できません。

ただし、以下の手順に従えば、こうしたアプリもMeta広告で宣伝し、インストールを記録できます。

1. 開発者は、アプリの広告配信に使用するストアごとに、個別のAPKを用意する必要があります。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">こちら</Anchor>を参照してください。
2. Meta広告で、モバイルアプリの計測を有効にした<strong>［トラフィック］</strong>または<strong>［コンバージョン］</strong>キャンペーンを作成し、見込みユーザーをランディングページに誘導します。
3. ランディングページには、APKを配信しているストアに直接リンクする<strong>［アプリをダウンロード］</strong>ボタンを配置します。
4. 見込みユーザーがボタンをクリックすると、対象のストアにリダイレクトされます。インストールが完了すると、AppsFlyerはMMP APIを介して、そのユーザーをMeta広告にアトリビューションします。

<div id="note-2" />

> 📘 **注意**
>
> この方法は、ストアへリダイレクトする前に<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">ランディングページを経由する必要があるGoogle</Anchor> PlayやApp Storeのアプリにも適用できます。

Amazonのアプリのアトリビューションに関する具体的な手順は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#driving-users-to-the-amazon-app-store-from-facebook">こちら</Anchor>を参照してください。

</Accordion>

<div id="what-is-facebook-android-and-ios-crossattribution" />

<Accordion title="Meta広告のAndroidとiOS間のクロスアトリビューションとは何ですか？">

Meta広告は、Meta広告アカウントを基にユーザーを識別します。同じMeta広告アカウントに、iOSとAndroidの両方のデバイスを関連付けているユーザーもいます。

こうしたユーザーがAndroidデバイスでアプリの広告をクリックまたは閲覧し、iOSデバイスにアプリをインストールした場合、Meta広告はそのインストールを自社の成果と見なします。その結果、iOSのダッシュボードにAndroid向けキャンペーンの名前が表示されます。

<div id="example" />

> 📄 **例**
>
> Andrew JosefがAndroidデバイスを使用しています。その際、MetaのAndroid向けキャンペーンで配信された**Bubbles**というアプリの広告をクリックします。ただし、アプリはダウンロードしません。
>
> 翌日、Andrew JosefはiOSデバイスで**Bubbles**をオーガニックでダウンロードし、起動します。
>
> この場合、AppsFlyerはMeta広告からAndroid向けキャンペーンの情報を受け取り、Andrew Josefがダウンロードと起動を行ったiOSのダッシュボードに表示します。

</Accordion>

<div id="what-are-facebook-ads-channels" />

<Accordion title="Meta広告のチャネルとは何ですか？">

Meta広告では、キャンペーン、広告セット、広告だけでなく、Meta広告のチャネル（配置）別にデータを確認できます。

* **Facebook**：Facebookアプリ経由のユーザー
* **Instagram**：Instagramアプリ経由のユーザー
* **Messenger**：Facebook Messengerアプリ経由のユーザー
* **AudienceNetwork**：Meta広告のネットワークに属する、または提携する他のアプリ経由のユーザー
* **Threads**：Threadsアプリ経由のユーザー
* **WhatsApp**：WhatsAppアプリ経由のユーザー

このデータを使って、チャネルごとに獲得したユーザーの質を比較できます。

<Image align="center" alt="Facebook_channels.png" src="https://files.readme.io/f6b51baf3056f42ee32ac9709b1e4b3661580ce6148acfa36fc2bad102e7bfd8-4411036713745.png" />

</Accordion>

<div data-zendesk-anchors="facebook-ads-faq=meta%E5%BA%83%E5%91%8A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HD1JTW2EP1MY3DD9136E9CHC=meta%E5%BA%83%E5%91%8A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HD1JTW2EN36V9SHH11283Y3A=i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard h_01HD1JTW2EJE0K034KSV8B3WZQ=can-appsflyer-show-the-campaign-level-and-ad-groups h_01HD1JTW2EFKCJMNBXBK2C55DN=is-facebook-data-shown-in-realtime h_01HD1JTW2E4SVC1Z9C3K6XJB2G=when-can-i-see-a-new-campaigns-data-on-appsflyer h_01HD1JTW2ECWSXFKQC1YBP1592=how-can-i-get-more-installs-from-facebook h_01K8B4YFDKKYP25V6NR12CE9RF=how-can-i-get-device-level h_google_play_referrer=google-play-install-referrer-api h_meta_install_referrer=meta%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9 meta-install-referrer=meta%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AA%E3%83%95%E3%82%A1%E3%83%A9 h_attribution_fields=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E9%A0%85%E7%9B%AE campaign-attribution-fields=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E9%A0%85%E7%9B%AE h_sdk_requirements=sdk%E3%81%A8%E8%A8%AD%E5%AE%9A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 sdk-requirements=sdk%E3%81%A8%E8%A8%AD%E5%AE%9A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 h_decryption=%E5%BE%A9%E5%8F%B7%E3%82%AD%E3%83%BC%E3%81%AE%E7%99%BB%E9%8C%B2 decryption-key=%E5%BE%A9%E5%8F%B7%E3%82%AD%E3%83%BC%E3%81%AE%E7%99%BB%E9%8C%B2 h_01HD1JTW2ED762B3K1QS6QC38M=do-you-make-facebook-raw-data-available-to-agencies h_01HD1JTW2EWQGK4QA9W8DFZTMH=i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports h_01HD1JTW2EYSBJ38WNS1HP5MCE=any-specific-columns-for-facebook-in-appsflyers-performance-reports h_01HD1JTW2ETTXQAP7ZSTMVGA8K=can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer h_01HD1JTW2EPY8W5Z84PBWSM86G=what-should-i-do-when-i-receive-the-following-warning h_01HD1JTW2ED2DNPTXAFYJTTGV3=what-happens-with-different-lookback-windows-than-on-facebook h_01HD1JTW2EXF1R0MA91ZSW7QG4=what-are-the-facebook-api-parameters how-long-do-you-keep-facebook%E2%80%99s-userlevel-data=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EPDNSY30J45JB443A=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EN8THFCRNZ0EBQ2M3=are-ios-universal-links-and-android-app-links-supported-in-meta-ads h_01JJVVX9NCSTVQKG2ENTGDRDK9=are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content 01H7YJVNMVBRVTT9HH7KM8P33B=aem-attribution-is-not-working h_01HD1JTW2ETG739TWQVTKPCM2R=can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads h_01JTG2474VHWAD8EK8ASPWZY0W=conversion-events-are-not-sent-to-meta-ads h_01K8B4AKSHSMP18MM0GAAZEQMF=can-i-use-get h_01K8B4AKSH7E8TBEG024NAV1A5=%E6%B3%A8%E6%84%8F facebook-ads-cost-faq=meta%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HD1JTW2EEVD1PDPFW15K45CE=meta%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HD1JTW2EE0WQ90J431Z8NQ8Q=getting-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2ESVMMPK32W34PA54T=facebook-cost-example h_01HD1JTW2EVFXAET26WK2KSHTV=i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2EJQHKVJF4XHWGVASJ=can-i-stop-cost-data-sync h_01HD1JTW2EYJTA2TRY7EE75KXA=cost-data-was-fine-for-a-few-months-but-it-stopped-displaying h_01HD1JTW2EYXZW2QCMQH5CRFSK=i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer h_01HD1JTW2EYE2ZDNVRT5BCRXZJ=can-i-get-raw-data-on-clicks-and-impressions-from-facebook h_01HD1JTW2EG11RRBYHJ5BMJM5M=are-there-limitations-of-facebook-cost-data-by-geo h_01HD1JTW2E3RMV2TMPNZZ86HG5=what-are-the-limitations-of-facebook-cost-data-in-master-api h_01HD1JTW2EKVSAQ3706NC8JV9M=the-total-cost-doesnt-match h_01HD1JTW2EMJQJHBBB9SRJ6MZN=why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical h_01HD1JTW2E2S79FC9VAHA12X93=why-doesnt-cost-data-include-data-from-all-campaigns h_01HD1JTW2ET6Y2EHG29AQS09NA=is-facebook-cost-data-displayed-for-retargeting-campaigns h_01HD1JTW2EXTS1GDZHN8PAMV8C=why-does-the-facebook-cost-configuration-window-close-before-login h_01HD1JTW2FC0NJK00HZ76SFH30=why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store how-to-connect-cost-data-of%C2%A0a-new-facebook-ad-account-while-my-old-account-is-linked=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked h_01HD1JTW2F401DA2NHBSPTKATB=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked facebook-ads-sdk-faq=facebook-sdk%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HD1JTW2FPRCVGBF7CG7ZMKXF=facebook-sdk%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HD1JTW2F03XQSEVTFBW8JCX3=who-needs-facebooks-sdk h_01HD1JTW2FB09HM2CC83GMT901=%E6%B3%A8%E6%84%8F-1 h_01HD1JTW2FNNHPZQARZNCCP7ER=avoiding-duplicates-with-facebook-sdk facebook-ads-attribution-faq=meta%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HD1JTW2F2JV2BMDS40HFG6K0=meta%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HD1JTW2FK1ZTPTA8B8A4N64Z=attributing-agencies-with-facebook h_01HD1JTW2F63AT1NGBY96Y6CCE=attribution-for-facebook-for-outofstore-android-apps h_01HD1JTW2FMKYDHNSM7G182EY0=%E6%B3%A8%E6%84%8F-2 h_01HD1JTW2F8JT69CSN04GCZ91V=what-is-facebook-android-and-ios-crossattribution h_01HD1JTW2F5PY7A8T5NMHBZ87B=%E4%BE%8B h_01HD1JTW2FX3QWC9BKWQ65E5B8=what-are-facebook-ads-channels" />
