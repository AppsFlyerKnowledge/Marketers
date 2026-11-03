---
title: Persona.ly RTB キャンペーン設定
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-09-20T07:13:43Z'
  edited_at: '2026-10-14T09:34:49Z'
  id: 18699025653265
  locale: ja
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ja/articles/18699025653265
---
> **概要：**

<Image alt="persona.ly_logo.png" src="https://files.readme.io/b0dacbdc4c2e884610a040b5049a1410a88214f8275320163764bcf09f90305b-18699636413969.png" width="234px" />

## Persona.ly RTBの設定

**前提条件：** 連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡し</Anchor>、アカウントを開設してください。

**統合をアクティブ化または編集するには：**

1. **有効にする：** AppsFlyer管理画面左メニュー **コラボレーション**> **Partner Marketplace**を選択します。  
   **編集方法**：AppsFlyerのサイドメニューから、**[コラボレーション]** > **[アクティブ連携]** を選択します。
2. Amazon Adsを検索して選択します。
3. **連携の設定**をクリックします。**連携済みパートナー**設定画面に移動します。
4. **連携**タブで、**パートナーを有効にする**トグルをオンにします。  
   **注：<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーと作業している間は、トグルをオン（</Anchor><Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">アクティブ</Anchor>）にしたままにする必要があります。**
5. 次のセクションで説明されている関連タブを使用して設定を完了します。

Persona.ly RTB との統合により、クリックスルー アトリビューションおよびビュースルー アトリビューションがサポートされます。  
構成には次のタブが含まれます。連携、計測リンク、コスト、広告収益、権限Persona.ly RTBでは、使用可能なタブは、統合、計測リンク、コスト、権限です。

> 📘 **注意**
>
> * iOSとAndroidデバイスでは設定が異なります
> * 詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携の設定</Anchor>のページをご確認ください。

<div id="integration-tab" />

<Accordion title="連携タブ">

**連携**タブには、以下で説明するセクションがあります。

#### 連携設定

連携を設定するには、まず**パートナーを有効にする**トグルを<Anchor target="_blank" href="/marketers/ja/docs/amazon-ads-campaign-configuration#連携設定">オン</Anchor>にする必要があります。詳細：パートナーのアクティブ化と非アクティブ化のページを参照してください。

> 📘 **注意**
>
> Persona.ly RTB は、すべてのインストール ネットワークとして、アプリのすべての新規インストールのポストバックを任意のソースから受け取ることを好みます。これを行うには、**オーガニックを含むすべてのメディアソース**を選択して、すべてのインストールポストバックをPersona.ly RTBに送信します。

#### 高プライバシーポストバック

iOSアプリのみ:ポストバックやレポートを介してパートナーと共有されるデータのコントロールは、<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">高度なプライバシー（ iOS 14.5 以降）</Anchor>**の切り替え状態**によって異なります。

| 高度なプライバシー:：オン | 高度なプライバシー:：OFF |
| --- | --- |
| そのパートナーに紐付いているイベントのみのポストバックが送付されます。 | ご自身で設定された以下の内容に沿った形でポストバックが送付されます：<ul><li>**オーガニックを含む全メディアソース**</li><li>**このパートナーのみ**</li></ul> |
| ポストバックは<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高度なプライバシーテンプレート</Anchor>に従って送信されます。 |  |
| 集計された匿名データがパートナーと共有されます。つまり、ユーザーレベルのデータ（デバイスID）は共有されません。 |  |

#### トランザクションID

#### インストール計測

Persona.ly RTB からのビュースルーインストールをアトリビューションするには、 ビュースルーアトリビューションのインストールをオンにします。ビュースルー計測のルックバックスライダーは、 計測リンク タブで使うことができます。

#### デフォルトのポストバック

アプリ起動前に発生したユーザーアクションに関連するパートナーに自動ポストバックを送信するユーザーのソースを定義します。

* **インストール**で、次のいずれかを選択します。
  * このパートナーのみ：このパートナーのみ: ポストバックを送信するのは、インストールがこのパートナーに紐づいている場合、つまり、このアプリをインストールしたユーザーはPersona.ly RTB からのユーザーです。
  * オーガニックを含むすべてのメディアソース：

#### アプリ内イベントポストバック

ポストバック経由で送信される、アプリ内イベントとPersona.ly RTBイベントのマッピングを設定します。

1. **アプリ内イベントポストバック**を有効にします。
2. **イベントを追加**をクリックして、SDK または サーバー間イベントをリストに追加してください。各項目の説明は以下を参照してください。  

| パラメーター名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>非オーガニックインストールとして計測された端末上で、そのアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor></li></ul> |
| **パートナー側のイベント名** | パートナー側で定義されている各イベントの固有の名前またはID。オプションは以下の通りです：<ul><li>**テキストフィールド：** 対応するイベントIDをパートナーから取得します。</li><li>**ドロップダウンボックス：** 最適な事前定義されたAppsFlyerイベントを選択します。</li><li>**そのまま**：イベント名のマッピングなしで、イベントをそのまま送信します。</li></ul> |
| **送信オプション** | イベントの送信オプションを選択します。<ul><li>**このパートナーのみ**:このイベントがこのパートナーに起因する場合にのみポストバックを送信します。</li><li>**オーガニックを含む全メディアソース**:すべてのイベントを送信：オーガニックを含む全てパートナーに紐づくイベントに対してポストバックを送信します。</li></ul> |
| **送信データ** | <ul><li>**データなし（デフォルト）：** イベント値なしでイベント自体のみを送信します。</li><li>**イベント値と収益：** 収益値を含む全てのイベントパラメーターを送信します（イベント内にある場合）。</li><li>**収益を除いたイベント値：** 収益値以外のすべてのパラメーターを送信します。</li></ul> |

3. [オプション] イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>するには、<Image alt="conditional-iae-postbacks-icon.png条件を追加" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />アイコンをクリックします。
4. 必要に応じて、**アプリ内イベントのポストバック期間**を設定します。（詳細：<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間"> アプリ内イベントのポストバックウィンドウの設定</Anchor>）
5. **連携を保存**をクリックします。
6. [オプション] 連携を保存した後、設定画面に留まりつつ、ほかのアプリ / OSの設定へ進みます。
   1. 左上隅のパートナー名下にあるアプリ名をクリックし、アプリ一覧を開きます。
   2. ドロップダウンリストから別のアプリを選択してください。
   3. 選択したアプリで、連携ステップを再度実施してください。

> 📘 **注意**
>
> iOS アプリの場合のみ:ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を介してパートナーと共有されるデータのコントロールは、**高度なプライバシー（ iOS 14.5 以降）**<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#高プライバシーポストバック">の切り替え状態</Anchor>によって異なります。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたはOneLinkのいずれかを使用できます。 計測リンクの構造とパラメーターについての詳細はこちら 計測リンクを作成するには、次の手順に従ってください。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

AppsFlyerはコストの詳細をAPIで取得します。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークのコスト連携に関する表</Anchor>を参照してください。　**注意**：コストデータの取得にはROI360のご契約が必要です。

**コストAPIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と、AppsFlyerがコスト（および広告収入）統合ステータスのダッシュボード、または個々の広告ネットワークのダッシュボードのいずれかで、一致するコストデータを引き出すことができた最終時刻が表示されます。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

広告収益は Persona.ly RTB ではご利用いただけません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

データにアクセスしてさまざまなアクションを実行するために Persona.ly RTB <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">を付与する許可</Anchor> を選択します。

> 📘 **注意**
>
> 権限のトグルがオンの状態で連携が<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">無効化</Anchor>されても、権限は付与され続けます。

</Accordion>

<div data-zendesk-anchors="setting-up-amazon-dsp-integration=personaly-rtb%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3VENKYVRQY5RXN63P=personaly-rtb%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3BYZSXQGGZZJQ9N0C=%E6%B3%A8%E6%84%8F 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A 01H88VAJH34GP7FK1KTJGRDPM7=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HBB9EEMJ55BQDJ1ZEJT136ZF=%E6%B3%A8%E6%84%8F-1 advanced-privacy=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3G5FAR7RRNDEPNGME=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF transaction-id=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3id h_01HARQDVEDA206D0BBXBC6WEHH=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3id install-attribution=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC h_01HA6PNN6RJYTNXRAS3M9EA4M4=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3WE9Z0971WMBRBJRS=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3AS37MVF75GANWX4B=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH36MYZ9W1YPWA92Z1Z=%E6%B3%A8%E6%84%8F-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%E6%B3%A8%E6%84%8F-3" />
