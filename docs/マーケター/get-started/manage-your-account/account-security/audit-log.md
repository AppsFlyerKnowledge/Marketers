---
title: 監査ログ
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
  created_at: '2020-05-05T14:18:09Z'
  edited_at: '2026-10-28T09:13:59Z'
  id: 360007971697
  locale: ja
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ja/articles/360007971697
---
> **概要：** 監査ログを使い、AppsFlyerアカウントへの不正アクセスを特定して対策します。アカウント内のセキュリティ関連の操作を、一覧で確認・ダウンロードできます。

<div id="overview" />

## 概要

**監査ログ**では、ログイン、データへのアクセス、API呼び出し、連携済みパートナー・検証ルール・オーディエンスの設定や権限の変更など、アカウント内の重要な操作をまとめて確認できます。操作状況の把握、セキュリティの確保、コンプライアンス要件への対応に役立ちます。 AppsFlyerアカウントの安全を保つため、**誰が**、**どのような方法で**アクセスしているかを、定期的に確認することを推奨します。過去90日間の監査ログデータを確認できます。

**監査ログを開くには、次の手順に従います。**

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［監査ログ］</strong>セクションで、<strong>［監査ログを表示］</strong>をクリックします。

<div id="using-the-audit-log" />

## 監査ログの使い方

監査ログで確認できるデータと主な機能を、次の表で説明します。

<Image align="center" alt="audit_log.png" src="https://files.readme.io/4101dfb4dc84e4e916d165a22387bd6a84fa7889bc4e82e636c980fde1cac248-6867050961809.png" />

|  | 項目 | 説明 |
| --- | --- | --- |
| ![A.png](https://files.readme.io/66b5bb0c4ea35f232f65dbc8dcbdfd6a91c12cf94915b19d33dae44834127058-31237653543313.png) | 検索ボックスとフィルター | 表示するデータを絞り込み、必要な情報だけを確認できます。<ul><li>検索ボックスで、アプリIDやメールアドレスなど、特定の文字列によってデータを絞り込みます。</li><li>日付選択で、データの表示期間を指定します。</li><li>サービスフィルターで、アクセスされたサービスごとにデータを絞り込みます。<ul><li>システムへのアクセス</li><li>連携済みパートナーの権限</li><li>ユーザー管理</li><li>検証ルール</li><li>API呼び出し</li></ul></li></ul>レポートを見やすくするため、<strong>［API呼び出し］</strong>はデフォルトでは選択されていません。レポートに含める場合は、必ず選択してください。 |
| ![B.png](https://files.readme.io/f63914d3fefb55b627559c6e4c7d7cdef89239c0376a14c25c713a0a76dbad1b-31237653544337.png) | 監査ログのデータ | 監査ログの各レコードには、次のデータが含まれます。<ul><li>**日時：** サービスにアクセスした日時（UTC）</li><li>**アクセス先のアプリ／アカウント：**<ul><li>ユーザーのログイン（システムへのアクセス）とユーザー管理では、この列に<strong>［アカウント］</strong>と表示され、アカウント単位のアクセスを示します。</li><li>API呼び出しでは、**アカウント**へのアクセス、またはデータへのアクセス対象となったアプリの**アプリID**が表示されます。</li></ul></li><li>**認証情報**<ul><li>システムへのアクセスやユーザー管理では、サービスにアクセスしたユーザーのメールアドレスが表示されます。</li><li>API呼び出しでは、使用したAppsFlyerのAPIトークン（V2）が表示されます。</li></ul></li><li>**サービス：** アクセスしたサービス（システムへのアクセス、ユーザー管理、API呼び出し）</li><li>**操作：** 記録された操作（ログイン、ログアウト、APIでアクセスしたデータなど）</li><li>**詳細：** 記録された操作の補足情報</li></ul> |
| ![C.png](https://files.readme.io/b428e77b299e10fe0701b7850cea1da8942905ad38d7b30c32f99f0240b22a63-5397303804945.png) | ![audit_log_download_button.png](https://files.readme.io/50e6cfef2aceb4b199f79008090da39d021f94be8d88d329bb8c8a0723edfa75-6867407922577.png) | ダウンロードボタンをクリックすると、監査ログをCSVファイルで取得できます。<ul><li>検索ボックスやフィルターで絞り込んだ画面上の表示条件は、ダウンロードしたファイルにも適用されます。</li></ul> |

<div id="troubleshooting" />

## トラブルシューティング

<div id="why-does-an-advertiser-audit-log-show-partner-api-call-requests" />

<Accordion title="広告主の監査ログに、パートナーのAPIリクエストが表示されるのはなぜですか？">

パートナーが広告主のアプリに対してAPIリクエストを行うと、パートナーと広告主の両方の監査ログに、そのリクエストが表示されます。

広告主が自分のトークンを使ってAPIリクエストを行った場合は、広告主の監査ログにのみ表示されます。

</Accordion>
