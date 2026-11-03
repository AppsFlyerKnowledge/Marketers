---
title: PBA Webサイト計測の管理画面
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
  created_at: '2018-12-09T07:49:24Z'
  edited_at: '2026-10-14T09:33:54Z'
  id: 360000654377
  locale: ja
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ja/articles/360000654377
---
> **概要：** 概要：効果的なWebサイトトラフィックを促進するためのマーケティング施策の成果を測定します。どのメディアソース、広告タイプ、チャネルが、サイト訪問、コンバージョンイベントをもたらしているかを広告レベルのメトリクスで確認できます。

[![Website_Attribution.jpg](https://files.readme.io/59cda285cb1f2b88c6992f3d303ee87e33176f82f0cf7afedb4711ee363e3a73-360015253418.jpg)](https://files.readme.io/59cda285cb1f2b88c6992f3d303ee87e33176f82f0cf7afedb4711ee363e3a73-360015253418.jpg)

## PBA Webサイト計測

Webサイト計測管理画面を使用することで、訪問者とコンバージョンをもたらすメディアソースについてのインサイトを得ることができます。

* トレンドチャートを使用して、メディアソースおよびチャネルについての全体的な傾向と貢献度の内訳を確認できます。
* 広告／広告セットレベルまでの詳細な情報を把握し、各コンバージョンイベントのパフォーマンス指標を確認します。

**マーケターは、管理画面を使用して次のようなインサイトを得ることができます。**

| ![icon2.png](https://files.readme.io/77fda01229f4b1b50755bc94f35cc021928ba7af1e3b5b45e61606ab18e8fd7a-360013383917.png) | **パフォーマンス**<br /><br />どのメディアソースやキャンペーンが、自社のWebサイトへ最も多くの訪問者、コンバージョン、価値をもたらしたのか。 |
| --- | --- |
| ![Icon1.png](https://files.readme.io/b20da70a56d881dd2fe31b18df8919db43b47e3e2338b89da7ef5ef6467590d6-360013383937.png) | **効果**<br /><br />どの獲得チャンネルが最高のパフォーマンスKPI（コンバージョン率、ARPU等）を持っているか。 |
| ![s4.png](https://files.readme.io/9a426232668022a9b4d006e685d2384d61efe4814c377aa9295e9b7887f14fef-360013383957.png) | **比較分析** |

## 管理画面の使い方

**PBA管理画面を開くには、次のいずれかを実行してください。**

* PBA管理画面 をクリックしてください。 Websiteアトリビューション のタブを開いてください。

<Table>
  <thead>
    <tr>
      <th>
        要素
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        日付選択とフィルタ
      </td>
      <td>
        ![WebsiteAttributionFilterPaner_us-en.jpg](https://files.readme.io/1d4cb6145bd0a297d9d358b904968cdffadc4235499ba661048983de8dbc348c-360013057737.jpg)

        * 計測日の範囲、<Anchor target="_blank" href="/marketers/ja/docs/using-pba-dashboards">フィルタ、グループ化オプション</Anchor>を選択します。
        * フィルターフィルタ：メディアソース、メディアタイプ、メディアチャネル、地域、コンバージョンイベント
        * グループ化グループ化：メディアソース／キャンペーン、メディアタイプ、メディアチャネル、デバイスタイプ、プラットフォーム
      </td>
    </tr>
    <tr>
      <td>
        Chart（グラフ）
      </td>
      <td>
        **時間経過に伴うWebサイトのアクティビティ**

        ![WebsiteAttribution_us-en__1_.jpg](https://files.readme.io/cfa214a82b39db1fdbed128029dd28fdf4b623f2c0c7d7f51e067d5e182431ca-360013057717.jpg)

        * 特定の期間の訪問とコンバージョンのソースを表示します。
      </td>
    </tr>
    <tr>
      <td>
        テーブル
      </td>
      <td>
        **計測テーブル**

        [![WebsiteAttributionTable_us-en.jpg](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)

        * ウェブサイト全体の指標は、コンバージョンイベントごとの内訳とともに利用できます。
        * メディアソースから広告レベルまでドリルダウンして、ウェブサイトへのトラフィックを促進する特定のメディアソースや広告を明らかにします。
        * トラフィックの誘導とコンバージョンにおける広告効果を比較します。

        | 指標 | 説明 |
        | --- | --- |
        | <span id="visits"></span>アクセス数 | Webサイトを訪問するユーザーのセッション数 |
        | <span id="unique-visitors"></span>ユニークユーザー数 | サイトへのユニーク訪問者数。ユニークユーザーは、PBAによりPBAプライベートユーザーのグラフを使って決定します。グラフの整合性を保つためには、<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">CUID</Anchor>を実装する必要があります。同じユーザーが異なるブラウザを使ってサイトにアクセスしても、1回しかカウントされません。 |
        | <span id="conversions"></span>コンバージョン | 実行されたコンバージョンイベント数 |
        | <span id="conversion-rate"></span>コンバージョン率 | 数式： |
        | <span id="acpu"></span>ACPU | ユニーク訪問者あたりの平均コンバージョン数。数式： |
        | <span id="revenue"></span>収益 | すべてのイベントからの収益 |
        | <span id="arpu"></span>ARPU | ユーザー当たりの平均収益数式：収益 ÷ ユニークユーザー数 |

        | コンバージョンイベント指標 | 説明 |
        | --- | --- |
        | <span id="event-count"></span>イベントカウント | イベントが実行された回数 |
        | <span id="unique-users"></span>ユニークユーザー数 | コンバージョンイベントを実行したユニークユーザー |
        | <span id="revenue::58195989"></span>収益 | このコンバージョンイベントに関連する収益 |
        | <span id="arpe"></span>ARPE | コンバージョンイベントあたりの平均収益。数式： |
      </td>
    </tr>
    <tr>
      <td>
        CSVファイルを抽出する
      </td>
      <td>
        [**Export CSV**] をクリックして表をエクスポートしてください。
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="pba-website-attribution=pba-web%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%88%E6%B8%AC h_01HJR6ZPF5VWPX9020G0W7NX4X=pba-web%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%88%E6%B8%AC dashboard-reference=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E4%BD%BF%E3%81%84%E6%96%B9 h_01HJR6ZPF58VWA51QWY4BGZN8E=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E4%BD%BF%E3%81%84%E6%96%B9" />
