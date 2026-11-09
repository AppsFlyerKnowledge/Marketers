---
title: Meta AdsとのSKAN連携
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-01-17T10:08:28Z'
  edited_at: '2026-10-29T04:33:47Z'
  id: 360017095198
  locale: ja
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ja/articles/360017095198
---
> **概要：** 連携を有効にすると、Meta AdsからAppsFlyerへデコード済みのSKANデータを共有し、AppsFlyerからMeta Adsへコンバージョン値（CV）の計測ビットの割り当て（マッピング）を共有できます。

<Embed title="Meta AdsとのSKAN連携" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/15jnbml3h7" providerUrl="https://fast.wistia.com" />

<div id="skan-interoperability-appsflyer---meta-ads" />

## SKAN連携 ｜ AppsFlyer &lt;-> Meta Ads

複数のアドネットワークパートナーと連携する場合は、AppsFlyerで設定することをおすすめします。これにより、AppsFlyer上でSKANのパフォーマンス指標をコストなどの指標とあわせて確認できます。

<div id="scope-of-skan-interoperability-with-meta-ads" />

#### Meta AdsとのSKAN連携でできること

Meta Adsとの連携により、次のことが可能になります。

* AppsFlyerとMeta AdsでSKANのコンバージョン値（CV）の設定ルールを共有し、両方のプラットフォームでパフォーマンス指標を確認できます。
* AppsFlyerは、キャンペーンの最適化に使用する次のすべてのMeta Adsキャンペーン目的に対応しています。
  * モバイルアプリのインストール（MAI）
  * モバイルアプリのエンゲージメント（MAE）
  * バリュー最適化（VO）
* SKAN連携を有効にすると、次の処理が行われます。
  * Facebook SDKによるSKANのCVの更新が停止します（*キルスイッチ*）。
  * AppsFlyer SDKがCVを更新します。
  * Meta AdsからSKANポストバックデータが共有され、SKANダッシュボードと集計レポートに反映されます。

その他の注意点：

* SKANのパートナー連携を有効にしない場合、Meta Ads経由のインストールは、SKANダッシュボードでオーガニックインストールとしてカウントされます。
* AppsFlyerのアトリビューション（オーバービューダッシュボード）では、次のように扱われます。
  * 同意を得ているユーザーのMeta Ads経由のインストールは、正しくアトリビューションされます。
  * 同意を得ていないユーザーのインストールは、オーガニックとして扱われます。
* <Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#ios-145-srn-attribution">iOS 14.5がSRNのレポートに与える影響</Anchor>
* AppsFlyerとMeta AdsのMMP連携では、常に*Advertiser Tracking Enabled*フラグが実装されています。（この情報は、2021年2月のMeta Adsのアプリ向けガイダンスに掲載されたiOS 14チェックリストに基づいています。）

<div id="considerations" />

#### 考慮事項

* 一度連携を有効にすれば、計測設定を変更するたびに、この記事のMMP連携手順を繰り返す必要はありません。MMP接続URLを再度コピーする必要はありません。
* AppsFlyerでSKAN計測をオフにすると、Meta AdsはCVのマッピングを取得できなくなります。
* AppsFlyer SDKとFacebook SDKの比較：Meta Adsのみでキャンペーンを配信する場合は、Facebook SDKが適しています。複数のパートナーでキャンペーンを配信する場合は、AppsFlyer SDKを使用すると、すべてのパートナーのデータを確認できます。
* この記事の[データの差異](/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq)に関するセクションを確認してください。

<div id="meta-ads-app-install-ads-guidance" />

#### Meta Adsのアプリインストール広告に関するガイダンス

Meta AdsでiOS 14向けのアプリインストールキャンペーンを設定する際は、次の<Anchor target="_blank" href="https://developers.facebook.com/blog/post/2020/10/29/preparing-our-partners-ios-14-latest-guidance-on-skadnetwork/">Meta Adsのガイダンス</Anchor>を確認してください。

* アプリごとに最大18件のキャンペーンを作成でき、各キャンペーンには5件の広告セットを設定できます。
* iOS 14キャンペーン用に別のアカウントを用意する必要はありません。既存のアカウントからiOS 14キャンペーンを配信できます。
* Meta Adsの最適化方法と、AppsFlyerで選択する計測タイプは、次のように対応しています。
  * **収益計測**：バリュー最適化（VO）とアプリイベント最適化（AEO）
  * **コンバージョン計測**：アプリイベント最適化（AEO）。Meta Adsの標準イベントと購入イベントが含まれます。AppsFlyerのアプリ内イベントを、対応するMeta Adsイベントにマッピングする必要があります。

<div id="interoperation-procedures" />

## 連携手順

連携を有効にするには、次の手順を行ってください。

アプリインストールのアトリビューション：

<div id="allow-facebook-to-share-skadnetwork-data-with-appsflyer" />

<Accordion title="Meta AdsからAppsFlyerへのSKANデータの共有を許可">

Meta AdsからAppsFlyerへのSKANデータの共有を許可します。共有を許可しないと、Meta AdsにアトリビューションされたSKANインストールが、AppsFlyerのSKANダッシュボードに表示されません。

この手順は、アプリごとに1回行う必要があります。

**Meta AdsからAppsFlyerへのSKANデータの共有を許可するには、次の手順を行います。**

1. AppsFlyerで、［**コラボレーション］>［パートナー連携］>［連携済みパートナー**］に移動します。
2. Meta Adsを検索して選択します。
3. ［**SKAN**］タブに移動します。

   <Image align="center" alt="skan_repprtiing_-_connected_accounts.png" src="https://files.readme.io/41514c220de398871292c990e448e2bc8ce450a17512649842cdb2bc4fd78846-40032591356817.png" />
4. ［**f login**］をクリックします。使用するアカウントは、<Anchor target="_blank" href="https://www.facebook.com/business/help/155909647811305?id=829106167281625">次の権限を持つ</Anchor>管理者アカウントまたは広告主アカウントである必要があります。
   * ads\_read権限。[ads\_read権限の確認方法](/docs/skadnetwork-skan-interoperation-with-meta-ads#verifying-the-ads_read-permission)を参照してください。
   * Meta Business Partnerの設定で、広告対象のアプリIDにアクセスする権限
5. 画面の指示に従って操作します。  
   Metaが、AppsFlyerとのデータ共有を許可する<Anchor target="_blank" href="https://developers.facebook.com/docs/facebook-login/guides/access-tokens/get-long-lived/">アクセストークン</Anchor>を生成します。操作が完了すると、AppsFlyerの画面に戻ります。
6. 初めて連携を設定する場合は、アカウントのステータスに［**同期待ち（Waiting for sync）**］と表示されることを確認します。  
   このメッセージは、AppsFlyerがMeta Adsからデータを受信するまで表示されます。
7. 翌日の02:00 UTCを過ぎてから、ステータスが［**データを正常に取得しました（Data was pulled successfully）**］に変わったことを確認します。  
   SKANダッシュボードのデータは、毎日08:00 UTCまでに更新されます。
8. [計測の差異](/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook)に関するセクションを確認してください。

</Accordion>

アプリ内イベントのアトリビューション：

<div id="share-cv-schema-with-facebook" />

<Accordion title="Meta AdsとのCVの設定ルールの共有">

<Image align="center" alt="SKAdNetwork-Facebook-AppsFlyer_integration__5_.png" src="https://files.readme.io/f5965dc535a47b3d665a3cf1ae1df564a176ff9be76d5fb4a9f01d80b0e58994-40032652599953.png" />

<div id="enabling-appsflyer-skan-interoperation-with-meta-ads" />

#### AppsFlyerのSKANとMeta Adsの連携の有効化

<Table>
  <thead>
    <tr>
      <th>
        ステップ
      </th>
      <th>
        作業
      </th>
      <th>
        詳細
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="1"></span>
        1
      </td>
      <td>
        アプリの前提条件
      </td>
      <td>
        * 最新のAppsFlyer <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">SDK</Anchor>をアプリに実装します。
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        SKAN設定の確認
      </td>
      <td>
        AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKANソリューション</Anchor>の設定が完了し、有効になっていることを確認します。これにより、AppsFlyer SDKからSKAN APIを呼び出し、CVを設定できるようになります。

        **SKAN設定を表示するには、次の手順を行います。**

        1. AppsFlyerで、［**設定**］>［**SKAN Conversion Studio**］に移動します。
        2. オプション（⋮）アイコンをクリックし、［**SKAN計測**］がオンになっていることを確認します。  
           [![Measurement_mode_on_facebook_ads.png](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)
        3. 使用する計測モードを選択します。  
           詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>を参照してください。
        4. 設定したイベント名を、表記を変えずに正確に控えておきます。次のステップで使用します。**注意：** イベント名では大文字と小文字が区別されます。
      </td>
    </tr>
    <tr>
      <td><span id="in-app-event-mapping"></span>
        3
      </td>
      <td>
        アプリ内イベントのマッピング
      </td>
      <td>
        アプリ内イベントのマッピングを確認し、必要に応じて変更します。

        **アプリ内イベントのマッピングを確認・設定するには、次の手順を行います。**

        1. AppsFlyerで、［**コラボレーション］>［パートナー連携］>［連携済みパートナー**］に移動します。
        2. ［**Meta Ads**］を選択します。
        3. ［必須］［**連携**］タブで、［**アプリ内イベントポストバック**］をオンにします。
           * 現在選択しているSKAN計測タイプに対応するマッピングを設定する必要があります。デフォルトの計測タイプは収益です。  
             ![in-app_events_fb_en-us.png](https://files.readme.io/98e2c8048444331c5d24343e683605e8388ee93bbfcb70aa5e8dad183c995859-40032591364241.png)
           * SKAN計測で設定したアプリ内イベント（［**AppsFlyerイベント**］）が、Meta Adsのイベント識別子（［**パートナー側のイベント名／ID**］）にマッピングされていることを確認します。イベントをマッピングしないと、Meta Adsでは最適化が行えず、インストール数のみがカウントされます。

             <div id="h_01H8XRMVR5GY77K7GJ4TXGWEHS" />

             > 📘 **注意**
             >
             > SKAN Conversion Studioでコンバージョン値（CV）を追加・変更・削除する際は、対象のイベントが［**アプリ内イベントポストバック**］でマッピングされていることを確認してください。マッピングされていない場合、Meta AdsでCVが更新されません。
             >
             > #### <span id="inapp-event-mapping-guide"></span>アプリ内イベントのマッピングガイド


        | 計測タイプ | 必要なマッピング |
        | --- | --- |
        | <span id="custom"></span><Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#custom">カスタム</Anchor> | ［カスタム］で設定したアプリ内イベントを、対応するMeta Adsイベントにマッピングします。<br /><br />ポストバックで収益をレポートするには、［**収益の送信**］を［**値と収益**］に設定する必要があります。<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />収益全体の計測には*af\_skad\_revenue*を使用し、Meta Adsの収益イベント（通常は*fb\_mobile\_purchase*）にマッピングします。<br /><br />注意：複数のイベントを*fb\_mobile\_purchase*にマッピングしても問題ありません。 |
        | <span id="revenue"></span>収益 | アドネットワークへポストバックで収益をレポートする場合は、アプリ内イベントポストバックのマッピングに、設定したアプリ内収益イベントが含まれていることを確認します。<br /><br />収益全体の計測には*af\_skad\_revenue*を使用し、Meta Adsの収益イベント（通常は*fb\_mobile\_purchase*）にマッピングします。<br /><br />注意：複数のイベントを*fb\_mobile\_purchase*にマッピングしても問題ありません。 |
        | <span id="conversion"></span>コンバージョン | 1～6件のコンバージョンイベントを、対応するMeta Adsイベントにマッピングします。 |

        4. ［**連携を保存**］をクリックします。
        5. ［**SKAN設定**］までスクロールし、［**MMP接続URL**］をクリックしてコピーします。次のセクションで、Metaの画面でのURLの貼り付け先を説明します。

           ![meta_ads_skan_configuration_mmp_url.png](https://files.readme.io/341918a757014d51a240898d157a6576b50cb269ad3bd0a574e4e6aef9d504ef-40032652607377.png)
      </td>
    </tr>
    <tr>
      <td><span id="4"></span>
        4
      </td>
      <td>
        AppsFlyerとMeta Adsの接続
      </td>
      <td>
        1. Meta Adsでイベントマネージャを開き、［**設定**］タブに移動します。

           [<Image alt="FacebookSkadNetworkSetup.jpg" src="https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg" width="503px" />](https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg)
        2. 設定画面で［**イベントを設定（Configure events）**］をクリックします。

           [<Image alt="mceclip0.jpg" src="https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg" width="503px" />](https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg)
        3. イベントマネージャで［**パートナーアプリからインポート（Import from Partner App）**］を選択します。

           [<Image alt="mceclip1.png" src="https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png" width="503px" />](https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png)
        4. ［**MMP接続URL**］の貼り付け欄が表示されます。   
           これにより、MetaのCVのマッピングが更新され、**アプリ内のFacebook SDKによるCVの設定が停止されます**。［パートナーアプリからインポート］が無効になっている場合は、[トラブルシューティング](/docs/skadnetwork-skan-interoperation-with-meta-ads#import-from-partner-app-is-disabled)を参照してください。
        5. Meta Adsの画面の指示に従って操作します。結果に応じて、次の内容を確認してください。
           1. Meta Adsの画面に**MMP接続URL**を正常に貼り付けられた場合：これで準備が整いました。連携が完了しました。以下の注意事項を確認してください。
           2. **MMP接続URL**の貼り付けに失敗し、Meta Adsの画面にエラーメッセージが表示された場合：次の対応を行ってください。  
              - 24時間待ってから、再度この手順を行います。  
              - 24時間以上経過してもエラーが解消しない場合は、AppsFlyerサポートにお問い合わせください。

        注意事項

        * この手順は、一度行えば完了です。AppsFlyerで計測設定を変更しても、接続URLを再度コピーして貼り付ける必要はありません。たとえば、収益計測からコンバージョン計測に切り替えた場合、Meta Adsは既存のURLを使用して現在の設定ルールを取得します。
        * この手順を完了すると、Meta Adsは独自のランダム化された構造を通じて、AppsFlyerからCVの設定ルールを取得できるようになります。この構造をお客様側で設定することはできません。
        * 更新した計測設定がMeta Adsに反映されるまで、最大24時間かかります。
      </td>
    </tr>
    <tr>
      <td><span id="5"></span>
        5
      </td>
      <td>
        iOS 14キャンペーンの設定
      </td>
      <td>
        Meta Adsで、iOS 14キャンペーンの設定がオンになっていることを確認します。

        この設定は、［**新規アプリインストールキャンペーン（New App installs Campaign）**］の設定ページにあります。

        [![FBiOS14.png](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="additional-information" />

## 補足情報

<div id="turning-off-the-skan-integration" />

<Accordion title="SKAN連携の解除">

Meta Adsとの連携を解除する際は、［**パートナーを有効にする**］をオフにするだけではSKANデータの記録は停止しません。SKANの接続も別途削除する必要があります。

**SKAN連携を解除するには、次の手順を行います。**

1. AppsFlyerで、［**コラボレーション］>［パートナー連携］>［連携済みパートナー**］に移動します。
2. Meta Adsを検索して選択します。
3. ［**SKAN**］タブに移動します。
4. 接続を解除するアカウントの削除アイコンをクリックします。

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-facebook" />

<Accordion title="AppsFlyerとMeta Adsの計測方法・タイミングの違い">

| 項目 | 詳細 |
| --- | --- |
| アプリ内イベント名 | 2021年8月15日までは、ダッシュボードのイベント名にMeta Adsのイベント名が使用されていました。現在は、この扱いは適用されません。 |
| 収益モードのコンバージョンユーザー数の指標 | ［2021年8月16日に廃止］<br /><br />~~収益モードのコンバージョンユーザー数（課金ユーザー数）には、Meta Adsキャンペーン経由で収益をレポートしたユーザー数が含まれません。これは、前の「アプリ内イベント名」で説明した収益の命名規則によるものです。~~ |
| 取得できるデータの開始日 | 連携後の初回のデータ同期でも、その後の同期でも、AppsFlyerは最大で過去7日分のMeta Adsデータをさかのぼって取得します。 |
| インストール日 | AppsFlyerとMeta Adsでは、インストール日の決定方法が異なります。次の点に注意してください。<ul><li>iOSのSKANポストバックには、実際のインストールのタイムスタンプが含まれていません。</li><li>Meta Adsは、ポストバックの受信時刻をインストール時刻として扱い、Meta Adsで設定されているアプリのタイムゾーンを考慮して日付を決定します。</li><li>AppsFlyerは、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#activity-window">アクティビティ期間の設定</Anchor>に基づいてインストール時刻を算出します。この計算では、アプリのタイムゾーンもMeta Adsの広告アカウントのタイムゾーンも考慮しません。</li></ul> |
| データの更新タイミング | <ul><li>AppsFlyerは、01:00 UTCにMeta AdsのSKANデータを収集します。</li><li>ダッシュボードと集計データは、その7時間後に更新されます。</li></ul> |

</Accordion>

<div id="verifying-the-ads_read-permission" />

<Accordion title="ads_read権限の確認">

ads\_read権限があると、Meta Adsの利用者はAPI経由で広告のパフォーマンスデータにアクセスし、カスタムダッシュボードやデータ分析に利用できます。

**Meta Adsアカウントのads\_read権限を確認するには、次の手順を行います。**

1. <Anchor target="_blank" href="https://developers.facebook.com/apps">Meta Adsの開発者アカウント</Anchor>に移動します。
2. FacebookアプリIDを選択します。
3. ［**ユースケース（Use Cases）］>［アクセス許可と機能（Permissions and Features）**］に移動します。
4. `ads_read`を検索します。
5. `ads_read`のステータスが［利用準備完了（ready for use）］になっていることを確認します。このステータスになっていれば、追加の操作は不要です。
6. `ads_read`のステータスが［利用準備完了（ready for use）］になっていない場合は、権限のリクエストを作成して送信します。
7. Metaがリクエストを承認したら、AppsFlyerのMeta Ads連携ページに戻り、［**接続**］をクリックします。  
   **注意：** Metaは最近、このセクションの名称と構成を変更しました。［**アプリレビュー（App Review）**］が表示されなくても問題ありません。権限のリクエストは、［**ユースケース（Use Cases）］>［アクセス許可と機能（Permissions and Features）**］から行います。

</Accordion>

<div id="troubleshooting-discrepancies-and-faq" />

<Accordion title="トラブルシューティング・データの差異・よくある質問">

| 作業 | 詳細 |
| --- | --- |
| <span id="not-seeing-skan-inapp-events-from-meta"></span>MetaのSKANアプリ内イベントが表示されない場合 | MetaのSKANキャンペーンでインストールは表示されるものの、アプリ内イベントが表示されない場合は、次のチェックリストで設定の不足を確認してください。<br /><br />注意：インストールも表示されていない場合は、先にインストールのチェックリストを確認してください。<br /><br />**<span id="quick-fix-checklist"></span>設定確認のチェックリスト**<br /><br />**ステップ1**<ol><li>AppsFlyerでSKANイベントのマッピングを確認します。</li><li>［**設定**］>［**SKAN Conversion Studio**］に移動します。</li><li>計測するアプリ内イベントが正しくマッピングされていることを確認します。</li></ol>**ステップ2**<ol><li>Meta Ads連携のイベントマッピングを確認します。</li><li>AppsFlyerで、［**コラボレーション］>［パートナー連携］>［連携済みパートナー**］に移動し、［**Meta Ads**］を選択します。</li></ol><ul><li>［アプリ内イベントポストバック］で、SKAN Conversion Studioと同じイベント名がMetaにマッピングされていることを確認します。イベント名では大文字と小文字が区別されます。</li><li>収益を計測する場合は、af\_skad\_revenueが含まれ、fb\_mobile\_purchaseにマッピングされていることを確認します。</li></ul>**<span id="still-not-working"></span>それでも表示されない場合**<br /><br />**必要な最低インストール数の確認**<ul><li>SKANのインストール後のデータが表示されるには、Meta経由のインストール数が、キャンペーンごと・日ごとに必要な最低数に達している必要があります。</li><li>このしきい値を下回ると、インストールのコンバージョン値（CV）がnullになり、イベントデータをデコードできません。</li></ul>このしきい値はMetaから公開されていませんが、SKANダッシュボードで対象キャンペーンの「コンバージョン値のNull率」を確認できます。この値がほぼ100%の場合は、インストール数を増やす必要があります。ターゲットユーザーの絞り込み条件を調整するか、キャンペーンのインストール数を増やしてください。 |
| <span id="facebook-cant-connect"></span>Meta Adsに接続できない場合 | **症状**<br /><br />Meta Adsに次のメッセージが表示される場合：*「接続できません。正しいURLを使用しているか確認してください。問題が解消しない場合は、連携先アプリのサポートにお問い合わせください。」*<br /><br />**対処方法**<br /><br />AppsFlyerでアプリ内イベントのマッピングが有効になっており、AppsFlyerのイベントがMeta Adsのイベントにマッピングされていることを確認してください。（前のセクションのアプリ内イベントのマッピング手順を参照してください。）<br /><br />［2021年4月20日ガイダンス更新］ |
| <span id="event-priority"></span>イベントの優先度 | Q：Meta Adsでイベントの優先度を設定するには、どうすればよいですか？<br /><br />A：Meta Adsで優先度を設定する必要はありません。この優先度の機能は、Facebook SDKでCVを設定するアプリ向けのものです。ここで説明している構成では、AppsFlyer SDKがCVを設定します。Meta Adsの優先度のオプションは無視してください。AppsFlyerのコンバージョン計測では、優先度を設けずに6つのイベントを計測します。<br /><br />［2021年4月20日ガイダンス更新］ |
| <span id="event-occurrences"></span>イベントの発生回数 | Q：AppsFlyerに表示されるイベントの発生回数が、Meta Adsより多いのはなぜですか？<br /><br />A：Meta Adsは、イベントの発生回数を0～1回の範囲でのみカウントします。そのため、範囲の設定でそれ以上の発生回数を定義しても、追加の発生回数がカウントされるのはAppsFlyerのみです。 |
| <span id="import-from-partner-app-is-disabled"></span>［パートナーアプリからインポート］が無効になっている場合 | ![ImportFromPartnerApp.png](https://files.readme.io/c124696c4a8bca7c0d95d812f5390e9672adbfd6fc510a6fa573972f5441cd02-40032591386129.png)<br /><br />**症状**<br /><br />Meta Adsで［**パートナーアプリからインポート**］が無効になっている**場合**は、そのアプリからMMP SDKを使用してMeta Adsにイベントが送信されたことがありません。<br /><br />**対処方法**<br /><br />次のいずれかを行ってください。<ul><li>MMP SDKを使用して、できるだけ早くMeta Adsへのイベント送信を開始します。</li><li>Facebook SDKまたはApp Events APIを使用してMeta Adsへのイベント送信を開始し、他のいずれかの方法でコンバージョン値の設定ルールを定義します。</li></ul>Meta Adsに最初のイベントが記録されたら、AppsFlyerとの連携を設定します。<br /><br />［2021年4月25日ガイダンス更新］ |
| <span id="ranges-cant-overlap-and-must-be-in-consecutive-order"></span>範囲が重複している、または連続していない場合 | **症状**<br /><br />AppsFlyerのSKANカスタム計測モードを使用している場合：計測の設定ルールをMeta Adsにインポートする際、次のメッセージが表示されます。*「範囲は重複させず、連続する順序で設定してください。」*<br /><br />**対処方法**<br /><br />カスタムのコンバージョン値の設定ルールでは、収益値を小さい順に、途切れなく連続するよう設定する必要があります。<br /><br />［2021年4月26日ガイダンス更新］ |
| <span id="sending-events-to-facebook"></span>Meta Adsへのイベント送信 | **Q**：CVの計測対象として選択していないイベントについても、Meta Adsへ追加でポストバックを送信する意味はありますか？<br /><br />**A**：同意を得ているユーザーについては、Meta Adsによる最適化の効果を最大限に引き出すため、すべてのイベントを送信してください。 |
| <span id="map-multiple-events-to-the-same-facebook-event"></span>複数のイベントを同じMeta Adsイベントにマッピング | **Q**：複数のアプリ内イベントを1つのMeta Adsイベントにマッピングできますか？<br /><br />**A**：複数のイベントを1つのMeta Ads標準イベントにマッピングすると、Meta Adsはそれらのイベントを区別できません。そのため、Meta Adsが認識する1つのイベントに対して最適化が行われます。 |
| <span id="no-data-to-pull"></span>取得できるデータがない場合 | **Q：** 接続ステータスに「取得できるデータがありません：Metaのデータ共有権限を確認してください」と表示されるのはなぜですか？<br /><br />**A**：SKANデータがまだ存在しないか、Meta Adsアカウントの管理者権限を持つユーザーでログインする必要があります。<br /><br />**Q：** 「取得できるデータがありません：Metaのデータ共有権限を確認してください」と表示されました。Meta Adsの詳細は表示されていますが、この状態で問題ありませんか？<br /><br />**A**：はい、問題ありません。このエラーメッセージが表示されても、データは正常に取得されます。 |
| <span id="facebook-data-is-not-in-the-dashboard"></span>Meta Adsのデータがダッシュボードに表示されない場合 | **症状**<br /><br />SKAN連携タブに［*データの取得に失敗しました（failed to pull data）*］と表示されます。<br /><br />![FacebookSKAdIntegration.png](https://files.readme.io/42538a59d27815b95b71ec136ebc45b8d918eebf6a2235c90fef59c467128fb2-40032591388177.png)<br /><br />**対処方法**<br /><br />接続しているアカウントが、Facebookの管理者アカウント、またはads\_read権限を持つMeta Adsの広告主アカウントであることを確認してください。 |
| <span id="there-is-an-error-in-facebook-when-you-try-to-run-ios-14-campaigns"></span>iOS 14キャンペーンの配信時にMeta Adsでエラーが発生する場合 | **症状**<br /><br />次の条件がすべて当てはまる場合：<ul><li>iOS 14キャンペーンを配信しようとすると、Meta Adsでエラーメッセージが表示されます。</li><li>最近、新しいアプリまたは子ども向けアプリをApp Storeに追加しました。</li></ul>これは、SKANに対応したSDKを使用していることをMeta Adsが認識していないために発生します。ここでは、AppsFlyer SDKが該当します。<br /><br />**対処方法**<ol><li>AppsFlyerで、［**コラボレーション］>［パートナー連携］>［連携済みパートナー**］に移動します。</li><li>［**Meta Ads**］を検索して選択します。</li><li>［**連携**］タブで、［**パートナーを有効にする**］をオフにします。</li><li>［**連携を保存**］をクリックします。</li><li>15秒待ちます。</li><li>［**パートナーを有効にする**］をオンにします。</li><li>［**連携を保存**］をクリックします。</li><li>Meta Adsがシグナルを受信するまで、最大24時間待ちます。</li></ol> |
| <span id="revenue-reported-by-facebook"></span>Meta Adsがレポートする収益 | ［2021年7月12日更新］<br /><br />Meta Adsは、SKANの設定に基づいてCVから収益を算出します。ただし、単純な計算で求めるのではなく、アルゴリズムを使用して収益を算出します。<br /><br />そのため、収益を1ドル単位の整数で計測している場合でも、算出された収益に端数が含まれることがあります。 |
| <span id="retroactive-data-backfill"></span>過去のデータの補完 | ［2021年12月23日更新］<br /><br />ログインの失敗などにより、Meta Adsに接続できず、データを取得できない場合があります。この場合も心配はありません。次回ログインできた際に、過去7日分のレポートで欠落しているデータを補完します。 |
| <span id="appsflyer-is-showing-significantly-more-installseventsrevenue-than-facebook"></span>AppsFlyerのインストール数・イベント数・収益がMeta Adsより大幅に多い場合 | 多くの場合、Meta Adsの管理画面ではデフォルトでクリックスルーのインストールとイベントのみが表示される一方、AppsFlyerの管理画面ではクリックスルーとビュースルーの両方が表示されることが原因です。 |
| <span id="agency-integration"></span>代理店による連携設定 | 代理店が広告主のMeta Adsアカウントの管理者権限を持っている場合は、この記事の手順を実行し、広告主に代わってSKAN連携を有効にできます。広告主が別途Meta Adsアカウントにログインする必要はありません。広告主のアカウントには、代理店がログインしていることが表示されます。 |
| <span id="an-updated-cv-doesnt-appear-on-facebook"></span>更新したCVがMeta Adsに表示されない場合 | SKAN Conversion Studioでコンバージョン値（CV）を追加・変更・削除する際は、対象のイベントが［**アプリ内イベントポストバック**］でマッピングされていることを確認してください。マッピングされていない場合、Meta AdsでCVが更新されません。 |
| <span id="modeled-data-differences-in-appsflyer-and-facebook-ads-manager"></span>AppsFlyerとMeta Ads Managerのモデル化データの違い | AppsFlyerは、基本的なSKANレポートだけでは得られない集計データを、モデル化によって補完します。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data">詳しくはこちら</Anchor><br /><br />AppsFlyerは、確認済みの偏りのないデータのみを使用してモデル化を行うため、Meta Adsがモデル化したデータは考慮しません。そのため、Meta Ads ManagerのレポートとAppsFlyerのレポートでは、データやその粒度に差異が生じる場合があります。 |

</Accordion>

<div id="see-also" />

> 📄 **関連記事**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">AppsFlyerのSKANソリューションガイド</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-facebook=skan%E9%80%A3%E6%90%BA--appsflyer---meta-ads h_01H8XRMVR4JK6ZCGPQJE4D3T26=skan%E9%80%A3%E6%90%BA--appsflyer---meta-ads scope-of-skan-interoperability-with-meta-ads=meta-ads%E3%81%A8%E3%81%AEskan%E9%80%A3%E6%90%BA%E3%81%A7%E3%81%A7%E3%81%8D%E3%82%8B%E3%81%93%E3%81%A8 h_01H8XRMVR4Q7HAJV0B7QB5MDPH=meta-ads%E3%81%A8%E3%81%AEskan%E9%80%A3%E6%90%BA%E3%81%A7%E3%81%A7%E3%81%8D%E3%82%8B%E3%81%93%E3%81%A8 considerations=%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 h_01H8XRMVR43KEGWARYMD45S0VY=%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 facebook-app-install-ads-guidance=meta-ads%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E5%BA%83%E5%91%8A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%AC%E3%82%A4%E3%83%80%E3%83%B3%E3%82%B9 h_01H8XRMVR48NWM47043YWT63HK=meta-ads%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E5%BA%83%E5%91%8A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%AC%E3%82%A4%E3%83%80%E3%83%B3%E3%82%B9 interoperation-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 h_01H8XRMVR4NVDZ23572F6KJTA9=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 h_01H8XRMVR4D07SWXS1TWK42DS3=allow-facebook-to-share-skadnetwork-data-with-appsflyer h_01H8XRMVR5HKXWYB3XN11V48Y0=share-cv-schema-with-facebook enabling-appsflyer-skadnetwork-interoperation-with-facebook=appsflyer%E3%81%AEskan%E3%81%A8meta-ads%E3%81%AE%E9%80%A3%E6%90%BA%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H8XRMVR56T3X9MJ6KVJF0Z8W=appsflyer%E3%81%AEskan%E3%81%A8meta-ads%E3%81%AE%E9%80%A3%E6%90%BA%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H8XRMVR5GY77K7GJ4TXGWEHS=%E6%B3%A8%E6%84%8F inapp-event-mapping-guide=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%AC%E3%82%A4%E3%83%89 h_01H8XRMVR5T28Q0E8KP6BZ6CGH=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%AC%E3%82%A4%E3%83%89 additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01H8XRMVR5WXZ88676PAW9BKC9=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01H8XRMVR5AW2HZD6JFDYJRNFJ=turning-off-the-skan-integration h_01H8XRMVR5HZ2BBP4XXDEFYT34=measurement-and-timing-differences-between-appsflyer-and-facebook h_01H8XRMVR58DFA2SX20ZEKZRC3=verifying-the-ads_read-permission h_01H8XRMVR5Z9H83X0TAYS50CJ9=troubleshooting-discrepancies-and-faq h_01K7P24YAYSPB84PV0ZGBJ0QB0=quick-fix-checklist h_01K7P2811MRTVRC0D6YGVSXY4C=still-not-working h_01HE7SMBXBCEQM7KF2RG3V16KV=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />
