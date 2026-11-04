---
title: Enterprise-Grade Security Package
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
  created_at: '2025-04-03T11:42:43Z'
  edited_at: '2026-10-28T09:14:07Z'
  id: 34053592094737
  locale: ja
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ja/articles/34053592094737
---
> **概要：Enterprise-Grade Security Package**は、企業向けのID管理、トークンのアクセス制御、監査ログの拡張機能を備えた有料パッケージで、アカウントの保護を強化します。

<div id="intro" />

## はじめに

Enterprise-Grade Security Packageは、組織のセキュリティを強化する3つの主要機能をまとめたパッケージです。

* **利用サービスを制限できる複数トークンの管理**：API、S2S、OneLinkのトークンを用途に応じて作成し、アクセス権限を細かく設定できます。
* **監査ログAPIと保存期間の延長**：管理画面での操作を長期間さかのぼって確認し、監査イベントを既存の監視システムに取り込めます。
* **SCIMによるユーザー管理の自動化**：IDプロバイダーを通じて、ユーザーのアクセス管理を自動化・一元化できます。
* **ログイン用IP許可リスト：** 信頼できるネットワークとIPアドレスからのみAppsFlyer管理画面へのログインを許可し、不正アクセスを防ぎます。

<div id="compare-the-standard-and-enterprise-grade-packages" />

### 標準パッケージとの違いは、次のとおりです。

| 機能 | 標準パッケージ | Enterprise-Grade Security Package |
| --- | --- | --- |
| [シングルサインオン（SSO）](/docs/enterprise-grade-security-package#accordion-item) | SSOログイン（既存のお客様のみ） | SAML 2.0によるSSOと、SCIMによるユーザー・ロール管理の自動化 |
| [トークンの管理](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | 種類ごと（API、S2S、OneLink）に最大2個のトークンを管理 | 種類ごとに最大30個のトークンを管理し、権限を細かく設定可能 |
| [監査ログへのアクセス](/docs/enterprise-grade-security-package#audit-log-api-and-extended-retention) | 管理画面からのみアクセス可能、データの保存期間は90日 | 管理画面とAPIからアクセス可能、データの保存期間は180日 |
| [ロールに基づくユーザー管理（RBAC）](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | カスタムロールを最大10個作成可能 | カスタムロールを最大50個作成可能 |
| [IP許可リスト](/docs/enterprise-grade-security-package#ip-allowlist) | API用IP許可リスト | ログイン用・API用のIP許可リストによるセキュリティ強化 |
| 24時間365日のセキュリティ監視 | 含まれます | 含まれます |
| 多要素認証 | 含まれます | 含まれます |

<div id="multitoken-management-with-restrictions" />

<Accordion title="アクセス制限付きの複数トークンの管理">

種類ごと（API、S2S、OneLink）に最大**30個のトークン**を作成・管理し、**利用できるサービスを制限**することで、大規模な運用にも対応しながら、トークンの安全性と管理機能を強化できます。

<div id="key-features" />

#### 主な機能

* 管理者は、標準の2個に対して、**種類ごとに最大30個のトークン**を作成でき、大規模なチームや複雑な業務フローに対応できます。
* APIトークンにサービスごとのアクセス権限を設定し、機密性の高い操作へのアクセスを制限できます。
* 連携や自動処理を中断せずに、トークンの失効や切り替えができます。
* トークンの対象を特定のアプリに限定し、そのアプリのデータへのアクセスや操作だけを許可できます。
* トークンごとの権限設定により、社内チームや外部パートナーとの連携を管理しやすくなります。

<div id="example" />

> 📄 **例**
>
> 2つのトークンを作成してアクセスを必要最小限に分けることで、誤ってデータを公開するリスクを抑えられます。
>
> **データアクセス専用トークン：** 集計データにのみアクセスできるトークンを作成します。このトークンでは、ローデータへのアクセスや、設定変更などの操作はできません。分析チームや、データの閲覧のみを行う代理店ユーザー向けに使用します。
>
> **設定専用トークン：** 社内チームが設定を管理でき、データの取得はできないトークンを発行します。これにより、管理操作の権限とデータアクセスを分離できます。
>
> **特定アプリ専用トークン：** 1つのアプリでのみ利用できるトークンを作成します。社内チーム、外部パートナー、自動処理のアクセス対象を特定のアプリに限定する場合に使用します。

<div id="note" />

> 📘 **注意**
>
> 標準トークンの概要は、<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">AppsFlyerトークンの管理</Anchor>を参照してください。

<div id="how-to-access-and-control-tokens" />

#### トークンの確認と管理

**アクセスを制限したトークンを作成するには、次の手順に従います。**

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>に移動します。
2. <strong>［トークン管理］</strong>ページに移動します。
3. ［**トークンを作成**］をクリックします。
4. トークンの種類を選択します。
   * API
   * S2S
   * OneLink
5. **APIトークン**の場合、<strong>［アクセス制限］</strong>ドロップダウンから、1つ以上のサービスを選択します。  
   アクセスは、全面的に許可するか、許可しないかのいずれかです。
6. 制限の種類を選択します。
   1. サービスの制限：<strong>［アクセス制限］</strong>ドロップダウンリストから、1つ以上のサービスを選択します。
   2. アプリの制限：トークンでアクセスできるアプリを選択します。
7. ［**保存**］をクリックします。

**トークンの管理**

トークンを管理するには、上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター＞トークン管理］</strong>ページに移動します。

ここでは、次の操作ができます。

* トークン情報の確認：名前、種類、制限、作成日／有効期限
* トークンの個別削除
* 監査ログによるトークンの利用状況の確認

<div id="note-1" />

> 📘 **注意**
>
> トークンは編集できません。アクセス権限を変更するには、トークンを削除して再作成してください。

</Accordion>

<div id="audit-log-api-and-extended-retention" />

<Accordion title="監査ログAPIと保存期間の延長">

既存の監査ログ機能にAPIによる取得機能が加わり、データの保存期間が90日から180日に延長されます。ユーザーの操作ログを長期間確認したい場合や、監査イベントをSOCやSIEMなどの外部の監視環境に取り込みたいチームに適しています。

<div id="key-features-1" />

#### 主な機能

* 専用APIを使った監査ログへのプログラムからのアクセス
* 標準の90日に対し、最大**180日間**のログ保存
* コンプライアンス、セキュリティ、運用の目的に応じたデータの絞り込みとエクスポート
* サービス専用トークンによる、ログへのアクセス権限の分離
* SIEMツール、ダッシュボード、クラウドストレージへのデータのエクスポート

<div id="note-2" />

> 📘 **注意**
>
> 標準の監査ログの概要は、<Anchor target="_blank" href="/marketers/ja/docs/audit-log">標準の監査ログ</Anchor>を参照してください。

<div id="how-to-access-the-audit-log-via-api" />

### **APIから監査ログにアクセスする方法**

監査ログAPIを利用するには、次の手順に従います。

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［監査ログ］</strong>セクションで、<strong>［監査ログを表示］</strong>をクリックします。
3. <strong>［トークン管理］</strong>ページに移動します。
4. 既存の**APIトークン**を使用するか、新しく作成します。
5. <strong>［アクセス制限］</strong>で、<strong>［監査ログ］</strong>サービスを選択します。
6. トークンを使って、監査ログAPIエンドポイントへのリクエストを認証します。

<div id="note-3" />

> 📘 **注意**
>
> APIトークンは安全な場所に保管してください。作成後に取得し直すことはできません。

</Accordion>

<div id="accordion-item" />

<Accordion title="SSOとSCIMによるユーザー管理の自動化">

SCIMによるユーザー管理の自動化は、AppsFlyerのSSO機能を拡張し、Okta、Entra ID（Azure）、OneLogin、JumpCloud、属性に基づくアクセス管理に対応した自社管理のIdPなどから、ユーザーの作成・更新・無効化を直接管理できるようにします。ユーザーの追加、情報更新、無効化を、手動の操作なしで行えます。

SCIMでユーザーを同期することで、アクセス権限をリアルタイムで一元管理できます。 SAML 2.0によるSSOと組み合わせることで、企業向けの包括的なID・アクセス管理を実現できます。

<div id="key-features-2" />

#### **主な機能**

* IDプロバイダー（IdP）の登録情報に基づいて、AppsFlyerにユーザーを自動作成します。
* IdPでのユーザーのロールやステータスの変更が、AppsFlyerに即座に反映されます。
* 安全なSSOに**SAML 2.0**、ユーザー管理の自動化に**SCIM**を使用し、OktaやAzure ADなどの主要なIdPに対応しています。

<div id="how-to-set-up-scim-provisioning" />

#### **SCIMによるユーザー管理の自動化の設定**

AppsFlyerでSCIMによるユーザー管理の自動化を利用するには、次の設定が必要です。

1. [SSOの設定](/docs/enterprise-grade-security-package#ssoの設定)
2. [SCIMの有効化](/docs/enterprise-grade-security-package#scimの有効化)

<div id="sso-set-up" />

#### SSOの設定

SSOを設定するには、次の手順を実施します。

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-1-set-up-the-idp-platform">IdP側の設定</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-set-up-appsflyer">AppsFlyerでのSSOの設定</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-configuration">SSO設定のテスト</Anchor>

<div id="enable-scim" />

#### SCIMの有効化

<div id="note-4" />

> 📘 **注意**
>
> SCIMを有効にする前に、SSOを設定する必要があります。

SCIMを有効にするには、次の手順に従います。

* [IdPの設定手順](/docs/enterprise-grade-security-package#idpの設定手順へのリンク)に従います。
* [SCIM接続](/docs/enterprise-grade-security-package#scim接続)を設定します。
* [SCIM属性](/docs/enterprise-grade-security-package#scim属性)を追加します。
* [ロール](/docs/enterprise-grade-security-package#ロール)を追加します。
* [外部名前空間](/docs/enterprise-grade-security-package#external-namespace)を追加します。

<div id="idp-instruction-links" />

#### IdPの設定手順へのリンク

<div id="the-instructions-for-the-idps-can-be-found-below-okta-entra-id-azure-onelogin-jumpcloud" />

##### 各IdPの設定手順は、以下を参照してください。 <Anchor target="_blank" href="https://help.okta.com/en-us/content/topics/apps/apps_app_integration_wizard_scim.htm">Okta</Anchor>、<Anchor target="_blank" href="https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups#integrate-your-scim-endpoint-with-the-microsoft-entra-provisioning-service">Entra ID (Azure)</Anchor>、<Anchor target="_blank" href="https://onelogin.service-now.com/kb_view_customer.do?sysparm_article=KB0010298">OneLogin</Anchor>、<Anchor target="_blank" href="https://jumpcloud.com/support/get-started-identity-management-connectors">JumpCloud</Anchor>

<div id="scim-connections" />

#### SCIM接続

SCIM接続では、次の項目を入力します。

| **項目名** | **値** |
| --- | --- |
| SCIMコネクターのベースURL（SCIMエンドポイント） | https://hq1.appsflyer.com/api/scim/v2 |
| ユーザーの一意の識別子となるフィールド | userName |
| 認証方法：AuthorizationというHTTPヘッダー | Bearer &lt;<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">Your AppsFlyer API token</Anchor>> |

<div id="scim-attributes" />

#### SCIM属性

| **属性** | **型** | **必須** | **項目名** | **外部名前空間** | **説明** |
| --- | --- | --- | --- | --- | --- |
| ロール | 文字列 | ✅ | role | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | <ul><li>ユーザーに定義済みロールまたはカスタムロールを割り当てます。</li><li>入力するAppsFlyerのロール一覧は、以下を参照してください。</li></ul> |
| 今後追加するすべてのアプリへのアクセスを許可 | 真偽値 | ❌ | allowAccessToAllFutureApps | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | 有効にすると、今後追加されるアプリへのアクセスが自動的に許可されます。 |
| アクセスを許可するアプリID | 文字列 | ❌ | appIDs | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | アプリIDをカンマ区切りで指定します。すべてのアプリを許可する場合は空欄にし、どのアプリも許可しない場合は「None」を指定します。 |

<div id="roles" />

#### ロール

ロールは、<Anchor target="_blank" href="/marketers/ja/docs/user-management#roles-tab">AppsFlyerのロール</Anchor>と一致している必要があります。現在のAppsFlyerのロールと、その値を次の表に示します。カスタムロールも追加できます。 JumpCloudについては、以下の[制限事項](/docs/enterprise-grade-security-package#制限事項)を参照してください。

| **表示名** | **値** |
| --- | --- |
| Admin | admin |
| Team manager | team\_manager |
| Marketing lead | marketing\_lead |
| Marketing | marketing |
| Marketing-limited | marketing\_limited |
| Contributor | developer |
| Accounting | accounting |
| Security | security |
| Quality Assurance | quality\_assurance |
| カスタムロール | [enter custom role value] |

<div id="limitations" />

#### 制限事項

| **制限事項** | **説明** |
| --- | --- |
| **JumpCloud：カスタム属性** | <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#attribute-considerations">カスタム属性には対応していません</Anchor>。代わりに、Roleフィールドを、対応するWork Street Addressフィールドにマッピングします。 <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#custom-scim-user-attributes">JumpCloudのSCIMサポート</Anchor>を参照してください。 |

</Accordion>

<div id="ip-allowlist" />

<Accordion title="ログイン用IP許可リスト">

信頼できるネットワークからのみ管理画面へのアクセスを許可することで、不正アクセスを防ぎ、セキュリティを強化します。厳格なセキュリティポリシーを適用する企業や、リモートアクセスを管理する企業に特に役立つ機能です。

<div id="key-features-3" />

#### 主な機能

* 不明なIPアドレスからのログインをブロックし、攻撃のリスクを低減します。
* IPアドレスや範囲を指定することで、許可されたユーザーやネットワークからのみ管理画面へアクセスできるようにします。
* VPNを使用する組織や、厳格なアクセス管理が必要な組織に適しています。

<div id="adding-ips-to-the-list" />

#### IPアドレスをリストに追加する

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［ログイン用IP許可リスト］</strong>セクションで、<strong>［IP許可リストを管理］</strong>をクリックします。
3. IPアドレスを手動で追加するか、CSVファイルをアップロードします。
   1. 手動で追加する場合は、IPアドレスまたはCIDR範囲を入力し、<strong>［IPをリストに追加］</strong>をクリックします。
      1. 例：`192.168.1.1`、`185.114.120.140`
      2. IPアドレスの範囲を入力するには、`185.114.120.1/32`の形式を使用します  
         （`185.114.120.1`が範囲の開始アドレス、`185.114.120.32`が終了アドレス）。
4. 追加したIPアドレスは、右側の<strong>［許可リストのIPアドレスを表示］</strong>に表示されます。
5. <strong>［リストを保存］</strong>をクリックします。

<div id="important" />

> 🚧 **重要**
>
> * 追加するIPアドレスや範囲に誤りがないことを確認してください。入力を誤ると、自分のアカウントにアクセスできなくなる場合があります。
> * 保存して有効にするには、IPアドレスまたは範囲を少なくとも1件登録する必要があり、最大100件まで追加できます。
> * ［リストを保存］をクリックすると、次回ログイン時からIPアドレスによる制限が適用されます。

<div id="removing-ips-from-the-list" />

#### IPアドレスをリストから削除する

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［ログイン用IP許可リスト］</strong>セクションで、<strong>［IP許可リストを管理］</strong>をクリックします。
3. 追加したIPアドレスは、右側の<strong>［許可リストのIPアドレスを表示］</strong>に表示されます。
4. 削除するIPアドレスの横にあるごみ箱アイコンをクリックします。
5. 必ず<strong>［リストを保存］</strong>ボタンをクリックして、変更を保存してください。

</Accordion>

<div id="frequently-asked-questions-about-our-security-package" />

<Accordion title="セキュリティパッケージについてのよくある質問">

<div id="what-is-appsflyers-enterprise-grade-security-package" />

#### AppsFlyerのEnterprise-Grade Security Packageとは何ですか？

標準の保護機能に加え、高度なセキュリティ機能により、安全に利用規模を拡大できます。企業のセキュリティ・IT責任者向けに、SCIMによるユーザー管理の自動化を備えたSSO、細かなアクセス制御、監査ログの拡張、コンプライアンス対応のツールを提供します。

<div id="who-is-the-enterprise-grade-security-package-designed-for" />

#### Enterprise-Grade Security Packageは、どのような方に適していますか？

監査に備える企業のセキュリティ・IT責任者、規制の厳しい業界でSaaSベンダーを評価する調達・法務チーム、複数のチームや連携にまたがる複雑なアクセス要件を管理する管理者に適しています。

<div id="how-does-scim-provisioning-work" />

#### SCIMによるユーザー管理の自動化は、どのような仕組みですか？

IDプロバイダーと直接接続し、ユーザーの作成から更新・無効化までの管理を自動化します。 SCIMは、ユーザーのアクセス権限とロールを自動同期し、利用開始・終了を即座に反映することで、手動のアカウント管理や、不要なアクセス権限が残るリスクをなくします。

<div id="what-compliance-standards-does-this-support" />

#### どのようなコンプライアンス基準への対応を支援しますか？

180日間の監査ログ保存、包括的なアクセス記録、リアルタイムのSIEM連携により、継続的な監視と要件への適合確認を行い、SOC2、ISO 27001、GDPRの監査に備えることができます。

<div id="how-many-roles-and-api-tokens-can-i-create" />

#### ロールとAPIトークンは、それぞれいくつ作成できますか？

組織構成に合わせてカスタマイズできるロールを最大50個、サービス別またはアプリ別の制限を最大30個作成できます。連携や担当業務ごとにアクセス権限を分離しながら、必要最小限の権限だけを付与できます。

<div id="can-i-integrate-with-my-existing-security-tools" />

#### 既存のセキュリティツールと連携できますか？

はい。 APIを使ったログのストリーミングにより、監査データをSIEMやセキュリティツールに直接配信できます。既存のSOC（セキュリティ監視・対応組織）の基盤で、リアルタイムの監視、異常検知、セキュリティ対応の自動化を実現できます。

<div id="what-network-restrictions-can-i-apply" />

#### どのようなネットワーク制限を設定できますか？

IP許可リストと地域による制限を使って、管理画面へのアクセスを制御できます。信頼できるネットワークと場所を指定し、不正アクセスを防ぎながら、リモートワークやパートナーとの安全な連携に対応できます。

<div id="how-long-are-audit-logs-retained" />

#### 監査ログは、どのくらいの期間保存されますか？

管理画面でのあらゆる操作を記録した監査ログを、180日間保存できます。ユーザーの操作、API呼び出し、アクセスパターンを詳細に把握し、コンプライアンス対応の記録やセキュリティ調査に活用できます。

<div id="does-this-replace-standard-security-features" />

#### 標準のセキュリティ機能に代わるものですか？

いいえ。 Enterprise-Grade Security Packageは、標準のセキュリティ機能に、高度な機能を追加するものです。既存の保護機能をすべて維持したまま、アクセス制御、自動化、操作状況の把握を強化できます。

<div id="how-quickly-can-i-implement-these-security-controls" />

#### これらのセキュリティ機能は、どのくらいの期間で導入できますか？

SSOとの円滑な連携とSCIMによるユーザー管理の自動化により、企業向けのセキュリティ管理をすばやく導入できます。多くの組織では、通常の業務やユーザーの生産性を維持しながら、数日以内に主要機能を導入できます。

</Accordion>

<div data-zendesk-anchors="intro=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01JRA2GVNZCDW8C9VW6GH3G4KE=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB compare-the-standard-and-advanced-packages=%E6%A8%99%E6%BA%96%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%81%A8%E3%81%AE%E9%81%95%E3%81%84%E3%81%AF%E6%AC%A1%E3%81%AE%E3%81%A8%E3%81%8A%E3%82%8A%E3%81%A7%E3%81%99 h_01JVS101KETCVDMT1B2WZM89NF=%E6%A8%99%E6%BA%96%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%81%A8%E3%81%AE%E9%81%95%E3%81%84%E3%81%AF%E6%AC%A1%E3%81%AE%E3%81%A8%E3%81%8A%E3%82%8A%E3%81%A7%E3%81%99 h_01JQXQ178D9JKZEREHWTQ2FKBF=multitoken-management-with-restrictions key-features=%E4%B8%BB%E3%81%AA%E6%A9%9F%E8%83%BD h_01JQXRDEMJF2NT73FP1TFJG63Z=%E4%B8%BB%E3%81%AA%E6%A9%9F%E8%83%BD h_01JVRZRXPD4AC1GAMJ2HKC1R9E=%E4%BE%8B h_01JVRZ0ACA19TGC9WJCZ562B70=%E6%B3%A8%E6%84%8F how-to-access-and-control-tokens=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%A2%BA%E8%AA%8D%E3%81%A8%E7%AE%A1%E7%90%86 h_01JQXSE4TTYXTWCKXDHB20KJ1Z=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%A2%BA%E8%AA%8D%E3%81%A8%E7%AE%A1%E7%90%86 h_01JVRZ9X0D5V765FTXHVHMR807=%E6%B3%A8%E6%84%8F-1 h_01JQXQ178DHFQ2Y6JDYYBTKJ0V=audit-log-api-and-extended-retention key-features::8c048755=%E4%B8%BB%E3%81%AA%E6%A9%9F%E8%83%BD-1 h_01JQXR4X1CT8P8M3NYEVK0WQYM=%E4%B8%BB%E3%81%AA%E6%A9%9F%E8%83%BD-1 h_01JVRZ7WBBY3D8GJE2MJ2E4B0G=%E6%B3%A8%E6%84%8F-2 how-to-access-the-audit-log-via-api=api%E3%81%8B%E3%82%89%E7%9B%A3%E6%9F%BB%E3%83%AD%E3%82%B0%E3%81%AB%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 h_01JQXQM2H3VCJMWFRBJDWJ5FAZ=api%E3%81%8B%E3%82%89%E7%9B%A3%E6%9F%BB%E3%83%AD%E3%82%B0%E3%81%AB%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 h_01JVRZ69C2JYY9SK12SEVG3KXF=%E6%B3%A8%E6%84%8F-3 h_01JQXQ178DSG340QG8R05B8VNX=accordion-item key-features::e7dd8b4e=%E4%B8%BB%E3%81%AA%E6%A9%9F%E8%83%BD-2 h_01JV9W8DTENC21GS0380Q9DP8T=%E4%B8%BB%E3%81%AA%E6%A9%9F%E8%83%BD-2 how-to-set-up-scim-provisioning=scim%E3%81%AB%E3%82%88%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%AE%A1%E7%90%86%E3%81%AE%E8%87%AA%E5%8B%95%E5%8C%96%E3%81%AE%E8%A8%AD%E5%AE%9A h_01JV9W8DTFCE7Z0MQP96MK7BQC=scim%E3%81%AB%E3%82%88%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%AE%A1%E7%90%86%E3%81%AE%E8%87%AA%E5%8B%95%E5%8C%96%E3%81%AE%E8%A8%AD%E5%AE%9A sso-set-up=sso%E3%81%AE%E8%A8%AD%E5%AE%9A h_01JV9W8DTFHJME1J1JKKJ3NA6C=sso%E3%81%AE%E8%A8%AD%E5%AE%9A enable-scim=scim%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01JV9W8DTG50YYPQ9RS91K2CJ4=scim%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01JVRZ3MC8J0B1E66A47GM5WYZ=%E6%B3%A8%E6%84%8F-4 idp-instruction-links=idp%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%89%8B%E9%A0%86%E3%81%B8%E3%81%AE%E3%83%AA%E3%83%B3%E3%82%AF h_01JV9WBJCPQ0X5SKVVNK4TBYRR=idp%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%89%8B%E9%A0%86%E3%81%B8%E3%81%AE%E3%83%AA%E3%83%B3%E3%82%AF h_01JV9WTJ33KMJGZGM9P5PRK917=%E5%90%84idp%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%89%8B%E9%A0%86%E3%81%AF%E4%BB%A5%E4%B8%8B%E3%82%92%E5%8F%82%E7%85%A7%E3%81%97%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84-oktaentra-id-azureoneloginjumpcloud scim-connections=scim%E6%8E%A5%E7%B6%9A h_01JV9WBNC51WYW03RKWHBTP0AG=scim%E6%8E%A5%E7%B6%9A scim-attributes=scim%E5%B1%9E%E6%80%A7 h_01JV9WBS928Z7WKJ2A2CFSWNT4=scim%E5%B1%9E%E6%80%A7 roles=%E3%83%AD%E3%83%BC%E3%83%AB h_01JV9WBX3JHEMAG62JCASYXB59=%E3%83%AD%E3%83%BC%E3%83%AB limitations=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01JV9DMY0Y3795TAT3Q1E3PZRM=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01JVWCNK70QY6PKJRFZGEQ76SW=ip-allowlist key-features::cd0daf96=%E4%B8%BB%E3%81%AA%E6%A9%9F%E8%83%BD-3 h_01JVWCSA3D6DJZXJKKYDFWWPC0=%E4%B8%BB%E3%81%AA%E6%A9%9F%E8%83%BD-3 adding-ips-to-the-list=ip%E3%82%A2%E3%83%89%E3%83%AC%E3%82%B9%E3%82%92%E3%83%AA%E3%82%B9%E3%83%88%E3%81%AB%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B h_01K35NHF44511J17KCXTE073QB=ip%E3%82%A2%E3%83%89%E3%83%AC%E3%82%B9%E3%82%92%E3%83%AA%E3%82%B9%E3%83%88%E3%81%AB%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B h_01K3DGBBVYY08KVYS60F2MYDCW=%E9%87%8D%E8%A6%81 removing-ips-from-the-list=ip%E3%82%A2%E3%83%89%E3%83%AC%E3%82%B9%E3%82%92%E3%83%AA%E3%82%B9%E3%83%88%E3%81%8B%E3%82%89%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B h_01K35PGV6Y84JR4CZJ0KGQNWZS=ip%E3%82%A2%E3%83%89%E3%83%AC%E3%82%B9%E3%82%92%E3%83%AA%E3%82%B9%E3%83%88%E3%81%8B%E3%82%89%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B h_01K85MXJJ7A9ZTS3PSY2Q0ZDGZ=frequently-asked-questions-about-our-security-package what-is-appsflyers-enterprisegrade-security-package=appsflyer%E3%81%AEenterprise-grade-security-package%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B h_01K85MZT9TDAV684V6PBBFGPTX=appsflyer%E3%81%AEenterprise-grade-security-package%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B who-is-the-enterprisegrade-security-package-designed-for=enterprise-grade-security-package%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E6%96%B9%E3%81%AB%E9%81%A9%E3%81%97%E3%81%A6%E3%81%84%E3%81%BE%E3%81%99%E3%81%8B h_01K85N0D7WVGH94HT1B7NY4KTZ=enterprise-grade-security-package%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E6%96%B9%E3%81%AB%E9%81%A9%E3%81%97%E3%81%A6%E3%81%84%E3%81%BE%E3%81%99%E3%81%8B how-does-scim-provisioning-work=scim%E3%81%AB%E3%82%88%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%AE%A1%E7%90%86%E3%81%AE%E8%87%AA%E5%8B%95%E5%8C%96%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E4%BB%95%E7%B5%84%E3%81%BF%E3%81%A7%E3%81%99%E3%81%8B h_01K85N0ZV1CMH5VANHQCEGENAW=scim%E3%81%AB%E3%82%88%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%AE%A1%E7%90%86%E3%81%AE%E8%87%AA%E5%8B%95%E5%8C%96%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E4%BB%95%E7%B5%84%E3%81%BF%E3%81%A7%E3%81%99%E3%81%8B what-compliance-standards-does-this-support=%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E3%82%B3%E3%83%B3%E3%83%97%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%82%B9%E5%9F%BA%E6%BA%96%E3%81%B8%E3%81%AE%E5%AF%BE%E5%BF%9C%E3%82%92%E6%94%AF%E6%8F%B4%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B h_01K85N1KB8VSR1Y44YJ7CJD4C2=%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E3%82%B3%E3%83%B3%E3%83%97%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%82%B9%E5%9F%BA%E6%BA%96%E3%81%B8%E3%81%AE%E5%AF%BE%E5%BF%9C%E3%82%92%E6%94%AF%E6%8F%B4%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B how-many-roles-and-api-tokens-can-i-create=%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%A8api%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AF%E3%81%9D%E3%82%8C%E3%81%9E%E3%82%8C%E3%81%84%E3%81%8F%E3%81%A4%E4%BD%9C%E6%88%90%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01K85N26X17PGVN4C6108A47TB=%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%A8api%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AF%E3%81%9D%E3%82%8C%E3%81%9E%E3%82%8C%E3%81%84%E3%81%8F%E3%81%A4%E4%BD%9C%E6%88%90%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B can-i-integrate-with-my-existing-security-tools=%E6%97%A2%E5%AD%98%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%83%84%E3%83%BC%E3%83%AB%E3%81%A8%E9%80%A3%E6%90%BA%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01K85N2QW51KDHKE4CQE7VJQHE=%E6%97%A2%E5%AD%98%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%83%84%E3%83%BC%E3%83%AB%E3%81%A8%E9%80%A3%E6%90%BA%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B what-network-restrictions-can-i-apply=%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E5%88%B6%E9%99%90%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01K85N37KPK5XTFRRGW62CCN4M=%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E5%88%B6%E9%99%90%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B how-long-are-audit-logs-retained=%E7%9B%A3%E6%9F%BB%E3%83%AD%E3%82%B0%E3%81%AF%E3%81%A9%E3%81%AE%E3%81%8F%E3%82%89%E3%81%84%E3%81%AE%E6%9C%9F%E9%96%93%E4%BF%9D%E5%AD%98%E3%81%95%E3%82%8C%E3%81%BE%E3%81%99%E3%81%8B h_01K85N3SVXVC6TD85V1PQ4EF2D=%E7%9B%A3%E6%9F%BB%E3%83%AD%E3%82%B0%E3%81%AF%E3%81%A9%E3%81%AE%E3%81%8F%E3%82%89%E3%81%84%E3%81%AE%E6%9C%9F%E9%96%93%E4%BF%9D%E5%AD%98%E3%81%95%E3%82%8C%E3%81%BE%E3%81%99%E3%81%8B does-this-replace-standard-security-features=%E6%A8%99%E6%BA%96%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E6%A9%9F%E8%83%BD%E3%81%AB%E4%BB%A3%E3%82%8F%E3%82%8B%E3%82%82%E3%81%AE%E3%81%A7%E3%81%99%E3%81%8B h_01K85N4BCQ3NCH1G2P0EFWE3TQ=%E6%A8%99%E6%BA%96%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E6%A9%9F%E8%83%BD%E3%81%AB%E4%BB%A3%E3%82%8F%E3%82%8B%E3%82%82%E3%81%AE%E3%81%A7%E3%81%99%E3%81%8B how-quickly-can-i-implement-these-security-controls=%E3%81%93%E3%82%8C%E3%82%89%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E6%A9%9F%E8%83%BD%E3%81%AF%E3%81%A9%E3%81%AE%E3%81%8F%E3%82%89%E3%81%84%E3%81%AE%E6%9C%9F%E9%96%93%E3%81%A7%E5%B0%8E%E5%85%A5%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01K85N4VR1FBESRN1QDRYF077A=%E3%81%93%E3%82%8C%E3%82%89%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E6%A9%9F%E8%83%BD%E3%81%AF%E3%81%A9%E3%81%AE%E3%81%8F%E3%82%89%E3%81%84%E3%81%AE%E6%9C%9F%E9%96%93%E3%81%A7%E5%B0%8E%E5%85%A5%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B" />
