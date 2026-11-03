---
title: お知らせ：お知らせ：集計データの更新頻度の変更
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Marketing Analytics
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Ad Networks
  created_at: '2021-07-20T11:47:58Z'
  edited_at: '2026-10-14T09:25:26Z'
  id: 4404329828497
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/4404329828497
---

<Table>
  <tbody>
    <tr>
      <td>
        ヘッドライン
      </td>
      <td>
        アナリティクスレポートと管理画面のインストールとアプリ内イベントのデータ更新頻度
      </td>
    </tr>
    <tr>
      <td>
        更新日
      </td>
      <td>
        2021年8月24日
      </td>
    </tr>
    <tr>
      <td>
        変更点
      </td>
      <td>
        インストールとアプリ内イベントのデータ更新頻度が変わります。この表では、変更前と変更後の更新頻度を示しています。

        #### イベントタイプごとのデータ更新頻度

        | イベントタイプ | 変更前（分） | 変更後<br /><br />（分） |
        | --- | --- | --- |
        | インストール、リアトリビューション、およびリエンゲージメント | 2024-02-26 | 2024-02-26 |
        | アプリ内イベント | 90 | 30-60 |
      </td>
    </tr>
    <tr>
      <td>
        変更点
      </td>
      <td>
        データ更新頻度の変更はリストにある管理画面とレポーティングツールに影響します。変更は、次のように段階的に行われます。

        **フェーズ1—2021年9月12日より開始（変更する可能性があります）**

        * ダッシュボード：
          * 概要
          * オーバービューV2
          * リターゲティング
          * イベント
          * カスタム
        * Pull API - 集計パフォーマンスレポート

        フェーズ2—<strong>2021年10月6日（予定）</strong>開始

        * ダッシュボード：
          * アクティビティ
          * コホート
        * API*コホート
      </td>
    </tr>
    <tr>
      <td>
        変更しない点
      </td>
      <td>
        Master PIとローデータ
      </td>
    </tr>
    <tr>
      <td>
        必要な対応
      </td>
      <td>
        * データの閲覧やダウンロード時に、データ更新頻度を考慮してください。
        * オーバービュー管理画面を使用して、SDK連携やアドネットワークパートナーとの連携をテストする場合、インストールイベントが表示されるまで時間がかかります。連携テストの際にローデータレポートを使用することを検討してください。
      </td>
    </tr>
  </tbody>
</Table>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support">AppsFlyerのデータの更新頻度</Anchor>
> * AppsFlyerの新機能・リリース情報

<div data-zendesk-anchors="data-freshness-rate-per-event-type=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%BF%E3%82%A4%E3%83%97%E3%81%94%E3%81%A8%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E6%9B%B4%E6%96%B0%E9%A0%BB%E5%BA%A6 h_01HDP21Y0H5S3R4GR5411R6D4Y=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%BF%E3%82%A4%E3%83%97%E3%81%94%E3%81%A8%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E6%9B%B4%E6%96%B0%E9%A0%BB%E5%BA%A6 h_01HDPE9QAQ41ADC9DQGSK80288=%E5%8F%82%E7%85%A7" />
