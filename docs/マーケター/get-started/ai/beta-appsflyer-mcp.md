---
title: ［Beta機能］AppsFlyer MCP
metadata:
  keywords:
    - Marketers
    - Beta feature
    - MCP
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-eden-locker
    - Marketers
    - MCP
  created_at: '2025-06-19T07:19:33Z'
  edited_at: '2026-10-20T12:58:58Z'
  id: 36349070304785
  locale: ja
  section: AI
  section_id: 36348470056081
  url: https://support.appsflyer.com/hc/ja/articles/36349070304785
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **概要：** AppsFlyer MCPは、AppsFlyerのデータをClaude、ChatGPT、Gemini CLI、Copilot CLI、VS Codeなどの大規模言語モデル（LLM）に接続します。 AIチャットや開発環境から直接質問し、パフォーマンスに関する分析結果やAppsFlyerの情報を取得できます。

<div id="disclaimer" />

<Accordion title="免責事項">

**AppsFlyer MCPサーバーは、現在ベータ段階にあり、評価を目的としてAppsFlyerが提供するサービスです。**

本サービスを使用してサードパーティのAIツールを接続することにより、お客様は、それらのツール、その出力、結果、性能、動作、適法性、信頼性についてAppsFlyerが一切の責任を負わないことに同意するものとします。 AppsFlyerは、これらのツールやその結果を管理、推奨、検証せず、それらに関する明示または黙示のあらゆる保証を明確に否認します。 AppsFlyerは、これらのツールによるデータの保存、保持、処理、利用について責任を負いません。適用される法令およびお客様自身の社内規定の遵守については、お客様が単独で責任を負います。お客様は、これらのツールをMCPサーバーに接続し、お客様のデータへのアクセスを許可するために必要なすべての権利および同意を得ていることを表明するものとします。本サービスは、対応している用途に限り、「現状有姿」で提供されます。その範囲を超える利用は、すべてお客様ご自身の責任で行うものとします。本サービスの利用には、<Anchor target="_blank" href="https://www.appsflyer.com/legal/msa/">基本サービス契約</Anchor>の条件が適用されます。ただし、正式な契約を締結している場合は、その契約の条件が適用されます。

</Accordion>

## AppsFlyer MCPとは

AppsFlyer MCPを使用すると、LLMをAppsFlyerプラットフォームに安全に接続し、簡単な会話を通じてマーケティングデータを活用できます。 AppsFlyer MCPは、リアルタイムのデータに基づく、より的確で迅速な意思決定を支援します。

MCPでは、以下の操作が可能です。

* キャンペーンのパフォーマンス、傾向、KPIの情報を即座に取得。
* ROAS、インストール、LTVなどの指標を比較。
* OneLinkリンクの作成と、OneLinkテンプレートおよびリンクの点検・トラブルシューティング。
* Audiencesの接続の点検・トラブルシューティング。
* 設定ガイドや製品ドキュメントを取得。

## AppsFlyer MCPの設定

AppsFlyer MCPは、チャットアシスタント、CLI、IDE、自動化プラットフォーム、自社環境で運用するエージェントに接続できます。設定方法は、利用するクライアントと、そのクライアントが対応する認証方式によって異なります。

> 📘 **注記**
>
> プラットフォームによっては、MCPサーバーの接続に管理者の承認が必要な場合があります。以下で説明する設定項目が表示されない場合は、IT管理者またはワークスペース管理者にお問い合わせください。

## 認証方式

AppsFlyer MCPは、2つの認証方式に対応しています。 AppsFlyer MCPへの接続方法に合った方式を使用してください。

| 認証方式 | 利用するクライアントなど | 適した用途 | アクセスの有効期間 |
| --- | --- | --- | --- |
| ブラウザでのOAuthログイン | Gemini CLI、Copilot CLI、ChatGPT、Claude.ai、Claude Desktop | 随時の質問、探索的な分析、単発のレポート作成 | 接続から7日間有効です。セッション終了時には再認証が必要です。 |
| Bearerトークン認証 | Claude Code、自動化プラットフォーム、自社環境で運用するエージェント、外部連携 | 自動化、定期実行タスク、バックグラウンドエージェント、対話を必要としないワークフロー | 手動で失効させるまで有効です。 |

### ブラウザでのOAuthログイン

ブラウザでのOAuthログインでは、ブラウザ上で操作して接続します。接続時に、MCPクライアントがブラウザウィンドウを開き、AppsFlyerへのログインを求めます。アクセスを承認すると、クライアントがAppsFlyerアカウントに接続します。

対話形式のセッション、探索的な分析、単発のレポート作成に適しています。

### Bearerトークン認証

Bearerトークン認証では、対話を必要としないツールがAppsFlyer MCPトークンを使用してAppsFlyer MCPに接続します。トークンは、リクエストヘッダーに次の形式で渡します。

```http
Authorization: Bearer <0>
```

自動化、定期実行タスク、バックグラウンドエージェント、ブラウザログインを使用できない外部連携に適しています。

トークンを作成するには、［**アカウントメニュー > セキュリティセンター > AppsFlyerトークン**］に移動し、MCPトークンを作成します。

## クライアント別の設定方法

<div id="h_claude-ai-and-claude-desktop" />

<Accordion title="Claude ChatとCowork">

ClaudeのチャットとClaude Coworkでは、ブラウザでのOAuthログインを使用します。この手順は、Web版およびデスクトップ版のClaudeとCoworkに適用されます。

> 📘 **注意**
>
> TeamプランおよびEnterpriseプランでは、組織全体の連携を追加できるのはオーナーまたは管理者のみです。

#### ClaudeのチャットとCoworkの設定

1. 左下にある自分の名前をクリックし、［**Settings**］（設定）を選択します。または、新しいチャットで［**Search & tools**］（検索とツール）>［**Manage connectors**］（コネクタの管理）をクリックします。
2. ［<Anchor target="_blank" href="https://claude.ai/settings/integrations">Connectors</Anchor>］（コネクタ）タブを開きます。
3. ［**Organization connectors**］（組織のコネクタ）タブに切り替えます。
4. コネクタのセクションで、［**Add connector**］（コネクタを追加）をクリックします。
5. 以下のコネクタ情報を入力します。
   * **Connector name（コネクタ名）：** AppsFlyer
   * **Connector URL（コネクタURL）：**`https://mcp.appsflyer.com/auth/mcp`
6. ［**Add**］（追加）をクリックします。
7. ［**Your connectors**］（自分のコネクタ）タブに切り替えます。
8. コネクタのセクションで、AppsFlyerの接続の横にある［**Connect**］（接続）をクリックします。
9. 画面の案内に従ってAppsFlyerにログインします。

#### Claudeの接続テスト

1. 任意のチャットウィンドウで、設定ボタンをクリックします。
2. AppsFlyer MCPが正しく設定されている場合は、メニューにAppsFlyerのツールが表示されます。

> 📘 **注記**
>
> <strong>Coworkですぐに使い始めるには、スキルとして保存してください。</strong>チームでClaude Coworkを利用している場合は、<Anchor target="_blank" href="https://github.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/tree/main/Claude/AppsFlyer%20Cowork%20Starter%20Kit">マーケター向けClaude Coworkスターターキット</Anchor>を使用すると、より迅速に設定できます。スターターキットには、利用開始のためのプラン、すぐに使えるテンプレート、コピーして貼り付けられるプロンプトが含まれています。初日からAIを通じてAppsFlyerのデータを活用できるため、最初のワークフロー、レポート、ブリーフを一から作成する必要がありません。

</Accordion>

<div id="h_claude-code" />

<Accordion title="Claude Code">

Claude Codeでは、自動化、定期実行、対話を必要としないワークフローにBearerトークン認証を使用します。

#### Claude CodeへのAppsFlyer MCPの追加

1. AppsFlyerで、［**アカウントメニュー > セキュリティセンター > AppsFlyerトークン**］に移動します。
2. MCPトークンを作成します。
3. ターミナルで、AppsFlyer MCPサーバーを追加します。

   ```bash
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
4. Claude Codeを起動します。

   ```bash
   claude .
   ```
5. MCPサーバーが追加されたことを確認します。

   ```bash
   claude mcp list
   ```
6. 設定済みのMCPサーバーの一覧に`appsflyer`が表示されていることを確認します。
7. AppsFlyerに関する質問をします。例：

   ```text
   私のAppsFlyerアカウントには、どのアプリがありますか？
   ```

   ```text
   先週、米国で「Mypets.android.com」の成果が高かったメディアソースを教えてください。
   ```

   ```text
   直近1日間の「Mypets.android.com」のパフォーマンスを、キャンペーン別にまとめてください。
   ```

</Accordion>

<div id="h_cursor-ide" />

<Accordion title="Cursor IDE">

Cursor IDEでは、ローカルの開発環境からAppsFlyer MCPに接続できます。

1. 適用範囲に応じて、以下の設定ファイルを作成するか開きます。
   * **全体に適用する設定：**`~/.cursor/mcp.json`
   * **プロジェクト固有の設定：**`.cursor/mcp.json`
2. JSONファイルの`mcpServers`フィールドに、以下のエントリを追加します。

   ```json
   {
     "mcpServers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
3. Cursor IDEを再起動し、新しい設定を適用します。
4. 画面の案内に従って認証を行い、AppsFlyer MCPのサービスにアクセスします。

</Accordion>

<div id="h_vs-code" />

<Accordion title="VS Code">

1. `Cmd+Shift+P`または`Ctrl+Shift+P`を押して、コマンドパレットを開きます。
2. ［**Configure MCP Servers**］（MCPサーバーを構成）を選択します。
3. `.vscode/mcp.json`に、AppsFlyer MCPサーバーの設定を追加します。

   ```json
   {
     "servers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
4. ファイルを保存し、Copilot Chatを再起動します。

</Accordion>

<div id="h_chatgpt" />

<Accordion title="ChatGPT">

ChatGPTでAppsFlyer MCPを使用する方法は2つあります。

* [カスタムGPT](#appsflyerのカスタムgptの追加)：AppsFlyerのアシスタントを手軽に利用したい場合に適しています。
* [ChatGPTでのMCP利用](#chatgptへのappsflyer-mcpの追加)：AppsFlyerのデータをChatGPTでの会話に取り込みたい場合に適しています。

#### AppsFlyerのカスタムGPTの追加

1. <Anchor target="_blank" href="https://chatgpt.com/g/g-68b6a92eb8e0819194cbb81e1e635c0d-appsflyer">AppsFlyerのカスタムGPT</Anchor>をクリックします。
2. GPTをサイドバーに保存すると、簡単にアクセスできます。
3. カスタムGPTを開きます。
4. 質問を入力します。例：

   ```text
   先週のMetaキャンペーンのパフォーマンスを表示してください。
   ```

#### ChatGPTへのAppsFlyer MCPの追加

> 📘 **注意**
>
> 組織にコネクタを追加して公開するには、管理者による設定が必要な場合があります。

1. コネクタを追加し、組織内に公開します。
2. 以下のコネクタ情報を入力します。
   * **Name（名前）：** AppsFlyer MCP
   * **URL：**`https://mcp.appsflyer.com/auth/mcp`
   * **Authentication（認証）：** OAuth
3. 初めて接続する際は、［**Settings > Apps & Sources > AppsFlyer MCP**］（設定 > アプリとソース > AppsFlyer MCP）に移動します。
4. AppsFlyer MCPに接続します。
5. 接続手順に従い、AppsFlyerの認証情報でログインします。

設定後、チャットを開き、［**Sources**］（ソース）または［**Connectors**］（コネクタ）を選択して、AppsFlyerの接続を有効にします。

セキュリティ上の理由から、AppsFlyer MCPは約10時間ごとに切断されます。再接続するには、接続手順をもう一度実行します。

</Accordion>

<div id="h_gemini-cli" />

<Accordion title="Gemini CLI">

Gemini CLIでは、ブラウザでのOAuthログインを使用します。

#### Gemini CLIへのAppsFlyer MCPの追加

1. ターミナルで、AppsFlyer MCPサーバーを追加します。

   ```bash
   gemini mcp add appsflyer https://mcp.appsflyer.com/auth/mcp -t http
   ```
2. Gemini CLIを起動します。

   ```bash
   gemini
   ```
3. Gemini CLIのプロンプトに、以下を入力します。

   ```text
   auth
   ```
4. ブラウザで認証を完了し、ターミナルに戻ります。
5. AppsFlyerに関する質問をします。例：

   ```text
   私のAppsFlyerアカウントには、どのアプリがありますか？
   ```

#### Gemini CLIの認証に関するトラブルシューティング

認証に失敗する場合は、Gemini CLIをデバッグモードで起動します。

```bash
GEMINI_LOG_LEVEL=debug gemini
```

その後、Gemini CLIのプロンプトに`auth`を再度入力します。

</Accordion>

<div id="h_copilot-cli" />

<Accordion title="Copilot CLI">

Copilot CLIでは、ブラウザでのOAuthログインを使用します。

#### Copilot CLIへのAppsFlyer MCPの追加

1. ターミナルを開きます。
2. Copilot CLIを起動します。

   ```bash
   copilot
   ```
3. ログインしていない場合は、Copilot CLIのプロンプトに以下のコマンドを入力します。

   ```text
   /login
   ```
4. ブラウザでのログインを完了します。
5. Copilot CLIのプロンプトに、以下を入力します。

   ```text
   /mcp add
   ```
6. 以下のMCPサーバー情報を入力します。

| 項目 | 値 |
| --- | --- |
| Server Name（サーバー名） | `appsflyer` |
| Server Type（サーバーの種類） | `HTTP` |
| URL |  |
| Tools（ツール） | `*` |

7. **Ctrl+S**を押して設定を保存します。
8. 画面の案内に従って、ブラウザでAppsFlyerの認証を完了します。
9. ターミナルに戻ります。
10. AppsFlyerに関する質問をします。例：

    ```text
    私のAppsFlyerアカウントには、どのアプリがありますか？
    ```

</Accordion>

<div id="h_third-party-and-self-hosted-platforms" />

<Accordion title="サードパーティおよび自社環境で運用するプラットフォーム">

サードパーティまたは自社環境で運用するシステムをAppsFlyer MCPに接続するには、MCPトークンを使用して認証します。 n8n、Makeなどのプラットフォームや、独自のLLMを活用したエージェントで、自動化やAI連携を行えます。

MCPトークンは、作成した管理者の権限を引き継ぐ、アカウント単位のBearerトークンです。［<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">セキュリティセンター > AppsFlyerトークン</Anchor>］からアクセスして管理できます。

#### MCPの接続情報

自動化プラットフォームまたはエージェントプラットフォームをAppsFlyer MCPに接続するには、以下の設定を使用します。

* **Auth Type（認証方式）：** Bearer Token
* **Base URL / Endpoint（ベースURL / エンドポイント）：**`https://mcp.appsflyer.com/auth/mcp`
* **Bearer Token（Bearerトークン）：** お客様のMCPトークン

> 📘 **注意**
>
> トークンを公開したり、誰でもアクセスできる場所で共有したりしないでください。非公開の認証情報として取り扱ってください。 MCPトークンを使用すると、MCP環境に直接アクセスできます。

#### 活用例

| カテゴリ | サンプル |
| --- | --- |
| カスタムエージェント | MCPでデータを取得・分析し、提案を配信するAIエージェントを構築します。 |
| LLM連携 | 自社環境で運用するLLMから、MCPを通じてキャンペーンのパフォーマンス指標を照会します。 |

</Accordion>

<div id="h_other-platforms" />

<Accordion title="その他のプラットフォーム">

AppsFlyer MCPは、以下のプラットフォームへの接続にも対応しています。

| プラットフォーム | リダイレクトURI | 参考資料 |
| --- | --- | --- |
| Microsoft 365 Copilot |  | Microsoft 365 Copilot：プラグインとMCPアプリ |
| Microsoft Azure AI Foundry |  | Azure AI Foundry：MCP認証 |
| Microsoft Copilot Studio / Power Platform（カスタムコネクタ） |  | Copilot StudioでのエンタープライズMCPサーバーの使用 |
| Google Gemini Enterprise |  | カスタムMCPサーバーの設定 |
| Amazon Quick（旧QuickSight） | `https://{region}.quicksight.aws.amazon.com/sn/oauthcallback` | MCP連携 – Amazon Quick |

対応プラットフォームの検証とドキュメントの整備を進めながら、この一覧を継続的に拡充しています。利用しているプラットフォームが一覧にない場合は、担当のCSMにお問い合わせいただくか、[hello@appsflyer.com](mailto:hello@appsflyer.com)にメールをお送りください。接続を支援します。

</Accordion>

<div id="h_use-multiple-accounts-or-agencies" />

<Accordion title="複数アカウントでの利用と代理店による利用">

AppsFlyer MCPは、1つの接続につき1つのAppsFlyerアカウントに接続します。

#### アカウントの切り替え（ブラウザでのOAuth）

同じメールアドレスで複数のAppsFlyerアカウントを管理している場合は、以下の手順でMCPの接続先アカウントを切り替えられます。

1. AppsFlyerで、接続するアカウントをプライマリアカウントに設定します。
2. MCPクライアントで再度ログインします。

1つの接続で複数のアカウントを並べて表示したり、照会したりすることはできません。

#### 複数アカウントへの同時接続（Bearerトークン）

代理店での利用など、複数のアカウントに同時に接続する場合は、ブラウザでのOAuthではなく、複数のエージェントを使用する以下の手順に従います。

1. 各アカウントで、［**アカウントメニュー > セキュリティセンター > AppsFlyerトークン**］からMCPトークンを作成します。
2. エージェントプラットフォームで、各アカウント固有のBearerトークンを使用して、それぞれ個別に接続します。

この手順の例は、<Anchor target="_blank" href="https://www.youtube.com/watch?v=o5oK-yWuE5E">こちらの動画</Anchor>で確認できます。

</Accordion>

## AppsFlyer MCPの利用

### 用途とプロンプト

AppsFlyer MCPは、マーケティング分析、パフォーマンスに関する知見、設定情報を取得するためのツールとリソースを提供します。

> 🚧 **重要**
>
> AppsFlyer MCPで生成される回答の信頼性が確認されているのは、以下に記載する対応用途で使用した場合のみです。これらの用途以外の回答はAppsFlyerによる検証が行われておらず、不正確な内容や誤解を招く内容が含まれる可能性があります。 AppsFlyer MCP連携の想定範囲を超えてAIが生成した回答については、その精度や正確性を保証できません。

用途とプロンプトの例を以下に示します。

<div id="analyze-performance" />

<Accordion title="パフォーマンスの分析">

集計されたマーケティングパフォーマンスデータを、リアルタイムに分析できます。成果の高いキャンペーンと低いキャンペーンを特定し、比較や傾向の把握を行い、意思決定に役立つ知見を得られます。

**プロンプト：** 「先週、米国でMypets.android.comの成果が高かったメディアソースを教えてください。」

**想定されるAIの回答：** インストール、収益、ROASを含む、成果の高いメディアソースの情報を取得します。

**プロンプト：** 「合計インストール数が5,000以上のキャンペーンのうち、ROASが最も高いものはどれですか？」

**想定されるAIの回答：** 条件に合うキャンペーンを特定して順位付けし、パフォーマンスに関する分析結果を示します。

**プロンプト：** 「昨日、中国でMypets.android.comアプリのインストールは何件ありましたか？」

**想定されるAIの回答：** 指定された日付とアプリについて、中国でのインストール数を取得します。

**プロンプト：** 「直近1日間のMypets.android.comのパフォーマンスを、キャンペーン別にまとめてください。」

**想定されるAIの回答：** 対象アプリのキャンペーン別パフォーマンスレポートを返します。

**プロンプト：** 「先週とその前の週のD1リテンションを、メディアソース別に比較してください。」

**想定されるAIの回答：** D1リテンション率をメディアソース別にグループ化し、前週と比較します。

> 📘 **注記**
>
> <strong>Coworkですぐに使い始めるには、スキルとして保存してください。</strong>チームでClaude Coworkを利用している場合は、<Anchor target="_blank" href="https://github.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/tree/main/Claude/AppsFlyer%20Cowork%20Starter%20Kit">マーケター向けClaude Coworkスターターキット</Anchor>を使用すると、より迅速に設定できます。スターターキットには、利用開始のためのプラン、すぐに使えるテンプレート、コピーして貼り付けられるプロンプトが含まれています。初日からAIを通じてAppsFlyerのデータを活用できるため、最初のワークフロー、レポート、ブリーフを一から作成する必要がありません。

</Accordion>

<div id="h_analyze-incrementality-experiments" />

<Accordion title="Incrementality for UAの実験の分析">

Incrementality for UAの実験とその結果を取得できます。リフト、増分コンバージョン、増分係数、増分コンバージョン単価が含まれます。これらの情報から、実際に増分の成長をもたらしたキャンペーンを確認し、予算をどこに振り向けるかを判断できます。

**プロンプト：** 「前四半期に、米国でMypets.android.comを対象に実施された増分効果の検証実験を教えてください。」

**想定されるAIの回答：** アプリ、国、期間の条件に合う実験を返します。各実験のステータス、メディアソース、計測対象のイベント、実験期間が含まれます。

**プロンプト：** 「Incrementalityの実験12345の結果をまとめてください。」

**想定されるAIの回答：** 実験のリフト、増分コンバージョン、従来のアトリビューションと比較した増分係数、増分コンバージョン単価を返します。実験に設定された信頼水準に対応する信用区間も含まれます。

**プロンプト：** 「過去6か月間のすべてのIncrementalityの実験について、増分アクション単価と増分ROASを比較してください。」

**想定されるAIの回答：** 過去6か月間に完了した実験の効率を並べて比較し、広告費1ドルあたりの増分効果が最も高かったキャンペーンを示します。

</Accordion>

<div id="analyze-skan-performance" />

<Accordion title="SKANパフォーマンスの分析">

AppleのSKAdNetworkフレームワークを使用して、iOSキャンペーンのパフォーマンスに関する知見を得られます。成果の高いキャンペーンを特定し、KPIの傾向を分析して、意思決定に活用できます。

**プロンプト：** 「先月のアドネットワーク別のROIを教えてください。」

**想定されるAIの回答：** 選択した期間のROIを取得し、成果の高いアドネットワークを示します。

**プロンプト：** 「CPIが最も低いキャンペーンはどれですか？」

**想定されるAIの回答：** CPIが最も低いキャンペーンを特定し、成果の高いものを順位付けします。

**プロンプト：** 「先月のaf\_subscribedイベントの週次コンバージョン率を教えてください。」

**想定されるAIの回答：** 対象イベントのコンバージョン率を週ごとに示し、全体の傾向を説明します。

**プロンプト：** 「null率が最も高いアドネットワークはどれですか？ また、そのアドネットワーク内でnull率が最も高いキャンペーンはどれですか？」

**想定されるAIの回答：** null率が最も高いアドネットワークを特定し、そのnull率への寄与が最も大きいキャンペーンの概要を示します。

</Accordion>

<div id="onelink-management" />

<Accordion title="OneLinkの管理">

OneLinkリンクを作成し、テンプレートやSmart Bannersを照会・点検して、一貫した遷移設定と適切なユーザー導線を確保できます。 MCPは、問題のトラブルシューティング、大量のリンクの設定確認、会話を通じた新しいリンクの作成を支援します。

**プロンプト：** 「メールニュースレター用に、HolidayPush2025テンプレートを使用してOneLinkリンクを作成してください。キャンペーン名はblack\_friday、ディープリンク値はsale\_pageにしてください。」

**想定されるAIの回答：** テンプレートとそのドメインを特定し、リンクのパラメータをまとめたうえで、確認を求めます。承認すると、リンクを作成して短縮URLを返します。

**プロンプト：** 「HolidayPush2025テンプレートを点検し、すべてのリンクをパラメータとともに表示してください。」

**想定されるAIの回答：** 短縮リンクと、それぞれのパラメータ値を含むCSV形式の表を返します。

**プロンプト：** 「このOneLinkで、既存ユーザーがApp Storeにリダイレクトされるのはなぜですか？」

**想定されるAIの回答：** リンクのパラメータとフォールバックのロジックに基づき、トラブルシューティングに役立つ情報を返します。

**プロンプト：** 「TravelBuddyアプリで、QRコードが有効になっているすべてのOneLinkを一覧にしてください。」

**想定されるAIの回答：** 生成済みのOneLinkを、QRコードのリンクおよび関連するメタデータとともに一覧で返します。

**プロンプト：** 「このリンクのパラメータ、機能、リダイレクトの挙動を教えてください：[https://mypets.onelink.me/abc123](https://mypets.onelink.me/abc123)?」

**想定されるAIの回答：** カテゴリ別のリンクパラメータ、ディープリンクやリターゲティングなどの有効な機能、デバイス・プラットフォーム・インストール状況ごとのリダイレクトの挙動を返します。

**プロンプト：** 「私のアカウントで有効になっているすべてのSmart Bannersを一覧にしてください。」

**想定されるAIの回答：** バナーID、名前、グループ、Webサイト、バナーの種類を含むメタデータを返します。

**プロンプト：** 「過去30日間の、2つのSmart Bannerクリエイティブのパフォーマンスを比較してください。」

**想定されるAIの回答：** 選択したバナーのインプレッション、クリック、インストールを並べて返します。

</Accordion>

<div id="knowledge-base-and-developer-support" />

<Accordion title="ナレッジベースと開発者サポート">

AppsFlyerのドキュメントやDevHubのリソースにすばやくアクセスできます。 SDKの設定、製品の挙動、計測ロジックについて、AIチャットで直接回答を得られます。

**プロンプト：** 「Androidでアプリ内イベントの重複排除を設定するには、どうすればよいですか？」

**想定されるAIの回答：** 設定手順、コード例、ベストプラクティスを示します。

**プロンプト：** 「TikTokのインストールのアトリビューションルックバック期間を教えてください。」

**想定されるAIの回答：** プラットフォームごとの最新のアトリビューションルールを説明します。

**プロンプト：** 「AppsFlyerでアプリのROASを最適化するには、どのような方法が効果的ですか？」

**想定されるAIの回答：** セグメンテーション、パートナーの最適化、LTV計測のベストプラクティスなど、改善につながる施策の概要を示します。

</Accordion>

<div id="apps-management" />

<Accordion title="アプリの管理">

アトリビューション期間、セッションタイムアウト、リエンゲージメント設定など、アプリの主要な設定情報を取得できます。これらの情報から、管理する複数のアプリの設定を点検・比較できます。

**プロンプト：** 「私のゲームアプリに設定されているアトリビューション期間を教えてください。」

**想定されるAIの回答：** 各アプリと設定済みのアトリビューション期間を一覧で返し、標準と異なる設定を示します。

**プロンプト：** 「ルックバック期間の設定が異なるアプリはどれですか？」

**想定されるAIの回答：** 標準とは異なるルックバック期間を設定しているアプリを特定し、設定値を示します。

**プロンプト：** 「ピン留めしているiOSアプリのうち、有効なものをすべて一覧にしてください。」

**想定されるAIの回答：** 現在有効な、ピン留め済みのiOSアプリを、アプリIDと名前を含めて一覧で返します。

**プロンプト：** 「AppsFlyerのゲームアプリの現在のセッションタイムアウト設定を教えてください。この設定が、リエンゲージメントのアトリビューションに影響する可能性はありますか？」

**想定されるAIの回答：** セッションタイムアウトの設定値を返し、リエンゲージメントへの影響を説明します。

</Accordion>

<div id="audiences-management" />

<Accordion title="Audiencesの管理">

### Audiencesの管理

オーディエンスの構成、所有者、パートナーへの接続、実行中のテストを把握できます。アップロードの状態を監視し、接続の失敗や更新されていないオーディエンスを検出して、各オーディエンスの設定を確認できます。これらの情報を活用して、部門を横断したキャンペーン管理を効率化できます。

**プロンプト：** 「FinanceProアプリで有効なオーディエンスをすべて表示してください。」

**想定されるAIの回答：** 有効なオーディエンスを、作成日、所有者、パートナーなどのメタデータとともに一覧で返します。

**プロンプト：** 「Churned Users - Tier Aオーディエンスを最後に更新したのは誰ですか？」

**想定されるAIの回答：** ユーザーIDまたはメールアドレスと、最終更新日時を返します。

**プロンプト：** 「現在、MetaとTikTokでスプリットテストを実施しているオーディエンスをすべて一覧にしてください。」

**想定されるAIの回答：** 有効なオーディエンスを、テスト設定と分割比率を含めて一覧で返します。

**プロンプト：** 「MolocoとGoogleを比較するテストを実施したいので、Googleに接続されているオーディエンスをすべて表示してください。」

**想定されるAIの回答：** Googleに接続されているオーディエンスを、現在のステータスと設定とともに一覧で返します。

**プロンプト：** 「（アドネットワーク）の利用を終了する予定です。配信中の有効なオーディエンスを一覧にしてください。」

**想定されるAIの回答：** 有効なすべてのオーディエンスを、接続先のパートナーと現在のステータスを含めて返します。

**プロンプト：** 「有効なすべてのオーディエンスと、接続先のパートナー、現在の分割比率を一覧にしてください。」

**想定されるAIの回答：** 各パートナーへの接続とその分割比率を含む、オーディエンスの完全な一覧を返します。

**プロンプト：** 「Metaのオーディエンスで、現在アップロードに失敗しているものはありますか？」

**想定されるAIの回答：** Metaに接続され、アップロード失敗のステータスになっているオーディエンスを、各エラーメッセージとともに一覧で返します。

**プロンプト：** 「TikTokキャンペーンを確認したいので、TikTokに接続されているオーディエンスのうち、失敗しているものと、いつから失敗しているかを教えてください。」

**想定されるAIの回答：** TikTokに接続され、失敗のステータスになっているすべてのオーディエンスと、最後にアップロードに成功した日時を返します。

**プロンプト：** 「過去7日間、一度もアップロードに成功していないオーディエンスをすべて表示してください。」

**想定されるAIの回答：** 過去7日間にアップロードの成功がないオーディエンスを、現在の接続ステータスとともに一覧で返します。

</Accordion>

<div id="feedback-tool" />

<Accordion title="フィードバックツール">

AppsFlyer MCPの利用についてのフィードバックを、アシスタントの画面から直接送信できます。いただいたフィードバックは、製品の改善と今後の開発に役立てられます。

**プロンプト：** 「分析ツールの分析結果はとても優れており、意思決定に役立っています。分析の選択肢に、アプリ内イベントの計測を追加してほしいです。」

**想定されるAIの回答：** AppsFlyer MCPの製品チームにフィードバックを送信します。

</Accordion>

<div id="cost-configuration-integration" />

<Accordion title="コスト設定の連携">

Cost Configuration MCPを使用して、コストデータを把握・管理できます。この連携により、コストデータの取得範囲を最大化し、未連携の箇所を早期に発見して、各アドネットワークのコストデータの完全性と正確性を維持できます。

**プロンプト：** 「私のAppsFlyerアカウントで有効になっているコスト連携を教えてください。」

**想定されるAIの回答：** AppsFlyerアカウントで有効なすべてのコスト連携を、紐づいたアプリIDと現在のステータスとともに一覧で返します。

**プロンプト：** 「有効なコスト連携で発生している問題を表示してください。」

**想定されるAIの回答：** 有効なコスト連携のうち、過去7日間に問題が発生したものを、アドネットワークと接続先のアプリ別に整理して表示します。

**プロンプト：** 「直近のアトリビューションデータに基づいて、どのコスト連携を設定すべきか教えてください。」

**想定されるAIの回答：** コスト連携に対応しているものの、まだ接続されていないアドネットワークを、アプリごとの直近のトラフィック量で順位付けして表示します。

</Accordion>

<div id="ad-revenue-integrations" />

<Accordion title="広告収益の連携">

AppsFlyer MCPを使用して、広告収益の連携を把握・管理できます。 MCPで有効な広告収益連携を確認し、連携の状態を監視して、不備を早期に発見できます。アプリと収益化パートナーを横断して、広告収益データの安定した取得を維持できます。

**プロンプト：** 「私のAppsFlyerアカウントで有効になっている広告収益連携を教えてください。」

**想定されるAIの回答：** AppsFlyerアカウントで有効なすべての広告収益連携を、接続先のアプリと現在の連携ステータスを含めて一覧で返します。

**プロンプト：** 「有効な広告収益連携で発生している問題を表示してください。」

**想定されるAIの回答：** 有効な広告収益連携のうち、過去7日間に問題が発生したものを、メディエーションパートナー、連携の種類、アプリ別にグループ化して表示します。

</Accordion>

<div id="user-management-and-role-control" />

<Accordion title="ユーザー管理とロール管理">

AppsFlyerアカウントのユーザー情報とロール情報を取得できます。管理者は、ユーザー情報を明確に把握し、アクセス権限を効率的に管理できます。

**プロンプト：** 「過去6か月間、AppsFlyerにログインしていない非アクティブユーザーを一覧にしてください。」

**想定されるAIの回答：** 最終ログインが6か月より前のユーザーと、一度もログインしていないユーザーを、メールアドレス、ロール、最終ログイン日時を含めて返します。

**プロンプト：** 「すべてのユーザーを権限レベル別にグループ化し、管理者権限を持つユーザーを強調してください。」

**想定されるAIの回答：** ユーザーをロールの種類別に整理し、管理者権限を持つユーザーを強調します。対象アプリと、地域別のアクセス権限も含まれます。

**プロンプト：** 「チームメンバーの1人から、AppsFlyerにログインできないとの連絡がありました。そのユーザーが存在するか、現在どのようなステータスかを確認できますか？」

**想定されるAIの回答：** ユーザーの存在を確認し、現在のロール、対象アプリ、最終ログイン日、アクセス制限の可能性を返します。

**プロンプト：** 「6つ以上のアプリにアクセスできるユーザーと、そのロールを教えてください。」

**想定されるAIの回答：** 多数のアプリへのアクセス権を持つユーザーを、ロールおよびアクセス可能なすべてのアプリの一覧とともに返します。

</Accordion>

## その他の情報

<div id="h_privacy-and-security" />

<Accordion title="プライバシーとセキュリティ">

AppsFlyer MCPを使用すると、選択したAIツールから、既存の権限に基づいてAppsFlyerのデータを照会できます。

#### データ処理

AppsFlyer MCPは、安全なプロキシとして機能します。 AppsFlyerのデータをリアルタイムに取得し、質問への回答に必要なデータを返します。 AppsFlyer MCPは、照会結果をアーカイブしたり、長期間保存したりしません。

#### 認証情報

AppsFlyerにログインすることで、AppsFlyer MCPがお客様に代わってAPIを呼び出せるようになります。 AppsFlyerの認証情報がAIツールに共有されることはありません。

#### 権限

AppsFlyer MCPは、既存のAppsFlyerの権限を使用します。ユーザーがアクセスできるのは、AppsFlyerで閲覧権限を持つアプリとデータのみです。

MCPへのアクセス用に、別途権限を設定する必要はありません。

#### 読み取りと書き込みの権限

AppsFlyer MCPのほとんどのツールは、読み取りと照会のみを行います。例外はcreate\_onelink\_linkで、アカウント内にOneLinkリンクを作成します。リンクを作成する前に、AIが詳細を表示し、確認を求めます。承認するまで、リンクは作成されません。

#### AI提供元によるデータの利用

AppsFlyer MCPで取得したデータは、質問に回答するため、選択したAIツールに共有される場合があります。共有されるのは、回答の生成に必要なデータのみです。

選択したAIツールによるデータの保存、処理、学習への利用について、AppsFlyerは管理しません。 AppsFlyer MCPを接続する前に、AI提供元の利用規約とデータ利用ポリシーを確認してください。

#### 認証

AppsFlyerは、ISO 27001とSOC 2の認証を取得しています。 ISO 42001の認証取得を進めています。

</Accordion>

<div id="tool-mapping" />

<Accordion title="ツールとカテゴリの対応">

デフォルトでは、すべてのツールが有効です。すべての機能を利用できるようにし、利用中の問題を防ぐため、有効なままにしておくことをおすすめします。

各ツールは、「パフォーマンスの分析」「アプリの管理」「OneLinkの管理」など、機能別のカテゴリに分類されています。 1つのカテゴリに複数のツールが含まれる場合があります。

すべてのツールとカテゴリの対応は、以下の表をご確認ください。

<table><thead><tr><th>カテゴリ</th><th>ツール</th><th>参照：</th></tr></thead><tbody><tr><td><a href="#analyze-performance">パフォーマンスの分析</a></td><td>fetch_aggregated_data</td><td>指定した期間、グループ化、指標、フィルターに基づいて、ダッシュボードの集計データを取得します。</td></tr><tr><td rowspan="2"><a href="#h_analyze-incrementality-experiments">Incrementality for UAの実験の分析</a></td><td>incrementality_list_experiments</td><td>ステータス、アプリ、国、メディアソース、期間で絞り込んだ増分効果の検証実験を一覧で返します。</td></tr><tr><td>incrementality_get_experiment_results</td><td>特定の実験の結果を取得します。リフト、増分コンバージョン、増分係数、増分コンバージョン単価が含まれます。</td></tr><tr><td rowspan="2"><a href="#apps-management">アプリの管理</a></td><td>get_apps</td><td>アクセスが許可されているすべてのアプリを、ピン留めの有無別に整理し、移管リクエストとともに一覧で返します。</td></tr><tr><td>get_app_settings</td><td>アトリビューション期間、プライバシー設定、セッション管理、プラットフォーム固有の設定など、アプリの設定を取得します。</td></tr><tr><td><a href="#cost-configuration-integration">コスト設定の連携</a></td><td><p>get_active_cost_integrations</p><p>list_cost_supported_media_source</p></td><td>アカウント内の有効なコスト連携の状況と、未設定のコスト連携の概要を取得します。</td></tr><tr><td><a href="#ad-revenue-integrations">広告収益の連携</a></td><td><p>list_adrevenue_supported_media_sources</p><p>get_active_adrevenue_integrations</p></td><td>有効な連携を確認し、連携の状態を監視して、設定の不備を検出します。広告収益データの一貫性の維持を支援します。</td></tr><tr><td><a href="#analyze-skan-performance">SKANパフォーマンス</a></td><td>skan_get_app_data</td><td>指定した期間のSKANパフォーマンスの集計データを、アドネットワーク、キャンペーン、イベント別にグループ化して取得します。</td></tr><tr><td rowspan="4"><a href="#onelink-management">OneLinkの管理</a></td><td>get_onelink_templates</td><td>すべてのOneLinkテンプレートを一覧で返します。</td></tr><tr><td>get_onelink_template_links</td><td>特定のテンプレートから作成されたすべてのOneLinkリンクを取得します。</td></tr><tr><td>get_onelink_details</td><td>特定のOneLinkの設定の詳細を取得します。</td></tr><tr><td>discover_onelink</td><td>短縮URLまたは長いURLから、リンクのパラメータ、機能、リダイレクトの挙動を確認します。</td></tr><tr><td> </td><td>create_onelink_link</td><td>既存のOneLinkテンプレートを使用して、新しい短縮リンクを作成します。リンクの作成前に、ユーザーの確認が必要です。</td></tr><tr><td> </td><td>list_smart_banners</td><td><p>アカウントのSmart Bannersをメタデータとともに一覧で返します。有効かどうかと作成日で絞り込めます。</p><p><strong>注意：</strong>list_smart_bannersが返すバナーは、1アカウントあたり最大30件です。有効なバナーを優先し、その後、最終更新日時の順に並べます。</p></td></tr><tr><td> </td><td>get_smart_banner_performance</td><td>指定したバナーIDのSmart Bannerパフォーマンスを、合計または日次単位で取得します。</td></tr><tr><td rowspan="3"><a href="#audiences-management">Audiencesの管理</a></td><td>list_active_audiences</td><td>日次で計算される、有効なすべてのオーディエンスを一覧で返します。</td></tr><tr><td>list_audiences_connections</td><td>オーディエンスデータの広告パートナー連携を一覧で返します。</td></tr><tr><td>get_audience_connections</td><td>特定のオーディエンスのパートナー接続を取得します。</td></tr><tr><td><a href="#knowledge-base-and-developer-support">ナレッジベースと開発者サポート</a></td><td>get_public_knowledge</td><td>AppsFlyerのナレッジベースとDevHubのドキュメントを検索します。</td></tr><tr><td><a href="#feedback-tool">フィードバックツール</a></td><td>send_feedback</td><td>ツールまたはシステムに関するフィードバックを送信します。</td></tr><tr><td><a href="#user-management-and-role-control">ユーザー管理とロール管理</a></td><td>get_users</td><td>AppsFlyerのユーザーとロールを一覧で返します。</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特徴と制限事項">

| 項目 | 参照： |
| --- | --- |
| 複数アカウントでの利用 | AppsFlyer MCPは、デフォルトのアカウントのデータのみを使用します。アカウントの切り替えや複数アカウントへの同時接続については、[複数アカウントでの利用と代理店による利用](#h_use-multiple-accounts-or-agencies)をご確認ください。 |
| OneLinkリンク | <ul><li>**OneLinkリンクの作成：**</li></ul><ul><li>1アカウントにつき、1日あたり最大10件のリンクを作成できます。</li><li>リンクは、既存のOneLinkテンプレートを使用して作成されます。</li></ul><ul><li>get\_onelink\_template\_linksツールの対象は、OneLink管理画面から作成したリンクのみです。API、SDK、一括作成で作成したリンクは含まれません。</li><li>Discover OneLink（discover\_onelink）には、この制限はありません。単一プラットフォーム向けの従来のリンク、ブランドドメイン、UI・API・SDK・一括作成で作成したリンクなど、すべてのAppsFlyerリンクの種類に対応しています。</li></ul> |
| リクエスト数の制限 | <ul><li>Analytics：1分あたり20リクエスト</li><li>Audiences：1分あたり350リクエスト</li><li>SKAN：1回の照会につき最大10,000行</li></ul> |
| 期間 | <ul><li>Analytics：3年間</li><li>SKAN：1リクエストあたり最大90日間</li></ul> |
| グループ | <ul><li>Analytics：1リクエストあたり4つのグループ化</li><li>SKAN：<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#metrics">SKANダッシュボード</Anchor>で利用可能なもの</li></ul> |
| アプリ数の制限 | <ul><li>Analytics：1リクエストあたり10アプリ</li><li>SKAN：1リクエストあたり1アプリ（iOSのみ）</li></ul> |
| 対応するディメンション | Analyticsは、マイダッシュボードで利用可能なすべてのディメンションに対応しています。 |
| 集計データ | 集計データに対応しています。週次・月次の粒度とカスタム指標も含まれます。 |
| データの更新タイミング | SKANデータは、UTCで最大3日遅れて利用可能になります。 |
| 通貨とタイムゾーン | SKANデータは、デフォルトで米ドルで表示されます。 `revenue_alt = true`を使用すると、ほかの通貨にも対応できます。データはUTCでレポートされます。 |
| MCPの無効化 | <ul><li>MCPはデフォルトで有効です。管理者は、［**アカウントとプロフィール > AI機能**］で無効にできます。</li><li>MCPを無効にすると、ユーザーは外部のAIツールからMCPを通じてAppsFlyerのデータにアクセスできなくなります。</li><li>既存の接続は、現在のセッションの有効期限が切れるまで継続する場合があります。</li><li>MCPを無効にしても、通常のAPI接続やAppsFlyerのほかのAI機能には影響しません。</li><li>MCPトークンを使用している場合は、先に［**セキュリティセンター > AppsFlyerトークン**］で削除してください。</li></ul> |

</Accordion>

## 接続に関するトラブルシューティング

AppsFlyer MCPの接続が機能しない場合は、認証方式に応じた手順を実行してください。

<div id="h_troubleshoot-browser-based-oauth-login" />

<Accordion title="ブラウザでのOAuthログイン">

このセクションは、Gemini CLI、Copilot CLI、ChatGPT、Claude.ai、Claude Desktopなど、ブラウザログインで接続するクライアント向けです。

1. **セッションを再認証します。** OAuthセッションは、約7日ごとに有効期限が切れます。接続手順を再度実行し、ブラウザでのログインをもう一度完了してください。
2. <strong>認証を最後まで完了します。</strong>ブラウザでのログインが正常に完了したことを確認してください。画面の案内に従って［**Allow**］（許可）または［**Approve**］（承認）をクリックし、MCPクライアントに戻ります。
3. **セッションを再起動します。** CLI、チャット、アプリケーションのセッションを再起動します。その後、MCPサーバーに再接続します。
4. <strong>MCPサーバーの設定を確認します。</strong>以下の値を確認してください。

| 項目 | 値 |
| --- | --- |
| Server Type（サーバーの種類） | `HTTP` |
| URL |  |

5. **ユーザーの権限を確認します。** AppsFlyerのユーザーが、対象のアプリとリクエストしたデータにアクセスできることを確認してください。

</Accordion>

<div id="h_troubleshoot-bearer-token-authentication" />

<Accordion title="Bearerトークン認証">

このセクションは、Claude Code、n8n、Make、自社環境で運用するエージェント、その他の自動化ツール向けです。

1. <strong>トークンが失効していないか確認します。</strong>トークンは手動で失効させることができます。 <strong>2026年3月10日19:00（UTC）</strong>より前に作成したトークンは、使用できなくなっている場合があります。
2. <strong>新しいMCPトークンを作成します。</strong>アクセスを復旧するには、以下の手順を実行します。
   1. AppsFlyerにログインします。
   2. ［**アカウントメニュー > セキュリティセンター > トークン管理**］に移動します。
   3. 失効したトークンを探します。
   4. 失効したトークンを削除します。
   5. 新しいMCPトークンを作成します。
   6. MCPクライアントまたは自動化の設定を、新しいトークンに更新します。
3. <strong>Authorizationヘッダーを確認します。</strong>ヘッダーが、次の形式と完全に一致することを確認してください。

   ```http
   Authorization: Bearer <0>
   ```
4. <strong>MCPサーバーの設定を確認します。</strong>以下の値を確認してください。

| 項目 | 値 |
| --- | --- |
| URL |  |
| Transport（通信方式） | `HTTP` |
| Header（ヘッダー） | `Authorization: Bearer <0>` |

5. **サーバーが登録されていることを確認します。** Claude Codeの場合は、以下を実行します。

   ```bash
   claude mcp list
   ```
6. **必要に応じて、MCPサーバーを再度追加します。**

   ```bash
   claude mcp remove appsflyer
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
7. **トークンの権限を確認します。** MCPトークンは、作成した管理者の権限を引き継ぎます。トークンが、対象のアプリとリクエストしたデータにアクセスできることを確認してください。

</Accordion>

<div id="h_access-and-permission-issues" />

<Accordion title="アクセスと権限に関する問題">

認証に成功してもアクセスできない場合は、以下を確認してください。

* AppsFlyerの管理者によって、MCPへのアクセスが制限されている可能性があります。
* ［アカウントとプロフィール］の設定にアクセスできない場合は、MCPへのアクセスがブロックされている可能性があります。
* AppsFlyerの管理者に、アクセスの有効化を依頼してください。
* ユーザーまたはトークンが、対象のアプリとリクエストしたデータにアクセスできることを確認してください。

</Accordion>

<div id="h_general-connection-checks" />

<Accordion title="一般的な確認事項">

問題が解決しない場合は、以下を確認してください。

* クライアントがMCPに対応していることを確認してください。
* ネットワークやファイアウォールの制限により、MCPのエンドポイントがブロックされていないか確認してください。
* MCPのURLが正しいことを確認してください。
* 新しいセッションまたは環境から、再接続を試してください。

</Accordion>

<div data-zendesk-anchors="h_01K9CJ9WQ3JJSYWDMNJ5GP7N04=disclaimer what-is-appsflyer-mcp=appsflyer-mcp%E3%81%A8%E3%81%AF h_01JY3G849QAT2GC714FR6CADH2=appsflyer-mcp%E3%81%A8%E3%81%AF h_set-up-appsflyer-mcp=appsflyer-mcp%E3%81%AE%E8%A8%AD%E5%AE%9A set-up-appsflyer-mcp=appsflyer-mcp%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KT8Y9JEJEZ26BRHK530JDB0D=%E6%B3%A8%E8%A8%98 h_authentication-methods=%E8%AA%8D%E8%A8%BC%E6%96%B9%E5%BC%8F authentication-methods=%E8%AA%8D%E8%A8%BC%E6%96%B9%E5%BC%8F h_browser-based-oauth-login=%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%A7%E3%81%AEoauth%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3 browser-based-oauth-login=%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%A7%E3%81%AEoauth%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3 h_bearer-token-authentication=bearer%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E8%AA%8D%E8%A8%BC bearer-token-authentication=bearer%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E8%AA%8D%E8%A8%BC h_set-up-by-client=%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E5%88%A5%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 set-up-by-client=%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E5%88%A5%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 claude-ai-and-claude-desktop=h_claude-ai-and-claude-desktop h_01KT8Y9JEJQNXK3SZ7M0ETH5RN=%E6%B3%A8%E6%84%8F h_set-up-claude-ai-and-desktop=claude%E3%81%AE%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%81%A8cowork%E3%81%AE%E8%A8%AD%E5%AE%9A set-up-claude-ai-and-desktop=claude%E3%81%AE%E3%83%81%E3%83%A3%E3%83%83%E3%83%88%E3%81%A8cowork%E3%81%AE%E8%A8%AD%E5%AE%9A h_test-claude-connection=claude%E3%81%AE%E6%8E%A5%E7%B6%9A%E3%83%86%E3%82%B9%E3%83%88 test-claude-connection=claude%E3%81%AE%E6%8E%A5%E7%B6%9A%E3%83%86%E3%82%B9%E3%83%88 h_01M09YV6XHR3DPYSHZA127XB50=%E6%B3%A8%E8%A8%98-2 claude-code=h_claude-code h_add-appsflyer-mcp-to-claude-code=claude-code%E3%81%B8%E3%81%AEappsflyer-mcp%E3%81%AE%E8%BF%BD%E5%8A%A0 add-appsflyer-mcp-to-claude-code=claude-code%E3%81%B8%E3%81%AEappsflyer-mcp%E3%81%AE%E8%BF%BD%E5%8A%A0 cursor-ide=h_cursor-ide vs-code=h_vs-code chatgpt=h_chatgpt custom-gpt-available-for-all-packages-including-free-enterprise=appsflyer%E3%81%AE%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0gpt%E3%81%AE%E8%BF%BD%E5%8A%A0 mcp-in-chatgpt-supported-for-chatgpt-users-on-all-paid-plans=chatgpt%E3%81%B8%E3%81%AEappsflyer-mcp%E3%81%AE%E8%BF%BD%E5%8A%A0 h_01KT8Y9JEJ806MVHJACM0VNM0K=%E6%B3%A8%E6%84%8F-1 gemini-cli=h_gemini-cli h_add-appsflyer-mcp-to-gemini-cli=gemini-cli%E3%81%B8%E3%81%AEappsflyer-mcp%E3%81%AE%E8%BF%BD%E5%8A%A0 add-appsflyer-mcp-to-gemini-cli=gemini-cli%E3%81%B8%E3%81%AEappsflyer-mcp%E3%81%AE%E8%BF%BD%E5%8A%A0 h_troubleshoot-gemini-cli-authentication=gemini-cli%E3%81%AE%E8%AA%8D%E8%A8%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 troubleshoot-gemini-cli-authentication=gemini-cli%E3%81%AE%E8%AA%8D%E8%A8%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 copilot-cli=h_copilot-cli h_add-appsflyer-mcp-to-copilot-cli=copilot-cli%E3%81%B8%E3%81%AEappsflyer-mcp%E3%81%AE%E8%BF%BD%E5%8A%A0 add-appsflyer-mcp-to-copilot-cli=copilot-cli%E3%81%B8%E3%81%AEappsflyer-mcp%E3%81%AE%E8%BF%BD%E5%8A%A0 third-party-and-self-hosted-platforms=h_third-party-and-self-hosted-platforms h_mcp-connection-details=mcp%E3%81%AE%E6%8E%A5%E7%B6%9A%E6%83%85%E5%A0%B1 mcp-connection-details=mcp%E3%81%AE%E6%8E%A5%E7%B6%9A%E6%83%85%E5%A0%B1 h_01KT8Y9JEKZRB56RZJXMMN4WV0=%E6%B3%A8%E6%84%8F-2 h_example-use-cases=%E6%B4%BB%E7%94%A8%E4%BE%8B example-use-cases=%E6%B4%BB%E7%94%A8%E4%BE%8B other-platforms=h_other-platforms use-multiple-accounts-or-agencies=h_use-multiple-accounts-or-agencies h_switch-between-accounts=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E5%88%87%E3%82%8A%E6%9B%BF%E3%81%88%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%A7%E3%81%AEoauth switch-between-accounts=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E5%88%87%E3%82%8A%E6%9B%BF%E3%81%88%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%A7%E3%81%AEoauth h_connect-multiple-accounts-simultaneously=%E8%A4%87%E6%95%B0%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%B8%E3%81%AE%E5%90%8C%E6%99%82%E6%8E%A5%E7%B6%9Abearer%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3 connect-multiple-accounts-simultaneously=%E8%A4%87%E6%95%B0%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%B8%E3%81%AE%E5%90%8C%E6%99%82%E6%8E%A5%E7%B6%9Abearer%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3 using-appsflyer-mcp=appsflyer-mcp%E3%81%AE%E5%88%A9%E7%94%A8 h_01JY3G1ZEC5Q30KP49RAA7EHRS=appsflyer-mcp%E3%81%AE%E5%88%A9%E7%94%A8 use-cases-and-prompts=%E7%94%A8%E9%80%94%E3%81%A8%E3%83%97%E3%83%AD%E3%83%B3%E3%83%97%E3%83%88 h_01JY3WMZ41HHQ4G13DGV8DPJMW=%E7%94%A8%E9%80%94%E3%81%A8%E3%83%97%E3%83%AD%E3%83%B3%E3%83%97%E3%83%88 h_01JZHT6BA2NX8GXNV8675XNVWT=%E9%87%8D%E8%A6%81 h_01JY3WZE6G2WB6DCWV68G1T36D=analyze-performance h_01M09YV6XJ7AM6S502BT2A594T=%E6%B3%A8%E8%A8%98-2 analyze-incrementality-experiments=h_analyze-incrementality-experiments h_01K7P0A6V86FZ3YQTQ4N5JZ4ZX=analyze-skan-performance h_01JY3VJEQMRDFAFTKZMPZ90RHP=onelink-management h_01JY3VJEQMXD32NSEE0E0FWG60=knowledge-base-and-developer-support h_01K01CE5NQ56HRT967F78ETKMS=apps-management h_01K01CE5NQBW6AADMHEPBQQN7S=audiences-management audiences-management::6584184=audiences%E3%81%AE%E7%AE%A1%E7%90%86 h_01KWBYTJ8GCJ884DN6XXPXZYMJ=audiences%E3%81%AE%E7%AE%A1%E7%90%86 h_01JY3VJEQNYKZ3Z724XM9JRWZF=feedback-tool h_01K9SHEQBWKK6AC0GD0YQVVJJ9=cost-configuration-integration h_01KGM1A7V6NB16A1Q07V5FQG2M=ad-revenue-integrations h_01K338G5KA09TESMNC6Z88RJCP=user-management-and-role-control other-information=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%83%85%E5%A0%B1 h_01JZHTJ1FQMXX9GSAN31E8HAYF=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%83%85%E5%A0%B1 privacy-and-security=h_privacy-and-security h_data-processing=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86 data-processing=%E3%83%87%E3%83%BC%E3%82%BF%E5%87%A6%E7%90%86 h_credentials=%E8%AA%8D%E8%A8%BC%E6%83%85%E5%A0%B1 credentials=%E8%AA%8D%E8%A8%BC%E6%83%85%E5%A0%B1 h_permissions=%E6%A8%A9%E9%99%90 permissions=%E6%A8%A9%E9%99%90 h_read-only-access=%E8%AA%AD%E3%81%BF%E5%8F%96%E3%82%8A%E3%81%A8%E6%9B%B8%E3%81%8D%E8%BE%BC%E3%81%BF%E3%81%AE%E6%A8%A9%E9%99%90 read-only-access=%E8%AA%AD%E3%81%BF%E5%8F%96%E3%82%8A%E3%81%A8%E6%9B%B8%E3%81%8D%E8%BE%BC%E3%81%BF%E3%81%AE%E6%A8%A9%E9%99%90 h_ai-provider-data-usage=ai%E6%8F%90%E4%BE%9B%E5%85%83%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8 ai-provider-data-usage=ai%E6%8F%90%E4%BE%9B%E5%85%83%E3%81%AB%E3%82%88%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8 h_certifications=%E8%AA%8D%E8%A8%BC certifications=%E8%AA%8D%E8%A8%BC h_01K044H4H18ED75GYQWMPDRA4R=tool-mapping h_01K01DT8656BQM1GW0HDHXGCY2=traits-and-limitations h_troubleshoot-connection-issues=%E6%8E%A5%E7%B6%9A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 troubleshoot-connection-issues=%E6%8E%A5%E7%B6%9A%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 troubleshoot-browser-based-oauth-login=h_troubleshoot-browser-based-oauth-login troubleshoot-bearer-token-authentication=h_troubleshoot-bearer-token-authentication access-and-permission-issues=h_access-and-permission-issues general-connection-checks=h_general-connection-checks" />
