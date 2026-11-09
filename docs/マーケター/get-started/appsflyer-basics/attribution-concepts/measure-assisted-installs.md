---
title: アシストインストールの計測
metadata:
  keywords:
    - Attribution
    - installs
    - Assisted
    - multi-touch
    - reporting
    - assisted intalls
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:21:25Z'
  edited_at: '2026-10-28T09:07:55Z'
  id: 207040506
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/207040506
---
> **概要：** 最後の広告接触だけでなく、それ以前にユーザーと接触し、インストールに貢献したメディアソースの効果も計測できます。

<div id="assisted-installs" />

## アシストインストール

<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/assisted-installs-mobile-advertising-assists/">アシストインストール</Anchor>（マルチタッチアトリビューションとも呼ばれる）とは、最後の広告接触ではないものの、インストール前かつアトリビューションの対象期間内にユーザーと接触したメディアソースやキャンペーンによる貢献を計測するものです。 1件のインストールに対し、最大3件のアシストインストールを計上できます。

アシストインストールの分析データは、メディアソース別とキャンペーン別に確認できます。これにより、それぞれがインストールに与えた効果を、より広い視点から計測できます。

<div id="view-assisted-installs-metrics-in-the-overview-dashboard" />

### Overview dashboardでのアシストインストール指標の確認

**Overview dashboardでアシストインストールを確認する手順**：

1. AppsFlyerのサイドメニューで、**分析**＞**概要**を選択します。
2. Extended Overviewレポートを選択します。
3. 時系列の推移を示すグラフまでスクロールします。
4. **メディアソース**または**キャンペーン**のディメンションを選択します。
5. **アシストインストール**の指標を選択します。  
   アシストインストールのグラフが表示されます。青はノンオーガニックインストール、オレンジはアシストインストールを示します。 ![AssitedInstallWidget.png](https://files.readme.io/a2fb5fb1f7414ede9a96858e325688d0c60b2ff910e24bc86e5597160c7548ca-33302646504977.png)

<div id="why-are-assists-important" />

### アシストを計測することの重要性

多くの場合、見込みユーザーはアシストしたメディアソースを通じてアプリを知っても、何らかの理由ですぐにはインストールしません。そのため、キャンペーンの最適化や効果計測では、アシストの貢献を計測・評価することが重要です。

<div id="assisted-installs-reporting" />

### アシストインストールのレポート

AppsFlyerは、インストールの計測元に加えて、最大3つのアドネットワークを貢献元として記録します。

集計ダッシュボードとローデータレポートでは、最大3つの貢献元のアドネットワークを「アシストインストール」という1つの指標にまとめます。つまり、1件のインストールに対して、最大3件のアシストインストールが計上されます。

ローデータレポートでは、貢献元のアドネットワークのデータがContributors 1～3の個別フィールドに分かれています。

<Image align="center" alt="" src="https://files.readme.io/ee3558f74cedbec698c5e466a9697cad7a5b1910c45cd0851cfaf741959deba1-33302646505617.png" />

貢献元のアドネットワークごとに、ローデータレポートに以下の情報が含まれます。

* アドネットワーク名（メディアソース）
* キャンペーン名
* 広告接触日時（touch time）
* 広告接触の種類（クリックまたはインプレッション）
* 関与した代理店（パートナー）がある場合は、その名前
* マッチタイプ（<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#attribution::cecc12c5">インストールのマッチタイプと同じです</Anchor>）。)

<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview#ユーザージャーニーレポート">ユーザージャーニーのローデータ</Anchor>を参照してください。

<div id="note" />

> 📘 **注意**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">ユーザーレベルデータの共有を制限するメディアソース</Anchor>は、インストールの計測元が決まった際に、貢献元やアシストとして記録できません。 そのため、一部のメディアソースは、インストール前にユーザーと接触していても、貢献元として表示されません。

<div id="note-1" />

> 📘 **注意**
>
> 一部の主要アドネットワークは、代理店を含む<Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention">第三者のプラットフォームへのデータ共有を制限しています</Anchor>。そのため、これらのアドネットワークのアシストインストールは、代理店のダッシュボードには表示されません。

ローデータレポートでは、貢献元のアドネットワークのデータが**Contributors 1～3**の個別フィールドに分かれています。

<div id="total-candidates-field" />

### Total candidatesフィールド

**Contributors 1–3**に加えて、`total_candidates`フィールドには、インストールやリエンゲージメントの時点で、同じデバイスに関連する広告接触（クリックやインプレッションなど）の数が表示されます。

ただし、`total_candidates`に含まれるすべての広告接触が、アトリビューションの条件を満たすわけではありません。たとえば、以下のような広告接触が含まれる場合があります。

* ルックバック期間外のもの。
* 不正対策によってブロックされたもの。
* アプリやパートナーの連携設定の影響を受けたもの。
* その他、AppsFlyerのアトリビューション条件を満たさないもの。

具体的には、以下のことを意味します。

* インストールがオーガニックとして計測されている場合、`total_candidates`に含まれる広告接触のいずれも、アトリビューションに必要な条件をすべて満たしていません。
* 貢献元がない場合も同様に、`total_candidates`の広告接触が貢献元としての条件を満たしていません。

`total_candidates`は、受信した広告接触の数を表すもので、必ずしもアトリビューションの有効な候補数ではありません。このフィールドに値があっても、インストールがオーガニックとして計測されたり、貢献元がなかったりする場合があります。

<div id="note-2" />

> 📘 **注意**
>
> アトリビューションロジックが複雑なため、AppsFlyerサポートは`total_candidates`の個々の広告接触に関する説明や内訳を提供しません。

<div data-zendesk-anchors="assisted-installs=%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HCBC922K9PCDXGDCCVEARADH=%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB view-assisted-installs-metrics-in-the-overview-dashboard=overview-dashboard%E3%81%A7%E3%81%AE%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E6%8C%87%E6%A8%99%E3%81%AE%E7%A2%BA%E8%AA%8D h_01HCBC922KRHB043FK1CQRKXDA=overview-dashboard%E3%81%A7%E3%81%AE%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E6%8C%87%E6%A8%99%E3%81%AE%E7%A2%BA%E8%AA%8D why-are-assists-important=%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%92%E8%A8%88%E6%B8%AC%E3%81%99%E3%82%8B%E3%81%93%E3%81%A8%E3%81%AE%E9%87%8D%E8%A6%81%E6%80%A7 h_01HCBC922KDAG8T27KK2JGRE7C=%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%92%E8%A8%88%E6%B8%AC%E3%81%99%E3%82%8B%E3%81%93%E3%81%A8%E3%81%AE%E9%87%8D%E8%A6%81%E6%80%A7 assisted-installs-reporting=%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HCBC922KJV54QW6G85SN2JM7=%E3%82%A2%E3%82%B7%E3%82%B9%E3%83%88%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01KSFPXWNAX8FZ6H2ZKN1Z2TJQ=%E6%B3%A8%E6%84%8F h_01HCBC922K5HKF94JCY7C88R88=%E6%B3%A8%E6%84%8F-1 total-candidates-field=total-candidates%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01K453B1K1X7QVJHPQ505P745N=%E6%B3%A8%E6%84%8F-2" />
