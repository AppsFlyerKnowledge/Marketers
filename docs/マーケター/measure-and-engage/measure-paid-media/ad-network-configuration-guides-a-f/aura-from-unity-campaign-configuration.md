---
title: Aura from Unityキャンペーン設定
metadata:
  keywords:
    - Campaign
    - Advertisers
    - Agencies
    - aura
    - ironsource
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2020-01-27T11:23:49Z'
  edited_at: '2026-10-14T09:25:30Z'
  id: 360005208578
  locale: ja
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ja/articles/360005208578
---
> **概要：概要： AppsFlyerアドネットワーク連携済みパートナーであるAura from Unityは、ユーザーが新しいデバイスをセットアップする際に、広告主がユーザーとつながることができるプラットフォームです。**

<Image align="center" alt="aura_logo.png" src="https://files.readme.io/83bca93f3dfe8f6ce9bd74b9141b8c3b4dc01cfcf8f1904c0f992346beee5014-17313206447889.png" />

<div id="aura-from-unity-integration-in-appsflyer" />

## AppsFlyerでのAura from Unityの連携

**前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer のサイドメニューから**共同作業** > **パートナー・マーケットプレイス**の順で選択します。  
   **編集方法：** AppsFlyer のサイドメニューから、 **共同作業** > **連携を有効にする**の順で選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注意：** トグルは、パートナーと作業している間、オン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>にしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

次のセクションでは各タブの説明をしています。

<div id="integration-tab" />

<Accordion title="連携タブ">

連携タブで連携を有効にし、パラメーターを設定し、Aura from Unityと接続します。

**連携を設定する方法**：

1. **パートナーを有効にする**をオンにしてください。
2. **一般設定**にて**ビュースルー計測**を有効／無効にしてください。
   * [デフォルト] 有効：ビュースルー計測をアクティベートしてインストール成果をAura from Unityに紐づけます。ルックバック期間は**計測リンク**タブで設定できます。
   * 無効：このパートナー経由のビュースルーインストールは計測されません。
3. **デフォルトのポストバック**はAura from Unityに送信されます：
   * インストールインストール：ユーザーがアプリをインストールするたびにポストバックが送信されます。Aura from Unityに紐づけられたユーザーに対してのみポストバックを送信するか、オーガニックインストールを含むすべてのユーザーに対してポストバックを送信するか選択してください。
   * 拒否されたインストール拒否されたインストール：**Protect360**を利用すると、<Anchor target="_blank" href="/partners/ja/docs/rejected-attribution-postbacks-to-integrated-partners">不正によりインストールが拒否された</Anchor>際にポストバックが送信されます。Aura from Unityに紐づけられたユーザーのみがレポートの対象になります。
4. アプリ内イベントの設定以下のようにパラメーターを設定してください。
   * **アプリ内イベントポストバック**を有効にしてください。
   * 送信オプション: 送信オプション：**このパートナーに紐づくイベントのみ**、またはオーガニックインストールを含む**全てのパートナーに紐づくイベント**を送信するかを選択してください。
   * **イベントを追加** をクリックしてSDKイベントをリストに追加してください。以下の表で説明されているパラメーターを入力してください。

| 設定名 | 説明 |
| --- | --- |
| SDKイベント名 | AppsFlyerが以下のいずれかから受信するイベント名：<ul><li>アプリに実装されているSDK</li><li>サーバー間 (S2S) イベント</li></ul>**ヒント：ヒント：必要なイベントがリストに表示されない場合、デバイス上で非オーガニックインストールを実行し、再度確認してください。** |
| パートナー側のイベント名 | Aura from Unityが定義した一意のイベント名またはID。<br /><br />イベントに最も近いイベント名をドロップダウンリストから選択してください。 |
| 収益を送信 | [デフォルト]**有効になっていない場合：** 収益パラメーター (`af_revenue`af\_revenueaf\_revenue) を除くすべてのアプリ内パラメーターをAura from Unityに送信します。<br /><br />**有効の場合：** 収益額を含む（利用可能な場合）すべてのアプリ内パラメーターを送信します。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

アトリビューションリンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UAおよびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたは<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>のいずれかを使用できます。<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構造とパラメーターについての詳細は、こちらをご覧ください</Anchor>。**計測リンクを作成**するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">次の手順</Anchor>に従ってください。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

AppsFlyerはコストの詳細をAPIで取得します。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークのコスト連携に関する表</Anchor>を参照してください。　**注意**：コストデータの取得にはROI360のご契約が必要です。

**コストAPIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

コストデータをサポートしているすべてのパートナーのリストについては、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">こちら</Anchor>を参照してください。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

広告収益アトリビューションはこのパートナーでは利用できません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

Aura from Unityが情報を閲覧し、連携内容を変更する権限を付与することができます。権限の種類はAura from Unityとのビジネス関係（アドネットワーク／広告代理店）により異なります。

**注！ Aura from Unityとのアクティブな連携がない場合でも、Aura from Unityに権限を付与することは可能です。**

<div id="ad-network-permissions" />

<Accordion title="アドネットワークへの権限付与">

**広告ネットワークの権限を有効にするには**：

1. **アドネットワーク権限**を有効にしてください。
2. Aura from Unityのチームメンバーに、以下から1つ以上のアクセス権を付与する。
   * パートナー連携の設定を許可するアプリ内イベントのポストバックを除き、パートナーにインテグレーションタブの設定を許可します。
   * アプリ内イベントのポストバックを許可する
   * リテンションレポートへのアクセスを許可する
   * 集計レベルのロイヤルユーザーデータへのアクセスを許可
   * アプリ内イベントの集計データへのアクセス権限を付与する
   * 集計収益データへのアクセス権限を付与する
   * コストデータのアップロードを許可する
   * Protect360管理画面へのアクセスを許可する

</Accordion>

</Accordion>

<div data-zendesk-anchors="aura-integration-in-appsflyer=appsflyer%E3%81%A7%E3%81%AEaura-from-unity%E3%81%AE%E9%80%A3%E6%90%BA h_01HKW9GGARZY4X1FAA6BD89K5N=appsflyer%E3%81%A7%E3%81%AEaura-from-unity%E3%81%AE%E9%80%A3%E6%90%BA h_01HKW9GGAR9CWWYGRH6C1EMFVM=integration-tab h_01HKW9GGAR9CVKH192FN4P9YND=attribution-link-tab h_01HKW9GGARNCSQ0TAV69550BS8=cost-tab h_01HKW9GGAR0TET4Q5284NHFM7R=ad-revenue-tab h_01HKW9GGAR5ZTPA9R49WN5P7P4=permissions-tab h_01HKW9GGAREEN9YQ065D1ZX1AQ=ad-network-permissions" />
