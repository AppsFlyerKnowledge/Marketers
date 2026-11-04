---
title: 'Liftoff: AppsFlyerとの計測連携'
metadata:
  keywords:
    - liftoff
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-28T09:38:23Z'
  edited_at: '2026-10-14T09:27:57Z'
  id: 209731633
  locale: ja
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ja/articles/209731633
---
> **概要：** AppsFlyerの連携済みパートナーであるLiftoffは、ブランドやアプリ開発者にとって最も需要の高いパートナーの1つです。Liftoffでは、クリックベースとビュースルーのモバイルアトリビューションとリターゲティングを提供しており、これらはAppsFlyerで計測可能です。

![](https://cdn.appsflyer.com/marketplace/static/logo/liftoff.png)

<div id="important" />

> 🚧 **重要！**
>
> 一部のメディアソースは、第三者とのデータ共有を制限しています。AppsFlyerでは、これらのメディアソース経由で獲得したユーザーに関するユーザーレベルデータを第三者プラットフォームやサービスと共有できません。そのため、このようなメディアソースからのインストールはオーガニックとして送信されます。
>
> 第三者プラットフォームとのデータ共有を制限しているメディアソースの詳細とリストに関しては、<Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention">こちら</Anchor>をクリックしてください。

<div id="setting-up-liftoff" />

## Liftoffの連携設定

**前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer のサイドメニューから**共同作業** > **パートナー・マーケットプレイス**の順で選択します。  
   **編集方法：** AppsFlyer のサイドメニューから、 **共同作業** > **連携を有効にする**の順で選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注意：** トグルは、パートナーと作業している間、オン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>にしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

連携タブは次のセクションに分かれています。

<div id="activate-partners" />

### パートナーの有効化

連携設定を有効にするには、最初の訪問時に [<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#パートナー統合を有効にする">**パートナーを有効にする**</Anchor> ]のトグルをオンにして、パートナーをアクティブ化する必要があります。

<div id="general-settings" />

### 一般的な設定

**ビュースルーアトリビューションの有効化**

Liftoffにおいてビュースルー計測を有効化したい場合には、設定をONにしてください。ビュースルー計測のルックバック期間の設定は、 [**計測リンク**](/docs/liftoff-campaign-configuration-in-appsflyer#attribution-link-tab) タブで行ってください。

<div id="default-postbacks" />

### デフォルトのポストバック

Liftoffに対してインストール、ブロック済みインストール、リエンゲージメントの自動ポストバックを行えます。このセクションでは、これらのポストバックの**送信を許可するユーザー**を定義してください。

Liftoff に紐付いたユーザーからのイベントのみを送信する場合は、[ **This partner only** ] を選択してください。  
全ユーザーのデータをLiftoffへ送信する場合には、 **[All sources, including organic** ] を選択してください。

<div id="note" />

> 📘 **注意**
>
> 全てのインストールデータを受信できるネットワークであるLINEは、オーガニックを含む全てのメディアソースに紐づく新規インストールのポストバック受信を希望しています。そのためには、**オーガニックを含む全てのパートナーに紐づくイベント**を選択し、全てのインストールポストバックを Liftoff に送信してください。

**アプリ内イベントポストバックを設定する：**

1. **アプリ内イベントのポストバック**を有効にしてください。
2. **選択したイベントのみを**パートナーに送信するか、**全てのイベントすべての** イベントを報告するかを選択します。
   * 注記：注：すべてのイベントを送信するオプションを選択した場合でも、af\_app\_openedのイベントその中に含まれません。
3. イベントを手動で選択する場合は、[ **イベントを追加** ]をクリックして、SDKイベントをリストに追加してください。
4. 以下の情報を入力してください。 

| パラメーター名 | 説明 |
| --- | --- |
| **SDKイベント**(手動追加の際のみ必要) | SDKもしくはS2SによりAppsFlyerが受け取ったイベント名  <br />**ヒント：** ヒント：アプリ内イベント名がリストに表示されない場合、非オーガニックインストールに紐づく形でそのアプリ内イベントが発生させてから、再確認してください。 |
| <strong>送信オプション</strong> | イベントの送信オプションを選択してください：  <br />Liftoff に紐付いたユーザーからのイベントのみを送信する場合は、[ This partner only ] を選択してください。  <br />全ユーザーのデータをLiftoffへ送信する場合には、 <strong>[All sources, including organic</strong> ] を選択してください。 |
| **イベント値を送信** | <ul><li>**No values & no revenue**：イベント値なしでイベント名のみを送信します。</li><li>**Values & no revenue**：収益値以外のすべてのパラメータを送信します。</li><li>**Values & revenue**：収益値（イベントに存在する場合）を含むすべてのイベントパラメータを送信します。</li></ul> |

5. **保存**をクリックしてください。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

アトリビューションリンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたは<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>のいずれかを使用できます。  
<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構造とパラメーターについての詳細は、こちらをご覧ください</Anchor>。  

**計測リンクを作成**するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">次の手順</Anchor>に従ってください。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

AppsFlyerはコストの詳細をAPIで取得します。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークのコスト連携に関する表</Anchor>を参照してください。　**注意**：コストデータの取得にはROI360のご契約が必要です。

**コストAPIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

広告収益データはこのパートナーではサポートしていません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブではLiftoffに対して付与する権限を選択できます。パートナーの計測設定が無効になっている場合でも、権限タブは使用可能で、パートナーに対して権限付与できます。

<div id="ad-network-permissions" />

### アドネットワークへの権限付与

このタブではLiftoffに対して付与する権限を選択できます。パートナーの計測設定が無効になっている場合でも、権限タブは使用可能で、パートナーに対して権限付与できます。

これらのトグルを使用して、アプリごとにアドネットワークへの権限付与を設定してください：

* **パートナー連携の設定を許可する** - パートナーに連携タブの設定（アプリ内イベントのポストバックを除く）を許可します。
* **アプリ内イベントのポストバック設定を許可する** - 連携タブでアプリ内イベントのポストバックをマッピングする設定をパートナーに許可します。
* **リテンションレポートへのアクセスを許可** - パートナーのリテンションデータへのアクセスを許可します。
* **リテンションレポートへのアクセスを許可する**  - このパートナー経由のロイヤルユーザーデータのみへアクセスを許可します。
* **アプリ内イベント集計データへのアクセスを許可する** - このパートナー経由のアプリ内イベントデータのみへアクセスを許可します。
* **収益集計データへのアクセス権限を許可する**‐ このパートナーに紐づく収益データのみへアクセスを許可します。
* **Protect360管理画面へのアクセスを許可する** - 広告主がProtect360機能を利用している場合、パートナーのProtect360データへアクセスを許可します。

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>をご覧ください。

<div id="agency-permissions" />

### 代理店の許可

Liftoffを代理店として扱う場合に、このセクションではアプリの設定を処理する権限をLiftoffの代理店アカウントに対して与えることができます。

* 代理店への権限付与 ‐ これをオンにすると：  
  * 代理店の権限のオプションが表示されます。
  * 代理店がアプリのインストール成果を獲得できるようになります。要注意警告：このトグルがオフになっている間に発生した代理店経由のインストールは、代理店の成果に紐づかず、代理店の管理画面やデータにも表示されません（詳細はこちら/strong>）。

* **Protect360管理画面へのアクセスを許可する**
* **リテンションとコホートレポートへのアクセス権限付与**：代理店が獲得したユーザーのリテンション／コホートデータのみへアクセスを許可します。
* **オーガニック集計データへのアクセスを許可します。**
* **アプリ内イベントのポストバック設定を許可する**：代理店に連携タブでアプリ内イベントのポストバックをマッピングする権限を許可します。
  * **イベントポストバック権限** - ２つあるオプションから選択してください。  
    **このパートナーのみ：** 代理店が獲得したトラフィックから発生したイベントのみを送信します。  
    **オーガニックを含む全てのメディアソース：** 他のメディアソースや代理店、オーガニックユーザーを含む全てのメディアソースのトラフィックからのイベントを送信します。
  * **収益のポストバック設定を許可する**：代理店が収益額を含むイベントデータを送信することを許可します。
  * 代理店に権限を許可するイベント名を必ず選択してください。**イベントを追加**をクリックして、ドロップダウンからイベントを選択します。 追加したいイベントごとにこの作業を行います。

<Anchor target="_blank" href="/partners/ja/docs/about-agency-accounts">代理店との連携</Anchor>について詳細はこちら。

</Accordion>


3. <span id="set-up-skadnetwork-integration-with-liftoff"></span>例：

<div id="product-feed-retargeting-with-liftoff" />

## Liftoffでのプロダクトフィードのリターゲティング

商品関連のイベント計測を正しく機能させるためには、Liftoffは各イベントに関連付けられた製品IDを受け取る必要があります。たとえば、ユーザーが商品を購入したり、カートに追加したりした際のその商品のIDです。

これらのIDは、プロダクトフィード内でLiftoffに渡すIDと一致させる必要があります。Liftoffでは、 <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#定義済みのイベントパラメータ">af\_content\_id</Anchor> のパラメータを使うことでAppsFlyerのデータ共有の標準規約をサポートしています。

スタンダードではないイベントのデータ実装を行っている場合には、Liftoff の担当に連絡して、連携が可能かどうかを確認してください。

<div data-zendesk-anchors="h_01HGFR9QYBQ3BK3TM364SJDKWZ=%E9%87%8D%E8%A6%81 setting-up-liftoff=liftoff%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HGFR9QYBPY2XR4KMWMJKHHMQ=liftoff%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HGFR9QYBJG0WD6X203X8MYFV=integration-tab activate-partners=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HGFR9QYBXAQQKPRW1KKF6989=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01HGFR9QYBPCYCJRY20S1TCF6R=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HGFR9QYB8JHTAAB591QQ1P6J=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HGFR9QYBW8DFZK63EZ3V5622=%E6%B3%A8%E6%84%8F h_01HGFR9QYB42YK8FJD308YWXC7=attribution-link-tab h_01HGFR9QYBJ20T4F0W5486B4NW=cost-tab h_01HGFR9QYBV9ZCGJ1D6BD1T9JG=ad-revenue-tab h_01HGFR9QYB9DA5XYXPEARZSCHF=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E h_01HGFR9QYB0VCPG7YCX64BBKY9=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E agency-permissions=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF h_01HGFR9QYBR3W0JXY7MHQ8PZT7=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF h_01HGFR9QYBG4830DKGMGV716B7=set-up-skadnetwork-integration-with-liftoff product-feed-retargeting-with-liftoff=liftoff%E3%81%A7%E3%81%AE%E3%83%97%E3%83%AD%E3%83%80%E3%82%AF%E3%83%88%E3%83%95%E3%82%A3%E3%83%BC%E3%83%89%E3%81%AE%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01HGFR9QYB302DVBYXMK0XY4ED=liftoff%E3%81%A7%E3%81%AE%E3%83%97%E3%83%AD%E3%83%80%E3%82%AF%E3%83%88%E3%83%95%E3%82%A3%E3%83%BC%E3%83%89%E3%81%AE%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0" />
