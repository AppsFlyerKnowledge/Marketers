---
title: ランディングページURL用のアトリビューションパラメータの選択
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T16:46:08Z'
  edited_at: '2026-10-14T09:23:17Z'
  id: 43525434385809
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/43525434385809
---
> **概要：** Web Performance Measurementで正確なアトリビューションを維持しながら、キャンペーンをより細かな粒度で分析するには、WebサイトのランディングページURLに、一貫性のある適切なパラメーターを設定することが重要です。

<div id="about-url-attribution-parameter-classes" />

## URLアトリビューションパラメータの種類について

AppsFlyerは、ランディングページURL（ユーザーがクリックするリンク）に含まれるキャンペーンパラメータを読み取り、セッションやイベントを適切な**メディアソース**、**キャンペーン**、および利用可能な場合は**広告セット**や**広告**などのより詳細な階層へアトリビューションします。

設定するパラメータによって、キャンペーンの計測結果は変わります。つまり、同じランディングページであっても、設定するパラメータによって得られる計測結果は大きく異なる場合があります。

URLパラメーターは、大きく以下の2種類に分かれます。

* PIDクラス：AppsFlyer独自のURLパラメーター
* UTMクラス：標準的なUTMパラメーター

Web Performance MeasurementでURLパラメーターがどのように処理されるかについては、「<Anchor target="_blank" href="/marketers/ja/docs/about-traffic-source-resolution">トラフィックソースの判別について</Anchor>」をご覧ください。

<div id="supported-pid-and-utm-parameters" />

### 対応しているPID／UTMパラメーター

Web Performance Measurementで利用できるパラメーターは以下のとおりです。

| # | パラメータ | 用途 | パラメータの種類 | ダッシュボード表示 | ローデータレポートの項目 |
| --- | --- | --- | --- | --- | --- |
| 1 | `pid` | メディアソース | PID | 可能 | `media_source` |
| 2 | `c` | キャンペーン名 | PID | 可能 | `campaign_name` |
| 3 | `af_c_id` | キャンペーンID | PID | 可能 | `campaign_id` |
| 4 | `af_adset` | 広告セット名 | PID | 可能 | `adset_name` |
| 5 | `af_adset_id` | 広告セットID | PID | 可能 | `adset_id` |
| 6 | `af_ad` | 広告名 | PID | 可能 | `ad_name` |
| 7 | `af_ad_id` | 広告ID | PID | 可能 | `ad_id` |
| 8 | `utm_source` | メディアソース | UTM | 可能 | `media_source` |
| 9 | `utm_medium` | メディアタイプ | UTM | 不可 | `media_type` |
| 10 | `utm_campaign` | キャンペーン名 | UTM | 可能 | `campaign_name` |

<div id="choose-the-right-attribution-parameters" />

## 適切なアトリビューションパラメータの選択

AppsFlyerは、メディアソースやキャンペーンなど、レポート項目ごとに定義された優先順位（ウォーターフォール）に従って、URLパラメータを個別に評価します。この仕組みにより、AppsFlyer独自の**PIDパラメータ**と、標準的なマーケティングパラメータである**UTM**を同じURL内で併用できるため、Google Analyticsなど他の分析ツールと併せてAppsFlyerのWebアトリビューションを利用できます。

値の決定は、フィールドごとに定められた優先順位に基づいて行われます。ある項目について優先度の高いPIDパラメータが存在しない場合は、その項目に対応するUTMパラメータへ自動的にフォールバックし、その値を使用して該当項目を判定します。

<div id="scenario-a-url-with-pid-class-only-appsflyer-reporting" />

<Accordion title="シナリオA：PIDパラメータのみを使用する場合（AppsFlyerでのレポートを重視）">

AppsFlyerでのレポートを主な目的とする場合は、PIDパラメータを使用します。

<div id="example" />

#### 例

```http
www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}
```

**結果**：AppsFlyerは、`pid` を使用してメディアソースを判定し、`c` を使用してキャンペーンを判定します。

</Accordion>

<div id="scenario-b-url-with-utm-class-only-fallback" />

<Accordion title="シナリオB：UTMパラメータのみを使用する場合（フォールバック）">

`pid` が存在しない場合、AppsFlyerはUTMパラメータを使用して判定します。

<div id="example-1" />

#### 例

```http
 www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}
```

**結果**：AppsFlyerは、`utm_source` を使用してメディアソースを判定し、`utm_campaign` を使用してキャンペーンを判定します。

</Accordion>

<div id="scenario-c-url-with-both-pid-and-utm-classes" />

<Accordion title="シナリオC：PIDパラメータとUTMパラメータを併用する場合">

AppsFlyerでは、同じURL内でPIDパラメータとUTMパラメータを併用できます。これは、Google Analyticsや社内計測システムなど、AppsFlyer以外の分析ツールと併せて利用する場合に便利です。

AppsFlyerは、メディアソースやキャンペーンなどの各アトリビューション項目をそれぞれ独立して処理します。各項目について優先順位（ウォーターフォール）に従って判定を行い、通常は該当項目において**PIDパラメータ**が**UTMパラメータ**より優先されます。

<div id="example-1-overlapping-parameters" />

#### 例1：同じ項目がPIDパラメータとUTMパラメータの両方に含まれている場合

```http
www.website.com?pid=facebook_ads&c=summer_sale&utm_source=facebook&utm_campaign=seasonal_promo
```

* **メディアソース：** AppsFlyerは `pid` と `utm_source` の両方を検出します。この項目では優先順位に従い、`facebook_ads`を記録します。
* **キャンペーン：** AppsFlyerは `c` と `utm_campaign` の両方を検出します。この項目では優先順位に従い、`summer_sale`を記録します。
* **結果：** AppsFlyerでは優先順位の高いPIDパラメータの値が使用されます。一方で、外部ツールでは引き続きUTMパラメータを利用できます。

<div id="example-2-mixed-parameter-classes" />

#### 例2：PIDパラメータとUTMパラメータが異なる項目に設定されている場合

```http
www.website.com?utm_source=facebook&c=summer_sale
```

* **メディアソース：** AppsFlyerは`utm_source`を検出します。対応するPIDパラメータ（`pid`）が存在しないため、UTMパラメータの`facebook`をメディアソースとして記録します。
* **キャンペーン：** AppsFlyerは`c`を検出します。対応するUTMパラメータ（`utm_campaign`）が存在しないため、PIDパラメータの`summer_sale`をキャンペーンとして記録します。
* **結果：** AppsFlyerは各項目を個別に判定するため、PIDパラメータとUTMパラメータを組み合わせていても、両方の値を利用して正しくアトリビューションを行います。

</Accordion>

<div id="other-best-practices" />

## その他のベストプラクティス

<div id="keep-parameter-values-in-a-consistent-case" />

<Accordion title="パラメータ値の大文字・小文字を統一する">

パラメータ値では、大文字と小文字が区別されます。例えば、`utm_source=channel1`と`utm_source=CHANNEL1`は、**異なるメディアソースとして扱われます。**

ベストプラクティス：パラメータ値の表記ルール（一般的にはすべて小文字）を決め、すべてのURLで統一してください。

</Accordion>

<div id="use-question-marks-only-once" />

<Accordion title="クエリパラメータの前に「?」を使用するのは1回だけにする">

ルール：

* URLのクエリパラメータの前には、「`?`」を**1回だけ**使用してください。
* URL内で「?」を複数回使用しないでください。

正しいフォーマット：

* `www.website.com?parameters`

間違ったフォーマット：

* `www.website.com??parameters`
* `www.website.com?parameter1?parameter2`

</Accordion>

<div id="don-t-use-anchor-signs" />

<Accordion title="アンカー記号（#）を使用しない">

URLにアンカー記号（`#`）を使用しないでください。

理由：`#`以降のパラメータは読み込まれない場合があり、Web SDKで記録されない可能性があります。

</Accordion>

<div data-zendesk-anchors="about-website-attribution-urls=url%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E7%A8%AE%E9%A1%9E%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KGMRXNWGXQ3CH5XGSREV6Z3R=url%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E7%A8%AE%E9%A1%9E%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 supported-pid-and-utm-parameters=%E5%AF%BE%E5%BF%9C%E3%81%97%E3%81%A6%E3%81%84%E3%82%8Bpidutm%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01KGMRXNWG88REW1CVJ4XMYFHQ=%E5%AF%BE%E5%BF%9C%E3%81%97%E3%81%A6%E3%81%84%E3%82%8Bpidutm%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC choose-the-right-attribution-parameters=%E9%81%A9%E5%88%87%E3%81%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E9%81%B8%E6%8A%9E h_01KGMRXNWGP1SFBWE3KG6VRZ9V=%E9%81%A9%E5%88%87%E3%81%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E9%81%B8%E6%8A%9E h_01KGMRXNWGT9MS799QH9EP29XR=scenario-a-url-with-pid-class-only-appsflyer-reporting example=%E4%BE%8B h_01KGMS1RMN3F1D0Q7HDZMGG19E=%E4%BE%8B h_01KGMRXNWG0T3YCK0RPKX4B3BT=scenario-b-url-with-utm-class-only-fallback example::4f5c28b5=%E4%BE%8B-1 h_01KGMS215ARDSY6NFQ8VEF6C2Y=%E4%BE%8B-1 h_01KGMRXNWGZH2ZBP9XR8C8TNFN=scenario-c-url-with-both-pid-and-utm-classes example-1-overlapping-parameters=%E4%BE%8B1%E5%90%8C%E3%81%98%E9%A0%85%E7%9B%AE%E3%81%8Cpid%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8utm%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E4%B8%A1%E6%96%B9%E3%81%AB%E5%90%AB%E3%81%BE%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 h_01KGMS10B1QCRJ5N28FBNEEKR2=%E4%BE%8B1%E5%90%8C%E3%81%98%E9%A0%85%E7%9B%AE%E3%81%8Cpid%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8utm%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E4%B8%A1%E6%96%B9%E3%81%AB%E5%90%AB%E3%81%BE%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 example-2-mixed-parameter-classes=%E4%BE%8B2pid%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8utm%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%8C%E7%95%B0%E3%81%AA%E3%82%8B%E9%A0%85%E7%9B%AE%E3%81%AB%E8%A8%AD%E5%AE%9A%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 h_01KGMS17B500RPGHSKJ1AJSYH8=%E4%BE%8B2pid%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8utm%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%8C%E7%95%B0%E3%81%AA%E3%82%8B%E9%A0%85%E7%9B%AE%E3%81%AB%E8%A8%AD%E5%AE%9A%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 other-best-practices=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E3%83%99%E3%82%B9%E3%83%88%E3%83%97%E3%83%A9%E3%82%AF%E3%83%86%E3%82%A3%E3%82%B9 h_01KGMRXNWGVJY55M83FVMKBP1X=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E3%83%99%E3%82%B9%E3%83%88%E3%83%97%E3%83%A9%E3%82%AF%E3%83%86%E3%82%A3%E3%82%B9 h_01KGMRXNWG9S03GGBDXPN34DDM=keep-parameter-values-in-a-consistent-case h_01KGMRXNWGEF9D0ZH5M81RP0PH=use-question-marks-only-once don%E2%80%99t-use-anchor-signs-=don-t-use-anchor-signs h_01KGMRXNWGX6HA0R9X3VC2WFXV=don-t-use-anchor-signs" />
