---
title: OneLink｜URLのエクスポート
metadata:
  keywords:
    - export
    - Marketers
    - download
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2022-01-09T11:58:46Z'
  edited_at: '2026-10-28T09:18:34Z'
  id: 4416027813905
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/4416027813905
---
> **概要：** AppsFlyerのUIで作成したすべてのOneLink URLをダウンロードします。

## OneLink URLのエクスポート

AppsFlyerのUIでOneLinkを設定して作成したすべてのURLを、OneLinkテンプレートごとにCSVファイルでダウンロードできます。 （SDK、OneLink API、一括アップロードで作成したOneLink URLは、エクスポートの対象外です。）

CSVファイルには、各リンクについて以下の情報が含まれます。

* リンク名
* メディアソース
* キャンペーン名
* ショートURL
* ロングURL
* 最終更新日時／作成日時（MM:DD:YY HH:MM）
* 更新者（メールアドレス）

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR02eohAyUA2fsr9iGEb0UiZI8v45wH58KGo-45wajF4KNGuk_2S_cY1WW3UV8LwPRg-wm9bkMjvWyZ/pub?output=csv">サンプルCSV</Anchor>

**注意**：AppsFlyerのUIでリンクを作成した後、UI以外（OneLink API、スプレッドシートなど）でパラメータを更新した場合、更新後のパラメータはダウンロードしたCSVに含まれません。

**CSVをダウンロードするには**：

1. AppsFlyerのサイドメニューから、［**Engage**］>［**OneLink管理**］を選択します。
2. リンクの一覧を取得するOneLinkテンプレートを選択します。
3. ［**エクスポート**］をクリックします。  
   CSVファイルがダウンロードされます。

### 特性と制限事項

| **項目** | **説明** |
| --- | --- |
| 代理店 | OneLinkテンプレートをもとに、自身が作成したリンクのみ取得できます。 |
| 広告主 | OneLinkテンプレートをもとに、自身が作成したリンクのみ取得できます。 |

<div data-zendesk-anchors="export-onelink-urls=onelink-url%E3%81%AE%E3%82%A8%E3%82%AF%E3%82%B9%E3%83%9D%E3%83%BC%E3%83%88 h_01HKA1YMN4J2HAXWWF00252XC3=onelink-url%E3%81%AE%E3%82%A8%E3%82%AF%E3%82%B9%E3%83%9D%E3%83%BC%E3%83%88 traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HKA1YMN4P9AR949BFCSG93VY=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
