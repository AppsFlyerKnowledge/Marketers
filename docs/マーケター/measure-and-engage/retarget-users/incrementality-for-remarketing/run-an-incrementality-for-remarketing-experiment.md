---
title: 'Incrementality: 純増検証の実行'
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2020-10-12T19:26:09Z'
  edited_at: '2026-10-14T09:37:00Z'
  id: 360014225577
  locale: ja
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/ja/articles/360014225577
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 純増検証を実施して、リマーケティングキャンペーンの真の効果を把握します。

<Image align="center" alt="KB_toggle_final.jpg" src="https://files.readme.io/4de8c3ff1edaaae77fc0571de6125b25c884bcc4e4ac67471fc90610298866e1-30780522054801.jpg" />

<div id="about-the-experiment" />

## 検証について

<Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview">インクリメンタリティ</Anchor>テストは、純増、つまりマーケティングキャンペーンの結果発生したコンバージョン数と、キャンペーン無しでも発生したであろうコンバージョン数の差を正確に測定するA/Bテストによって、キャンペーンの真の効果を計測します。

結果は、マーケティング投資によって生み出される実際の価値を理解するために重要です。インクリメンタリティテストにより、特定のチャネルやキャンペーンの影響を客観的に確認でき、予算の配分やキャンペーンの最適化においてより賢明な決定を下せます。

AppsFlyerは、オーディエンスの作成から始まる自動化されたプロセスで、インクリメンタリティテストを容易にします。新しいオーディエンスは、有効化された「純増影響を計測」トグルによって接続されたメディアパートナーとコントロールグループの間で自動的に分割されます。コントロールグループは、パートナーから除外されるオーディエンスの一部であり、テストに不可欠な部分です。オーディエンスを保存すると、インクリメンタリティ検証が自動で作成されます。パートナー側でキャンペーンを開始し、正しいキャンペーンが接続されていることを確認できれば、Incrementality管理画面で検証結果を確認できます。

<div id="get-started" />

## まずはじめに

インクリメンタリティはプレミアム機能です。ご契約後、以下の手順でご利用いただけます。各ステップの詳細については、以下の[検証の設定](/docs/run-an-incrementality-for-remarketing-experiment#検証を設定する)を参照してください。

|  | 手順 |
| --- | --- |
| 1 | [**テストの目的を確認**](/docs/run-an-incrementality-for-remarketing-experiment#know-your-test-objectives)<br /><br />明確なテスト目標と結果の仮説を立てることで、検証結果の活用性を最大化しましょう。 |
| 2 | [**ターゲットオーディエンスを作成し、グループに分ける**](/docs/run-an-incrementality-for-remarketing-experiment#create-the-target-audience-and-split-groups)<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">オーディエンス</Anchor>管理画面で：<ul><li>オーディエンスを設定します。</li><li>アドネットワークに接続します。</li><li>オーディエンスは、有効なトグルによって自動的にテストグループとコントロールグループに分割されます（インクリメンタリティをご契約の場合 / 2023年1月11日以降に作成されたオーディエンス）。<br />AppsFlyer Audiencesは、テストグループのメンバーをアドネットワークにアップロードし、コントロールグループのメンバーを保持します。</li></ul> |
| 3 | [**キャンペーン及び検証を開始する**](/docs/run-an-incrementality-for-remarketing-experiment#launch-the-campaign-and-experiment)<ul><li>アドネットワークで、オーディエンス内のユーザーをターゲットとするキャンペーンを作成し、開始します。</li><li>Incrementality検証は自動で作成されます（ご契約の場合）。</li></ul>テストグループのメンバーは広告にさらされます。コントロールグループは広告にさらされません。 |
| 4 | [**結果の分析**](/docs/run-an-incrementality-for-remarketing-experiment#analyze-the-results)<ul><li>純増分析が<Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview#incrementality管理画面">Incrementalityダッシュボード</Anchor>に表示されます。</li><li>ユーザーレベルのローデータは、 <Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview#ローデータレポート">Incrementalityローデータレポート</Anchor>（Data Locker経由のみ）で取得可能です。</li></ul>適切に実行された純増検証から得られたインサイトにより、マーケティングキャンペーンを最適化して最大のプラスの影響を得ることができます。例えば、ターゲットオーディエンスに最適なメッセージ、クリエイティブやプロモーション、最も効果的なメディアソースを見つける手助けをします。 |

<div id="set-up-the-experiment" />

## 検証を設定する

<div id="know-your-test-objectives" />

<Accordion title="テストの目的を理解する">

検証を行う際、何をテストするか（変数）や結果に対する仮説を明確に定義することが重要です。以下の表は、検証設計におけるガイドラインとベストプラクティスを提供します：

| 変数 ／ 仮説 | ガイドラインとベストプラクティス |
| --- | --- |
| オーディエンス | テストするオーディエンスを説明します。AppsFlyer Audiencesで既に設定しているオーディエンスを選ぶか、テスト基準を満たす新しいオーディエンスを作成してください。 |
| オーディエンスの規模 | ユーザーベースが大きく、コンバージョン率の高いイベントを持つオーディエンスを選択してください。大規模なサンプルサイズは、<Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview#statistical-significance">統計的に有意義な結果</Anchor>をもたらす可能性が高くなります。<br /><br />**ベストプラクティス：** 少なくとも50,000人のユーザーからなるオーディエンスを選択し、1～3つのアドネットワークとコントロールグループに分けます。 |
| キャンペーン | キャンペーンについて（メッセージ、インセンティブなど）説明します。 |
| コントロールグループの割合 | コントロールグループは、オーディエンス全体の15%に自動設定されます（ベストプラクティスは15%～25%です）。 |
| テストグループ | 検証するアドネットワークを決定してください。分割率はそれぞれ均等に分けられますが、それぞれに送信するオーディエンスの割合を調整できます。<br /><br />**ベストプラクティス：** 1〜3のアドネットワーク |
| 仮説 | 検証で期待する結果を明確にしましょう。<br /><br />始める前に結果を予測することは直感に反する感覚があるかもしれませんが、仮説を設定することは検証設計において重要な要素です。これが結果を解釈する助けとなります。<br /><br />**ベストプラクティス：** 曖昧な推定ではなく、実際のパーセンテージを使って容易に検証できる仮説を立てましょう。例えば：<ul><li>***アップグレードを購入するユーザーが15%増加する***は、容易に検証できる仮説です。</li><li>***アップグレードを購入するユーザーが大幅に増加する***は、テストが難しい例です。</li></ul> |

<div id="example" />

> 📄 **例**
>
> 上記のガイドラインを参考に、次のような検証を設定できるでしょう。
>
>
>
> | 変数 ／ 仮説 | 例 |
> | --- | --- |
> | オーディエンス | 登録を完了したが購入に至らなかったユーザー |
> | オーディエンスの規模 | 100,000 |
> | キャンペーン | 指定された期間内に購入したユーザーに割引券を提供するキャンペーン |
> | コントロールグループの割合 | オーディエンスの15% |
> | テストグループ | 残りのオーディエンスを次の接続先に送信します：<br /><br />* ネットワークA（オーディエンスの42%）<br />* ネットワークB（オーディエンスの43%） |
> | 仮説 | リマーケティングキャンペーンに参加して購入に至るテストグループのユーザーの割合は、コントロールグループのユーザーよりも10%高くなります。 |

</Accordion>

<div id="create-the-target-audience-and-split-groups" />

<Accordion title="ターゲットオーディエンスの作成とグループの分割">

目標を定義した後は、テストするオーディエンスを構成することが次のステップです：

1. AppsFlyer Audiences で、<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#オーディエンスの作成と管理">オーディエンスを作成</Anchor>してください（必要に応じて、既存のオーディエンスを検証設計に基づいて分割することも可能です）。
2. 選択したオーディエンスの **接続** タブで次の操作を実行します：
   * オーディエンスを 1～3社のアドネットワークパートナーに接続してください。
   * <Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#audience-split-and-control-groups">オーディエンスの分割</Anchor> するトグルがオンになっていることを確認します（**2023年1月11日以降に作成されたオーディエンス：自動的に有効**）。有効になっていない場合は、トグルをクリックして有効化してください。  
     <Image align="center" alt="Measure_inc_impact_toggle.jpg" src="https://files.readme.io/a04b3be68fcc00d62e6a92391fbbea685ca2bfcbf83bd5678660c6a1b8c58fc2-30780493858065.jpg" />
   * コントロールグループは自動的に15%（推奨）に設定されます。
   * 残りのオーディエンスは選択したアドネットワークパートナー間で自動的に均等に分割されます。
     * 合計の分割比率は100%に等しくならなければなりません（コントロールグループを含みます）。

分割を有効にしてオーディエンスを保存すると、Incrementality検証が自動的に開始されます（Incrementality契約者のみ）。これらの検証は、「[Auto]」という接頭辞がタイトルの前に付けられた状態でIncrementality管理画面で確認できます。

<Image align="center" alt="Auto_before_title.jpg" src="https://files.readme.io/fdab39eee29240ae0d9b907f7c6504a9e08e470454d5f8e43933512c65db15d4-30780522066833.jpg" />

**重要な注意事項：**

* 検証を行っている間は、オーディエンスの構成を変更しないでください。パートナー、オーディエンス名、その他の設定を変更すると、統計分析結果が不正確になります。  
  **ベストプラクティス：** 検証が終了した後であっても、以前にテストしたオーディエンスの定義を変更する必要がある場合、まずオーディエンスを複製してから新しいコピーに変更を加えてください。これにより、Incrementality管理画面上の履歴データの整合性が保たれます。
* 既存のオーディエンスの分割やパートナー構成を変更すると、現在進行中のIncrementality検証が終了し、新たな検証が開始されます。
* #### <span id="check-for-audience-expansion-features"></span>オーディエンス拡張機能を確認してください：

Meta広告とGoogle広告には、キャンペーンのリーチを拡大するために設定済みのオーディエンスリスト外をターゲットするオプション機能があります。この機能をオンのままにすると、Incrementality検証にバイアスがかかり、不正確な結果が発生します。**この機能がオフになっていることを確認してください。**

Meta広告では、この機能は「Advantageカスタムオーディエンス」と呼ばれています。これは広告セットレベルで表示され、デフォルトで有効になっています。

<Image align="center" alt="image__4_.png" src="https://files.readme.io/a0bee1bbb2c6521007146a5ac70de52ce821f459fd2aece127a97a2e0b75c93d-30780493862033.png" width="458px" />
Google広告では「オーディエンス拡張」と呼ばれています。

<Image align="center" alt="Google_Ads_Incrementality_limitation_cropped.jpg" src="https://files.readme.io/042aac534d0a527753b643bb63a52f59889219ebda922cc04f8a61c5984afb80-30780493867409.jpg" width="436px" />

</Accordion>

<div id="launch-the-campaign-and-experiment" />

<Accordion title="キャンペーンの開始と検証の設定">

**次のアクションを実行してください：**

<div id="1-configure-campaigns-on-ad-networks" />

#### 1. アドネットワークでキャンペーンを設定する

最初のステップとして、オーディエンス内のユーザーをターゲットとするキャンペーンを作成し、各アドネットワーク側（オーディエンスがアップロードされるアドネットワークごとに）で開始してください。

* <strong>重要！</strong>正確なテスト結果を得るため、テスト対象のオーディエンス内のユーザーのみをターゲットにするようにキャンペーンを構成し、他のソースのユーザーは含めないようにしてください。
* テスト対象のオーディエンスが新しく作成された場合、オーディエンスがアドネットワークプラットフォームで利用可能になるまで最大24時間かかることがあります。

<div id="2-ensure-the-correct-campaign-is-linked-to-the-experiment" />

#### 2. 正しいキャンペーンが検証に接続されているか確認してください。

新しいオーディエンスを作成し「純増影響の測定」トグルを有効にすると、純増検証が自動的に開始されます（既存のオーディエンスで有効にした場合も含まれます）。最も関連性の高いキャンペーンが自動的にテストに接続されますが、必要に応じてキャンペーンを変更できます。

**キャンペーンの接続／変更を行うには：**

1. **インクリメンタリティ管理画面**から、特定の検証を選択し、**検証の編集**をクリックします。

<Image align="center" alt="Edit_experiment.jpg" src="https://files.readme.io/f478737e2a8db560a5ea33b287fe8f41587ec1f743c1bc01ba15ab6ce72478e9-30780493873425.jpg" width="642px" />

または

**オーディエンス**から特定のオーディエンスを見つけ、インクリメンタリティの列の **+ キャンペーンの接続**をクリック。

<Image align="center" alt="Link_campaign__audiences_status_.jpg" src="https://files.readme.io/5da762448fb731843fef0aec66ae826ed6922a5dd213a78ccd93f544b21fcfdc-small-30780522084625.jpg" width="768px" />

キャンペーンを接続できる画面が表示されます。

<Image align="center" alt="Link_campaign_to_experiment_window.jpg" src="https://files.readme.io/9492444847bfc6a26778624d72d5b468acc62b705530db66d0bd0fdff89f5e89-30780493883409.jpg" width="506px" />

2. 各アドネットワークにおける適切なキャンペーンを選択します。

**注：** ドロップダウンメニューには、メディアパートナーから取得したキャンペーンが表示されます。データが利用可能になると、ドロップダウン内のキャンペーンは特定のオーディエンスにマーケティングされる可能性の高い順に並べられます。最上位の推奨があらかじめ選択されます。

3. **保存**をクリックします。

これでキャンペーンが検証に接続されました。

<div id="manually-create-an-experiment" />

#### 手動で検証を作成する

2023年1月11日以降にオーディエンスを作成したIncrementalityをご契約の方は手動で検証を作成する必要はありません。検証はオーディエンス向けに自動的に作成されます（Incrementality管理画面では、タイトルの前に「[Auto]」と表示されます）。以前のオーディエンスやその他の理由で手動の検証を作成したい場合、以下の手順に従ってください。

**新しい純増検証を手動で作成するには：**

* AppsFlyer管理画面 左メニュー **最適化** > **Incrementality: 純増検証** へ移動します。
* **インクリメンタリティ検証**ページで、**新しい検証**ボタンをクリックします。
* ウィザードのステップに従って検証を作成します。各ステップを進めるごとに詳細な指示が提供されます。

  <div id="notes" />

  > 📘 **注意**
  >
  > – **オーディエンス設定**
  >
  > <Image align="center" alt="" src="https://files.readme.io/e956b50df1931b190206f42b48a8f2f061937fe1f25c96801a416d287d7eb3f5-30780493888273.png" width="603px" />
  >
  > ウィザードのステップ 2 では、**オーディエンスに含める日付**を選択する必要があります。
  >
  > デフォルトでは、これはオーディエンスが最初にコントロールグループに分けられた日付です。正確な検証結果を確保するため、以下のいずれかの状況が該当する場合はこの日付を変更してください：
  >
  > * 選択したオーディエンスの定義（<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#ルールセットについて">セグメントルールセット</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#user-identifier-device-id-vs-customer-id">ユーザー識別子</Anchor>など）に変更を加えた場合 → この日付を、オーディエンス定義の変更が行われた最後の日付と一致するように変更します。
  > * 既存のオーディエンスに対して新しいキャンペーンをテストする場合 → この日付を新キャンペーン開始日へ変更します。
  >
  > **ウィザード ステップ 3 – ターゲット設定**
  >
  > <Image align="center" alt="Step_3_Set_targets.jpg" src="https://files.readme.io/9c58ad61463b1751f5ad8b2c5235d6d61b13baa156db56d5edeb156debbcfeaa-30780522104081.jpg" />
  >
  > ここでは、ターゲットアプリとKPIを選びます。
  >
  > **注：** 選択されていない場合でも、検証の終了時にはすべての他のKPIが利用可能となります。
  >
  > **ウィザード ステップ 4  – レビュー**
  >
  > <Image align="center" alt="" src="https://files.readme.io/75c90dc66cff6abc772a352d81b6b57498e5915da66efaa83a754d9a5a08be70-30780522113681.png" width="583px" />
  >
  > ウィザードのステップ 4 では、**検証期間**を設定する必要があります。
  >
  > * デフォルトでは、検証は開始後30日間行うように設定されています。これは検証の推奨される最低期間です。
  > * 検証を望むだけ続けたい場合は、**検証を無期限に継続する**オプションを選んでください。


</Accordion>

<div id="analyze-the-results" />

<Accordion title="結果の分析">

接続されたキャンペーンが広告ネットワーク上で開始されてから約48時間後に、<Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview#incrementality管理画面">インクリメンタリティ画面</Anchor>に初期の結果が表示されます（<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#eod">毎日</Anchor>更新）。結果の精度を影響する問題の識別と解決策提案のため、<Anchor target="_blank" href="/marketers/ja/docs/understand-incrementality-for-remarketing-experiment-alerts">検証アラート</Anchor>が表示されることがあります。

<Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview#ローデータレポート">インクリメンタリティローデータレポート</Anchor>はData Locker経由で取得できます。

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">オーディエンスガイド</Anchor>

<div data-zendesk-anchors="overview=%E6%A4%9C%E8%A8%BC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HARVCSMM80QXXXKJC8TX7CKC=%E6%A4%9C%E8%A8%BC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 get-started=%E3%81%BE%E3%81%9A%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HARVCSMMYJVN6GJ3TB46P8AC=%E3%81%BE%E3%81%9A%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB set-up-the-experiment=%E6%A4%9C%E8%A8%BC%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HARVCSMMMAJ6VTYHZ2ZJ5HNS=%E6%A4%9C%E8%A8%BC%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HARVCSMM9P2HN5WA9C16PA5E=know-your-test-objectives h_01HARVCSMM2THH54JH58GM1K57=%E4%BE%8B h_01HARVCSMM77RV7NM9K7D5FJM5=create-the-target-audience-and-split-groups check-for-audience-expansion-features=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%97%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84 h_01HARVCSMMXNE4NCWSQZ9SHK1J=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%97%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84 h_01HARVCSMMH11D6RKDZQZ3WVZ6=launch-the-campaign-and-experiment 1-configure-campaigns-on-ad-networks=1-%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%A7%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HARVCSMMVXJWCT2BX3CVC3VT=1-%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%A7%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B 2-link-campaigns-to-experiment=2-%E6%AD%A3%E3%81%97%E3%81%84%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%8C%E6%A4%9C%E8%A8%BC%E3%81%AB%E6%8E%A5%E7%B6%9A%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%81%8B%E7%A2%BA%E8%AA%8D%E3%81%97%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84 h_01HARVCSMNAWNYEY83NC6Y5XV4=2-%E6%AD%A3%E3%81%97%E3%81%84%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%8C%E6%A4%9C%E8%A8%BC%E3%81%AB%E6%8E%A5%E7%B6%9A%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%81%8B%E7%A2%BA%E8%AA%8D%E3%81%97%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84 manually-create-an-experiment=%E6%89%8B%E5%8B%95%E3%81%A7%E6%A4%9C%E8%A8%BC%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01HARVCSMNZVWK8Z36ER1HH10W=%E6%89%8B%E5%8B%95%E3%81%A7%E6%A4%9C%E8%A8%BC%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01HARVCSMN5944HRD9N7YEKT3P=%E6%B3%A8%E6%84%8F h_01HARVCSMNS961WKFX280J3R2X=analyze-the-results h_01HE7RBMSE1RHVSJC7B7FZG8SJ=%E5%8F%82%E7%85%A7" />
