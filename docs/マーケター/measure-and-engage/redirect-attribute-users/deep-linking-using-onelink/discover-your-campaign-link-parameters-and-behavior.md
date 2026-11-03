---
title: キャンペーンリンクのパラメータと動作の確認
metadata:
  keywords:
    - Marketers
    - discover
    - Social-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Social-to-App
  created_at: '2023-07-03T11:56:14Z'
  edited_at: '2026-10-21T19:14:45Z'
  id: 16678138044689
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/16678138044689
---
> **概要：** AppsFlyerのキャンペーンリンクに含まれるパラメータを確認し、想定されるユーザー体験とリンクの動作を把握します。

## Link Discoveryについて

Link Discoveryでは、AppsFlyerのキャンペーンリンクに関する情報を確認できます。リンクのパラメータや、そのリンクで想定されるユーザー体験などが表示されます。

### メリット

広告主はLink Discoveryを使用して、次のことができます。

* リンクの意味と動作への理解を深められます。
* リンクの作成を担当するチームと情報を共有できます。
* キャンペーンでリンクを公開する前に、詳細を確認できます。
* 想定外の動作の原因を調べられます。
* アトリビューションパラメータを確認し、管理画面でどの情報を探せばよいかを把握できます。

### Link Discoveryで確認できる情報

Link Discoveryでは、URLについて以下の情報が表示されます。

* **一般情報**：リンクの対象アプリ、作成元（OneLink管理ページやAPIなど）、リンクの土台となるOneLinkテンプレート、リンクの有効期限と更新期間に関する情報。   
  **注意：** 作成元が「Unknown」（不明）と表示される場合、UI（OneLink管理）で以前に作成されたリンクか、作成元情報の保存が開始される前に他の方法（一括作成／API／SDK）で作成された古いリンクである可能性があります。
* **パラメータ**：リンクに含まれるすべてのパラメータとその値が、カテゴリ別に表示されます。   
  **注意：** <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-domain-redirect-allowlist">リダイレクト許可リスト</Anchor>にないドメインへのリダイレクトが設定されている場合は、アラートが表示されます。
* **機能**：リターゲティング、ディープリンク、ソーシャルメディアプレビュー、ソーシャルメディア向けランディングページなど、リンクで有効になっている機能。
* **リダイレクト**：デバイス、プラットフォーム、アプリのインストール状況に応じて、ユーザーをどこへ誘導するよう設定されているかの概要。

## Link Discoveryの使用方法

**Link DiscoveryでURLの情報を確認するには**：

1. AppsFlyerのサイドメニューから、［**Engage**］>［**Link Discovery**］を選択します。
2. URLを入力し、［**確認**］をクリックします。

## 仕様と制限事項

| 項目 | 説明 |
| --- | --- |
| Link Discoveryが対応するリンク | <ul><li>AppsFlyerで作成したショートURLまたはロングURL。単一プラットフォーム用リンクと、OneLinkで作成した複数プラットフォーム用リンクの両方に対応しています。</li><li>AppsFlyerのUI、API、SDK、一括作成機能で作成したリンク。</li><li>ブランドドメインを使用するリンク。</li></ul> |
| 代理店 | 非対応 |
| アドネットワーク | 非対応 |
| インプレッションURL | 非対応 |
| クロスプラットフォームリンク | 非対応 |

<div data-zendesk-anchors="what-is-app-attribution=link-discovery%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HKW0CMGXXFKEY7W0NCN1SH76=link-discovery%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 benefits=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01HKW0CMGXEAYPDFMR4QCS9F52=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 information-available-via-link-discovery=link-discovery%E3%81%A7%E7%A2%BA%E8%AA%8D%E3%81%A7%E3%81%8D%E3%82%8B%E6%83%85%E5%A0%B1 h_01HKW0CMGXHZ2NYP6YVPW6QNX3=link-discovery%E3%81%A7%E7%A2%BA%E8%AA%8D%E3%81%A7%E3%81%8D%E3%82%8B%E6%83%85%E5%A0%B1 using-link-discovery=link-discovery%E3%81%AE%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95 h_01HKW0CMGXD4Z0J7CCKJFZNVCG=link-discovery%E3%81%AE%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95 specifications-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HKW0CMGXX4VXBHFGG3TGGPRV=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
