---
title: アカウント設定
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2026-03-15T11:09:02Z'
  edited_at: '2026-10-28T09:13:02Z'
  id: 44784756352273
  locale: ja
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/ja/articles/44784756352273
---
> <strong>概要：［アカウント設定］</strong>ページでは、プロフィール、アカウント全体の設定、AI機能を1か所で管理できます。

## **アカウント設定について**

<strong>［アカウント設定］</strong>ページには、次の3つのタブがあります。

* [**プロフィール**](/docs/account-settings#プロフィール)：自分のアカウント情報
* [**アカウント**](/docs/account-settings#アカウント)：アカウント全体の設定
* [**AI機能**](/docs/account-settings#ai機能)：AI搭載製品の利用とアクセスの管理

## **プロフィール**

<strong>［プロフィール］</strong>セクションには、アカウント名、所有者のメールアドレス、Webサイト、アカウントIDなどの情報が表示されます。

アカウント情報を確認し、編集可能なプロフィール項目を更新できます。

## **アカウント**

<strong>［アカウント］</strong>セクションには、アカウント全体のセキュリティ設定があります。今後、ユーザー自身で変更できるアカウント設定が追加される場合があります。

### <Anchor target="_blank" href="/marketers/ja/docs/dev-key-management">**アプリ固有のDevキー**</Anchor>

<strong>［アプリ固有のDevキー］</strong>では、新しいアプリごとに固有のDevキーを作成するかどうかを設定します。

<strong>［今後追加するアプリごとに固有のDevキーを作成］</strong>を有効にすると、新たに追加されるアプリごとに固有のDevキーが自動生成されます。

注意：この設定は、有効にした後に作成されるアプリにのみ適用されます。既存アプリのDevキーは変更されません。

## **AI機能**

<strong>［AI機能］</strong>セクションでは、アカウントで利用できる対応AI製品を管理者が設定できます。

### <Anchor target="_blank" href="/marketers/ja/docs/ai-assistant">AI Assistant</Anchor>

AI Assistantは、AppsFlyerでデータ分析や製品知識の確認をサポートする、自分専用のアシスタントです。 AppsFlyerのどのページからでも、分析結果の確認、成果の計測、好調・不調な施策の特定、キャンペーンの傾向の把握、表やグラフによるデータの確認などができます。

### <Anchor target="_blank" href="/marketers/ja/docs/beta-appsflyer-mcp">AppsFlyer MCP</Anchor>

AppsFlyer MCPは、AppsFlyerのデータをClaudeやVS Codeなどの大規模言語モデル（LLM）に接続します。 AIチャットから直接、質問、成果の分析、操作の実行ができます。

MCPは、すべてのアカウントでデフォルトで有効になっています。

MCPを無効にするには、<strong>［アカウントとプロフィール＞AI機能］</strong>に移動します。

MCPを無効にすると、次のようになります。

* 外部のAIツールからMCP経由でAppsFlyerのデータにアクセスできなくなります。
* 既存の接続は、現在のセッションの有効期限が切れるまで利用できる場合があります。
* 通常のAPI接続には影響しません。
* AppsFlyerのほかのAI機能には影響しません。

**重要：** MCPトークンを使用している場合は、先に<strong>［セキュリティセンター＞AppsFlyerトークン］</strong>で削除する必要があります。

### <Anchor target="_blank" href="/marketers/ja/docs/beta-agent-hub-overview">Agent Hub</Anchor>

Agent Hubは、マーケティング施策に役立つ分析結果を普段の業務の中で自動的に届ける、AIエージェントの一元管理プラットフォームです。エージェントはデータを継続的に分析し、チームが共同作業する環境に、有用な分析結果や次に取るべきアクションを提示します。

この設定は管理者のみが利用でき、デフォルトで有効になっています。

Agent Hubを無効にすると、次のようになります。

* Agent Hubにアクセスできなくなります。
* 既存のエージェントはすべて完全に削除され、復元できません。
* 実行中のエージェントの処理は停止します。
* 後からAgent Hubを再び有効にすると、ユーザーは再度アクセスできますが、エージェントを最初から作成する必要があります。

## **権限**

<strong>［アカウント設定］</strong>ページで表示・編集できる内容は、ユーザーの権限によって異なります。

基本的な仕組みは、次のとおりです。

* ユーザーによって、表示される設定が異なる場合があります。
* 一部の設定は閲覧のみ可能です。
* アカウント全体やAI関連の設定を変更するには、管理者権限が必要な場合があります。

<div data-zendesk-anchors="about-account-settings=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E8%A8%AD%E5%AE%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KKRJZMP6CDDSJ6RK8QN4T30A=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E8%A8%AD%E5%AE%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 profile=%E3%83%97%E3%83%AD%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB h_01KKRJZMP81BHTCA01W22CRQYG=%E3%83%97%E3%83%AD%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB account=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88 h_01KKRJZMP9PQB0BZQ0931D23AH=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88 unique-dev-key=%E3%82%A2%E3%83%97%E3%83%AA%E5%9B%BA%E6%9C%89%E3%81%AEdev%E3%82%AD%E3%83%BC h_01KKRJZMPA9YTMGY0A3A883T0N=%E3%82%A2%E3%83%97%E3%83%AA%E5%9B%BA%E6%9C%89%E3%81%AEdev%E3%82%AD%E3%83%BC ai-capabilities=ai%E6%A9%9F%E8%83%BD h_01KKRJZMPCAMQFZM3MKQBTYFVD=ai%E6%A9%9F%E8%83%BD h_01KKRJZMPCQJBRRA0EM2EF4BYB=ai-assistant h_01KKRJZMPDZQKY9VV25EKCP5YE=appsflyer-mcp h_01KKRJZMPEHQHPRJEH9PSDTT00=agent-hub permissions=%E6%A8%A9%E9%99%90 h_01KKRJZMPFQJK110AW1CDS23CW=%E6%A8%A9%E9%99%90" />
