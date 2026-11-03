---
title: Data Collaboration Platform（DCP）｜メディアパートナーの接続
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2026-04-12T14:19:36Z'
  edited_at: '2026-10-13T08:29:05Z'
  id: 45669216166417
  locale: ja
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ja/articles/45669216166417
---
## 概要

オーディエンスをメディアパートナーへ接続することで、目的に合わせたキャンペーンをアクティベーションし、成果の最大化を図ることができます。

## メディアパートナー接続について

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-guide">Data Collaboration Platform（DCP）</Anchor>のメディアパートナー接続を使用すると、DCPオーディエンスを対応するメディアパートナーへ安全に接続し、各パートナーのプラットフォーム上で目的に合わせたキャンペーンをアクティベーションできます。パートナーをオーディエンスに接続すると、DCPは最新のソースデータと<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#共有権限">権限</Anchor>を使用し、設定された更新・アクティベーションフローに従ってオーディエンスを配信します。

> 📘 **注意**
>
> * オーディエンスは、ユーザー識別子の一覧としてアクティベーション先へ配信されます。各配信には、エクスポート時点のオーディエンス全体のスナップショットが含まれます。
> * オーディエンスの更新は、継続的またはリアルタイムに行われるものではありません。定義されたポリシーに基づく一定の間隔で実行され、ソースデータが更新されているかどうかを確認したうえで更新されます。更新のたびにオーディエンスリストが生成され、選択した送信先へ配信されます。

## 対応するメディアパートナー接続

このセクションでは、DCPが対応しているメディアパートナー接続と、各パートナーの設定要件、必要な権限、対応するキャンペーンタイプ、その他の要件や制限事項について説明します。

<div id="google-ads" />

<Accordion title="Google Ads">

**メディアパートナープラットフォーム：**  
Google Ads

**DCP上のメディアパートナー名：**  
Google Ads

**メディアパートナー接続の設定要件とアカウント権限：**

* 有効なGoogleアカウント
* ユーザーアクセス権限：Google Adsアカウントに対するStandardまたはAdminアクセス
* Customer Match：有効化され、承認されていること
* パートナー承認：パートナーとの連携がアカウントで承認されていること（Google担当者経由）
* Partner Link：Googleによってバックエンド接続が作成されていること

**仕組み：**

設定時に、StandardまたはAdminユーザーが連携を有効化する必要があります。   
その後、DCPはPartner Link経由でオーディエンスを自動的にアップロードします。

**公式リソース：**  
<Anchor target="_blank" href="https://support.google.com/google-ads/answer/10589050">Google Ads Customer Matchヘルプ</Anchor>

**対応するキャンペーンタイプ：**

* **Search**  
  Customer MatchリストをObservationまたはTargetingモードで使用し、検索クエリに対する入札調整やターゲティングの最適化を行います。
* **Display**  
  Customer Matchリストを使用し、Google Display Network全体でオーディエンスを直接ターゲティングまたは除外します。
* **Video (YouTube)**  
  YouTube（インストリーム、インフィード、Shorts）での広告ターゲティングにオーディエンスを使用します。
* **Shopping**  
  Observationモードでオーディエンスを適用し、Shoppingキャンペーンのユーザーに対する入札を最適化します。
* **Performance Max (PMax)**  
  Customer Matchリストをオーディエンスシグナルとして使用し、Googleの自動最適化を補助します（厳密なターゲティングではありません）。
* **Demand Gen**  
  Customer Matchリストを使用し、YouTube、Discover、Gmail全体でオーディエンスを直接ターゲティングします。
* **App Campaigns**   
  アプリインストール向けApp Campaign（ACi）では、アップロードしたオーディエンスは最適化シグナルとしてのみ使用されます。一方、リエンゲージメントキャンペーン（ACe）は決定論的ターゲティングに対応しており、オーディエンスアクティベーションの主な方法となります。

#### App Campaign（ACi／ACe）のガイドライン

Google App Campaign（旧Universal App Campaign - UAC）では、Customer Matchオーディエンスの扱いが他のキャンペーンタイプと異なります。

**App Campaigns for Installs（ACi）**

大規模な新規ユーザー獲得を目的としたキャンペーンです。  
Customer Matchオーディエンスを**直接ターゲティングに使用することはできません。**  
アップロードしたオーディエンスは、Googleの機械学習と最適化を向上させるための**シグナルとしてのみ**使用されます。  
アクティベーションは**Google AIによって完全に自動化**され、オーディエンスの含有／除外を個別に制御することはできません。  
利用するには、コンバージョンデータや広告費など、十分なアカウント履歴が必要です。

**App Campaigns for Engagement（ACe）**

**既存ユーザーのリエンゲージメント**を目的としたキャンペーンです。  
Customer Matchオーディエンスは**決定論的ターゲティング**に対応しています。  
広告主は以下を実行できます。

* 特定のユーザーセグメント（離脱ユーザー、購入者など）をリターゲティング
* ライフサイクルキャンペーン（アップセル、クロスセル、リテンション）の実施

DCPのオーディエンスリストは、他のプラットフォームと同様に、主要なターゲティング条件として使用されます。

> 📘 **注意事項**
>
> * 規模拡大と新規ユーザー獲得が目的の場合はACiを使用します（オーディエンスはシグナルとしてのみ使用）。
> * リエンゲージメントと精度の高いオーディエンスターゲティングが目的の場合はACeを使用します（オーディエンスを直接ターゲティングに使用）。

**接続の有効期限：**

* 通常、接続は継続的に有効で、自動的に期限切れになることはありません。
* OAuthトークンが取り消された場合、アカウント権限が変更された場合、パスワード／セキュリティ設定が更新された場合、またはGoogleのパートナー承認が変更された場合は、再認証が必要になることがあります。

**オーディエンスの更新頻度：**

* Customer Matchのメンバーシップは、更新されない場合540日後に失効します。
* 推奨する運用確認：60〜90日ごと
* 推奨するオーディエンス更新：パフォーマンス／ライフサイクルキャンペーンでは毎日。少なくとも7日ごと
* 重要なオーディエンスは、7日を超えて未更新の状態にしないでください。

**その他の要件／制限事項：**

* Customer Matchリストを広告配信に使用するには、有効かつマッチ済みのユーザーが1,000人以上必要です。
* EU同意（DMA）：欧州経済領域（EEA）のユーザーについてCustomer Matchを使用するには、明示的に許諾された同意シグナル（ad\_user\_dataおよびad\_personalization）を渡す必要があります。同意が拒否されている、または同意情報がない場合、そのユーザーは処理されません。

</Accordion>

<div id="dv360" />

<Accordion title="DV360">

**メディアパートナープラットフォーム：**  
Google DV360（Display & Video 360）

**DCP上のメディアパートナー名：**  
DV360

**メディアパートナー接続の設定要件とアカウント権限：**

* 有効なDV360アカウント
* ユーザーアクセス権限：十分な権限を持つPartnerレベルまたはAdvertiserレベルのアクセス
* オーディエンス取り込み：アカウントでファーストパーティオーディエンスのアップロードが許可されていること
* パートナー承認：パートナーとの連携がアカウントで承認されていること（Google担当者経由）
* Partner Link：Googleによってバックエンド接続が作成されていること

**仕組み：**

設定時に連携を有効化するには、DV360で適切なアクセス権限が必要です。  
その後、DCPはPartner Link経由でオーディエンスを自動的にアップロードします。

**公式リソース：**  
<Anchor target="_blank" href="https://support.google.com/displayvideo/answer/9134175?hl=en">Display & Video 360のオーディエンスヘルプ</Anchor>

**対応するキャンペーンタイプ：**

* **Display** – オーディエンスの直接ターゲティングおよび除外に使用
* **Video (YouTube & Programmatic Video)** – YouTubeおよび動画インベントリ全体でのオーディエンスの直接ターゲティングに使用
* **Audio** – デジタルオーディオインベントリでのターゲティングに使用
* **Native** – ネイティブ広告枠全体でのオーディエンスターゲティングに使用
* **Connected TV (CTV)** – ストリーミングおよびTVインベントリでのターゲティングに使用
* **App campaigns：** DV360ではアプリインストールとリエンゲージメントの施策に対応していますが、プログラマティック広告のラインアイテムベースのモデルで運用します。 Google AdsのApp Campaignと同じ仕組みではなく、Customer Matchオーディエンスは主要な最適化シグナルや決定論的なアプリユーザーターゲティングではなく、ターゲティング／除外に直接使用されます。

**接続の有効期限：**

* 接続は、取り消しや権限変更がない限り有効な状態が維持されます（Google Adsと同様の動作）。
* オーディエンスのメンバーシップには、540日の有効期限を含むGoogle Customer Matchのポリシーが適用されます。

**オーディエンスの更新頻度：**

* 推奨する運用確認：60〜90日ごと
* 推奨するオーディエンス更新：毎日を推奨。有効なキャンペーンでは更新間隔を最大7日以内にしてください。

**その他の要件／制限事項：**

* Customer Matchリストを広告配信に使用するには、有効かつマッチ済みのユーザーが1,000人以上必要です。
* EU同意（DMA）：欧州経済領域（EEA）のユーザーについてCustomer Matchを使用するには、明示的に許諾された同意シグナル（ad\_user\_dataおよびad\_personalization）を渡す必要があります。同意が拒否されている、または同意情報がない場合、そのユーザーは処理されません。

</Accordion>

<div id="meta-ads" />

<Accordion title="Meta Ads">

**メディアパートナープラットフォーム：**  
Meta Ads Manager（Facebook／Instagram）

**DCP上のメディアパートナー名：**  
Meta Ads

**メディアパートナー接続の設定要件とアカウント権限：**

* 有効な個人用Meta（Facebook）アカウント
* 作成済みで、個人アカウントに紐づけられたBusiness Manager
* 1つ以上のFacebookページ
* Business Managerが所有している、またはBusiness Managerと共有されている広告アカウント
* **ユーザーアクセス権限：**
  * Business ManagerへのAdminアクセス
  * 広告アカウントへのAdminまたはAdvertiserアクセス

広告アカウントの所有者であるか、Business Managerに接続された広告アカウントに対するAdmin／Advertiser権限が必要です。これらの権限は広告やオーディエンスの管理に必要であり、DCPとの連携にも必須です。

**重要な要件：**

* DCPとの接続に使用するMetaユーザーは、以下に同意している必要があります。
  * Meta Adsの利用規約
  * Custom Audiencesの利用規約

DCP接続の認証に使用する同一ユーザーがこれらの規約に同意している必要があります。同意していない場合、接続は失敗します。

**仕組み：**

設定時にDCPへ接続するには、必要な権限を持っている必要があります。  

設定が完了すると：

* DCPがオーディエンスを自動的にアップロード・更新できます。

**公式リソース：**  
<Anchor target="_blank" href="https://www.facebook.com/business/help/1143109949216644/">Meta Businessヘルプ</Anchor>

**対応するキャンペーンタイプ：**

DCPで作成したCustom Audiencesは、以下のMetaキャンペーンタイプでアクティベーションできます。

* **Awareness (Brand Awareness / Reach)** – 幅広いオーディエンスへのターゲティングに使用
* **Traffic** – Webサイトやアプリなどの遷移先へユーザーを誘導するために使用
* **Engagement** – 投稿へのエンゲージメントや動画視聴などのインタラクション最適化に使用
* **Leads** – リード獲得キャンペーンに使用
* **App Promotion** – アプリインストールとリエンゲージメントに使用
* **Sales (Conversions)** – 購入やその他のコンバージョンイベントの促進に使用

DCPオーディエンス（Custom Audiences）は、すべてのMetaキャンペーンタイプで直接ターゲティングに使用でき、認知からコンバージョンまでフルファネルのユースケースに対応します。

**接続の有効期限：**

* 通常、接続は長期間維持されますが、パスワードのリセット、MFA／セキュリティ設定の変更、権限の取り消し、Business Managerの所有権変更、Metaのポリシーレビューなどにより接続が切れる場合があります。

**オーディエンスの更新頻度：**

* 推奨する運用確認：60〜90日ごと
* 推奨するオーディエンス更新：コンバージョン／ライフサイクルキャンペーンでは毎日。認知キャンペーンでは3〜7日ごとの更新でも可

</Accordion>

<div id="tiktok" />

<Accordion title="TikTok">

**メディアパートナープラットフォーム：**  
TikTok Ads Manager

**DCP上のメディアパートナー名：**  
TikTok

**メディアパートナー接続の設定要件とアカウント権限：**

TikTok Ads Managerアカウント  
承認済みかつ有効な広告主アカウント  
広告主へのAdminアクセス  

有効なTikTok Adsアカウント（Ads Manager）

* **広告アカウントのアクセス権限：**
  * TikTok AdsアカウントへのAdminまたはOperatorアクセス
* **オーディエンス権限：**
  * Custom Audiencesを作成・管理できること
* **パートナー承認：**
* TikTok Business CenterまたはAds Managerを通じて、パートナー（DCP）にアクセス権限を付与する必要があります。

**仕組み：**

設定時にDCPを承認・接続するには、AdminまたはStandardユーザーが必要です。  

設定が完了すると：

* DCPがオーディエンスを自動的にアップロード・更新できます。
* アップロードされたオーディエンスを使用し、TikTok Ads内で直接オーディエンスをアクティベーションします。

**公式リソース：**  
<Anchor target="_blank" href="https://ads.tiktok.com/help/article/invite-partners-into-tiktok-business-center?lang=en">TikTok Business Centerのパートナーアクセスに関するヘルプ</Anchor>

**対応するキャンペーンタイプ：**

DCPで作成したCustom Audiencesは、以下のTikTokキャンペーンタイプでアクティベーションできます。

* **Reach** – オーディエンスへの露出最大化に使用
* **Traffic** – Webサイトやランディングページへユーザーを誘導するために使用
* **Video Views** – 動画エンゲージメントの最大化に使用
* **Lead Generation** – TikTok上で直接リードを獲得するために使用
* **App Promotion** – アプリインストールとリエンゲージメントに使用
* **Conversions (Website Conversions)** – 購入や登録などのアクション促進に使用

DCPオーディエンス（Custom Audiences）は、すべてのTikTokキャンペーンタイプで直接ターゲティングに使用でき、認知からコンバージョンまでフルファネルのユースケースに対応します。

**接続の有効期限：**

* OAuth／ビジネス認証は、権限や管理者の変更によって期限切れになったり、取り消されたりする場合があります。

**オーディエンスの更新頻度：**

* 推奨するトークン・権限確認：四半期ごと
* 推奨するオーディエンス更新：毎日を推奨。有効なオーディエンスでは最大7日ごと

**その他の要件／制限事項：**

* 最小オーディエンスサイズ：Custom Audienceを広告グループに適用するには、マッチ済みユーザーが合計1,000人以上必要です。

</Accordion>

<div id="pinterest" />

<Accordion title="Pinterest">

**メディアパートナープラットフォーム：**  
Pinterest Ads Manager

**DCP上のメディアパートナー名：**  
Pinterest

**メディアパートナー接続の設定要件とアカウント権限：**

* 有効なPinterest Businessアカウント  
  ビジネスに紐づけられたAds Managerアカウント
* **ユーザーアクセス権限：**
  * 広告アカウントへのAdminまたはAnalyst（オーディエンス権限あり）アクセス
* **オーディエンス権限：**
  * Customer Lists（オーディエンス）を作成・管理できること
* **パートナーアクセス：**
  * Business Managerを通じて、パートナー（DCP）に広告アカウントへのアクセス権限を付与する必要があります。

**仕組み：**

設定時にDCPへ接続し、権限を付与するには、Adminまたは必要な権限を持つユーザーが必要です。  

設定が完了すると：

* DCPがオーディエンスを自動的にアップロード・更新できます。

**公式リソース：**  
<Anchor target="_blank" href="https://help.pinterest.com/en/business/article/audience-targeting">Pinterestのオーディエンスターゲティングに関するヘルプ</Anchor>

**対応するキャンペーンタイプ：**

DCPで作成したCustomer Listオーディエンスは、以下のPinterestキャンペーンタイプでアクティベーションできます。

* **Awareness** – リーチとブランド露出の最大化に使用
* **Consideration (Traffic / Engagement / Video Views)** – クリック、エンゲージメント、動画視聴の促進に使用
* **Conversions** – 購入、登録、その他のコンバージョンイベントの促進に使用
* **Catalog Sales (Shopping ads)** – カタログの商品をプロモーションし、購入を促進するために使用

DCPオーディエンス（Customer Lists）は、すべてのPinterestキャンペーンタイプで直接ターゲティングに使用でき、ショッピング／カタログキャンペーンを含め、認知からコンバージョンまでフルファネルのユースケースに対応します。

**接続の有効期限：**

* OAuthトークンやパートナー権限は、ビジネス／アカウントの変更に応じて期限切れになったり、取り消されたりする場合があります。

**オーディエンスの更新頻度：**

* 推奨する接続状態の運用確認：60〜90日ごと
* 推奨するオーディエンス更新：キャンペーンタイプに応じて1〜7日ごと

</Accordion>

<div id="the-trade-desk" />

<Accordion title="The Trade Desk">

**メディアパートナープラットフォーム：**  
The Trade Desk（TTD）

**DCP上のメディアパートナー名：**  
The Trade Desk

**メディアパートナー接続の設定要件とアカウント権限：**

* 有効なThe Trade Desk（TTD）アカウント
* **ユーザーアクセス権限：**
  * アカウントへのAdminまたはTraderレベルのアクセス
* **オーディエンス権限：**
  * ファーストパーティオーディエンス（データセグメント）を作成・管理できること
* **データ共有：**
  * 外部パートナー（DCPなど）からのデータオンボーディング／オーディエンス取り込みがアカウントで許可されていること
* **パートナー承認：**
  * パートナー（DCP）が、TTDでデータプロバイダーとして承認・連携されていること
* **API認証情報（必須）** API経由でオーディエンスをアップロード・アクティベーションするために必要です。
  * TTDの「First Party Data Credentials」セクションで以下を生成します（またはTTDのアカウント管理者へ発行を依頼します）。
    * Advertiser ID
    * Advertiser Secret Key

**仕組み：**

設定時には、AdminまたはTraderユーザーが以下を行う必要があります。

* 連携を有効化
* API認証情報を生成
* パートナーデータ共有を承認

設定が完了すると：

* DCPは、API認証情報とパートナー設定を使用してオーディエンスをアップロードします。
* オーディエンスは、TTDでファーストパーティデータセグメントとして利用できます。

**公式リソース：**  
<Anchor target="_blank" href="https://www.thetradedesk.com/">The Trade Deskプラットフォーム</Anchor>

**対応するキャンペーンタイプ：**

DCPで作成したファーストパーティオーディエンスは、以下のTTDキャンペーンタイプでアクティベーションできます。

* **Display** – Webおよびアプリ内インベントリ全体でのオーディエンスの直接ターゲティングに使用
* **Video (Online Video & CTV)** – プログラマティック動画およびコネクテッドTVインベントリでのターゲティングに使用
* **Audio** – デジタルオーディオ／ストリーミングプラットフォームでのターゲティングに使用
* **Native** – ネイティブ広告フォーマット全体でのオーディエンスターゲティングに使用

The Trade Desk上のDCPオーディエンスは、Display、Video（CTV／OLV）、Audio、Nativeを含むすべてのキャンペーンタイプで直接ターゲティングに使用され、チャネル横断で決定論的なオーディエンスアクティベーションが可能です。

**接続の有効期限：**

* API認証情報は通常、手動でローテーションまたは取り消されるまで長期間有効です。
* 推奨する認証情報のローテーション：セキュリティポリシーに従い6〜12か月ごと

**オーディエンスの更新頻度：**

* 推奨するオーディエンス更新：アクティベーションのユースケースやセグメントの変動性に応じて、毎日または毎週

</Accordion>

## メディアパートナー接続の作成

メディアパートナー接続は、オーディエンスビルダーのフロー内で設定することも、個別に設定することもできます。

<div id="setup-as-part-of-the-audiencebuilder-flow" />

<Accordion title="オーディエンスビルダーのフロー内での設定">

<span id="h_01HZHF5BWHBE7W8VNM3QFB7K58"></span>**オーディエンスビルダーのフロー内でメディアパートナー接続を作成するには：**

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-build-and-activate-audiences#step-3-connect-and-export">こちら</Anchor>の手順に従ってください。

</Accordion>

<div id="separate-setup" />

<Accordion title="個別に設定する場合">

<span id="h_01HZHF5BWH7P8HCWS9SG1JQ2BT"></span>**オーディエンスビルダーのフロー外で接続を作成するには：**

1. AppsFlyerのサイドメニューで、**Collaborate** > **Data Clean Room**の順に選択します。
2. 右上のメニューから**接続を管理**をクリックします。
3. **新しい接続**をクリックします。アカウントに既存のクラウド接続がある場合は、**パートナー**にすべて表示されます。
4. **新しいメディアパートナー接続**ダイアログで、対象のメディアパートナーを選択します。
5. 接続名を入力します。
6. 認証情報を使用してメディアパートナーのアカウントにログインし、パートナー側の手順に従ってAppsFlyerからのアクセスを許可します。
7. **アカウントIDを選択**をクリックし、この接続で使用するアカウントを選択します。
8. **保存**をクリックします。新しい接続がパートナー一覧に追加されます。

</Accordion>

<div data-zendesk-anchors="at-a-glance=%E6%A6%82%E8%A6%81 h_01KNS1JFT1R7K6MCWJRGA2EAAY=%E6%A6%82%E8%A6%81 about-partner-connections=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8E%A5%E7%B6%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KNS1JFT1C788JKA9ZH657TE0=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8E%A5%E7%B6%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KP0WCJVS71MZ5XEXRHRWXX2Q=%E6%B3%A8%E6%84%8F media-partner-connections=%E5%AF%BE%E5%BF%9C%E3%81%99%E3%82%8B%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8E%A5%E7%B6%9A h_01KNS1JFT1CT1AC1C6PAZAM779=%E5%AF%BE%E5%BF%9C%E3%81%99%E3%82%8B%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8E%A5%E7%B6%9A h_01KNS1JFT1RE8MA525AJ99D9DS=google-ads app-campaigns-aci-ace-guidelines=app-campaignaciace%E3%81%AE%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3 h_01KQC3Y84E1GT5VJB463N42SFT=app-campaignaciace%E3%81%AE%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3 h_01KQC759QZPWJ7MWGPK7TJ06HW=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 h_01KNS1JFT1VESJCKHV4S11EKST=dv360 h_01KNS1JFT1P3ZR6EG6YR0M1F98=meta-ads h_01KNS1JFT1GTXJ4PMV5QKSDEX9=tiktok h_01KNS1JFT18VRXFHBYPRTS2MS6=pinterest h_01KNS1JFT2GJMKYNGR6ZRMWN25=the-trade-desk create-a-partner-connection=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8E%A5%E7%B6%9A%E3%81%AE%E4%BD%9C%E6%88%90 h_01KP115WC2QNT7MAS73HZSHQJT=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8E%A5%E7%B6%9A%E3%81%AE%E4%BD%9C%E6%88%90 h_01KP11SX0VMYNRCY9C7GKQPYGB=setup-as-part-of-the-audiencebuilder-flow h_01KP11SX0VCAQM5MEGV3RKG086=separate-setup" />
