---
title: お知らせ：TikTok for Business— アドバンスSRN
metadata:
  keywords:
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
  created_at: '2022-07-26T12:27:56Z'
  edited_at: '2026-10-14T09:39:34Z'
  id: 7925111265041
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/7925111265041
---
> 📘 **注意**
>
> 2023年1月30日に、新しい**TikTok for Business—高度なSRN**統合`tiktokglobal_int`が追加されましたが、**レガシーTikTok for Business**統合`bytedanceglobal_int`は徐々にフェーズアウトされ、2025年9月9日までに廃止されます。この移行はTikTokによって管理され、古い統合を削除する時期をすべての顧客に通知します。**データの損失を防ぐために、移行フェーズ中は両方の連携をアクティブに保ってください**。

| <span id="headline"></span>**ヘッドライン** | AppsFlyerがTikTok For BusinessをアドバンスSRNとして計測対応しました |
| --- | --- |
| <span id="effective-date"></span>**発効日** | <ul><li>1月18日tiktokglobal\_int</li><li>2025年9月9日:レガシー`bytedanceglobal_int`の廃止</li></ul> |
| <span id="where-is-it-changing"></span>**変更点** | 連携済みパートナーページ：Tiktok for Business連携画面 |
| <span id="required-actions"></span>**必要なアクション** | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup">新しい連携を設定</Anchor>します。TikTok For Businessの新しいPIDは `tiktokglobal_int` です。</li><li>Legacy TikTok for Business `bytedanceglobal_int`との既存の連携が存在する場合、データの損失を防ぐため、**移行日**まで連携を解除しないでください（下の行を参照）。</li></ul> |
| <span id="transition-date"></span>**移行日** | 新しい統合を有効にし、TikTok For Businessが期待通りに機能することをテストした後、彼らはレガシー`bytedanceglobal_int`統合から新しい統合への移行の正確な日付を通知するために連絡します。この**最大45日かかる場合があります**。その間、ダッシュボードとレポートはレガシー統合からのデータを表示し続けます。<br /><br />移行日を過ぎると、管理画面とレポートには新しい`tiktokglobal_int` 連携のデータが表示されます。<br /><br />**注記：** 注意：レガシー連携から移行されていない新しい統合の場合、データは直ちに管理画面とレポートに表示されます。 |
| <span id="what-does-this-new-integration-mean"></span><strong>この新しい連携は何を意味しますか？</strong> | <ul><li><strong>ダッシュボードとレポート</strong><ul><li>移行日以降、TikTok for Businessの新規コンバージョンはすべて新しいPID `tiktokglobal_int`に紐付けられます。</li><li>新しい連携を有効にする前に計測されたクリック数とインプレッション数は、`bytedanceglobal_int` に紐付けられます。</li></ul></li><li><strong>集計されたクリック数とインプレッション</strong><br /><Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">クリックとインプレッションの集計データ</Anchor>移行日を過ぎると、クリックとインプレッションのローレベルのレポートでは利用できなくなります。 TikTokとのAPI接続を有効にすると、集計データを含むレポートで利用できるようになります。<br /><strong>注記：</strong><ul><li>連携設定するときは、必ずAPI接続を有効にしてください。</li><li>移行プロセスでは、AppsFlyerの計測レポートを大幅に変更する必要があるため、クリックとインプレッションのデータを新しい連携ですぐに利用することはできません。</li></ul></li><li><strong>コストデータ</strong><ul><li><strong>重複したコストデータ:</strong> 新しい<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">`tiktokglobal_int`</Anchor>とレガシー`bytedanceglobal_int`<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">コスト統合</Anchor>が同時に有効になっている場合、<strong>コストデータが二重に表示される可能性があります</strong>。これを避けるには、<strong>1つのコスト統合のみがオンになっていることを確認してください</strong>。<br />ただし、新しいコスト連携を有効にすると、移行日の5日前からコストデータが自動的に収集されます。つまり、新しい連携では、その5日間のコストデータが重複して表示されることになります。<strong>例えば</strong>、古いコスト連携が1月15日に無効化され、新しいコスト連携が同日に有効化された場合、新しいコスト連携は1月15日のみ有効だったにもかかわらず、1月10日から14日までの期間に重複したコストデータを表示します。</li><li><strong>1つのコスト統合のみがオンになっていることを確認するには:</strong><ol><li><strong>移行日</strong>に、<strong>コスト</strong>タブに移動し、<strong>レガシー統合</strong>の<strong>トグルをオフにします</strong>。</li><li>次に、<strong>コスト</strong>タブに移動し、<strong>新しい統合</strong>の<strong>トグルをオンにします</strong>。</li></ol></li><li>移行日以降、コストデータは新しいPIDに紐付けられます。古いコストデータを表示するには、ダッシュボードのフィルターオプションのいずれかに古い PIDを含めます。</li><li>移行期間中、インストール数は数日間2つの連携間で分割される可能性がありますが、コストデータにはすべてが表示されます。この間、このデータに依存するKPI（eCPIやROIなど）は正確ではない可能性があります。<br /><Image alt="コスト統合オン.png" src="https://files.readme.io/802e43a872253691d15cdf68feeaf59b7d21f348380819a38742be5e70987b51-18535286024337.png" width="283px" /></li></ul></li></ul><ul><li><strong>SKANポストバック</strong><br />`SKANポストバック`移行日以降、すべてのSKANポストバックは新しい連携 tiktokglobal\_intに紐付けられます。</li><li><strong>リターゲティングキャンペーン</strong><br /><strong>リターゲティングキャンペーン新しい連携に移行する場合、リエンゲージメントトグルは移行前の設定状態に関わらずデフォルトでオフに設定されます。<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティングキャンペーン</Anchor>では、</strong>継続性を維持するため<strong>、新しい連携でリエンゲージメントトグルをオンにしてください。</strong></li></ul> |
| <span id="example-illustrating-the-process"></span>**プロセスを示す例** | <ul><li>**1日目（有効化日）:** 統合タブから新しいTikTok統合を有効にしてください。コスト統合はオフのままにしてください。両方の統合がオンになっていても、新しい統合はまだアクティブではなく、それに対する帰属はありません。</li><li>**2日目から10日目（TikTokレビュー期間）。最大45日かかる場合があります):** TikTokは新しい統合をテストしています。データを承認した後、移行日を通知します。この例では、11日目になります。<br />その間、ダッシュボードとレポートはレガシー統合の帰属のみを表示します。両方の統合でコストがオンになっている場合、両方とも二重コストデータを表示します。これを避けるために、新しい統合のコストをオフにしておく方が良いです。</li><li>**11日目（移行日）：** TikTokは切り替えを行い、新しい統合に帰属を開始します。移行日から約1週間（すべての古いクリックが期限切れになるまで）、インストールアトリビューションデータは両方の統合間で分割されます。<ul><li>新しい統合のために、TikTokはデータをSRNとして送信します。</li><li>レガシー統合のために、AppsFlyerは移行日の前の古いクリックをまだ帰属させることがあります。</li></ul></li><li>**18日目（移行後のフェーズ）**： レガシー統合のインストール帰属はもうなく、新しい統合のためだけです。<br />次の60日間、レガシー統合のアプリ内イベントの帰属が続く可能性があります。したがって、これらのイベントのためにAppsFlyerがポストバックを送信し続けることを許可するために、レガシー統合をオンにしておくことをお勧めします（統合タブから）。<br />新しい統合のためにコスト統合がオフになっている場合、今すぐオンにできます。二重コストデータを表示しないように、レガシー統合からコストをオフにしてください。</li><li>**78日目（最終移行）：** レガシー統合をオフにします。TikTokは現在SRNとして機能し、アプリ内イベントのポストバックはもはや必要ありません。<br />レガシー統合がオフになっていても、レガシーコスト統合をまだオフにしていない場合、新しい統合で重複コストデータが表示され続けます。</li></ul> |

> 📄 **参照：**
>
> * <Anchor target="_blank" href="https://appsflyer.showpad.com/share/XB6r4QA1TN0wN63kqmslA">TikTokとの新しい高度なSRN統合 への移行に成功しました</Anchor>
> * AppsFlyerの新機能・リリース情報

<div data-zendesk-anchors="01H8JZVADPFQ4NTHMCB8PSCV6P=%E6%B3%A8%E6%84%8F h_01HDPFFJ6129APQF5DV3TV0SM2=%E5%8F%82%E7%85%A7" />
