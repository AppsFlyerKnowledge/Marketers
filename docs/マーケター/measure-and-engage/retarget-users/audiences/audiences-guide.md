---
title: Audiencesガイド
metadata:
  keywords:
    - Audiences
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2017-05-30T07:21:22Z'
  edited_at: '2026-10-14T09:30:00Z'
  id: 115002689186
  locale: ja
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ja/articles/115002689186
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** AppsFlyerのAudiences機能を使用して、オーディエンスセグメントを構築しパートナーネットワークに連携することで、ユーザー獲得とリマーケティングキャンペーンの効率を向上しましょう。

<Image align="center" alt="Intro_image.png" src="https://files.readme.io/645503f41e6a76c854c62236fc279be591849879790d02001eafc75f0d1a974a-30258966500753.png" />

<div id="audiences-basics" />

## Audienesの基本仕様

AppsFlyerのAudiencesでは、オーディエンスセグメントを簡単に作成し、オウンドチャネルや有料チャネルに連携することができます。また、キャンペーンが送信されると、Audiencesでパフォーマンス指標を見ることができます。

オーディエンスとは、定義した特定の条件を満たす、アプリの現在または過去のユーザーセグメントです。オーディエンスは、個人の特性、行動、アプリ内行動、アトリビューションソース、収益、国、デバイスの種類などに基づいて定義されます。

**ステップ1 - オーディエンスを作成：** ゼロからカスタムオーディエンスを構築することも、インポートすることも、または、時間を節約し、業界のベストプラクティスに基づいている、AppsFlyerデフォルトの完全にカスタマイズ可能な「推奨オーディエンス」のリストから選択することもできます。

**ステップ2 - オーディエンスの連携：** オーディエンスを作成したら、広告媒体やマーケティングツールなどのテックパートナーに連携しましょう。オーディエンスに含まれるユーザーの識別子をパートナーに送信し、パートナーのシステム内にオーディエンスを作成することができます。これにより、これらのユーザーのみに特定の広告を配信できるようになります。Audiencesは自動的に更新され、毎日一回パートナー側に送信されます。さらに、オーディエンスをAmazon S3などのサードパーティサービスにアップロードしたり、管理画面から直接CSVファイルでダウンロードすることもできます。

オーディエンスデータをメディアパートナーにアップロードするために必要なすべての情報は、パートナー連携画面で指定されています。一つのメディアパートナーに対して複数の接続を行うことができます（異なるアカウント、ログイン情報などを使用）。iOS 14.5以降のプライバシー要件やその他のユーザープライバシー規定に準拠できるように、Audiencesでは**どの識別子をパートナーと共有するか**を、アカウントレベルとパートナー設定ごとの両方で設定することができます。

<div id="audience-split-and-incrementality-testing" />

### オーディエンス分割とインクリメンタリティのテスト

<Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview">インクリメンタリティ</Anchor>テストは、増分リフト、つまりマーケティングキャンペーンの結果発生したコンバージョン数とキャンペーン無しでも発生したであろうコンバージョン数の差を正確に測定するA/Bテストによって、キャンペーンの真の効果を計測します。AppsFlyerのAudiencesは、選択したメディアパートナーとコントロールグループの間でオーディエンスを分割するオプション機能を使用してテストの段階を設定するため、Incrementality管理画面を使用してキャンペーンの真の価値を理解できます。

<div id="get-started" />

## まずはじめに

以下の手順で、Audiencesをご利用ください：

|  | ステップ |
| --- | --- |
| 1 | AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。<br /><br />**注記：** オーディエンスはプレミアム機能です。利用をご希望の場合は、カスタマーサクセスマネージャーまたは [hello@appsflyer.com](mailto:hello@appsflyer.com) へお問い合わせください。 |
| 2 | ユーザー識別子をパートナーと共有するアカウントレベルの<Anchor target="_blank" href="/marketers/ja/docs/audiences-user-identifier-policy">ポリシー</Anchor>を設定してください |
| 3 | 新しいオーディエンスを作成してください：<ul><li>[カスタムオーディエンス](/docs/audiences-guide#create-a-custom-audience)：一からオーディエンスを構築してください</li><li>[推奨オーディエンス](/docs/audiences-guide#create-a-suggested-audience) - 業界のベストプラクティスに基づいたデフォルトのカスタマイズ可能なオーディエンス</li><li><Anchor target="_blank" href="/marketers/ja/docs/audiences-import-audience-segments-from-internal-systems">オーディエンスのインポート</Anchor>：内部システム（BIまたはCRM）からオーディエンスセグメントをインポートしてください</li></ul> |
| 4 | オーディエンスを一つまたは複数のメディアパートナーに連携してください |
| オプション | [パートナーとコントロールグループ間でオーディエンスを分割してください](/docs/audiences-guide#audience-split-and-control-groups) |
| オプション | <Anchor target="_blank" href="/marketers/ja/docs/audiences-create-better-audiences-with-user-attribute-data">ユーザー属性をインポートしてください</Anchor> |

<div id="notes" />

<div id="create-and-manage-audiences" />

## オーディエンスの作成と管理

このセクションでは、オーディエンスの作成および管理方法と、インクリメンタリティテストの設定方法について説明します。

<div id="create-a-custom-audience" />

<Accordion title="カスタムオーディエンスの作成">

カスタムオーディエンスは、任意のルールセットとフィルタを使用して一から構築されます。

**カスタムオーディエンスを作成する方法：**

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。
2. **オーディエンスを追加**をクリックしてください。
3. **カスタムオーディエンス**を選択してください。  
   **作成** タブが表示されます。
4. ユニークな**オーディエンス名**を入力します。  
   **注記：** オーディエンス名には特殊文字（" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~）を含めることはできません。
5. プラットフォームを選択する：**Android** または **iOS**
6. [ユーザー識別子](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)を選択してください。
7. [デフォルト] **デバイスID**：デバイスIDのみでルールを評価する。
8. **Customer ID：** CUIDを使用してデバイスをグループ化することにより、ルールを適用します（この方法はデータに有効なCUIDが含まれていることを確かめてからのみ使用してください）。
9. **新しいルールセット**、または既存オーディエンスのユーザーを追加したい場合は、**既存オーディエンス**をクリックし、リストから特定の対象オーディエンスを選択してください。
10. ユーザーインターフェイス上のガイドに従ってオーディエンスを構築します。ルールオプションに関する詳細な情報については、[ルールセットについて](/docs/audiences-guide#ルールセットについて)を参照してください。
11. [AND]、[OR]、[除外] のいずれかを使用してルールセットを結合してください。
12. オーディエンスを作成すると、右側のパネルにオーディエンス推定数とパートナーごとのアップロードサイズが自動的に更新されます。
13. オーディエンスの定義を完了し、**次へ**をクリックしてください。  
    **オーディエンス連携**画面が表示されます。ここで[オーディエンスをメディアパートナーに接続](/docs/audiences-guide#connect-an-audience-to-media-partners)します。

**注：**

* カスタム / 推奨オーディエンスは一度に100個までアクティブに設定できます。
* * オーディエンス名は接続されているメディアパートナーのサイトに表示される場合があります。機密情報を含めないよう注意してください。

</Accordion>

<div id="create-a-suggested-audience" />

<Accordion title="推奨オーディエンスを作成">

推奨オーディエンスを使用すると、**業界のベストプラクティスに基づいたデフォルトのオーディエンスセグメント**を探索して最適なものを見つけることができます。オーディエンスを選択し、カスタマイズし、パートナーネットワークに連携して、最適なターゲットを絞ったマーケティングキャンペーンを行うことができます。

**新規獲得、休眠復帰、収益化、業界特有のセグメントなどのカテゴリ**内の30個以上からオーディエンスを選択できます。オーディエンスは100%カスタマイズでき、必要なオーディエンスを正確に作成できます。オーディエンスには以下のものが含まれています：

* 広告をクリックしたユーザーにインストールを促す
* 類似オーディエンスの取得
* 除外リスト
* ユーザー登録の促進
* 購入の促進
* 購入者の収益化
* その他多数…

<div id="example-use-case" />

<div id="notes-1" />

> 📄 **活用事例**
>
> この例では、典型的な事例の一つを説明します。まだ購入を一度も実行したことがないアプリのアクティブユーザーに初回購入を促したいとしましょう。「購入の促進」というオーディエンスを選択し、アプリ内購入を意味するイベントを指定することでオーディエンスをカスタマイズします。次に、オーディエンスをパートナーに接続し、購入を促してアプリの購入ページに誘導するプロモーションキャンペーンを実行します。
>
> <Image align="center" alt="Encourage_purchase_image_this_one.jpeg" src="https://files.readme.io/8b49590a0c97707bd4a0b151d30cc48183e15ffb13d2d4e9ee25d522de71846c-30259018203153.jpg" />

**推奨オーディエンスを作成する方法：**

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。
2. **オーディエンスを追加**をクリックしてください。
3. **推奨オーディエンス**を選択してください。
4. アプリを選択してください。
5. 様々なカテゴリーを閲覧し、あなたのゴールにマッチするオーディエンスを選択しましょう。    
   **注：** オーディエンスによっては、オーディエンス基準を定義するために、特定の<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">アプリ内イベント</Anchor>を追加する必要があります。AppsFlyer<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#定義済みのイベント名">定義済みイベント</Anchor> がすでにアプリに実装されている場合は、あらかじめ選択されています。そうでない場合は、ドロップダウンメニューから適切なカスタムイベントを選択する必要があります。 <Image alt="Select_an_event__1_.jpeg" src="https://files.readme.io/b5055ca61791f15efc3a91f3f2d749e1df9e3f5e8b956b9167e186474de57ac4-30258966520721.jpg" width="419px" />
6. **選択＆カスタマイズ**をクリックしてください。
7. ユニークな**オーディエンス名**を入力します。  
   **注記：** オーディエンス名には特殊文字（" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~）を含めることはできません。
8. プラットフォームを選択する：AndroidまたはiOS）用に開発されたアプリ。
9. [ユーザー識別子](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)を選択してください。
   * [デフォルト] **デバイスID**：デバイスIDのみでルールを評価する。
   * **Customer ID：** CUIDを使用してデバイスをグループ化することにより、ルールを適用します（この方法はデータに有効なCUIDが含まれていることを確かめてからのみ使用してください）。
10. 追加の[ルールセット](/docs/audiences-guide#ルールセットについて)を追加してオーディエンスをさらにカスタマイズしたい場合は、**+フィルタ**をクリックしてください。完了したら、**次へ**をクリックしてください。   
    **オーディエンス連携**画面が表示されます。ここで[オーディエンスをメディアパートナーに接続します。](/docs/audiences-guide#connect-an-audience-to-media-partners)   

    **注記：** カスタム / 推奨オーディエンスは一度に100個までアクティブに設定できます。

</Accordion>

<div id="import-an-audience" />

<Accordion title="オーディエンスをインポートする">

内部システム（BIやCRMなど）からAppsFlyer Audiencesに<Anchor target="_blank" href="/marketers/ja/docs/audiences-import-audience-segments-from-internal-systems">既定のオーディエンスセグメントをインポート</Anchor>し、全てのオーディエンスセグメントを広告パートナーに連携し一元管理する中核的な場所として使用できます。さらに、識別子の一致／データ強化、キャンペーン指標などのAudiences機能をお楽しみいただくことも可能です。

</Accordion>

<div id="connect-an-audience-to-media-partners" />

<Accordion title="オーディエンスをメディアパートナーに連携">

オーディエンスを定義したら、次のステップはそれらをメディアパートナーに連携することです。

**オーディエンスをメディアパートナーに連携する方法：**

1. オーディエンスの**作成**ページにて新しいオーディエンスを定義したら、**次へ**をクリックしてください。 **オーディエンス連携**画面が表示されます。
2. **＋パートナー接続**をクリックして、以下のいずれかを実行してください。
   * **新しい連携を追加**するには、**+パートナー連携を追加**をクリックしてください（詳細な手順は以下の[新しい連携を作成](/docs/audiences-guide#create-a-new-connection)セクションを参照してください）。
   * **既存の連携から選択する方法：**
     1. パートナー連携を検索してください。
     2. 既存の連携を一つまたは複数選択してください。
     3. **保存**をクリックしてください。  
        オーディエンスの連携画面が開きます。
     4. [オプション] [パートナーとコントロールグループ間でオーディエンスを分割](/docs/audiences-guide#audience-split-and-control-groups)してください。
     5. [オプション] [分割グループをS3にコピーしてください。](/docs/audiences-guide#audience-split-and-control-groups)
3. **保存**をクリックしてください。  
   接続したあとは、オーディエンスが更新されパートナーに毎日送信されます。

</Accordion>

<div id="user-identifier-device-id-vs-customer-id" />

<Accordion title="ユーザー識別子 — デバイスID vs.Customer ID">

オーディエンスルールの推定は、アプリのユーザー識別子を使用して実行されます。以下から選択してください：

* [デフォルト] **デバイスID：** デバイスID：ルールセットへの準拠はデバイスID（GAIDまたはIDFA／IDFV）を使用して検証されます。ルールセットに準拠されている場合、デバイスIDはオーディエンスリストに追加されます。**注記：** デバイスIDは、ユーザー識別子ポリシーで許可されている場合にのみ、共有されます。
* <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">**カスタマーユーザーID（CUID）**</Anchor>：
  * ルールセットの準拠は、同じCUIDに関連する全てのデバイスIDをグループ化することによって評価されます。そのグループがルールセットに準拠していれば、そのグループを構成するデバイスIDがオーディエンスに追加されます。**注：** CUID自体はオーディエンスリストの一部ではなく、メディアパートナーには送信されません。
  * CUID実装の注意事項：
    * 有効なCUIDを入力してください。
    * CUIDのないアプリユーザー（デバイス）は無視されます。
    * デバイスIDがCUIDに一致すると、ユーザーの過去のオーディエンスデータが遡及的に更新され、今後のオーディエンス構築に含まれます。**注：** ローデータは変更されません。
    * デバイスIDが2つの異なるCUIDに紐づいている場合、最後に紐づけられたCUIDが使用されます。
    * CUIDを識別子としてオーディエンスを構築する場合、関連するデバイスとの完全な関連付けとデバイス識別子(GAID、IDFAなど)によるエンリッチメントを成功させるために、インストール時に(インストール後のイベントだけでなく) CUIDの関連付けをAppsFlyerが受信する必要があります。<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid#cuidの設定">詳細はこちら</Anchor>

<Image align="center" alt="CuidExaplainded_us-en.jpg" src="https://files.readme.io/d40309ab2fd34a4862b9c089ac2fade2f5642973fc4d4977da66f1ee6bf1e390-30258966523921.jpg" width="387px" />

<div id="h_01K0PAQ4SFXBK0TZ3MH07PWN4A" />

<div id="example-device-id-vs-cuid" />

> 📄 **例：デバイスID vs.CUID**
>
> 5ドル以上の買い物をしたユーザー
>
>
>
> | Advertising  <br />ID | CUID | 購入金額 |
> | --- | --- | --- |
> | A | 99 | 1 |
> | A | 99 | 2 |
> | B | 77 | 1 |
> | B | 77 | 5 |
> | C | 99 | 3 |
> | D | なし | 50 |
>
>
>
> | ルール基準 | オーディエンスに含まれるデバイスID | 概要 |
> | --- | --- | --- |
> | 端末ID | B, D | 課金額が$5未満のため、AとCは含まれていません。 |
> | CUID | A、B、C | * AとCは同じCUID（99）を持っています。これらの合計支出額は$6です。<br />* CUIDがないため、Dは無視されます。 |

</Accordion>

<div id="audience-split-and-control-groups" />

<Accordion title="オーディエンス分割とコントロールグループ">

パートナーとコントロールグループの間でオーディエンスを分割するトグルを使用して、A/Bテストと <Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview">インクリメンタリティ測定</Anchor>の環境を簡単に設定し、キャンペーンの効果について重要なインサイトを得ることができます。この機能を有効にすると、選択したパートナーとコントロールグループの間でオーディエンスがランダムに分割されます。コントロールグループは、パートナーに割り当てられないオーディエンスの一部であり、インクリメンタリティ測定に必要な要件です。分割率のいずれかを調整し、オーディエンスごとの分割を無効または再度有効にすることができます。

| 機能 | 説明 |
| --- | --- |
| オーディエンスの分割 | <ul><li>選択したパートナーとコントロールグループの間でオーディエンスがランダムに分割されます。Incrementality機能を利用するお客様に対して**デフォルトで有効**になっており、いつでも簡単に無効にしたり再度有効にしたりできます。</li><li>A/Bテストやインクリメンタリティ計測などのさまざまな理由でオーディエンスを分割します。</li><li>**注：** パートナー間の既存の分割率を変更すると、オーディエンス全体が再配布されます。これは、A/Bテストの有効性に悪影響を及ぼすため、現在アクティブなインクリメンタリティテストが停止され、新しいテストが開始されます。</li></ul> |
| コントロールグループ（非接触者） | オーディエンスの一部は、どのパートナーにも割り当てられないコントロールグループとなります。<ul><li>コントロールグループは、A/Bテストやリマーケティングキャンペーンの増分リフトを測定する際に使用されます。</li><li>効果的なコントロールグループは、オーディエンスの15% (またはそれ以上) が推奨されています。</li><li>インクリメンタリティテストを実行するために必要な最小コントロールグループの割合は1%です。</li></ul> |
| 分割リストのコピーをS3バケットに送信します。 | 分割オーディエンスリストとコントロールグループを含むCSVファイルは、Amazon S3バケットに送信できます。<ul><li>**注：** Amazon S3を接続するパートナーと設定することと同じではありません。</li><li>オーディエンスリストは、CSVファイルにダウンロードできます。例えば、AppsFlyerと連携されてないパートナーにCSVファイルでオーディエンスを送信できます。</li></ul> |

**オーディエンスを分割し、他のパートナーアクションを実行する方法：**

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。
2. **オーディエンス**タブで、オーディエンスを選択してください。
3. **連携**タブに移動します。  
   [![audience_split_1200px.png](https://support.appsflyer.com/hc/article_attachments/30258966527249)](https://support.appsflyer.com/hc/article_attachments/30258966527249) 現在の設定が表示されます：  
   * 上部右側のパネルには、推定オーディエンス数とアップロードサイズが表示されます（すべてのパートナーの場合）。
   * 右下には、以下のようなイメージが表示されます。
     * 各パートナーの推定アップロードサイズ
     * パートナーのオーバーラップ（分割されていないオーディエンスの場合）
4. 以下のいずれかのアクションを実行してください。

<Table>
  <thead>
    <tr>
      <th>
        アクション
      </th>
      <th>
        手順
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="split-an-audience-between-partners-and-control-group"></span>
        パートナーとコントロールグループ間でオーディエンスを分割してください
      </td>
      <td>
        1. **オーディエンスの分割／インクリメンタリティの効果測定**のトグルが有効になっていることを確認してください。
           * コントロールグループとパートナーへの分割を合わせると100%になります。
           * コントロールグループを分割に含めたくない場合は、0%を割り当ててください。
           * すべての連携先パートナーは分割の一部を割り当てられる必要があります（パートナーに0%を割り当てないでください）
           * 分割の合計を表示するには、スクロールダウンし、合計分割率を確認してください。
        2. 分割率を入力してください。
           * **コントロールグループ** - 15%以上に設定することを推奨します。
           * 連携先ごとに分割率を入力します。
           * 下にスクロールして割り当ての合計をパーセントで表示し、その合計が100%であることを確認してください。
           * **分割を保存**をクリックしてください。
           * **保存** をクリックしてください。
      </td>
    </tr>
    <tr>
      <td><span id="copy-split-groups-to-s3"></span>
        分割グループをS3にコピーしてください
      </td>
      <td>
        **オーディエンス分割リストのコピーをS3バケットに送信する方法：**

        1. **分割グループをS3にコピーする**をクリックしてください。
        2. 連携先を選択してください。
        3. **保存**をクリックしてください。

        ファイルは以下のディレクトリとファイル名の構造で送信されます。

        * **ディレクトリ**：

          ```
           \YYYY-MM-DD\audienceID_audienceName_timestamp\
          ```
        * **ファイル名**：パートナーまたはコントロールグループの名前。  
          注記：パートナーへの接続が失敗し、ファイルがアップロードされない場合、パートナー名の後に**failed**という文字列が追加されます。（例：*partner\_name\_failed.csv*）
      </td>
    </tr>
    <tr>
      <td><span id="create-and-add-a-new-connection"></span>
        新規連携先を作成または追加してください。
      </td>
      <td>
        **新しい連携を作成する方法：**

        1. **パートナー接続を追加**をクリックしてください。
        2. 連携の名前を入力してください。
        3. パートナーを選択してください。
        4. ユーザーインターフェイスの指示に従って、プロセスを完了してください。
        5. **パートナー接続を追加**をクリックしてください。
      </td>
    </tr>
    <tr>
      <td><span id="add-or-remove-an-existing-connection"></span>
        既存の連携先の追加または削除してください
      </td>
      <td>
        **既存の連携先を削除または追加する方法：**

        1. パートナー連携にカーソルを合わせてください。
        2. 削除アイコンをクリックしてください。
        3. **保存** をクリックしてください。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="manage-audiences" />

<Accordion title="オーディエンスの管理">

**Audiencesの管理画面からオーディエンスを管理する方法：**

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。
2. 次のオプションが利用できます。  

| オプション | 説明 |
| --- | --- |
| <span id="create-a-new-audience"></span>新しいオーディエンスの作成 | 新しいオーディエンスの作成 |
| <span id="change-audience-settings"></span>オーディエンス設定の変更 | **オーディエンス名**をクリックし、次の作業を実行してください。<ul><li>**作成**タブで：ルールセットの表示と変更</li><li>**連携**タブに移動します。オーディエンス分割とコントロールグループ</li></ul> |
| <span id="actions"></span>アクション | <Image alt="3_dots_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018212369" width="7px" /> アイコンは、メインのAudiencesページでオーディエンスの上にカーソルを置くと右側に表示されます：<ul><li>**履歴の表示**：オーディエンスのサイズやパートナー間の分割などを含むオーディエンスのアップロード履歴を表示します。</li><li>**今すぐアップロード** ：接続パートナーにオーディエンスを送信します。</li><li>**CSVとしてダウンロード** ：<ul><li>選択した識別子を含むCSVファイルを生成してダウンロードします。<Anchor target="_blank" href="/marketers/ja/docs/audiences-user-identifier-policy">ユーザー識別子ポリシー</Anchor>に準拠したデータのみがダウンロードされます。</li><li>各パートナーごとに1つのファイルが生成されます。</li><li>ファイルのダウンロードは、オーディエンスの計算後に行われますが、オーディエンスを作成または変更してから時間がかかることがあります。</li><li>ダウンロードするファイルに含まれるレコードは、最大500万件までです。大きなファイルの場合は、ファイルを<Anchor target="_blank" href="/marketers/ja/docs/audiences-partner-connections#amazon-s3">S3バケット</Anchor>に送信してください。</li><li>パートナーネットワークに連携されているオーディエンスのみが毎日更新され、最新の状態に保たれます。オーディエンスがパートナーネットワークに接続されていない場合、オーディエンス作成日を超えて最新の状態に保たれることはありません。最新の情報をダウンロードする場合は、オーディエンスを複製して再作成し (以下を参照)、複製したオーディエンスからCSVをダウンロードします。</li></ul></li><li>**複製**：<ul><li>オーディエンスの定義をコピーします。</li><li>オーディエンスを複製する場合は、一意の名前を付けてください。</li><li>[オプション] 複製中に、接続されているパートナーを1つ以上削除できます。</li></ul></li><li>**今すぐ計算**：[インポートされたオーディエンス向け] オーディエンスに含まれるユーザー数を再度計算します。必要に応じて、オーディエンスのサイズが正しくなさそうな場合に、オーディエンスサイズを更新してください。</li><li>**<span id="pause"></span>一時停止：**</li></ul><ul><li>オーディエンスを一時停止すると、そのデータが計算されなくなり、接続パートナーにアップロードされなくなります（過去3年間の既存のオーディエンスデータは保持されます）。</li><li>使用しないオーディエンスを一時停止することで、アクティブなオーディエンスの最大数を維持できます。一度に最大100のアクティブなカスタム / 推奨オーディエンスと最大500のアクティブなインポートオーディエンスを持つことができます。</li></ul>**オーディエンスを停止する：**<br /><br />1.メインのオーディエンス画面で各行のオーディエンスにカーソルを合わせると、<Image alt="3dots icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018212369" width="7px" />（アクションメニュー）アイコンが右側に表示されます。<br /><br />![Actions menu.jpg](https://support.appsflyer.com/hc/article_attachments/30258966545297)<br /><br />2.アイコンをクリックし、**一時停止**を選択します。<br /><br />オーディエンスが停止されます。<br /><br />また、オーディエンスの横にあるボックスをチェックし、右上に表示される**一時停止**をクリックすることで、複数のオーディエンスを一度に一時停止することができます。<ul><li>**削除：** オーディエンスを永久に削除します。</li></ul> |
| <span id="bulk-actions"></span>一括操作 | 複数オーディエンスに同じアクションを適用します。一括アクションを使用するには、2つ以上のオーディエンスを選択し、以下の一括アクションのいずれかを選択してください。<ul><li>**今すぐアップロード**</li><li>**複製**：選択したオーディエンスを複製します。</li><li>**削除**</li></ul> |

</Accordion>

<div id="all-about-rulesets" />

## ルールセットについて

ルールセットを使用してオーディエンスを定義する方法について説明します。

<div id="audience-segmentation-rulesets" />

<Accordion title="オーディエンスセグメントのルールセット">

<Image align="center" alt="audience_segmentation_rulesets.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018214801" />

* オーディエンスセグメントのルールセットは、正確なフィルタリングを有効にするために1つまたは複数のルールで構成されます。
* [AND]、[OR]、[除外] のいずれかを使用してルールセットを結合します。
* ルールを定義し、階層化すると、推定オーディエンスサイズがリアルタイムに表示されます。
* ルールセットは、<Image alt="duplicate_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30258966550033" width="17px" />アイコンをクリックして複製することができます。
* オーディエンスが複数のルールセットで構成されている場合は、重複ビジュアライゼーション表示を使用することで、オーディエンスセグメントを理解しやすくなります。
* ルールを適用するために使用される[ユーザー識別子](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)は、デバイスID [デフォルト] または顧客ユーザーID（CUID）です。

以下の例は、さまざまなシナリオでのルールセットの実装を示しています。

</Accordion>

<div id="ruleset-examples" />

<Accordion title="ルールセットの例">

<div id="example-location-based-rule" />

> 📄 **例：ロケーションに基づくルール**
>
> 先月アプリをアンインストールしたニューヨークのユーザー
>
> <Image align="center" alt="example_location_based_rule.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966552209" />

<div id="example-user-attributes-based-rule" />

> 📄 **例：ユーザー属性に基づくルール**
>
> 過去7日間に最低1回アプリを起動し、好きな武器 (FavoriteWeapon) が刀 (Sword) であるユーザー。
>
> <Image align="center" alt="example_user_attributes_based_rule.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966566801" />

<div id="example-revenue" />

> 📄 **例：収益**
>
> 過去7日間にアプリをインストールし、$1を課金したユーザー
>
> <Image align="center" alt="example_revenue.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966567825" />

<div id="example-owned-media-filter" />

> 📄 **例：オウンドメディアフィルター**
>
> ソーシャルメディア (有料広告を除く)、SMS、メール、ユーザー紹介、Web、QR コードなど、特定のオウンドメディア媒体に紐づくユーザーで構成されるターゲットオーディエンスを構築します。粒度のレベルを選択し、特定のメディアソース、キャンペーン、広告セット、または個々の広告から来たユーザーをターゲットにすることもできます。
>
> 過去7日間に少なくとも1回アプリを起動し、インストールが特定のメールキャンペーンと特定の広告セットと広告に紐づくユーザーの例を次に示します。
>
> <Image align="center" alt="Owned_media_example.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966580753" />
>
> オーディエンスは、オウンドメディアまたは有料メディアでパーソナライズされたメッセージでこれらのユーザーをリエンゲージするために、またはキャンペーンの実行時に無関係または不要な広告が表示されないようにするための除外リストとして使用できます。

<div id="example-remarketing" />

> 📄 **例：リマーケティング**
>
> クリックと広告ビューのデータを使用して、効果的なリマーケティングを行います。これらのユーザーがコンバージョンに至るためには、あと少しの説得や簡単なリマインダーが必要です。これらのユーザーはコンバージョンに至る可能性が高いため、リマーケティングは、新しいセグメントに広告を出すよりもはるかに良い結果が得られます。クリックとインプレッションデータに基づいて、リマーケティング向けの正確なオーディエンスを作成しましょう。
>
> 過去2日間に広告をクリックしたがインストールしていない見込みユーザーのオーディエンスを構築しましょう。
>
> <Image align="center" alt="example_remarketing.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018231313" />
>
> これらは最近モバイルアプリに興味を持って広告をクリックしたが何かしらの理由でアプリをインストールしなかった、またはアプリをインストールしたが起動しなかったユーザーです。一部のユーザーはインストールさせるためのリマインダー（プッシュ）が必要です。他のユーザーは、最終的にコンバージョンに至るためにはアプリ画面や機能をより詳しく見る必要があるかもしれません。したがって、新規オーディエンスに使用している主な広告デザインがある場合、クリックしたがインストールしなかったオーディエンスには、別のデザインを用意したほうが効果的な場合があります。

</Accordion>

<div id="ruleset-filters" />

<Accordion title="ルールセットのフィルタ">

* ルールセットは1つまたは複数のルールで構成されています。
* イベント、収益、国、属性、ユーザー属性、デバイス、オウンドメディアなど、さまざまなルールセットのフィルタの種類があります。
* 以下の表で示すとおり、ルールには異なるパラメーターと設定があります。

<table><tbody><tr><td colspan="3"><h4><span id="h_01K5EH9WVTEX56980MCR81ZAHH"></span><span id="contains-does-not-contain-logic"></span><span id="h_01K5EHGKDPWS16HP9Q7KX9JXFY"></span><span id="events"></span>イベント</h4><img alt="engagement_filter_with_A___B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966588305"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>広告を閲覧した</li><li>広告をクリックした</li><li>アプリをインストールした</li><li>アプリをインストールしなかった</li><li>アプリを起動した</li><li>アプリを起動しなかった</li><li>アプリのアンインストール </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><p>時間枠と頻度 </p></td></tr><tr><td colspan="3"><h4><span id="inapp-events"></span>アプリ内イベント</h4><img alt="in-app_event_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018249873"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>イベントを実行した [<em>イベント名を選択</em>]</li><li>イベントを実行しなかった [<em>イベント名を選択</em>] </li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><p>時間枠と頻度 </p></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/></p><p>イベント属性 + 値：</p><ul><li>である</li><li>より大きい</li><li>より小さい</li></ul></td></tr><tr><td colspan="3"><p><strong><a href="./in-app-events-overview" target="_blank">アプリ内イベント</a>に関する注意事項：</strong></p><ul><li>アプリ内イベントの一覧は<a href="./about-data-freshness-and-timezone-support#日次処理" target="_blank">毎日</a>更新されます。 </li><li> <strong>イベントを実行した</strong>が選択され、アプリ内イベントに属性がある場合、アプリ内イベントの属性の値で絞り込むことができます。 </li><li><p>デフォルトでは、アプリ内イベントは、属性ごとに100個の一意の値に制限されています。例えば、イベントが「purchase」で、属性が「content-type」である場合、可能なコンテンツタイプは100個（以下）までしか設定できません。ただし、数値は無制限です。<br/>リストに表示されないアプリ内イベントの属性（パラメーター）と値がある場合、<strong>イベント属性を追加</strong> &gt; <strong>アイテムを追加</strong> をクリックして、手動で追加できます。<br/> </p><p><strong><img alt="Add_item.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966609297"/></strong></p><p>注記：</p><p>- 手動で追加されたすべてのイベント項目は、文字列型 (テキスト) のみで入力する必要があります。数値は追加すべきではなく、追加すると正しく機能しません。</p><p>- 手動で追加したイベント項目が追加されると、「推定オーディエンスサイズ」が正確に反映されない場合があります。 <br/>100個以上の属性／値をリストに表示する必要がある場合は、担当CSMまたは hello@AppsFlyer.com までご連絡ください。</p></li></ul></td></tr><tr><td colspan="3"><h4><span id="revenue::3358edf4"></span>収益</h4><img alt="revenue_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966611089"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>アプリ内購入の合計収益</li><li>広告収益による収益合計</li><li>合計収益 </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/></p><ul><li>である</li><li>より大きい</li><li>未満 </li></ul><p><strong>定義：</strong></p><ul><li> <strong>アプリ内購入の合計収益：</strong> 特定のデバイス / CUIDの <code>af_revenue</code> パラメーターを使用してレポートされたすべてのイベントの合計値</li><li> <strong>総広告収益：</strong> 特定のデバイス / CUID によって生成された合計広告収益</li><li> <strong>合計収益</strong>：アプリ内購入の合計収益 + 広告の総収益</li></ul><p><strong>注：</strong></p><ul><li> <strong>合計広告収益</strong>フィルターと <strong>合計収益</strong>フィルターを使用するには、<a href="./roi360-guide-ad-revenue-attribution" target="_blank">広告収益計測</a>を実装する必要があります。</li><li>すべての収益フィルターオプションは米ドルで計測されます。</li></ul></td></tr><tr><td colspan="3"><h4><span id="geo"></span>国</h4><img alt="location_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018257041"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>Location </li></ul></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>である</li><li>でない</li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/></p><p><strong>地域オプション</strong></p><ul><li>国</li><li>State</li><li>City</li></ul></td></tr><tr><td colspan="3"> <strong>位置情報に関して：</strong><ul><li>複数の国が選択されている場合、州は選択できません。</li><li>複数の州が選択されている場合は、都市を選択できます。</li></ul></td></tr><tr><td colspan="3"><h4><span id="owned-media"></span>オウンドメディア</h4><img alt="doctored_owned_media_image_with_app_specified__final_version_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966614801"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>オウンドメディアソース</li><li>オウンドメディアキャンペーン</li><li>オウンドメディア広告セット</li><li>オウンドメディア広告</li></ul></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>である</li><li>でない</li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/></p><p>以下のような値：</p><ul><li>Email</li><li>SMS</li><li>Web</li><li>ソーシャルメディア（有料広告を除く）</li><li>QRコード</li><li>紹介</li><li>特定のメディアキャンペーン、広告セット、広告</li></ul></td></tr><tr><td colspan="3"><p>特定のオウンドメディアソースに帰属するユーザーで構成されるターゲットオーディエンスを構築できます。さらに、粒度のレベルを選択し、特定のオウンドメディアソース、キャンペーン、広告セット、個々の広告から来たユーザーをターゲットにすることもできます。</p><p>作成したオーディエンスを使用して、オウンドメディアまたは有料メディアでパーソナライズされたメッセージでユーザーをリエンゲージしたり、除外リストとして使用して、ユーザー獲得キャンペーンやリエンゲージメントキャンペーンの実行時に無関係な広告や不要な広告が表示されないようにします。</p></td></tr><tr><td colspan="3"><h4><span id="device"></span>デバイス</h4><img alt="device_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966618897"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li>Device brand</li><li>Device model</li><li>App version</li><li>OS version</li><li>Carrier</li></ul></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>である</li><li>でない </li></ul></td><td> <img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/> 選択された値</td></tr><tr><td colspan="3"><h4> <span id="attribution"></span>アトリビューション</h4><img alt="Attribution_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966620049"/> </td></tr><tr><td> <img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/><ul><li> オーガニック</li><li>リターゲティング</li></ul></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>False</li><li>True</li></ul></td><td> </td></tr><tr><td colspan="3"><h4><a href="./audiences-create-better-audiences-with-user-attribute-data" target="_blank"><span id="user-attributes"></span>ユーザー属性</a></h4><img alt="user_attribute_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966622097"/> </td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018241809"/></p><p>ユーザー属性名</p></td><td> <img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966598929"/><ul><li>文字列型<ul><li>である</li><li>でない</li></ul></li><li>数値型<ul><li>である</li><li>より大きい</li><li>より小さい</li></ul></li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018252561"/><br/>文字列の場合：値を選択</p><p>数字の場合：数値を入力します。</p></td></tr></tbody></table>

</Accordion>

<div id="combine-rulesets" />

<Accordion title="ルールセットを統合する">

**既存オーディエンスとルールセットを統合する方法：**

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。
2. **オーディエンスを追加**をクリックします。  
   **作成** タブが表示されます。
3. ユニークな**オーディエンス名**を入力します。
4. プラットフォームを選択する：**Android** または **iOS**
5. [オプション] **詳細設定**を選択して、[ユーザー識別子](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)を選択します。
   * [デフォルト] **デバイスI：** デバイスIDのみでルールを適用します。
   * **顧客ユーザーID**：CUIDを使用してデバイスをグループ化することにより、ルールを適用します。データに有効なCUIDがあることを確認した後で、この方法を使用してください。
6. **既存オーディエンス**をクリックして、特定のオーディエンスを選択してください。
7. [AND]、[OR]、[除外] のいずれかを選択します。

**制限：**

* 既存のオーディエンスは、新しいオーディエンスと同じプラットフォーム (iOSやAndroidなど) 上にいる必要があります。
* 既存のオーディエンスに基づくオーディエンスは含めることができません。
* インポートされたオーディエンスは含めることができません。

</Accordion>

<div id="create-and-manage-partner-connections" />

## パートナー連携の作成と管理

このセクションでは、メディアパートナーの連携を作成し管理する方法について説明します。

<div id="create-a-new-connection" />

<Accordion title="新しい連携の作成">

**連携先**タブには、全てのパートナー連携とそれぞれのステータスが表示されます。オーディエンスデータをメディアパートナーにアップロードするために必要なすべての情報は、パートナー連携画面で指定されています。一つのメディアパートナーに対して複数の接続を行うことができます（異なるアカウント、ログイン情報などを使用）。

**新しい連携を作成する方法：**

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。
2. **+ 新しい連携先**をクリックします。  

   **注記：** オーディエンスビルダー内から新しいパートナー連携を作成する場合は、**オーディエンス連携の管理**画面内の **+新しいパートナー連携**をクリックして下さい。
3. **パートナー名**を選択してください。
4. **連携名**を入力します。  

   **注記：** それは、他の接続を作成するときに使用されたことのない新しい名前でなければならない。
5. パートナーの必須項目／ログイン情報を入力してください。一部のパートナーでは<Anchor target="_blank" href="/marketers/ja/docs/audiences-partner-connections">連携方法について詳細な手順</Anchor>があります。  

   **注：** 資格情報は一意である必要があります。重複した接続の作成を防ぐため、資格情報が他のパートナー接続で既に使用されている場合、新しい接続の作成がブロックされます。
6. このパートナーとの共有を許可するユーザー識別子を選択してください。
   * 対応する識別子は、パートナーによって異なります。選択したパートナーがサポートしている識別子のみがリストに表示されます。
   * <Anchor target="_blank" href="/marketers/ja/docs/audiences-user-identifier-policy">アカウントレベルのユーザー識別子ポリシー</Anchor>に準拠した識別子のみがアップロードされます。アカウントポリシーで許可されていない識別子を選択した場合は、注意書きが表示されます。  
     <Image align="center" alt="doctored_connection_image.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966624017" />
7. **保存**をクリックします。

</Accordion>

<div id="manage-connections" />

<Accordion title="連携先の管理">

**既存の連携を管理する方法：**

1. パートナーを選択してください。
2. 接続を選択してください。 ![](https://support.appsflyer.com/hc/article_attachments/30259018273553) alt>接続画面.jpgalt
3. 以下のいずれかのアクションを実行してください：

| オプション | 手順 |
| --- | --- |
| <span id="change-the-connection-name"></span>連携名の変更 | **連携名を変更するには、連携名**の項目で直接編集してください。 |
| <span id="reconnect"></span>再接続 | **再接続する：**<ol><li>連携ステータスがアクティブでない場合、**再接続**をクリックしてください。</li><li>ユーザーインターフェイスの指示に従って、連携に必要な認証情報を更新するか、パートナーにログインして再認証します。</li></ol> |
| <span id="modify-user-identifiers"></span>ユーザー識別子の変更 | <strong>ユーザー識別子を変更するには、</strong>このパートナーとの共有を許可するユーザー識別子を選択／解除してください。 <Anchor target="_blank" href="/marketers/ja/docs/audiences-user-identifier-policy">アカウントレベルのユーザー識別子ポリシー</Anchor>に準拠した識別子のみがアップロードされます。 |
| <span id="delete-connection"></span>連携先の削除 | **連携先を削除する方法：**<ol><li>連携されているオーディエンスがある場合は、次のように削除します。<ol><li>オーディエンスを選択します。</li><li>オーディエンスの連携先タブが新しいタブで開きます。</li><li>連携を削除します。</li><li>タブを閉じます。</li></ol></li><li>連携されているオーディエンスがなくなるまで、この手順を繰り返します。</li><li>**連携先を削除**をクリックします。</li></ol> |

</Accordion>

<div id="dashboard-and-metrics" />

## 管理画面と指標

このセクションでは、管理画面に表示される機能とキャンペーン指標について説明します。

<div id="audiences-dashboard" />

<Accordion title="オーディエンス管理画面">

<Image align="center" alt="new_dashboard_image_doctored.jpg" src="https://support.appsflyer.com/hc/article_attachments/30258966628625" />

| 列 | 説明 |
| --- | --- |
| <span id="audience-name"></span>オーディエンス名 | オーディエンス名 |
| <span id="size"></span>サイズ | 視聴者の条件に一致するすべてのユーザー |
| <span id="upload-size"></span>アップロードサイズ | アカウントレベルの<Anchor target="_blank" href="/marketers/ja/docs/audiences-user-identifier-policy">ユーザー識別子ポリシー</Anchor>を適用し、接続されたパートナー連携の識別子を選択した後の、アップロード可能なオーディエンスサイズの推定値。<br /><br />**注記：** パートナー側の実際のサイズは、さまざまな理由により異なる場合があります：<ul><li>パートナーのマッチングプロセス。</li><li>iOSのアップロードサイズは、重複したIDFAを含む可能性のあるIDFVに基づく強化されたセグメントの数を反映しています。パートナー側にアップロードされるときに重複排除が行われ、サイズの不一致が生じる可能性があります。</li></ul> |
| <span id="app-name"></span>アプリ名 | オーディエンスの定義で参照されるアプリ。これらは、オーディエンスを活用したキャンペーンで対象となるアプリとは限りません。 |
| <span id="upload-to"></span>アップロード先： | <ul><li>オーディエンスが送信されるパートナーのアイコンが表示されます</li><li><Image alt="SplitAudiences.png" src="https://support.appsflyer.com/hc/article_attachments/30259018280465" width="36px" />は、オーディエンスがパートナー間で分割されていることを示します。</li></ul> |
| <span id="incrementality"></span>Incrementality | この列は、<Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview">Incrementality機能を契約している場合に表示されます。</Anchor> ステータスには以下のいずれかが表示されます：<ul><li>**保留中** - キャンペーン開始日から始まる初期データ収集期間（48時間）</li><li>**接続先キャンペーン** - テストにリンクする関連するキャンペーンを選択してください。キャンペーンの提案がある場合は、事前に選択されます (ドロップダウンリストで関連性順に並べられた追加の提案が表示されます)。</li><li>**アクティブ** - テストが進行中です。</li><li>**完了** - テストが終了しました。</li></ul>ステータスをクリックすると、Incrementality管理画面に移動します。 |
| <span id="upload-status"></span>アップロード状況 | <ul><li>現在のオーディエンスアップロード状況</li><li>ツールチップには、最新のアップロードの日時が表示されます。</li><li>失敗した場合は、**詳細を表示**をクリックし、表示されるエラーメッセージの詳細に従って修正措置を実行します</li></ul> |

</Accordion>

<div id="campaign-metrics" />

<Accordion title="キャンペーン指標">

#### metrics hash

<div id="campaign-metrics-basics" />

#### キャンペーン指標の基本

オーディエンス管理画面の **キャンペーン指標** セクションには、ターゲティングにオーディエンスを使用したキャンペーンのデータが表示されます（包含、除外、または類似オーディエンスの基礎として使用したかどうかに関わらず）。

* ターゲティングのためにオーディエンスを使用すること（およびその使用方法を決定すること）は、メディアパートナーとのキャンペーン設定の一部です。オーディエンスをどのように使用できるかのサポート状況は、メディアパートナーによって異なります。

**サポートしているパートナー：** 現在、データはMeta広告、Google広告、Snapchatで利用できます。管理画面の**キャンペーン指標**セクションは、対応しているパートナーに連携されているオーディエンスがある場合のみ表示されます。

**キャンペーン指標を確認する方法：**

1. オーディエンス管理画面の一番右側までスクロールし、**キャンペーン指標**セクションが全て表示されるようにします。
2. 日付範囲を選択して、データを表示したい期間を選択してください。（デフォルトでは、管理画面は過去7日間を表示します。）

**選択した期間のキャンペーン指標をダウンロードする方法**：

1. オーディエンス管理画面の上部にある**エクスポート**ボタンをクリックしてください。
2. ファイルが生成されたら、自動的にダウンロードされます。

<div id="summary-view" />

#### サマリー表示

最初に**キャンペーン指標**が表示される際には、各オーディエンスのキャンペーンデータのサマリーが表示されます。

[<Image align="center" alt="campaign_metrics_summary_view.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018286225" width="433px" />](https://support.appsflyer.com/hc/article_attachments/30258966633233)

| Column | 説明 |
| --- | --- |
| <span id="campaigns"></span>キャンペーン | 選択された期間中にターゲットとしてオーディエンスを使用したキャンペーンの総数（対応しているパートナーと実施したキャンペーンのみ） |
| <span id="campaign-cost"></span>キャンペーンコスト | 選択された期間中にこれらのキャンペーンに要した総費用 |
| <span id="campaign-revenue"></span>キャンペーン収益 | 選択された期間中にこれらのキャンペーンに起因する総収益 |

<div id="detailed-view" />

#### 詳細表示

要約ビューから、<Image alt="show_detailed_view_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018287633" width="24px" />アイコンをクリックして、選択したオーディエンスの詳細画面に入ります。（<Image alt="show_detailed_view_icon.png" src="https://support.appsflyer.com/hc/article_attachments/30259018287633" width="24px" />アイコンは、マウスを行のどこかに置くと、行の右端に表示されます）。

詳細表示では、サポートされているパートナーやキャンペーンごとに分けられたデータが表示されます。

[<Image align="center" alt="campaign_metrics_detailed_view.jpg" src="https://support.appsflyer.com/hc/article_attachments/30259018293649" />](https://support.appsflyer.com/hc/article_attachments/30259018290321)

選択したオーディエンスが複数のアプリをターゲットにしていた場合は、ドロップダウンリスト ![pin_A.png](https://support.appsflyer.com/hc/article_attachments/30259018295697) を使用してアプリ別にデータを絞り込みます。

**オーバービュー管理画面の**リンク ![pin_B.png](https://support.appsflyer.com/hc/article_attachments/30258966657169) をクリックして、オーバービュー管理画面でキャンペーンを確認できます。

* 管理画面は新しいブラウザタブで開き、自動的に関連するキャンペーンで絞り込まれています。
* **オーバービュー管理画面**のリンクが無効になっている場合、ドロップダウンリスト ![pin_A.png](https://support.appsflyer.com/hc/article_attachments/30259018295697) から単一のアプリを選択することでリンクを有効にできます。リンクが有効になったら、それをクリックすることで選択したアプリのオーバービュー管理画面に移動します。

| Column | 説明 |
| --- | --- |
| <span id="cost"></span>コスト | 選択された期間中のキャンペーン費用（合計、および対応しているパートナーとキャンペーンごとの内訳） |
| <span id="revenue"></span>収益 | 選択された期間中のキャンペーンに起因する収益（合計、および対応しているパートナーとキャンペーンごとの内訳） |
| <span id="daily-reach"></span>日次リーチ | 選択された期間中にキャンペーンの広告を見た1日あたりの平均ユニークユーザー数（パートナーからの報告にもとづく） |

<div id="data-sources-and-availability" />

#### データソースと可用性

**キャンペーンの指標**のデータがどこから来ているのかを見てみると、より理解しやすくなります。

* **パートナーのデータ：** メディアパートナーを通じて特定のキャンペーンの対象となるオーディエンスを選択しているため、これらのパートナーのみが特定の情報を提供することができます。
  * オーディエンスとキャンペーンとの関連性（言い換えれば、特定のオーディエンスがそのキャンペーンのターゲティングに使用されたという事実）
  * キャンペーンの広告を見た1日あたりのユニークユーザー数 (「日次リーチ」)
* **AppsFlyerのデータ：** AppsFlyerが提供しているコストと収益データ。

<div id="partner-data-availability" />

<Accordion title="パートナーのデータの可用性">

データは、[対応するパートナー](/docs/audiences-guide#キャンペーン指標の基本)と実施したキャンペーンについてのみ報告されます。

* **注記：** Google Adsは日次リーチのレポートをサポートしていません。

</Accordion>

<div id="appsflyer-data-availability" />

<Accordion title="AppsFlyerデータの可用性">

コストと収益のデータは、AppsFlyerの他のエリア（「オーバービュー」や「イベント」管理画面など）でそのアプリについてのデータがある場合、**キャンペーン指標**のコンテキスト内で利用できます。

* コストデータには <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">ROI360</Anchor>のご契約が必要です。
* 収益データには、<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">広告収益の計測</Anchor> および／または <Anchor target="_blank" href="/marketers/ja/docs/roi360-revenue-attribution-overview">アプリ内イベントの収益の計測</Anchor> が設定されている必要があります。

</Accordion>

<div id="why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners" />

<Accordion title="サポートされているパートナーと実施したキャンペーン指標データが表示されないのはなぜですか？">

キャンペーン指標データは、次の場合にのみ使用できます：

* オーディエンスに接続されているキャンペーン
* サポートされているメディアパートナーサイトで実行されているキャンペーン
* 選択したメインの日付範囲内のアクティブなキャンペーン
* Google が受け取ったキャンペーンは、[キャンペーン指標] フィルタで選択した期間内にインストールトラフィックを獲得します。
* キャンペーンレベルのデータを受信する権限を持つパートナー接続用に構成されたユーザーこのデータを表示するには、パートナーのユーザーの権限を変更するか、パートナーの連携設定で異なる認証情報を使用してください。

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

## 特性と制限

以下の特性と制限事項にご注意ください。

<div id="traits" />

<Accordion title="特性">

| 特性 | 対応 | 備考 |
| --- | --- | --- |
| アドネットワーク | **x** |  |
| 代理店 | **x** |  |
| 代理店の運用媒体の開示設定 | **x** |  |
| アプリ固有のタイムゾーン | N/A |  |
| アプリ固有の通貨 | N/A |  |
| サイズ制限 | N/A |  |
| オーガニックデータ | ✓ | 含まれています |
| 非オーガニックデータ | ✓ | 含まれています |
| データ更新頻度 | 日単位 UTC | <ul><li>アップデートは毎日パートナーへ送信されます。</li><li>ルールビルダーのアプリ内イベントリストは毎日更新されます。</li></ul> |
| 過去データ | ✓ | Audiencesは、Audiencesの契約開始日から90日前のアプリイベントデータにアクセスできます（クリックとインプレッションの場合は31日前）。バックフィルプロセスが完了すると、すべてのデータにアクセスできるようになります（最大2週間かかる場合があります）。 |
| アカウントユーザーのアクセス | ✓ | <ul><li>CSVダウンロード、S3、SFTP、Slackパートナー接続の設定など、一部の機能では、ローデータにアクセスするためにはユーザーアカウントの権限 が必要です。</li><li>セキュリティ対策として、オーディエンスを作成したユーザーのアカウントが削除された場合、AppsFlyerはそのオーディエンスのデータをメディアパートナー（複数可）にアップロードすることを停止します。オーディエンスのアップロード状況を確認するには、AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。オーディエンスを再開するには、複製し[オーディエンス分割](/docs/audiences-guide#audience-split-and-control-groups)を設定してください。</li></ul> |

</Accordion>

<div id="limitations" />

<Accordion title="制限事項">

| 制限事項 | 備考 |
| --- | --- |
| アトリビューションデータ | クリック数と表示回数のデータは、元のクリックURLに advertising\_id / idfa パラメータが付与されているデバイスのみが含まれています。外部の計測リンクを使用しないSRNのユーザーのデバイスは、オーディエンスのクリックデータには含まれません。 |
| オーディエンス作成 | <ul><li>オーディエンスの接続先パートナー側で名前を変更することはできません。</li><li>オーディエンスを作成する際、上位100個のイベントのみが表示されます。ただし、イベント名を入力し始めることで、すべてのイベントが確認できます。</li><li>ルール構築画面内で総収益フィルターを使用している場合、「推定オーディエンスサイズ」は使用できません。これは、オーディエンス作成プロセスには影響しません。</li></ul> |
| 接続 | 同じアカウント / ログイン / プロパティIDなどを持つ重複したパートナー接続の作成はサポートされておらず、エラーが発生します。 |
| オーディエンスCSVファイルのダウンロード | ダウンロードファイルサイズは、最大500万件までです。 |
| インポートされたオーディエンス | インポートされたオーディエンスを他のオーディエンスやルールセットと組み合わせることはできません。 |
| 無効なオーディエンス | アクティブでないオーディエンスは一時停止されます。つまり、これらのオーディエンスは計算されたりパートナーにアップロードされたりしなくなります。ただし、「今すぐアップロード」をクリックすることで、オーディエンスの一時停止をいつでも解除することができます。これにより、以前と同様にオーディエンスの計算とパートナーへの自動アップロードが再開されます。 |
| 対応外 | AppsFlyer Audiencesでは次のものはサポートされていません：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/audiences-partner-connections#google-ads">Google Ads</Anchor>：UACキャンペーンはサポートされていません。その他のキャンペーンタイプはサポートされています。</li><li>Windows Phone OS</li><li>ネストされたイベント値</li></ul> |
| オーディエンス数 | <ul><li>オーディエンスは1日100個まで作成できます。</li><li>カスタム / 推奨オーディエンスは一度に100個までアクティブに設定できます。</li><li>一度に最大500のアクティブなインポート済みオーディエンスを持つことができます。</li></ul> |
| ルールセット | <ul><li>ルールセット内では、アプリ内イベントは属性ごとに100個の一意の値に制限されています。例えば、イベントが「purchase」で、属性が「content-type」である場合、可能なコンテンツタイプは100個（以下）までしか設定できません。ただし、数値は無制限です。属性1つあたりの値が100個以上必要な場合は、CSM または hello@AppsFlyer.com までご連絡ください。</li><li>数値ルール・セット・フィルターでサポートされるのは、整数のみです。浮動小数点型 (10 進数) の数値はサポートされていません。例：$1に相当するアプリ内収益はサポートされますが、$1.5はサポートされません。</li></ul> |
| S2Sレポーティング | ユーザー識別子（IDFVまたはIDFA）がS2Sモバイルイベントのペイロードに送信され、IDFVまたはIDFAがAppsFlyer SDKの収集と一致していることを確認してください。これにより、データの欠落を防ぎ、オーディエンスの計算が正確であることが保証されます。 |

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview">Incrementalityガイド</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/run-an-incrementality-for-remarketing-experiment">Incrementality： 純増検証の実行</Anchor>

<div data-zendesk-anchors="audiences-basics=audienes%E3%81%AE%E5%9F%BA%E6%9C%AC%E4%BB%95%E6%A7%98 h_01HBQMA619CKEESZD3ADSP3PSB=audienes%E3%81%AE%E5%9F%BA%E6%9C%AC%E4%BB%95%E6%A7%98 audience-split-and-incrementality-testing=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E5%88%86%E5%89%B2%E3%81%A8%E3%82%A4%E3%83%B3%E3%82%AF%E3%83%AA%E3%83%A1%E3%83%B3%E3%82%BF%E3%83%AA%E3%83%86%E3%82%A3%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01HBQMA619KMJFVX7Y8MXMMQ6N=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E5%88%86%E5%89%B2%E3%81%A8%E3%82%A4%E3%83%B3%E3%82%AF%E3%83%AA%E3%83%A1%E3%83%B3%E3%82%BF%E3%83%AA%E3%83%86%E3%82%A3%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 get-started=%E3%81%BE%E3%81%9A%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HBQMA619118PWF4TA98C4X0B=%E3%81%BE%E3%81%9A%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB create-and-manage-audiences=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%AE%E4%BD%9C%E6%88%90%E3%81%A8%E7%AE%A1%E7%90%86 h_01HBQMA619DBX2C7DRY7MSV3P9=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%AE%E4%BD%9C%E6%88%90%E3%81%A8%E7%AE%A1%E7%90%86 h_01HBQMA6195AT0YD7783V6BQR6=create-a-custom-audience h_01HBQMA619F2P2CVPCSMX9RTKB=create-a-suggested-audience h_01HBQMA619RBRYNMVMNQ839196=%E6%B4%BB%E7%94%A8%E4%BA%8B%E4%BE%8B h_01HBQMA619ATHVJARHYXQNY955=import-an-audience h_01HBQMA6193FFM66XDTB6WYX06=connect-an-audience-to-media-partners user-identifier%E2%80%94device-id-vs-customer-id=user-identifier-device-id-vs-customer-id h_01HBQMA61A192YFES8TK1347FJ=user-identifier-device-id-vs-customer-id 01ECF4ZD0NWN5QQPP88ZKW0578=%E4%BE%8B%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9id-vscuid 01ECF4ZD0WNEF6FRPF1NJHZ9WR=audience-split-and-control-groups h_01HBQMA61ANM52HBDAFA5QZPFN=manage-audiences h_01HT04HW2VBB9ZY28V5KQ5K2AJ=pause all-about-rulesets=%E3%83%AB%E3%83%BC%E3%83%AB%E3%82%BB%E3%83%83%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HBQMA61ANB4K0TCJ4WBHMV8D=%E3%83%AB%E3%83%BC%E3%83%AB%E3%82%BB%E3%83%83%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HBQMA61A30YGERD8Z6DXV3KA=audience-segmentation-rulesets h_01HBQMA61AF7V3M0Y8ZN1R0HZC=ruleset-examples h_01HBQMA61ATV5MHN35XMTJ8MEH=%E4%BE%8B%E3%83%AD%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E3%83%AB%E3%83%BC%E3%83%AB h_01HBQMA61ATB7NYKBP7CD6SZZH=%E4%BE%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%B1%9E%E6%80%A7%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E3%83%AB%E3%83%BC%E3%83%AB h_01HBQMA61APWHKS4EP2NKABSQD=%E4%BE%8B%E5%8F%8E%E7%9B%8A 01ECF4ZD0MJ8HVQCC54YHFE6DX=%E4%BE%8B%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC h_01JRAGFYEQ28R6RQNPEK6WZV2F=%E4%BE%8B%E3%83%AA%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01HBQMA61AEKT6N97SJBW4B01C=ruleset-filters h_01HBQMA61A17Y4928D2ZDGAEXV=events h_01HBQMA61BK8NZF79KDPK0JBX6=inapp-events h_01HBQMA61B4FGBE11W6BW2Z9AH=revenue::3358edf4 h_01HBQMA61BX9XQKBX3MAGYXC2Y=geo h_01HBQMA61B9DRMSNKJM3B0WBE1=owned-media h_01HBQMA61BC1G2VZSJEJF90T7Q=device h_01HBQMA61BF2N8FN6TJ3JD6YXC=attribution h_01HBQMA61CKVMYYS8GG6CP72WD=user-attributes h_01HBQMA61C7K8R4AR13D4WHTHX=combine-rulesets create-and-manage-partner-connections=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BA%E3%81%AE%E4%BD%9C%E6%88%90%E3%81%A8%E7%AE%A1%E7%90%86 h_01HBQMA61C6WS72DQ8FXVR0KVW=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BA%E3%81%AE%E4%BD%9C%E6%88%90%E3%81%A8%E7%AE%A1%E7%90%86 h_01HBQMA61CRDF41WBYCDQ91M3R=create-a-new-connection h_01HBQMA61CXZYEW2R12KS99X2N=manage-connections dashboard-and-metrics=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A8%E6%8C%87%E6%A8%99 h_01HBQMA61C6WPFFR1F8P0HE4KA=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A8%E6%8C%87%E6%A8%99 h_01HBQMA61CMPNC9TYAW82ED18Q=audiences-dashboard h_01HBQMA61CWHR9GDANKT7P6Z27=campaign-metrics h_01HBQMA61CMF3WZFPXKY89076K=metrics-hash campaign-metrics-basics=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E6%8C%87%E6%A8%99%E3%81%AE%E5%9F%BA%E6%9C%AC h_01HBQMA61C4D5HFCDY83HNF5K7=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E6%8C%87%E6%A8%99%E3%81%AE%E5%9F%BA%E6%9C%AC summary-view=%E3%82%B5%E3%83%9E%E3%83%AA%E3%83%BC%E8%A1%A8%E7%A4%BA h_01HBQMA61DW9Z84G8CH1RNY2RF=%E3%82%B5%E3%83%9E%E3%83%AA%E3%83%BC%E8%A1%A8%E7%A4%BA detailed-view=%E8%A9%B3%E7%B4%B0%E8%A1%A8%E7%A4%BA h_01HBQMA61D3VHDKD103EMN61YH=%E8%A9%B3%E7%B4%B0%E8%A1%A8%E7%A4%BA data-sources-and-availability=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A8%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HBQMA61DB595QKRTPE97F94E=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A8%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HBQMA61DCV0M97GMXRA1A30F=partner-data-availability h_01HBQMA61DXNR275AT9SK0G32S=appsflyer-data-availability h_01HBQMA61DH9P5B1H5GYXQ9CCN=why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HBQMA61DT46P43FNSRC1KGAX=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HBQMA61DYHF0REXYKDQBDXP5=traits h_01HBQMA61D28F5RG2WXT801XXZ=limitations h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=%E5%8F%82%E7%85%A7" />
