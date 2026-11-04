---
title: PBA：ウェブサイト計測URLのベストプラクティス
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-05-23T05:29:27Z'
  edited_at: '2026-10-14T09:26:27Z'
  id: 6313062676497
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/6313062676497
---
> **概要：概要：ウェブサイトアトリビューションキャンペーンに、利用可能な最適なキャンペーン粒度を割り当てるためのベストプラクティス**

<div id="pba-website-attribution-urls" />

## PBA：ウェブサイト計測URL

ウェブサイトのアトリビューションデータで最も正確なアトリビューションと組み合わせて、キャンペーンの粒度を最大限に高めるには、URL(リンク)を入力し、この記事で詳しく説明している方法を使用してユーザーをウェブサイトに誘導します。

<div id="url-parametersgroup-and-priority" />

### URL パラメータ — グループと優先度

AppsFlyerウェブサイトアトリビューションソリューションは、いくつかのキャンペーンパラメータクラスをサポートしています。クラスは次のように優先順位が付けられます：

* [最優先] PID
* Google, DoubleClick, Microsoft などの特定のチャネルのクリックID
* [最も低い優先度] UTM

<Anchor target="_blank" href="/marketers/ja/docs/pba-media-source-attribution-rules">PBAメディアソースのアトリビューションルール</Anchor>は、特定のユーザーの属性を決定します。パラメータークラスは優先度によってランク付けされます。リンク上で複数のパラメータクラスが見つかった場合、優先度が最も高いクラスにアトリビューションが付与されます。

<div id="supported-parameters" />

#### サポートされているパラメーター

| # | パラメータ | 用途 | パラメータークラス | 管理画面での利用可否 | PBAローデータ項目 |
| --- | --- | --- | --- | --- | --- |
| 1 | pid | Media source | pid | Y | media\_source |
| 2 | c | キャンペーン名 | pid | Y | campaign |
| 3 | af\_c\_id | Campaign ID | pid | Y | campaign\_id |
| 4 | af\_adset | 広告セット名 | pid | Y | query\_paramsから抽出 |
| 5 | af\_adset\_id | Adset ID | pid | Y | query\_paramsから抽出 |
| 6 | af\_ad | 広告名 | pid | Y | query\_paramsから抽出 |
| 7 | af\_ad\_id | Ad ID | pid | Y | query\_paramsから抽出 |
| 8 | utm\_source | Media source | UTM | Y | media\_source |
| 9 | utm\_medium | メディアタイプ | UTM | Y | media\_type |
| 10 | utm\_campagin | Campaign | UTM | Y | campaign |

<div id="url-parameter-best-practices" />

## URLパラメータのベストプラクティス

<div id="selecting-url-parameters" />

### URLパラメータの選択

各パラメータークラスは、サイロのコンテキストで機能します。そのため、複数のクラスを持つURLが必要な場合は、URLに各クラスの関連パラメーターが含まれている必要があります。これにより、レポートの粒度が最適化されます。

複数のクラスのパラメータの使用については、Meta広告のコンテキストで次のように説明されています：

* クラスを結合しても、必要なパラメーターの一部のみを含めると、AppsFlyer では完全な粒度が得られない可能性があります。

  * AppsFlyerは、PIDクラスがないため UTMクラスを使用し、utm\_source を使用してメディアソースを決定します。
  * ただし、 *c=* はPIDクラスの一部ですが、pidが含まれていないため、キャンペーンデータを利用できません。
  * この構造体では、AppsFlyer は PIDクラスを使用してメディアソースを識別します。c= などの他の PID パラメーターを含めることができ、utm\_source優先順位が低いため無視されます。

<div id="implement-dynamic-urls-using-ad-network-macros" />

### アドネットワークのマクロを使用した動的URLの実装

ネットワークマクロ（別名 valuetrackパラメータ）を使用して、テンプレートを作成し、有料キャンペーンにURLパラメータを適用する時間を節約します。

ネットワークでは、さまざまなマクロを使用して URL にパラメーターを入力します。そのため、広告ネットワークのドキュメントを参照して、マクロが正しく使用されていることを確認する必要があります。たとえば、af\_c\_id でキャンペーンIDを渡す場合は、各URLの実際のキャンペーンIDをハードコーディングする必要がなく、マクロを使用するだけです。

* Google Adwords
* Meta ads

<div id="consistent-case-within-parameters" />

### パラメーター内の一貫した大文字と小文字

パラメーター値では、大文字と小文字が区別されます。たとえば、utm\_source=channel1 と utm\_source=CHANNEL1 は異なるメディアソースと見なされます。そのため、大文字と小文字に関して一貫性があることを確認してください。

<div id="use-google-ads-integration-to-automate-granularity" />

### Google Adsの連携を使用して粒度を自動化

Google広告キャンペーンの場合は、PBAを Google Adsアカウントと連携することで、キャンペーンの粒度を高めることができます。これにより、URLに PID または UTMパラメーターを必要とせずに、すべてのデータにすべてのキャンペーン階層データが入力されます。

<div id="common-url-parameter-mistakes-to-avoid" />

## 避けるべき一般的なURLパラメータの間違い

<div id="question-marks" />

### 疑問符（?）

* 疑問符は、ランディングページのURLとパラメータの間に 1つだけ使用してください。
* URLに他の疑問符を使用しないでください。

　（例：）

誤った例：

`www.website.com??parameters`

`www.website.com?parameter1?parameter2`

<div id="anchor-signs" />

### アンカーサイン（#）

URLには、アンカー記号 (#) を使用しないでください。URLでアンカー記号を使用すると、署名フォームの後のパラメーターが読み込まれず、Web SDK によって収集されない可能性があります。

<div data-zendesk-anchors="pba-website-attribuiton-urls=pba%E3%82%A6%E3%82%A7%E3%83%96%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%88%E6%B8%ACurl url-parameters%E2%80%94group-and-priority=url-%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF--%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%97%E3%81%A8%E5%84%AA%E5%85%88%E5%BA%A6 supported-parameters=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC url-parameter-best-practices=url%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%99%E3%82%B9%E3%83%88%E3%83%97%E3%83%A9%E3%82%AF%E3%83%86%E3%82%A3%E3%82%B9 selecting-url-parameters=url%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E9%81%B8%E6%8A%9E implement-dynamic-urls-using-ad-network-macros=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E3%83%9E%E3%82%AF%E3%83%AD%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E5%8B%95%E7%9A%84url%E3%81%AE%E5%AE%9F%E8%A3%85 consistent-case-within-parameters=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC%E5%86%85%E3%81%AE%E4%B8%80%E8%B2%AB%E3%81%97%E3%81%9F%E5%A4%A7%E6%96%87%E5%AD%97%E3%81%A8%E5%B0%8F%E6%96%87%E5%AD%97 use-google-ads-integration-to-automate-granularity=google-ads%E3%81%AE%E9%80%A3%E6%90%BA%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%A6%E7%B2%92%E5%BA%A6%E3%82%92%E8%87%AA%E5%8B%95%E5%8C%96 common-url-parameter-mistakes-to-avoid=%E9%81%BF%E3%81%91%E3%82%8B%E3%81%B9%E3%81%8D%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AAurl%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E9%96%93%E9%81%95%E3%81%84 question-marks=%E7%96%91%E5%95%8F%E7%AC%A6 anchor-signs=%E3%82%A2%E3%83%B3%E3%82%AB%E3%83%BC%E3%82%B5%E3%82%A4%E3%83%B3" />
