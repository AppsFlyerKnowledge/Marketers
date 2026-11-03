---
title: PBA Web SDK実装テスト
metadata:
  keywords:
    - Developers
    - PBA
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-09-01T19:09:41Z'
  edited_at: '2026-10-14T09:26:49Z'
  id: 360012729178
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360012729178
---
> **概要：**

## PBA Webイベントのテスト

**テストページの使用に関する原則**

Web SDKは、ウェブイベントをPBAに送信します。これらのイベントは毎日デイリーで処理され、PBA管理画面とローデータレポートで利用できるようになります。効率的にテストを実行するためには、毎日のデイリー処理を待たずにテストイベントを送信します。テストイベントは：

* 受信時に解析され検証されます。
* ユーザーインターフェイス上で利用できます。これには処理エラーが含まれます。エラーが存在する場合は、修正したイベントを再度送信して、正しく処理されていることを確認します。
* 毎日行われるデイリーのデータ処理プロセスで他のイベントと同様に処理されます。つまり管理画面とローデータにも追加されます。

#### Web SDK実装テストページ

<Table>
  <tbody>
    <tr>
      <td>
        <span id="page-main-view"></span>**ページのメイン表示**

        [<Image alt="TestScreen_us-en.jpg" src="https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg" width="338px" />](https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg)

        * 最新のイベントが最初に表示されます。
        * **イベントキャッシュ**：
          * 最大100個のイベントが含まれます
          * 古いイベントは、新しいイベントが追加されるたびに削除されます
          * キャッシュされたイベントは24時間後に削除されます
        * **ページコントロール**：

          * すべてクリア：キャッシュからイベントを永久的にクリアします。**ご注意ください**キャッシュは同じWeb Dev Keyを共有するウェブサイトで一般的に使用されます。したがって、別のデベロッパーがテストページを使用している場合は、同様にすべてのキャッシュがクリアされます。
          * 開始をクリックするまで新しいイベントは表示されません。

        **イベントテーブルの列**

        | フィールド | 説明 |
        | --- | --- |
        | Time (UTC) | Event time |
        | イベントタイプ | イベントタイプは次のとおりです。<br /><br />* 広告主から送信するイベント：<br />  * `EVENT`<br />  * `setCustomerUserId`<br />  * `pageLoad`：pageLoad: Webサイトのページが読み込まれる / 更新されるたびに、Web SDKから送信されます。 |
        | Event content | PBAによって記録されたイベントペイロード。 |
        | 備考 | * **有効**：Valid：PBAはイベントを受信し記録しました。これ以上の操作は必要ありません。<br />* **無効**：Invalid: 修正処理が必要なエラーのリスト。<br />* エラーメッセージにカーソルを合わせ詳細を確認します：  <br /><br />  ![PBAWebSDKTestingErrorMessagesPopup_en-us.png](https://files.readme.io/0e050e60dbf9f1289880b5d58c4885d4be66392265986eaf4b2f76876697e429-360011317358.png) |
      </td>
    </tr>
    <tr>
      <td>
        **ドリルダウン表示**  

        [![mceclip0.png](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)

        イベント行をクリックして、処理後のコンテンツを表示します。詳細については、<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">Web SDKイベントパラメーター</Anchor>をご覧ください。
      </td>
    </tr>
  </tbody>
</Table>

## 手順

次の手順を実行します。

<div id="enable-test-mode" />

<Accordion title="テストモードを有効にする">

**前提条件**

テストを開始する前に、<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#installation-and-integration">Web SDKをWebサイトまたはテストサイトに実装する必要があります</Anchor>。

**ブラウザの制限**

特定のテストモードが有効になっている場合、タブに関係なく、ブラウザは指定されたWebサイトのみに使用でき、他のWebサイトへの接続はできません。同じコンピュータから別のWebサイトに接続するには、ChromeではなくSafariなどの別のブラウザを使用してください。

**テストモードを有効にする方法：**

1. **SDKが読み込まれていることを確認します：**

   2. 必要な**Web SDK integration test**を選択します。  
      実装テストページが開きます。Web Devキーが表示されます。  

      [![pba_web_sdk_integration_test_web_dev_key_en-us.png](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)
   3. 新しいブラウザタブにて、Web SDKが実装されているWebサイトを開きます。
   4. 右クリックをし、検証を選択して、ブラウザ開発者ツールを開きます。
   5. **Console** タブを開きます。
   6. Consoleタブにて、以下を入力します：  

      ```javascript
      window.AF_SDK.initPluginsConfig.pba.webAppId
      ```

      WebAppID が表示されます。

      [![testing_pba_integration_webappid_check_en-us.png](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)
   7. WebAppIDが、**Web SDK integration test**ページに表示されるWeb Devキーと同じであることを確認します。
2. **テストモードを有効にする**：
   1. ウェブサイトブラウザタブにて、**Console**タブを開きます。
   2. 次のように入力します。

      ```javascript
      window.AF_SDK.PLUGINS.PBA.turnOnDevMode()
      ```

      [![testing_pba_integration_turnondevmode.png](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)
3. **テストモードが有効になっていることを確認します。**
   * **Console**タブで、以下を入力します。  

     ```javascript
     window.AF_SDK.PLUGINS.PBA.isDevModeOn()
     ```

     これは、テストモードがアクティブであることを示します。   
     [![PBATestingWebSDKIntegrationIsDevModeOn_en-us.png](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)

</Accordion>

<div id="send-test-events" />

<Accordion title="テストイベントを送信する">

* テストモードでは、送信したイベントがテスト実装ページに表示されます。
* ご注意ください注！テストイベントは処理され、その後PBAレポートに含まれます。

以下で記載されている各タイプのサンプルイベントを送信します。

| ステップ | アクション<br /><br />(コマンド入力) | WebSDK実装テストページ<br /><br />期待される結果： |
| --- | --- | --- |
| 1 | ブラウザで新しいタブを開き、Webサイト上の任意のページを閲覧します。 | PBAは、ウェブサイトが開く／更新されるたびに `'pageLoad'`'pageLoad''pageLoad'イベントを記録します。<br /><br />[![PBATestingWebSDKPageLoadEvent_en-us.png](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png)](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png) |
| 2 | Webサイトにユーザーとしてログイン／登録し、<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">setCustomerUserId イベントをトリガーします</Anchor>。 | [![mceclip3.png](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png)](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png) |
| 3 | <Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#recording-event-scenarios">Webイベントの送信を開始し</Anchor>、PBAがそれらを正しく処理することを確認します。<br /><br />**注意：**<ul><li>`eventRevenueCurrency: "USD"`</li><li>`eventRevenue: 0`</li></ul>[![PBAWebSDKTestEventEVENT_en-us.png](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)<br /><br />詳細は、<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">Web SDK イベントパラメーター</Anchor>をご覧ください。 | [![mceclip5.png](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png)](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png) |

</Accordion>

## トラブルシューティング

<div id="events-do-not-display-in-the-test-page" />

<Accordion title="イベントがテストページに表示されない">

1. ブラウザ開発ツールんいて、**ネットワーク**タブを開きます。
2. フィルタにて、「websdk」と入力します。
3. HTTPレスポンスコードに基づいて、次の手順を実行します。
   * 2024-02-26200: AppsFlyerテクニカルサポートにお問合せください。
   * 2024-02-26400: " "内に含まれるすべてのパラメーターを確認します。

</Accordion>

<div data-zendesk-anchors="test-pba-web-events=pba-web%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01HKW32BE04AKHFMY853211C1A=pba-web%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 web-sdk-integration-test-page=web-sdk%E5%AE%9F%E8%A3%85%E3%83%86%E3%82%B9%E3%83%88%E3%83%9A%E3%83%BC%E3%82%B8 h_01HKW32BE0Z2ZKTBHSCSWVT04N=web-sdk%E5%AE%9F%E8%A3%85%E3%83%86%E3%82%B9%E3%83%88%E3%83%9A%E3%83%BC%E3%82%B8 procedures=%E6%89%8B%E9%A0%86 h_01HKW32BE0VA0X9ZX4Z26EY6CZ=%E6%89%8B%E9%A0%86 h_01HKW32BE08Z9CCMBPK4Z0854C=enable-test-mode h_01HKW32BE0E4A1W221FKY97EZB=send-test-events troubleshooting=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01HKW32BE1HFV0NM64QMASBCCT=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01HKW32BE1QHV0W6ZDYHG94RQA=events-do-not-display-in-the-test-page" />
