---
title: 公開情報： Google マーケティング プラットフォーム(GMP)統合の移行
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-12-18T11:43:04Z'
  edited_at: '2026-10-14T09:33:35Z'
  id: 21035061438737
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/21035061438737
---

<Table>
  <tbody>
    <tr>
      <td>
        **更新情報**
      </td>
      <td>
        <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">デジタル マーケティング法</Anchor> （DMA) の施行に向けた準備の一環として、Google は <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">EU ユーザーの同意ポリシー</Anchor>を更新しています。AppsFlyer は、Google のポリシー要件をサポートするために必要な変更を行っています。

        現在、次の Google マーケティングプラットフォーム (GMP) 統合を利用できます。

        * [レガシー] CM360 (DoubleClick) `doubleclick_int`
        * <Anchor target="_blank" href="/marketers/ja/docs/google-marketing-platform-display-video-360-dv360-integration">DV360 （新規統合）</Anchor> `dv360_int`

        2024年7月現在、レガシーのdoubleclick\_int統合は今後の廃止モードにあり、まもなく廃止される予定です（最終日付は発表されます）。この統合を使用している場合、新しい DV360 統合に移行して、キャンペーンの実行と GMP を使用した測定を続行する必要があります。
      </td>
    </tr>
    <tr>
      <td>
        **必要な対応**
      </td>
      <td>
        できるだけ早く新しいDV360`dv360_int` 統合に移行してください。
      </td>
    </tr>
    <tr>
      <td>
        **手順**
      </td>
      <td>
        GMP と AppsFlyer の両方のプラットフォームを設定してください。

        **GMP で設定する**

        1. CM360 または DV360 アカウントにログインします。   
           **注記：** CM360 でこの手順を完了すると、DV360 で実施する必要はなくなります。
        2. <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">これらの手順</Anchor>でパートナー計測リンク(リンクID)を作成または再利用します。

        **AppsFlyer の設定**

        1. <Anchor target="_blank" href="/marketers/ja/docs/google-marketing-platform-display-video-360-dv360-integration#integration-procedures">これらの手順</Anchor>で、AppsFlyer での DV360 統合を完了してください。   
           **注記：** データの一貫性を維持するため、設定がレガシー統合（ルックバック期間、アプリ内イベントのポストバックなど）と類似していることを確認してください。
        2. **新しい統合のテスト：**  
           新しい統合データを確認するために、約1日待ってください。その後、レガシー統合を無効にすることができます。
      </td>
    </tr>
    <tr>
      <td>
        **お知らせ事項**
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <table><thead><tr><th><strong>注意事項</strong></th><th>利用可能なオプション</th></tr></thead><tbody><tr><td colspan="2"><span id="media-source-pid"></span><p><strong>メディアソース PID</strong></p></td></tr><tr><td><span id="after-completing-the-migration-the-dv360-media-source-pid-changes-from-doubleclick_int-to-dv360_int"></span><p>移行が完了すると、DV360 メディアソースの PID が <kbd>doubleclick_int</kbd> から<kbd>dv360_int</kbd>に変わります。</p></td><td>AppsFlyer から BI やサードパーティーの分析ツールにローデータを取り込む場合は、メディアソース名の変更を検討してください。</td></tr><tr><td colspan="2"><span id="outofstore-apps"></span><p><strong>Google Play以外のAndroidストア</strong></p></td></tr><tr><td><span id="apps-from-unofficial-app-stores-arent-supported-in-the-dv360-integration-the-integration-relies-on-a-link-id-which-is-generated-for-apps-obtained-through-official-app-stores"></span><p>非公式アプリストアからのアプリは、DV360統合ではサポートされていません。統合は、公式アプリストアを通じて取得されたアプリのために生成されるリンクIDに依存しています。</p></td><td>公式アプリストア以外のソースからアプリをダウンロードした場合は、CSMまたはhello@appsflyer.comにお問い合わせください。</td></tr><tr><td colspan="2"><span id="attribution-data-duplication"></span><p>帰属データの配布</p></td></tr><tr><td colspan="2"><span id="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span>両方の統合がアクティブで、インストールの帰属を主張する場合、帰属はランダムに分割され、一方が主要なソースとなり、もう一方が貢献者として機能します。これによりデータが重複しないことが保証されます。例えば、DV360が100のインストールを担当している場合、レガシー統合から70のインストール、DV360から30のインストール、またはDV360から80のインストール、レガシー統合から20のインストールを見ることができます。</td></tr><tr><td colspan="2"><span id="inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span><span>レガシー統合に紐づくインストール/リエンゲージメントのアプリ内イベントは、それに応じてクレジットされます。</span></td></tr><tr><td colspan="2"><span id="reengagement-reengagement-attribution-is-supported-in-the-dv360-integration"></span><p><strong>リエンゲージメント</strong></p><p>DV360統合では、再エンゲージメントの帰属がサポートされています。</p></td></tr></tbody></table>

        フィールドの不一致

        レガシーAPIと更新されたAPIの利用可能なデータフィールドの違いにより、以下に示すように、いくつかのAppsFlyerフィールドに違いが見られる場合があります。

        | AppsFlyerのフィールド | レガシーフィールド（doubleclick\_int） | DV360フィールド（dv360\_int） |
        | --- | --- | --- |
        | キャンペーン名 | placement\_id | line\_item\_name |
        | Campaign ID | placement\_id | line\_item\_id |
        | 広告セット名 | ad\_id | は対応していません。 |
        | Adset ID | ad\_id | は対応していません。 |
        | 広告名 | creative\_id | は対応していません。 |
        | Ad ID | creative\_id | creative\_id |
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected%0Ainapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly=while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly reengagement%0Areengagement-attribution-is-supported-in-the-dv360-integration=reengagement-reengagement-attribution-is-supported-in-the-dv360-integration" />
