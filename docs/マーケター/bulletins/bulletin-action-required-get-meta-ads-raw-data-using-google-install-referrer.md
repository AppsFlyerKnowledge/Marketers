---
title: お知らせ：お知らせ：必要な対応 — Google インストール参照元を使用してメタ広告のローデータを取得する
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-21T07:02:51Z'
  edited_at: '2026-10-14T09:37:03Z'
  id: 4409322107537
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/4409322107537
---

<Table>
  <tbody>
    <tr>
      <td>
        **更新情報**
      </td>
      <td>
        インストールリファラを使用してGoogle Playストアに遷移する広告のMetaキャンペーンローデータを取得できます。
      </td>
    </tr>
    <tr>
      <td>
        **変更点**

        Information\_icon.png
      </td>
      <td>
        2021年10月29日**以降**、Meta広告によってもたらされたユーザーのユーザーレベルのアトリビューションデータ（ローデータ）は制限されます。メタ広告では、このデータをAppsFlyerなどのMMPが利用できるようにしますが、広告主は利用できません。

        ただし、Google Play Storeへ遷移する広告の場合、<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">アプリに実装されている</Anchor>必要があるインストールリファラを介して、広告主が利用できるアトリビューション項目があります。リファラー経由で提供されたデータは、お客様が利用できるAppsFlyerのローデータレポートに反映され、AppsFlyerにとっては広告IDを持たないユーザー（LAT対応）の計測も可能にします。

        リファラメカニズムを使用するには、AppsFlyer SDK V5.4以上が必要です。

        **注記：** リファラデータは、API経由で提供されるデータよりも優先され、制限されていません。

        リファラー内のデータはMetaによって暗号化され、Metaデベロッパーアカウントで利用可能なキーを使用して復号化されます。お客様は、［必要なアクション］の箇所に記載されている手順に従って、復号化キーをAppsFlyerへ提供する必要があります。

        **リファラ経由で利用可能なキャンペーンの計測項目：**

        * Ad ID
        * 広告名
        * Adset ID
        * 広告セット名
        * Campaign ID
        * キャンペーン名
        * アカウントID
        * Channel
        * Ad type (この項目はまだ利用できません)

        **注：**

        * その他の項目は、リファラー経由では利用できません。
        * また、このソリューションはクリックスルー計測にのみ適用され、ビュースルー計測には適用されません。
        * リファラーデータは、ユーザーがストアを経由しないため、リエンゲージメントキャンペーンには適用されません。

        **AppsFlyerはいつからこの変更を適用開始しますか？**

        * 2021年10月29日：
          * Metaキャンペーンのクリックスルーデータ（アトリビューションローデータ）に関する制限が導入されました。
          * 広告主は、AppsFlyerの管理画面上でリファラのdecryption keyを設定可能になります。
        * 2021年11月3日：
          * AppsFlyerは、リファラメカニズムによって提供されるデータを使用して、ローデータを入力しアトリビューションを行います。
      </td>
    </tr>
    <tr>
      <td>
        **利用可能なデータについて**
      </td>
      <td>
        <table><tbody><tr><th rowspan="2">計測方法</th><th rowspan="2">計測データソース</th><th colspan="2">広告主が利用可能なデータ  </th><th>備考</th></tr><tr><th>ローデータ</th><th>集計データ</th><th> </th></tr><tr><td>クリックスルー</td><td>リファラ (Google PlayストアからダウンロードされたAndroidアプリのみが対象)</td><td>利用可能</td><td>利用可能</td><td><ul><li>LATユーザーの計測データが利用可能です。</li><li>MMPデータとリファラデータが両方あった場合には、リファラデータが優先されます。</li><li>リエンゲージメントキャンペーンには適用されません。</li></ul></td></tr><tr><td>クリックスルー</td><td>MMP API</td><td>Restricted（制限有）</td><td>利用可能</td><td> </td></tr><tr><td>ビュースルー</td><td>MMP API</td><td>Restricted（制限有）</td><td>利用可能</td><td>リファラ機能はサポート対象外です。</td></tr><tr><td colspan="5"><p><strong>注記：</strong>注意： データの可用性が制限されている場合：</p><ul><li><ul><li>インストールとアプリ内イベントのポストバックは、制限のあるアドネットワークにのみ送信されます。分析パートナーなどのサードパーティパートナーは、制限付きアトリビューションのポストバックを取得しません。 </li><li>アトリビューションなしのポストバック（アトリビューション項目を含まない）は、すべてのイベント（オーガニックおよびアトリビューションなしを含む）を受信するように設定されたアドネットワークに送信されます。これには、Metaのキャンペーン管理パートナーも含まれます。</li></ul></li></ul></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        **必要な対応**
      </td>
      <td>
        **Metaから復号化キーを取得するには：**

        【以下はFacebookから提供された情報に基づいています。】

        1. Metaデベロッパーポータルにログインします。
        2. 画面右上にある、**My App**に移動してください。
        3. decryption keyを取得したいアプリを選択してください。
        4. ページ左側にある**設定 (Settings)** > **基本 (Basic)** に移動してください。

           [![FBUIforKey.png](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
        5. **Androidセクション** までスクロールダウンすると、decryption keyのラベルが表示されます。**インストールリファラのdecryption key** は、**Package Names** フィールドの下にあります。　**注：** これは、Google Play Storeとパッケージネームを設定した場所と同じセクションにあります。

        **AppsFlyerでリファラメカニズムを有効にする方法：**

        1. [必須] AppsFlyer SDK V5.4以上がアプリに実装されていること確認してください（AppsFlyer Android SDK V5.3以下はサポート対象外です）。
        2. 次のいずれかを実行してください：
           1. [近日公開] APIを使用してdecryption keyを設定します。
           2. 画面上で decryption key を設定する方法：
              1. AppsFlyer管理画面 左メニュー **設定** > **連携済みパートナー**に移動します。
              2. Meta Adsを選択します。  

                 ![meta-ads-install-referrer-decryption-key.png](https://files.readme.io/adf6caa8d7cee493695eb8fb7db1b61c60e6a1cef0273e615c43a05ad8a9485d-13963525463825.png)
           3. **[連携]** タブを開いて、**Install Referrer** **Decryption Key**に取得したKeyを貼り付けてください。
           4. **連携を保存**をクリックします。
      </td>
    </tr>
    <tr>
      <td>
        **APIによるdecryption keyの更新**
      </td>
      <td>
        **[準備中]**
      </td>
    </tr>
    <tr>
      <td>
        **今後のローデータの利用可否について**
      </td>
      <td>
        * 計測データをリファラの機能を介して取得出来た場合には、データに制限はかからず、ローデータレポートからデータを取得可能です。
        * 計測データがAPIで取得された場合には、Metaがもたらしたユーザーのローデータは、*restricted* というメディアソース名で記録されます。
        * この変更は、2021年10月29日 08:00 UTCよりも前に計測されたユーザーのローデータには適用されません。
      </td>
    </tr>
    <tr>
      <td>
        **これまでと変わらない点**
      </td>
      <td>
        AppsFlyerは、引き続きMetaからデバイスレベルのデータを受信します。つまり、当社のアトリビューションおよびレポート機能（マルチタッチアトリビューション、LTV、ROI、コホート、リテンションレポート、不正防止、Audiences、その他のサービス）には何も変更はありません。詳細：<Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">集計・分析レポートツール</Anchor>

        **注：** 注意：decryption keyをAppsFlyerに提供していただければ、広告IDを持たないユーザー(LAT ONの状態)の計測も可能になります。これにより計測精度が向上します。
      </td>
    </tr>
    <tr>
      <td>
        **計測の変更点**
      </td>
      <td>
        GCDによるディファードディープリンクは、Google Install Referrerの機能を使用するAndroidアプリで利用可能になる予定ですが、iOSアプリでは利用できません。
      </td>
    </tr>
    <tr>
      <td>
        **よくある質問**
      </td>
      <td>
        * **インストールリファラの decryption keyは更新する必要がありますか？**  
          一度提出した decryption key は、更新する必要がありません。
        * **いつローデーターレポートでユーザーレベルデータを確認できますか？**  
          ユーザーレベルデータは、有効なインストールリファラ decryption key が提出され、インストールがMeta Adsに計測されるとロデータレポートに表示されます。
        * **2021年10月29日から2021年11月3日の間に発生したインストールについて、ユーザーレベルの計測データは利用できますか？**  
          申し訳ございませんが、このデータは利用できません。
      </td>
    </tr>
  </tbody>
</Table>
