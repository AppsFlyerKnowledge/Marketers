---
title: Awinキャンペーン設定
metadata:
  keywords:
    - Advertisers
    - Quora
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-02-17T12:56:30Z'
  edited_at: '2026-10-14T09:37:36Z'
  id: 360000974737
  locale: ja
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ja/articles/360000974737
---
> **概要：**

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/quora.png?v=1" width="83px" />


**<span id="setting-up-quora"></span>前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer のサイドメニューから**共同作業** > **パートナー・マーケットプレイス**の順で選択します。  
   **編集方法：** AppsFlyer のサイドメニューから、 **共同作業** > **連携を有効にする**の順で選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注意：** トグルは、パートナーと作業している間、オン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>にしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

<div id="tip" />

> 👍 **ヒント**
>
> * 連携タブでの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#d-general-settings">一般的な設定</Anchor>の項目は、全てのパートナーにおいて**必須**です。
> * その他すべてのステップは、説明的または**任意**の設定です。

<div id="integration-tab" />

<Accordion title="連携タブ">

<div id="note" />

<div id="activate-partner" />

### パートナーの有効化

このタブを**初めて**開く場合、連携タブのパラメーター設定を有効にするために*パートナーを有効にする*のトグルをオンにする必要があります。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーの有効化についての詳細は、 <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をご覧ください。

Default Postback（デフォルトのポストバック）

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

アトリビューションリンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたは<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>のいずれかを使用できます。  
<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構造とパラメーターについての詳細は、こちらをご覧ください</Anchor>。  

**計測リンクを作成**するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">次の手順</Anchor>に従ってください。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

Twitterでは、広告収益の連携はサポートしておりません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブでは、パートナーがアドネットワークの場合、代理店の場合、または両方の場合に、MoPub に付与する権限を選択できます。MoPubのアトリビューションが無効になっている場合でも、権限タブはアクティブであり、MoPub に権限を付与することができます。

これらのトグルを使用して、アプリごとにアドネットワークへの権限付与を設定してください：

<div id="ad-network-permissions" />

### アドネットワークへの権限付与

* ***パートナー連携の設定を許可する*** - パートナーに連携タブの設定（アプリ内イベントのポストバックを除く）を許可します。
* ***アプリ内イベントのポストバック設定を許可する*** - 連携タブでアプリ内イベントのポストバックをマッピングする設定をパートナーに許可します。
* ***リテンションレポートへのアクセスを許可*** - パートナーのリテンションデータへのアクセスを許可します。
* ***リテンションレポートへのアクセスを許可する***  - このパートナー経由のロイヤルユーザーデータのみへアクセスを許可します。
* ***アプリ内イベント集計データへのアクセスを許可する** -* このパートナー経由のアプリ内イベントデータのみへアクセスを許可します。
* ***収益集計データへのアクセス権限を許可する***‐ このパートナーに紐づく収益データのみへアクセスを許可します。
* ***Protect360管理画面へのアクセスを許可する*** - Protect360のデータへのアクセスを許可します（パートナーのデータのみ）。＜広告主がProtect360に申込みしている場合のみ＞

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>をご覧ください。

</Accordion>

<div data-zendesk-anchors="h_01HKW851RK4MHYEW1AY2E2KH5Q=setting-up-quora h_01HKW851RK9KMV6PJ7YEN7ZMW2=%E3%83%92%E3%83%B3%E3%83%88 h_01HKW851RKYQ0T9XY74EXB4GWX=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW851RKD56502S4PSX8096T=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW851RM09VR496Q7XFB3EMY=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKW851RM4HP8EVGKD2EJH529=attribution-link-tab h_01HKW851RM4DGBABR81ZJZHBYW=cost-tab h_01HKW851RMQ0KY4CMWP7N4F2T4=ad-revenue-tab h_01HKW851RMV5A43RS3ZFZEPW8Z=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E h_01HKW851RM2G6Y4J4KQBHAEF3A=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E" />
