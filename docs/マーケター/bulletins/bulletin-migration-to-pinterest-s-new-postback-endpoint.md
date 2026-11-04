---
title: お知らせ：Pinterestの新しいポストバックエンドポイントへの移行
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2025-07-23T07:26:53Z'
  edited_at: '2026-10-14T09:24:46Z'
  id: 37418019002641
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/37418019002641
---

<Table>
  <thead>
    <tr>
      <th>
        セクション
      </th>
      <th>
        詳細
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **更新情報**
      </td>
      <td>
        Pinterestは、コンバージョンAPI（CAPI）インフラストラクチャに基づく新しいエンドポイントに移行しました。アプリイベントを引き続きPinterestに送信するには、既存の設定から新たな設定へ更新する必要があります。2025年9月30日に古いエンドポイントを廃止する予定です。
      </td>
    </tr>
    <tr>
      <td>
        **発効日**
      </td>
      <td>
        2025年7月23日
      </td>
    </tr>
    <tr>
      <td>
        **更新内容**
      </td>
      <td>
        > 📘 **注意**
        >
        > この箇条書きには、CAPIへの移行フェーズに関する情報が含まれています。Pinterest連携に関する一般的な情報については、<Anchor target="_blank" href="/marketers/ja/docs/pinterest-create-a-mobile-app-integration#アプリ内イベントの設定">こちらの連携ガイド</Anchor>を参照してください。

        新しいAPIのアプリ内イベント設定にアップデートすることで、Pinterest計測が中断されることなく継続されるようになり、次が含まれます：

        * **さらに多くのイベントタイプ**：目標に合わせて、次のような追加イベントを追跡できるようになります - リード、検索、カテゴリ閲覧、ページ訪問など。
          * **注：** 新しい Pinterest V5エンドポイントのイベント名は異なります。これに応じて管理画面を更新しない場合、イベントレポートには「unknown」（不明）と表示されます。以下の新しいイベント名を確認してください。
        * **データ品質の向上：** 強化されたマッチングとより強力なアトリビューション精度

        新しい連携には、**広告アカウントID**と**アクセストークン**の両方が必要です。ポストバック機能を維持するために、パートナーは2025年9月30日までに新しいポストバックエンドポイントに移行する必要があります。   

        **Pinterest AppsFlyer広告アカウントIDの見つけ方**  
        現在のAppsFlyer Pinterestコンバージョンレポートの広告アカウントIDは、Pinterest **Business Manager**またはPinterest**コンバージョン**レポートで確認できます。

        1. Pinterest ビジネスアカウントにログインします（Hub オプションを表示するには、ビジネスプロファイルにログインする必要があります）。
        2. https://www.pinterest.com/business/hub/ をブラウザに入力または貼り付け、Enter キーを押します。
        3. ハブの左側の暗いグレーのナビゲーション列を見てください。列が折りたたまれている場合は、左上隅にある小さな「≡」（ハンバーガー）アイコンをクリックして展開します。
        4. 少しスクロールダウンすると「Manage business」というセクションが表示されます。
        5. 「Manage business」傘下の「Conversion」クリックします。Conversionダッシュボードが開き、Pinterestに送信されたAppsFlyerのコンバージョンを確認できます。
        6. 広告アカウントIDがURLに表示されます。
        7. 複数のPinterest広告アカウントIDがAppsFlyerからクローンされたコンバージョンを受信する場合は、Pinterest Business Managerで既存のすべての広告アカウントIDをConversionsで確認してください。AppsFlyerコンバージョンの元の親広告アカウントIDが選択されていることを確認してください。

        **Pinterest AppsFlyerアクセストークンの見つけ方**  
        <Anchor target="_blank" href="https://help.pinterest.com/en/business/article/getting-started-with-the-conversions-api">Pinterestのヘルプセンターで説明されている手順</Anchor>を参照してください。Pinterest Conversions で、**Conversions API** > **Set-up API** をクリックし、アカウントの新しいアクセストークンを生成します。  

         重要な注意点：すでにAppsFlyer以外でPinterestのコンバージョンAPIを別途設定している場合は、AppsFlyerのコンバージョンにもここで同じアクセストークンを使用してください。
      </td>
    </tr>
    <tr>
      <td>
        **必要な対応**
      </td>
      <td>
        AppsFlyer管理画面でアプリ内イベントポストバックの設定と移行を行うには、以下の手順に従ってください。

        1. **アプリ内イベントの設定と管理画面パラメータの処理**  
           現在、AppsFlyerイベントをPinterestにマッピングするために、次の管理画面パラメーターをサポートしています。

           * **広告アカウントID**（表示）
           * **アクセストークン**（表示）
           * **タグID**（管理画面には表示されませんが、新しいV5バージョンへの移行を支援するためにバックエンドでサポートされています。V5エンドポイントへの移行が完全にサポートされると、タグIDもバックエンドから削除されます。)

           **注記：**  
           新しいポストバック設定では、**広告アカウントID**と**アクセストークン**の両方を入力する必要があります（これらはまだ利用できない場合はPinterestから取得できます）。**これらの値のいずれかが欠けている場合、ポストバックは失敗**します。Pinterestの**AppsFlyer連携済みパートナー**画面に両方のパラメータが正しく入力されていることを確認してください。詳細：<Anchor target="_blank" href="/marketers/ja/docs/pinterest-create-a-mobile-app-integration#アプリ内イベントの設定">こちら</Anchor>を参照  
           スムーズな移行には、皆様のご協力が重要です。ご支援ありがとうございます。
        2. **アプリ内イベントマッピングとポストバック設定**
           1. <span class="af-ol-a"></span>現在の Pinterest イベント名を、**パートナーイベント名**セクションの新しい Pinterest コンバージョン API イベント名に置き換えてマッピングしてください。たとえば、パートナーイベントセクションで `pin_add_to_cart` を使用している場合は、代わりに `add_to_cart` に置き換えます。詳細：**こちら**を参照

        | event name (Legacy) | event name（新しいコンバージョンAPI） |
        | --- | --- |
        | pin\_add\_to\_cart | add\_to\_cart |
        | pin\_purchase | checkout |
        | pin\_search | serach |
        | pin\_registration | signup |
        | pin\_sign\_up | signup |
        | pin\_category\_view | view\_category |
        | add\_cart | add\_to\_cart |
        | start\_checkout | checkout |
        | content\_view | view\_category |

              **注記：** コンバージョンAPIの従来のイベント名を正しいイベント名で更新しないと、Pinterestのイベント名に正しいイベント名ではなく「その他」と表示されます。
           2. **アプリ内イベントポストバック期間**を**ライフタイム**に選択すると、Pinterestは広告最適化のために最大数のコンバージョンを取得できます。
           3. Pinterest が広告最適化のために最大数のコンバージョンを受け取れるようにするには、**送信オプション**で**オーガニックを含む全てのメディアソース**を選択します。詳細：**こちら**を参照
        3. **問題発生時のロールバックプロセス**  
           広告主は、PinterestでAppsFlyerアプリのコンバージョンを監視し、移行に伴う問題を検出することをお勧めします。AppsFlyerのコンバージョンデータがPinterestに表示されるまで最大30分程度の猶予期間を設け、数日間の定期的なモニタリングを行い、移行の成功を検証してください。  

           広告主は、連携設定で `account_id` と `access_token` の一方または両方を省略することで、従来のエンドポイントに戻すことができます。 

           **動作ルール：**

           * `account_id` と `access_token` の両方がない → ポストバックはレガシー（古い）エンドポイントに送信されます。
           * `account_id` のみが存在（`access_token` が空白） → ポストバックはレガシー（古い）エンドポイントに送信されます。
           * `access_token` のみが存在（`account_id` が空白） → ポストバックはレガシー（古い）エンドポイントに送信されます。
           * `account_id` と`access_token` の両方が存在 → ポストバックが新しいエンドポイントに送信されます。

           問題が発生した場合は、support@appsflyer.com 経由でAppsFlyerサポートにお問い合わせください。Pinterestに関するご質問は、api-support@pinterest.com またはPinterest担当者までお問い合わせください。
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="h_01K0VD1AY1XVQWA6JP0WCQP8RN=%E6%B3%A8%E6%84%8F" />
