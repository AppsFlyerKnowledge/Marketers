---
title: マーケター向けSDK実装テスト
metadata:
  keywords:
    - Testing
    - SDK
    - Advertisers
    - Debug
    - Debugging
    - redirects test
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-11-12T14:15:08Z'
  edited_at: '2026-10-28T09:09:43Z'
  id: 360001559405
  locale: ja
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ja/articles/360001559405
---
> **At a glance:** AndroidまたはiOSアプリとAppsFlyerの連携をテストします。

## 概要

SDKの実装が完了したら、SDKがAppsFlyerサーバーと正常に通信しているか確認できます。マーケターは、次の2つのテスト方法から選べます。

* <strong>［SDK実装テスト（SDK Integration Tests）］</strong>ページでは、次のテストを行えます。
  * <Image alt="" src="https://files.readme.io/16b90e430d7beea0eaa1530130d094d590c0a202f6c6ad298a88aac9508fee7a-31828933593745.png" width="30px" /> テスト対象のアプリで発生した[イベントをリアルタイムで確認](#view-live-events)します。
  * [非オーガニックインストールのテスト](#h_01HYX9R15931HJEA06SY3K47W5)
  * [ディープリンク（リターゲティング）のテスト](#h_01HYX9R159DDNJW53AWTWT4C2Z)
* [アトリビューションリンクを使ったテスト。](#アトリビューションリンクを使ったテスト)

開発者は、開発環境で実装テストを行えます。 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing">Developer Hubの実装テストに関する記事</Anchor>を参照してください。

CTVアプリもテストできます。[CTVのテスト](#ctvのテスト)を参照してください。

## 「SDK実装テスト」ページを使ったテスト

<strong>［SDK実装テスト］</strong>ページでは、インストール、広告収益、アプリ内イベントなど、アプリで発生するイベントをリアルタイムで確認できます。非オーガニックインストール、アプリ内イベント、ディープリンク（リターゲティング）のテストを行い、実装上の問題を特定することもできます。イベントのリアルタイム表示ツールは、従来のアプリ内イベントテストツールに代わるものです。

> 📘 **Note**
>
> 「SDK実装テスト」ページは、SDKがデバイスIDを取得しているアプリでのみ利用できます。
>
> * **iOS：** IDFAを取得できるよう、ユーザーがApp Tracking Transparency（ATT）でトラッキングを許可していることを確認してください。 ATTに対応していないアプリは、この記事で説明する手順でテストできます。
> * **Android：** 通常、デバイスID（GAID）は自動的に取得されますが、SDKが取得できているか確認することを推奨します。

### **テストデバイスの準備**

1. 対象アプリがインストールされていないデバイス（AndroidまたはiOS）を用意します。必要に応じて、デバイスからアプリをアンインストールしてください。
2. <Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">デバイスをテストデバイスとして登録します。</Anchor>

### 実装テストの実行

<strong>［SDK実装テスト］</strong>ページでは、次の3つのテストを行えます。

<Accordion title="イベントのリアルタイム表示">

イベントのリアルタイム表示ツールは、SDKからAppsFlyerに送信されたデータをリアルタイムで表示するテストツールです。インストール、広告収益、ストア収益のイベントや、その他のアプリ内イベントを確認できます。取得されたイベントごとに、イベントログと詳細を確認できます。

> 📘 **Note**
>
> このツールは、テストデバイスで発生し、お客様のサーバーに送信された後、S2S APIを通じてAppsFlyerに取り込まれたアプリ内イベントとセッションにも対応しています。 S2Sイベントには、登録済みテストデバイスの識別子（iOSはIDFA、AndroidはGAID）を含めてください。

**イベントのリアルタイム表示ツールでイベントを確認するには、次の手順を実行します。**

1. AppsFlyerのサイドメニューから、**［設定］**＞<strong>［SDK実装テスト］</strong>を選択します。

   [![](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)
2. <strong>［リアルタイムイベント（Live Events）］</strong>をクリックします。

   [![](https://files.readme.io/6ec1edba14e51bb27babf80d2d6f4873dbaa5113752217b4fb13399f7a1c61f1-31828925849489.png)](https://files.readme.io/6ec1edba14e51bb27babf80d2d6f4873dbaa5113752217b4fb13399f7a1c61f1-31828925849489.png)
3. <strong>［アプリ］</strong>の一覧で、テストするアプリを選択します。
4. <strong>［テストデバイス］</strong>の一覧<strong>で、</strong>アプリのテストに使用するデバイスを選択します。テストデバイスがない場合は、<strong>［テストデバイスを追加］</strong>リンクをクリックして登録できます。
5. <strong>［続行］</strong>をクリックすると、アプリのイベントの記録が始まります。
6. アプリを起動して操作し、セッションやアプリ内イベントを発生させます。

   [![](https://files.readme.io/72b8822197dc626c1b28a9f8d43bb3c1a91f99e600ae0d8d1f74829bc62dcce6-31828933607313.png)](https://files.readme.io/72b8822197dc626c1b28a9f8d43bb3c1a91f99e600ae0d8d1f74829bc62dcce6-31828933607313.png)
7. イベントの項目をクリックすると、右側のパネルに詳細が表示されます。
8. イベントの記録を停止する場合は、<strong>［停止］</strong>をクリックします。再開する場合は、<strong>［開始］</strong>を再度クリックします。

</Accordion>

<Accordion title="非オーガニックインストールのテスト">

**非オーガニックインストールをテストするには、次の手順を実行します。**

1. AppsFlyerのサイドメニューから、**［設定］**＞<strong>［SDK実装テスト］</strong>を選択します。

   [![](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)
2. <strong>［非オーガニックインストール（Non-Organic Installs）］</strong>のテストをクリックします。

   [![](https://files.readme.io/34440ab6d328e2d519f759f3c2a1b17dbcbee55af32b47bdbd52bb9f537c6735-31828933612177.png)](https://files.readme.io/34440ab6d328e2d519f759f3c2a1b17dbcbee55af32b47bdbd52bb9f537c6735-31828933612177.png)
3. <strong>［アプリ］</strong>の一覧で、テストするアプリを選択します。
4. <strong>［テストデバイス］</strong>の一覧<strong>で、</strong>アプリのテストに使用するデバイスを選択します。テストデバイスがない場合は、<strong>［テストデバイスを追加］</strong>リンクをクリックして登録できます。
5. テストデバイスに対象アプリがインストールされている場合は、アンインストールします。
6. <strong>［テストデバイスからアプリを削除しました（I removed the app from the tested device）］</strong>のチェックボックスを選択します。
7. <strong>［続行］</strong>をクリックし、画面の案内に従って進めます。

**非オーガニックインストールが記録されない場合は、次のような原因が考えられます。**

* IDFAは取得できているものの、テストデバイスが<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices#iosテストデバイスの登録">［テストデバイス］ページでIDFAを使って登録されていない</Anchor>。
* テスト対象のアプリ以外にも、お客様のアプリが2つ以上テストデバイスにインストールされているものの、テストデバイスが<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices#iosテストデバイスの登録">［テストデバイス］ページでIDFVを使って登録されていない</Anchor>。
* オーガニックインストールとして記録された。
* SDKが組み込まれていないバージョンのアプリでテストを行った。

実装に関するエラーは、開発者にお問い合わせください。

</Accordion>

<Accordion title="ディープリンク（リターゲティング）のテスト">

**開始前の準備：**

* テスト対象のアプリを3回以上起動します。
* ディープリンク（リターゲティング）をテストするには、アプリのOneLinkを設定しておく必要があります。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">OneLinkの設定ガイド</Anchor>を参照してください。
* <Anchor target="_blank" href="/marketers/ja/docs/app-settings#reengagement-attribution">リターゲティング</Anchor> が有効になっていることを確認します。

**ディープリンクをテストするには、次の手順を実行します。**

1. AppsFlyerのサイドメニューから、**［設定］**＞<strong>［SDK実装テスト］</strong>を選択します。

   [<Image alt="Keyboard Maestro Engine 2024-10-06 10.00.47.png" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" width="2895px" />](https://support.appsflyer.com/hc/article_attachments/52396465173905)
2. <strong>［リターゲティング］</strong>をクリックします。

   [![](https://files.readme.io/7c5eb6870e8d4c25a817f6c2895163b699e0a4972a6cc675b94396c386288d72-31828925858961.png)](https://files.readme.io/7c5eb6870e8d4c25a817f6c2895163b699e0a4972a6cc675b94396c386288d72-31828925858961.png)
3. <strong>［アプリ］</strong>の一覧で、テストするアプリを選択します。
4. <strong>［テストデバイス］</strong>の一覧<strong>で、</strong>アプリのテストに使用するデバイスを選択します。テストデバイスがない場合は、<strong>［テストデバイスを追加］</strong>リンクをクリックして登録できます。
5. <strong>［続行］</strong>をクリックし、画面の案内に従って進めます。

</Accordion>

## アトリビューションリンクを使ったテスト

以下では、アトリビューションリンクを使ってインストールをテストする手順を説明します。アプリがまだ保留中の場合（Google PlayストアやApple App Storeで公開されていない場合）でも、テストできます。

<Accordion title="インストールのアトリビューションのテスト">

インストールをテストすると、AppsFlyer SDKが各メディアソースにインストールを正しく紐付けているか確認できます。

**インストールのアトリビューションをテストするには、次の手順を実行します。**

1. 以下のリンク（AndroidまたはiOS）をコピーし、次のように変更します。

   1. **app\_id**の値：AppsFlyerに登録したアプリIDを指定します。
   2. **pid**パラメータ：インストールを紐付けるメディアソース名を指定します。
   3. **c**パラメータ：キャンペーン名を指定します。
   4. サードパーティのAndroidアプリストアで配信するアプリをテストする場合は、アトリビューションリンクに<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links">af\_rパラメータ</Anchor>を追加します。
   5. GAID、IDFA、IDFVを、使用するデバイスの識別子に置き換えます。

   <Tabs>
   <Tab title="Android">

   ```
   https://app.appsflyer.com/<0>?pid=Test&c=Test&advertising_id=<1>
   ```

   </Tab>

   <Tab title="iOS">

   IDFA

   ```
   https://app.appsflyer.com/<0>?pid=Test&c=Test&idfa=<1>
   ```

   IDFV

   ```
   https://app.appsflyer.com/<0>?pid=Test&c=Test&idfv=<1>
   ```

   </Tab>
   </Tabs>

   具体的な値を指定したアトリビューションリンクの例を以下に示します。

   <Tabs>
   <Tab title="Android">

   ```

   ```

   ```
   https://app.appsflyer.com/com.my.app?pid=Test&c=Test&advertising_id=12345f9*-eba*-421*-876*-7654ac67876*
   ```

   </Tab>

   <Tab title="iOS">

   ```

   ```

   ```
   https://app.appsflyer.com/id123456789?pid=Test&c=Test&idfa=1A2B****-9128-4***-123*-04E***654321
   ```

   </Tab>
   </Tabs>

> 📘 **Note**
>
> テストデバイスを登録せずにiOSアプリをテストすると、Protect360によってテストのクリックが不正と判定される場合があります。
>
> 不正と判定されないように、リンクに次のクエリパラメータを追加します：pid=ios\_testing

1. 変更したリンクをコピーしてテストデバイスに送信し、リンクをクリックします。

> 📘 **Note**
>
> iOSでは、iMessageまたはメールでデバイスにリンクを送信してください。 iOSの「メモ」アプリにリンクを貼り付けてクリックしないでください。この操作によって、リンクが正しく機能しなくなる場合があります。

1. 次のいずれかを実行します。

   * アプリが公開済みの場合は、そのままインストールします。
   * アプリが保留中の場合は、「*お探しのアプリはまだストアで公開されていません。*」というメッセージが表示されます。これは正常な動作です。アプリが公開されていないため、アトリビューションリンクからアプリストアには移動しません。ただし、リンクはアトリビューションに利用できるため、次の方法でアプリをインストールしてください。
     * **Androidの場合：** APKファイルからインストールします。開発者はAndroid Studioからインストールすることもできます。
     * **iOSの場合：** TestFlightからインストールします。開発者はXcodeからインストールすることもできます。

   **Test**というメディアソースのテストキャンペーンに紐付いたインストールが表示されます。アプリのダッシュボードにインストールが表示されるまで、最大30分かかります。

   [![Test_Install_Attribution_Link](https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png)](https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png)

> 👍 **Tip**
>
> テスト結果は、次の方法でも確認できます。
>
> * ローデータレポートへのアクセス権がある場合は、インストールのローデータレポートをダウンロードします。レポートのダウンロードには、数分かかります。**レポートのダウンロード手順：**
>   1. AppsFlyerのサイドメニューから、**［レポート］**＞<strong>［ローデータ出力］</strong>を選択します。
>   2. <strong>［ユーザー獲得（非オーガニック）］</strong>の一覧で<strong>［インストール］</strong>をクリックし、レポートをダウンロードします。
> * デバッグログにアクセスできる場合は、コンバージョンデータ取得API（Get the conversion data API）を使って、特定のインストールのアトリビューション結果を取得できます。

</Accordion>

<Accordion title="アプリ内イベントのアトリビューションのテスト">

アプリ内イベントをテストすると、イベントに関連付けられた収益が表示されることと、インストールを獲得したメディアソースにアプリ内イベントが紐付けられていることを確認できます。

**アプリ内イベントのアトリビューションをテストするには、次の手順を実行します。**

1. アプリを起動し、いくつかのアプリ内イベントを発生させます。
2. アプリのアクティビティダッシュボードを開き、イベントが表示されていることを確認します。  
   イベント、イベントに関連する収益（収益がある場合）、紐付けられたメディアソースが表示されます。ダッシュボードにイベントが表示されるまで、最大60～70分かかります。

**ヒント：** <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">アプリ内イベントのローデータレポート</Anchor>をダウンロードし、イベントが正しく紐付けられているか確認することを推奨します。レポートのダウンロードには、数分かかります。

**レポートのダウンロード手順：**

1. AppsFlyerのサイドメニューから、**［レポート］**＞<strong>［ローデータ出力］</strong>を選択します。
2. <strong>［ローデータレポート］</strong>セクションで、アプリ内イベントのローデータレポートをダウンロードします。

</Accordion>

<Accordion title="OneLinkのテスト">

OneLinkでは、AndroidとiOSの両方に対応するアトリビューションリンクを1つ作成できます。 OneLinkはユーザーのデバイスを識別し、適切なアプリストアにリダイレクトします。

また、OneLinkはディープリンクにも対応しています。ディープリンクでは、ユーザーに合わせたコンテンツを表示しながら、アプリの特定の画面を開けます。

詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">OneLink URLのテスト</Anchor>のガイドを参照してください。

</Accordion>

## アトリビューションリンクを使ったリターゲティングのテスト

以下では、リターゲティングのアトリビューションをテストする手順を説明します。

<Accordion title="リターゲティングテストの概要">

ユーザーがリターゲティング用のアトリビューションリンクをクリックしてキャンペーンに接触すると、リターゲティングのアトリビューションが行われます。この結果、リアトリビューションまたはリエンゲージメントのイベントが発生します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティングのアトリビューションガイド</Anchor>を参照してください。

リターゲティングのテストには、次のものがあります。

* [**リアトリビューション：**](/docs/testing-the-sdk-integration-for-marketers#test-reattribution)アプリをアンインストールし、再インストールします。その後、ダッシュボードでインストールが記録されたことを確認します。
* [**リエンゲージメント：**](/docs/testing-the-sdk-integration-for-marketers#test-reengagement)リターゲティング用のアトリビューションリンクまたはディープリンクをクリックし、正しいメディアソースにリエンゲージメントが紐付けられていることを確認します。

</Accordion>

<Accordion title="リターゲティングテストの事前準備">

リターゲティングをテストする前に、次の設定が必要です。

* テスト対象のアプリで、リターゲティングを有効にします。
* アプリ専用リンクを作成するか、OneLinkのカスタムリンクを取得します。リンクには、リターゲティング用のパラメータを含める必要があります。

**リターゲティングテストの設定手順：**

1. アプリの設定でリターゲティングを有効にします。

   アプリのダッシュボードで<strong>［アプリ設定］</strong>をクリックし、<strong>［リターゲティングのアトリビューションを有効にする］</strong>をオンにします。

   ![Set_Reattribution_window](https://files.readme.io/1fe0c8c4add90c75237b0c5c97b6ff26d8f08ff95bd952912ef746fdec2e9f3d-31828933628561.png)
2. 次のいずれかを実行します。
   * アプリ専用のアトリビューションリンクを作成します。リターゲティング用のパラメータ`is_retargeting=true`と広告IDを必ず含めてください。 GAID、IDFA、IDFVの確認方法は、<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">テストデバイスの登録</Anchor>の手順を参照してください。    
     デバイス識別子として、Android用のパラメータ（GAID）を含むアトリビューションリンクの例を以下に示します。 IDFAやIDFVなど、その他のデバイス識別子のパラメータの追加方法は、<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#ios専用のパラメータ">アトリビューションリンクの構造とパラメータ</Anchor>を参照してください。

     ```
     https://app.appsflyer.com/<0>?pid=Test&c=Test&is_retargeting=true&advertising_id=<1>
     ```
   * <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">カスタムリンクのロングURL</Anchor>を、<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>から取得します。<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">［リターゲティングキャンペーン］</Anchor>を必ず有効にしてください。以下の画像は、カスタムリンクのロングURLの例です。 ![Testing_LongLink_en-us.png](https://files.readme.io/19c706b0cc11b83a5cb08d51b3418654c6fa1e597ee7ff9e631db21c33c00b82-31828933632401.png)

ここまでの設定が完了したら、リアトリビューションとリエンゲージメントをテストできます。

</Accordion>

<Accordion title="リアトリビューションのテスト">

**開始前の準備：**

* リターゲティングテストの設定[手順](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)に従います。
* デバイスがテストデバイスとして**登録されていない**ことを確認してください。

**リアトリビューションをテストするには、次の手順を実行します。**

1. デバイスからアプリをアンインストールします。インストールしたばかりの場合は、数分待ちます。
2. 事前に作成した[アトリビューションリンク](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)（アプリ専用のアトリビューションリンク、またはOneLinkテンプレートのカスタムリンクのロングURL）をコピーしてテストデバイスに送信し、リンクをクリックします。

> 📘 **Note**
>
> iOSでは、iMessageまたはメールでデバイスにリンクを送信してください。 iOSの「メモ」アプリにリンクを貼り付けてクリックしないでください。この操作によって、リンクが正しく機能しなくなる場合があります。

1. 次のいずれかを実行します。
   * アプリが公開済みの場合は、そのままインストールします。
   * アプリが保留中の場合は、次の方法でインストールします。
     * **Androidの場合**：Android StudioまたはAPKファイルからインストールします。
     * **iOSの場合：** TestFlightからインストールします。
2. アプリのダッシュボードを開き、<strong>［表示タイプ］</strong>で<strong>［リターゲティング］</strong>を選択します。
3. <strong>［アトリビューションタイプ］</strong>で<strong>［リアトリビューション］</strong>を選択します。

   メディアソースとキャンペーンに紐付いたインストールが表示されます。リターゲティングによるインストールがダッシュボードに表示されるまで、最大30分かかります。

   [![Testing_SDK_Reattribution](https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png)](https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png)

> 👍 **Tip**
>
> テスト結果は、次の方法でも確認できます。
>
> * ローデータレポートへのアクセス権がある場合は、コンバージョンのローデータレポートをダウンロードします。レポートのダウンロードには、数分かかります。**レポートのダウンロード手順：**
>   1. AppsFlyerのサイドメニューから、**［レポート］**＞<strong>［ローデータ出力］</strong>を選択します。
>   2. <strong>［リターゲティング］</strong>の一覧で<strong>［コンバージョン（リエンゲージメントとリアトリビューション）］</strong>をクリックし、レポートをダウンロードします。
> * デバッグログにアクセスできる場合は、SDK実装テストAPIを使って、特定のインストールのアトリビューション結果を取得できます。

</Accordion>

<Accordion title="リエンゲージメントのテスト">

**開始前の準備：**

* リターゲティングテストの設定[手順](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)に従います。
* テストでは、コンバージョン間の最短間隔を<strong>［なし（None）］</strong>に設定します。これにより、テスト中のすべてのリエンゲージメントコンバージョンを記録し、紐付けられます。 ![Testing_Reattribution_window](https://files.readme.io/ec8c7c923093dbed0e99aa5ef57d0239217ead5a9db41f42fe4af8a70eb04551-4406211661841.png)
* テストデバイスにアプリがインストールされ、複数回起動されていることを確認します。インストールしたばかりの場合は、数分待ちます。

**リエンゲージメント（直接ディープリンク）をテストする方法：**

アプリに<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">ディープリンク</Anchor>が設定されていることを確認し、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">こちらの手順</Anchor>に従ってテストします。

**リエンゲージメント（間接ディープリンク）をテストする方法：**

1. 事前に作成した[アトリビューションリンク](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)（アプリ専用のアトリビューションリンク、またはOneLinkテンプレートのカスタムリンクのロングURL）をコピーします。
2. リンクをテストデバイスに送信し、クリックします。
3. 次のいずれかの方法でアプリを開きます。

   * アプリストアで<strong>［開く］</strong>をクリックします。
   * デバイスからアプリを起動します。

   ダッシュボードに、メディアソースとキャンペーンに紐付いたリエンゲージメントが表示されます。リエンゲージメントが表示されるまで、最大30分かかります。

   [![Testing_SDK_Re-engagement](https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png)](https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png)

**ヒント：** コンバージョンのローデータレポートをダウンロードし、リエンゲージメントが正しいメディアソースに紐付けられているか確認することを推奨します。レポートのダウンロードには、数分かかります。

**レポートのダウンロード手順：**

1. AppsFlyerのサイドメニューから、**［レポート］**＞<strong>［ローデータ出力］</strong>を選択します。
2. <strong>［リターゲティング］</strong>セクションで、<strong>［コンバージョン（リエンゲージメントとリアトリビューション）］</strong>レポートをダウンロードします。

</Accordion>

## オーガニックインストールのテスト

最初にオーガニックインストールをテストすることを推奨します。

**オーガニックインストールをテストするには、次の手順を実行します。**

1. <Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">登録済みのテストデバイス</Anchor>にアプリをインストールします。
2. アプリを起動します。

アプリのダッシュボードに、新しいオーガニックインストールが表示されます。インストールが表示されるまで、最大30分かかります。

[![](https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png)](https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png)

## CTVのテスト

特殊なテストケースには、次のものがあります。

* **Android TV：** SDKは、Androidベースのスマートテレビに対応しています。マーケターやチームメンバーは、この記事の手順に従って、これらのテレビ向けアプリをテストできます。
* **Apple TV（tvOS）：** SDKは、Apple TV（tvOS）に対応しています。マーケターやチームメンバーは、この記事の手順に従って、これらのテレビ向けアプリをテストできます。
* **未公開のtvOSアプリ：** マーケターと開発者が協力してテストする必要があります。<Anchor target="_blank" href="/marketers/ja/docs/testing-tvos-integration-before-publishing">公開前のtvOS実装テスト</Anchor>を参照してください。
* **Amazon Fire TV：** マーケターは、AppsFlyerダッシュボードのAndroid SDKのテスト方法を使って、[実装をテスト](/docs/testing-the-sdk-integration-for-marketers#testing-from-the-dashboard)できます。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/setting-up-amazon-fire-tv-ad-attribution">Amazon Fire TVのアトリビューション</Anchor>を参照してください。
* **PBAのWebイベント：** マーケターと開発者が協力してテストする必要があります。<Anchor target="_blank" href="/marketers/ja/docs/test-pba-web-sdk-integration">PBAのWeb SDK実装テスト</Anchor>を参照してください。

> 📘 **Note**
>
> 関連記事
>
> * アドネットワーク連携のテスト アドネットワーク連携のテスト

## 仕様と制限事項

| 項目 | 補足 |
| --- | --- |
| テスト用リンク | 登録済みテストデバイスを使用する場合は、テスト用リンクから`af_inactivity_window`パラメータを削除してください。削除しないと、テスト用リンクに紐付くはずのインストールが、誤って*オーガニック*に紐付けられる場合があります。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01H88X11QS2VYFXJGC95TXC6PN=%E6%A6%82%E8%A6%81 testing-using-the-sdk-integration-tests-page=sdk%E5%AE%9F%E8%A3%85%E3%83%86%E3%82%B9%E3%83%88%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%86%E3%82%B9%E3%83%88 h_01HYX9R159XMZKMH1MBMBH9K9J=sdk%E5%AE%9F%E8%A3%85%E3%83%86%E3%82%B9%E3%83%88%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%86%E3%82%B9%E3%83%88 prepare-a-test-device=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E6%BA%96%E5%82%99 h_01J9GTS4S2RXJAMYGG6XJ5HFRZ=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E6%BA%96%E5%82%99 perform-the-integration-tests=%E5%AE%9F%E8%A3%85%E3%83%86%E3%82%B9%E3%83%88%E3%81%AE%E5%AE%9F%E8%A1%8C h_01J9GTW7RAGZXE7GK5BWGBA7N5=%E5%AE%9F%E8%A3%85%E3%83%86%E3%82%B9%E3%83%88%E3%81%AE%E5%AE%9F%E8%A1%8C testing-using-attribution-links=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%86%E3%82%B9%E3%83%88 01H88X11QT0WDRW5GZDCR7MZ3D=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%86%E3%82%B9%E3%83%88 testing-retargeting-using-attribution-links=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 01H88X11QTQ94BAJGEE1V11F6X=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 testing-organic-installs=%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01HYX9R1594DD9BEZ6PMV9PJM8=%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 Testing%20CTV=ctv%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 01H88X11QT72F71N49G65BAEAE=ctv%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
