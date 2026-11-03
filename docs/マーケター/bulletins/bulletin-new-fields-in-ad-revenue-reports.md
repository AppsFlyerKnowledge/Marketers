---
title: お知らせ：広告収益レポートの新しいデータ項目
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-07-22T13:25:32Z'
  edited_at: '2026-10-14T09:33:17Z'
  id: 26907692192273
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/26907692192273
---

<Table>
  <tbody>
    <tr>
      <td>
        **変更点**
      </td>
      <td>
        広告収益レポートに新しい項目が追加されました。
      </td>
    </tr>
    <tr>
      <td>
        **発効日**
      </td>
      <td>
        2022年9月
      </td>
    </tr>
    <tr>
      <td>
        **知っておくべきこと**
      </td>
      <td>
        次の表は、どのフィールドがどのレポートに追加されているかを示しています。各フィールドの定義と詳細については、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">ローデータ項目の手引き</Anchor>を参照してください。

        | レポート | APIフィールド名 |
        | --- | --- |
        | <Anchor target="_blank" href="/marketers/ja/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">従来の広告収益 [単一バージョン]</Anchor> | * {"engagement_type"}<br />* カスタムデータ<br />* {"customer_user_id"}<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/ja/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">広告収益（バージョン管理済み）</Anchor> | * {"engagement_type"}<br />* カスタムデータ<br />* {"customer_user_id"}<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/ja/docs/revenue-etl-reports#impression-level-report">広告収益 [SDKインプレッションレベル]</Anchor> | * {"engagement_type"}<br />* カスタムデータ<br />* {"customer_user_id"}<br />* {"ad_revenue_ad_type"}<br />* {"ad_revenue_custom_parameters"}<br />* {"app_version"}<br />* {"sdk_version"} |
      </td>
    </tr>
    <tr>
      <td>
        **必要な対応**
      </td>
      <td>
        * <Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#set-up-data-locker">AppsFlyerのData Locker設定</Anchor>で、レポートに追加する新しいフィールドを選択します。  
          **ヒント**!デフォルトのData Locker設定で customer\_user\_id のようなフィールドをすでに受け取っている場合、広告収益レポートにフィールドを入力するには、別の新しいフィールドを追加して設定を保存する必要があります。後で変更を元に戻すことができます。
        * 新しいフィールドを取り込んで使用できるようにBIシステムを設定してください。
      </td>
    </tr>
  </tbody>
</Table>
