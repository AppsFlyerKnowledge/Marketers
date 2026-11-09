---
title: AppsFlyerトークンの管理
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2026-10-28T09:14:12Z'
  id: 360004562377
  locale: ja
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ja/articles/360004562377
---
> **概要：** トークンは、データのセキュリティを高めるために使用します。ユーザーがAppsFlyer API経由でデータにアクセスしたり、サーバー間通信でイベントデータを受信したりする際に使用します。管理者は、データの送受信を中断せずに、複数のトークンを管理できます。必要に応じて、APIトークンやサーバー間トークンの作成、名前の変更、削除を行えます。

<div id="important" />

> 🚧 **重要**
>
> <Image align="center" alt="AppsFlyerAdmin_us-en.png" src="https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png" />
>
> * トークンの確認と管理を行えるのは、管理者のみです。一般のアカウントユーザーは、［トークン］ページにアクセスできません。
> * トークンはデータへのアクセスを可能にするため、安全に保管してください。公開コードリポジトリにトークンを掲載しないでください。
> * 180日ごとにトークンを切り替えることを推奨します。

<div id="about-appsflyer-tokens" />

## AppsFlyerトークンについて

トークンは、AppsFlyer APIやS2Sの呼び出しで、ユーザーがデータにアクセスできるようにするために使用します。管理者は、さまざまな目的でトークンを使用します。

* セキュリティ対策：
  * トークンの漏洩や不正アクセスの疑いなど、特定のセキュリティ上の問題に対応するための切り替え
  * 定期的なセキュリティポリシーの更新に合わせた、トークンの切り替え
* 異なるAPI呼び出しの管理
* テスト
* OneLink APIなど、特定機能での利用

<div id="reaching-the-tokens-page" />

## トークンページを開く

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［AppsFlyer APIトークン］</strong>セクションで、**［AppsFlyer APIトークンを管理］をクリックします。** 現在のトークンが表示されます。

<div id="token-types" />

## トークンの種類

用途に応じて、さまざまな種類のトークンがあります。新しいアカウントには、デフォルトでAPIトークン（APIトークンV2）が生成されます。管理者は、以下の表に示す種類ごとに、最大2個のトークンを作成できます。

| トークンの種類 | 用途 |
| --- | --- |
| <span id="api-token"></span>APIトークン | Pull API、Cohort API、ROI APIなどのAPI呼び出しを認可する、JWT（JSON Web Token）形式のトークン。 |
| <span id="onelink-api-premium"></span><Anchor target="_blank" href="/marketers/ja/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor>（有料機能） | 大規模なキャンペーンでユーザーエンゲージメントを最適化するため、ユーザーに合わせたリンクを生成するOneLink API専用のトークン。 |
| <span id="s2s-token"></span>S2Sトークン | サーバー間通信でデータを送信するために使用します。 |
| <span id="mcp-token"></span>MCPトークン | サードパーティのシステムや自社運用のシステムを、AppsFlyer MCPで認証するために使用します。 |

<div id="note" />

> 📘 **注意**
>
> <Anchor target="_blank" href="/marketers/ja/docs/beta-advanced-security-protect360-module">Advanced Security Module</Anchor>など、専用のAPI V2トークンを必要とする機能を連携する際に、すでに上限の2個に達している場合は、新規発行を依頼する代わりに既存のAPI V2トークンを再利用できます。同じトークンを複数の用途に使用できます。

<div id="manage-your-tokens" />

## トークンの管理

管理者は、複数のトークンの作成、名前の変更、削除を行えます。主な用途は、現在のトークンから新しいトークンへの切り替えです。先に新しいトークンを[作成](#トークンの作成)して自社システムに設定し、利用可能になってから古いトークンを[削除](#トークンの削除)します。

<div id="retrieve-tokens" />

### トークンの取得

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［AppsFlyer APIトークン］</strong>セクションで、<strong>［AppsFlyer APIトークンを管理］</strong>をクリックします。
3. 利用可能なトークンが表示されます。
4. 必要なトークンをコピーします。

<div id="create-a-token" />

### トークンの作成

1. [<strong>［トークン］</strong>ページ](#トークンページを開く)で、<strong>［＋新しいトークン］</strong>をクリックします。
2. トークン名を入力します。
3. トークンの種類を選択します。
4. ［**トークンを作成**］をクリックします。

<div id="note-1" />

> 📘 **注意**
>
> * API V2トークンは、作成直後に有効になります。
> * S2S、OneLink、そのほかの種類のトークンは、有効になるまで最大30分かかることがあります。
>   * 有効化が完了するまで、トークンのステータスは<strong>［有効化待ち］</strong>になります。
>   * ステータスが<strong>［有効］</strong>に変わってから、トークンを使用してください。
> * 新しいトークンを、必ず自社システムに設定してください。

<div id="delete-a-token" />

### トークンの削除

<div id="warning" />

> ❗️ **警告**
>
> * トークンを削除すると、そのトークンを使用するシステムに障害が発生することがあります。
> * 削除したトークンは［トークン］ページから消え、そのトークンによる呼び出しはすべて拒否されます。
> * トークンを切り替える場合は、先に新しいトークンを作成してシステムに設定し、有効化待ちではなく利用可能な状態になったことを確認してから、古いトークンを削除してください。

1. [<strong>［トークン］</strong>ページ](#トークンページを開く)で、削除するトークンの削除アイコンをクリックします。
2. 削除の確認として「Delete token」と入力する必要があります。
3. <strong>［トークンを削除］</strong>をクリックします。

<div id="applications-of-the-api-v2-token" />

## API V2トークンの用途

広告主とアドネットワークの、API V2トークンの用途は次のとおりです。

<div id="advertiser" />

### 広告主

| API V2トークン |
| --- |
| <Anchor target="_blank" href="/marketers/ja/docs/pull-api-raw-data">Pull APIのローデータ</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/pull-api-aggregate-data">Pull APIの集計データ</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/app-list-api-for-app-owners">アプリ一覧の取得</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/cohort-api">Cohort</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/skan-aggregated-performance-report-api">SKAdNetworkの集計レポート</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">パートナー連携設定のコピー</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">インストールリファラの復号キーの設定</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-tax-and-store-commission-rates-with-the-net-revenue-api">Net Revenue API</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/send-opendsr-api-requests">OpenDSR API</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/audiences-import-audience-segments-from-internal-systems#imported-audience-management-api">オーディエンスのインポートAPI</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/beta-advanced-security-protect360-module">Advanced Security Moduleの連携（Android）</Anchor> |

<div id="ad-network" />

### アドネットワーク

| API V2トークン |
| --- |
| <Anchor target="_blank" href="/partners/ja/docs/app-list-api-for-ad-networks">アドネットワーク向けアプリ一覧</Anchor> |
| <Anchor target="_blank" href="/partners/ja/docs/access-to-aggregated-analytics-tools-for-api-partners">キャンペーン管理プラットフォームとの連携</Anchor> |
| <Anchor target="_blank" href="/partners/ja/docs/protect360-for-integrated-partners#protect360のアドネットワーク向けレポートapi">連携済みパートナー向けProtect360レポート</Anchor> |
| <Anchor target="_blank" href="/partners/ja/docs/incost-api-for-ad-networks">InCost</Anchor> |

<div id="applications-of-the-s2s-token" />

## S2Sトークンの用途

広告主とアドネットワーク向けのS2Sトークンの用途は、次のとおりです。

<div id="advertiser-1" />

### 広告主

| S2Sトークン |
| --- |
| <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">モバイルのアプリ内イベント用S2S API</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-s2s-api-for-web-performance-measurement">Webイベント用S2S API</Anchor> |

<div id="ad-network-1" />

### アドネットワーク

| S2Sトークン |
| --- |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-appsflyer-preload-referrer-attribution">AppsFlyerのプリロードリファラによるアトリビューション</Anchor> |

<div id="note-2" />

> 📘 **注意**
>
> ほとんどのアドネットワークでは、管理画面からS2Sトークンを生成することはできなくなっています。そのため、管理者の画面にはS2Sトークンの生成オプションが表示されません。管理画面からトークンを生成できるのは、個別に管理されている一部のパートナーのみです。

<div id="applications-for-the-onelink-token" />

## OneLinkトークンの用途

広告主向けのOneLink APIトークンの用途は、次のとおりです。

パラメータをカスタマイズしたOneLink短縮URLの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">作成</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">取得</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">更新</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">削除</Anchor>。

<div id="applications-for-the-mcp-token" />

## MCPトークンの用途

MCPトークンの用途は、<Anchor target="_blank" href="/marketers/ja/docs/beta-appsflyer-mcp">AppsFlyer MCPの記事</Anchor>を参照してください。

<div data-zendesk-anchors="01HFNX0XS4RAB543NKR12B2W50=%E9%87%8D%E8%A6%81 overview=appsflyer%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HFY5D0E1H66CEB3KMJQEXV4K=appsflyer%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 reaching-the-tokens-page=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E9%96%8B%E3%81%8F h_01HFTT570KF3XM9MBSFYRDYN9S=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%83%9A%E3%83%BC%E3%82%B8%E3%82%92%E9%96%8B%E3%81%8F token-types=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%A8%AE%E9%A1%9E h_01HFBR7KP8BZN7KH0BNJ982WK8=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%A8%AE%E9%A1%9E h_01M36NWJZ03NKZVAC2SCTAWBFX=%E6%B3%A8%E6%84%8F manage-your-tokens=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%AE%A1%E7%90%86 h_01HFY5D0E1AF4NYPX31W3VJYQC=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%AE%A1%E7%90%86 retrieving-api-tokens=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E5%8F%96%E5%BE%97 h_01HBQN3T2HKEMNC8MSR0THYW2S=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E5%8F%96%E5%BE%97 create-a-token=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90 h_01HFY5D0E1FECQC1HN0EXWMXAV=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90 h_01HFY5D0E1HJFKFPRT8WVNPHDG=%E6%B3%A8%E6%84%8F-1 delete-a-token=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E5%89%8A%E9%99%A4 h_01HFY5D0E2B1KXGSFZR0AYAER5=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E5%89%8A%E9%99%A4 h_01HFY5D0E2KZYG0J2R7GR1R7W5=%E8%AD%A6%E5%91%8A applications-of-the-api-v2-token=api-v2%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%94%A8%E9%80%94 h_01HG64DMW7PYRXBMZN00EQN991=api-v2%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%94%A8%E9%80%94 v20-token%E2%80%94advertiser-apis=%E5%BA%83%E5%91%8A%E4%B8%BB h_01HBQN7TBASK192P8D7AEWM9P6=%E5%BA%83%E5%91%8A%E4%B8%BB v20-token%E2%80%94ad-network-apis=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF h_01HBQN7TBAWAHEQXMYK9V14G0M=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF applications-of-the-s2s-token=s2s%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%94%A8%E9%80%94 h_01HG64M8K1PPY2Z2406MC78EEN=s2s%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%94%A8%E9%80%94 advertiser=%E5%BA%83%E5%91%8A%E4%B8%BB-1 h_01JSKCVT6ACKHECVJGZ0QVD8C6=%E5%BA%83%E5%91%8A%E4%B8%BB-1 h_01JSKD341C1EKE51Z16MMPG3Ckjh=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF-1 ad-network=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF-1 h_01KKBYBR8M9ZJWVB3MP1QG4FR4=%E6%B3%A8%E6%84%8F-2 applications-for-the-onelink-token=onelink%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%94%A8%E9%80%94 h_01JSKCWS5406YQJP3RR9KAXJC9=onelink%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%94%A8%E9%80%94 applications-for-the-mcp-token=mcp%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%94%A8%E9%80%94 h_01K9YD2Y9M1C8QDBS5H048XYYD=mcp%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%94%A8%E9%80%94" />
