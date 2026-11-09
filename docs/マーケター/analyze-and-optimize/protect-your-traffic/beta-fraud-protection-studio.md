---
title: ［Beta機能］Fraud Protection Studio
metadata:
  keywords:
    - Marketers
    - Beta feature
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2024-12-08T06:38:30Z'
  edited_at: '2026-10-28T08:58:15Z'
  id: 30754984040977
  locale: ja
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ja/articles/30754984040977
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **概要：** Fraud Protection Studio（不正対策の設定・検証機能、FPS）を使うと、通常の方法よりも、不正検知の適用方法を細かく設定できます。検知したデータをブロックして不正としてレポートするか、タグ付けするかを選択でき、目的に合った不正対策を行えます。

<div id="about-fraud-protection-studio" />

## Fraud Protection Studioについて

Fraud Protection Studioでは、検知ステータスに「タグ付け」が追加されます。

このステータスを使うと、広告主は自動で処理を実行せずに不正を検知でき、次のことが可能になります。

* 検証：不正検知機能の更新が適用される前に、その影響を確認できます。
* 設定：ビジネスモデルやニーズに合わせて、不正検知を調整できます。
* 状況の把握：タグ付けデータから、追加の不正対策による効果を把握できます。

<div id="important" />

> 🚧 **重要**
>
> Fraud Protection Studioにアクセスできるのは、<Anchor target="_blank" href="/marketers/ja/docs/user-management#ロールの管理">権限ロール</Anchor>が「管理者」「マーケティング責任者」「チームマネージャー」「セキュリティ」のユーザーのみです。

<div id="how-the-fraud-protection-studio-works" />

## Fraud Protection Studioの仕組み

<div id="key-concepts" />

<Accordion title="基本的な考え方">

<div id="fps-modes" />

#### FPSのモード

FPSには、**適用**と**タグ付け**の2つのモードがあります。広告主は、目的に応じてモードを切り替え、ニーズに合った不正検知を行えます。

**従来の検知の仕組み：** インストールは、次のいずれかに分類されます。

* **有効**なアトリビューション
* **不正を検知**
  * リアルタイムで**ブロック**
  * ポストアトリビューション不正として**レポートに表示**

<Image align="center" alt="図の説明" src="https://files.readme.io/86996ca9cf4fb83b5cfa24473a302d4e978732495348e3e7432ca2117d1f03c9-30885578633745.png" width="75%" />
**FPSでの仕組み：** インストールは、次のいずれかに分類されます。

* **有効**なアトリビューション
* **不正を検知**した場合
  * **タグ付け**し、アトリビューションは**有効**のまま維持
  * **適用**
    * リアルタイムで**ブロック**
    * ポストアトリビューション不正として**レポートに表示**

<Image align="center" alt="図の説明" src="https://files.readme.io/465289666e54257f02cfe0a3b34a765e7109426c1f6438f455613cc53351e4f4-31990048826513.png" width="75%" />

<div id="note" />

> 📘 **注意**
>
> タグ付けモードでは、検知してタグ付けしても有効なまま維持するデータは、お客様の設定に基づいて有効とみなされます。このため、従量課金プランの計測件数からは差し引かれません。

<div id="where-is-tagged-detection-reflected" />

#### タグ付けした検知結果はどこに表示されますか？

タグ付けした検知結果は、不正のレポートには表示されません。通常のアトリビューションレポートとProtect360ダッシュボードに、次のように表示されます。

**レポート**：

* リアルタイムでタグ付けされたインストール
* ポストアトリビューションでタグ付けされたインストール
* リアルタイムでタグ付けされたアプリ内イベント
* ポストアトリビューションでタグ付けされたアプリ内イベント

**Protect360ダッシュボード**：

<Image align="center" alt="example10.png" src="https://files.readme.io/cf4c836ee78519bd0723bcc1fafb202110fa014be1582853646261d89eb37104-48783289649937.png" width="50%" />

* ページ上部の各項目に表示されるタグ付け件数の合計（1）
* 「検知ステータス」の時系列の推移（2）
* 「タグの種類」「タグ付け理由」「タグ付け理由の詳細」別に表示される、検知された不正（3）

</Accordion>

<div id="how-to-use-fraud-protection-studio" />

## Fraud Protection Studioの利用方法

<div id="general" />

<Accordion title="概要">

FPSは、検知したデータに対して、どのような場合に[適用またはタグ付け](/docs/beta-fraud-protection-studio#fpsのモード)を行うかを指定する設定ページです。次の機能を使って、タグ付けの条件を設定できます。

* 検知ステータスのデータ。
* 適用モードとタグ付けモードの切り替え。

利用を開始するには：

1. AppsFlyerにログインします。
2. 左側のメニューから、**設定 > Protect360 > Fraud Protection Studio**に移動します。
3. ページ上部のアプリのドロップダウンから、設定するアプリを選択します。
4. 左側のメニューからカードを選択します。現在の選択肢は次のとおりです。
   * [クリック洪水](/docs/beta-fraud-protection-studio#click-flood-detection)
   * [新しい検知機能](/docs/beta-fraud-protection-studio#new-releases)

</Accordion>

<div id="click-flood-detection" />

<Accordion title="クリック洪水の検知">

FPSでは、クリック洪水の検知を簡単に管理し、設定を調整できます。アプリ単位（すべてのパートナーが対象）でクリック洪水の検知結果にタグ付けし、そのデータを専用レポートで確認できます。

クリック洪水のカードのページでは、[検知ステータスを確認し、適用とタグ付けを切り替える](/docs/beta-fraud-protection-studio#クリック洪水の画面を開く方法)ことができます。また、[現在の検知状況](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source)のデータも確認できます。

クリック洪水レポートのサンプルデータをダウンロード

<div id="important-2" />

<div id="important-1" />

> 🚧 **重要**
>
> * タグ付けを選択した場合、検知結果は不正のレポートではなく、ローデータレポートに表示されます。
> * クリック洪水のタグ付けはアプリ単位で適用され、ブロックやポストアトリビューションでの不正判定の適用は行われなくなります。そのため、タグ付けにすると、非オーガニックとオーガニックのインストールが不正の影響を受けるリスクがあります。

<div id="how-to-access-click-flood" />

#### クリック洪水の画面を開く方法

1. AppsFlyerにログインします。
2. 左側のメニューから、**設定 > Protect360 > Fraud Protection Studio**に移動します。
3. ページ上部のアプリのドロップダウンから、設定するアプリを選択します。
4. 左側のメニューから、**クリック洪水**のカードを選択します。

<div id="click-flood-page" />

### クリック洪水のページ

クリック洪水のページは、2つのセクションで構成されています。

[検知ステータス](/docs/beta-fraud-protection-studio#検知ステータス)

[現在の検知状況](/docs/beta-fraud-protection-studio#現在の検知状況)

<div id="detection-status" />

#### 検知ステータス

* [検知ステータス](/docs/beta-fraud-protection-studio#クリック洪水の画面を開く方法)：[検知](/docs/beta-fraud-protection-studio#fpsのモード)モードを選択できます。**適用**または**タグ付け**を選択できます。
* [現在の検知状況](/docs/beta-fraud-protection-studio#現在の検知状況)：先週より前の7日間のデータに基づき、クリック洪水の検知を適用した場合に、インストールと関連イベントにどのような影響があったかを表示します。このセクションは、さらに次の項目に分かれています。
  * 現在の検知状況のウィジェット
  * クリック洪水の検知内訳のウィジェット
  * メディアソース別のクリック洪水のウィジェット

<div id="how-to-adjust-the-detection-status" />

#### **検知ステータスの変更方法**

検知ステータスで、[検知](/docs/beta-fraud-protection-studio#fpsのモード)モードを選択できます。**適用**または**タグ付け**を選択できます。

1. クリック洪水の画面で、[検知モード](/docs/beta-fraud-protection-studio#fpsのモード)を選択します。
2. ページ下部の**保存**ボタンをクリックします。

   <Image align="center" alt="拡大表示できる画像" src="https://files.readme.io/c472a15b2775d97c097196d2ce97d59f997219beb44c662a7c7a0e1c17682fb6-31776609579025.png" width="1906px" />

<div id="current-detection-status" />

#### **現在の検知状況**

「現在の検知状況」セクションには、先週より前の7日間のデータに基づく推定が表示されます。

「現在の検知状況」セクションには、次の情報が表示されます。

* 現在の検知状況のウィジェット
* クリック洪水の検知内訳のウィジェット
* メディアソース別のクリック洪水のウィジェット

**現在の検知状況のウィジェット**

* **総インストール数**：アプリのインストール総数。
* **クリック洪水の検知件数**：検知されたクリック洪水の総数。
* **総検知件数**（クリック洪水を除く）：クリック洪水を除いた不正の検知総数。
* **総検知件数**（クリック洪水を含む）：クリック洪水を含めた不正の総数。計算式：クリック洪水の検知件数＋総検知件数（クリック洪水を除く）。

**クリック洪水の検知内訳のウィジェット**

検知されたクリック洪水の内訳を、オーガニックと非オーガニックのインストール別に表示します。

**メディアソース別のクリック洪水のウィジェット**

クリック洪水と判定されたインストールを、メディアソース別に表示します。

注意：詳しく分析するには、**出力**ボタンで検知指標をCSVファイルとしてダウンロードし、手元で分析できます。

</Accordion>

<div id="new-releases" />

<Accordion title="新しい検知機能">

「新しい検知機能」では、不正検知機能の更新を適用する前に、その影響を検証できます。新しい不正検知パッケージは、デフォルトでタグ付けモードから開始されるため、影響を確認する時間を確保し、適用を判断できます。

新しい検知機能のレポートのサンプルデータをダウンロード

<div id="note-1" />

> 📘 **注意**
>
> 検知パッケージとは、1つ以上の不正検知機能の更新をまとめてリリースするものです。

<div id="how-this-works" />

#### 仕組み

* 不正検知機能の更新は、パッケージにまとめられます。
* 不正検知パッケージは、[タグ付けモード](/docs/beta-fraud-protection-studio#fpsのモード)から開始されます。
* 新しいパッケージは、最大14日間、タグ付けモードに設定できます。
* 現在のパッケージを検証し、適用できます。
* 新しいパッケージがリリースされると、通知ベルでお知らせします。

<div id="how-to-access-new-releases" />

#### 新しい検知機能の画面を開く方法

1. AppsFlyerにログインします。
2. 左側のメニューから、**設定 > Protect360 > Fraud Protection Studio**に移動します。
3. ページ上部のアプリのドロップダウンから、設定するアプリを選択します。
4. 左側のメニューから、**新しい検知機能**のカードを選択します。

<div id="new-releases-page" />

### 新しい検知機能のページ

新しい検知機能のページは、2つのセクションで構成されています。

* [今後リリースされる検知機能](/docs/beta-fraud-protection-studio#新しい検知機能の画面を開く方法)：新しい不正検知パッケージの適用前に、最大14日間、検知結果にタグ付けして影響を検証できます。
* [新しい検知機能](/docs/beta-fraud-protection-studio#現在のパッケージの検証適用方法)：現在のパッケージの検知結果を確認して評価し、すぐに適用できます。

<div id="how-to-set-the-tagged-mode-time-period-for-future-packages" />

#### 今後のパッケージのタグ付け期間の設定方法

「今後リリースされる検知機能」では、今後の検知パッケージを適用するまでに[タグ付け](/docs/beta-fraud-protection-studio#fpsのモード)を行う日数を設定できます。設定手順：

1. 新しい検知機能の画面で、ドロップダウンから、新しいパッケージの適用前にタグ付けを行う日数を選択します（デフォルトは14日、最大14日まで設定可能）。
2. **保存**をクリックします。

<Image align="center" alt="futrele.png" src="https://files.readme.io/eb832fdacd720f273a5ac26bc8e08fe1d215a99e477ff3bcfe3b91d46c41234a-31500353666321.png" width="2142px" />

<div id="note-2" />

> 📘 **注意**
>
> * この設定は、今後のパッケージにのみ適用されます。すでに適用されている検知パッケージの適用が遅れたり、設定が変更されたりすることはありません。
> * ドロップダウンで0日を選択することは、[今すぐ適用](/docs/beta-fraud-protection-studio#タグ付け中の現在のパッケージを適用するには)を選択することと同じです。このパッケージに対する[今後リリースされる検知機能](/docs/beta-fraud-protection-studio#新しい検知機能の画面を開く方法)の設定よりも優先されます。

<div id="how-to-evaluate-and-implement-current-active-packages" />

#### 現在のパッケージの検証・適用方法

「現在の新しい検知機能」セクションでは、次の内容を確認できます。

* 最後にリリースされたパッケージ
* リリース日
* ステータス：パッケージがタグ付けモードの場合、いつ適用されるか。
* この検知パッケージがデータに与える影響を示す指標
* 詳細レポートの出力
* 今後リリースされる検知機能の設定に優先して、この検知パッケージをすぐに適用

<div id="to-implement-the-current-package-if-in-tagged-status" />

#### タグ付け中の現在のパッケージを適用するには：

1. FPSタブで、**新しい検知機能のカード**を開きます。
2. 表と出力可能なレポートを使って、検知結果を確認します。
3. 適用する準備ができたら、**今すぐ適用**をクリックします。  
   <Image align="center" alt="" src="https://files.readme.io/4c11614b4f74ffa435e75cb7e79ef4f61ac750f5bc49331387b45a0ceb83e0da-31776606696081.png" />

<div id="note-3" />

> 📘 **注意**
>
> この操作は、このパッケージに対する[今後リリースされる検知機能](/docs/beta-fraud-protection-studio#新しい検知機能の画面を開く方法)の設定よりも優先されます。

</Accordion>

<div id="app-detection-evaluation" />

<Accordion title="アプリ単位の不正検知の検証">

「アプリ単位の不正検知の検証」カードでは、ビジネス上の目的に応じて検知ステータスを変更できます。ここでの設定はアプリ単位で適用され、広告主のすべてのパートナーに影響します。

「アプリ単位の不正検知の検証」カードで検知結果をタグ付けにすると、Protect360のすべての判定ロジックに影響します。ただし、お客様が設定した検証ルールによる検知には影響しません。これらの検知は、該当する検証ルールを手動で無効にしない限り、「適用」ステータスのままになります。

「アプリ単位の不正検知の検証」ページでは、[検知ステータスを確認し、適用とタグ付けを切り替える](/docs/beta-fraud-protection-studio#クリック洪水の画面を開く方法)ことができます。また、[現在の検知状況](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source)のデータも確認できます。

> 🚧 **重要**
>
> * タグ付けを選択した場合、検知結果は不正のレポートではなく、ローデータレポートに表示されます。
> * 「アプリ単位の不正検知の検証」でのタグ付けはアプリ単位で適用され、Protect360の判定ロジックによるブロックやポストアトリビューションでの不正判定の適用は行われなくなります。そのため、タグ付けにすると、非オーガニックとオーガニックのインストールが不正の影響を受けるリスクがあります。
> * 設定して有効にした検証ルールは、常に適用モードのままになります。検証ルールの適用を停止するには、検証ルールのページでそのルールを無効にしてください。

<div id="how-to-access-app-detection-evaluation" />

#### **アプリ単位の不正検知の検証の画面を開く方法**

1. AppsFlyerにログインします。
2. 左側のメニューから、**設定 > Protect360 >** **Fraud Protection Studio**に移動します。
3. ページ上部のアプリのドロップダウンから、設定するアプリを選択します。
4. 左側のメニューから、**アプリ単位の不正検知の検証**のカードを選択します。

<div id="app-detection-evaluation-page" />

#### **アプリ単位の不正検知の検証のページ**

このページは、2つのセクションで構成されています。

* [検知ステータス](/docs/beta-fraud-protection-studio#クリック洪水の画面を開く方法)：[検知](/docs/beta-fraud-protection-studio#fpsのモード)モードを選択できます。適用またはタグ付けを選択できます。 0>
* [現在の検知状況](/docs/beta-fraud-protection-studio#現在の検知状況)：先週より前の7日間のデータに基づき、インストールと関連イベントに影響する現在の検知結果を表示します。このセクションは、さらに次の項目に分かれています。
  * **Protect360の判定ロジック**   
    適用モード：
    * **適用率**：*Protect360の判定ロジックによる適用件数*を、*アプリの総アトリビューション数*で割った割合です。
  * **アプリ単位**  
    タグ付けモード：
    * **タグ付け率**：*アプリ単位の不正検知の検証によってタグ付けされた件数*を、*アプリの総アトリビューション数*で割った割合です。
  * **総インストール数**
  * **総検知件数**
  * **適用された検知**：[検知ステータス](/docs/beta-fraud-protection-studio#クリック洪水の画面を開く方法)を適用からタグ付けに変更する前の判断に役立ちます。
    * Protect360の判定ロジック：Protect360の判定ロジックによる検知件数を表示します。タグ付けに変更した場合：タグ付けの検知に切り替わると想定される件数です。
    * 検証ルール：お客様が設定して有効にした検証ルールによる検知件数を表示します。検知モードをタグ付けに変更しても、検証ルールによる検知は適用モードのままになります。
  * **タグ付けされた検知**：[検知ステータス](/docs/beta-fraud-protection-studio#クリック洪水の画面を開く方法)をタグ付けから適用に変更する前の判断に役立ちます。検知ステータスをタグ付けから適用に変更する前に、すべてのタグ付け理由を確認し、想定される結果を把握できます。
    * アプリ単位：このKPIでは、アプリ単位の不正検知の検証カードによってタグ付けされた件数を把握できます。このKPIの数値は、検知ステータスを適用に変更した場合に想定される増加分です。
    * その他のタグ付け：Fraud Protection Studioの複数の機能（カード）で、検知結果にタグ付けできます。

<div id="how-to-adjust-the-detection-status-1" />

#### **検知ステータスの変更方法**

検知ステータスで、[検知](/docs/beta-fraud-protection-studio#fpsのモード)モードを選択できます。適用またはタグ付けを選択できます（デフォルトは適用）。

1. アプリ単位の不正検知の検証のページで、[検知モード](/docs/beta-fraud-protection-studio#fpsのモード)を選択します。
2. ページ下部の「保存」ボタンをクリックします。

</Accordion>

<div id="reengagement-hijacking-detection" />

<Accordion title="リエンゲージメントハイジャックの検知">

Protect360のリエンゲージメントハイジャック検知は、標準の不正検知の対象範囲を、リエンゲージメントに特化して拡張する機能です。この機能により、不正対策をより細かく設定できます。

デフォルトでは[タグ付けモード](/docs/beta-fraud-protection-studio#fpsのモード)でリリースされるため、適用前に効果と想定される影響を検証できます。

<div id="how-this-works-1" />

#### 仕組み

* リエンゲージメントハイジャック検知は、デフォルトでタグ付けモードに設定されています。実際のアトリビューションデータに影響を与えずに、検知の効果を検証できます。
* 適用モードでは、ポストアトリビューションで検知を行います。つまり、不正なリエンゲージメントをアトリビューション後に特定し、その記録から除外します。
* 適用モードでは、検知した不正の除外後に発生するすべてのアプリ内イベントが、元のユーザー獲得（UA）の流入元に付け替えられます。有効なUAの流入元がない場合は、オーガニックとして扱われます。

<div id="how-to-access" />

#### アクセス方法

1. **AppsFlyer**にログインします。
2. 左側のメニューから、**設定 > Protect360 > Fraud Protection Studio**に移動します。
3. ページ上部のアプリのドロップダウンから、設定するアプリを選択します。
4. 左側のメニューから、**リエンゲージメントハイジャック**のカードを選択します。

<div id="re-engagement-hijacking-page" />

#### リエンゲージメントハイジャックのページ

リエンゲージメントハイジャックのページは、2つのセクションで構成されています。

* [検知ステータス](/docs/beta-fraud-protection-studio#クリック洪水の画面を開く方法)：[検知](/docs/beta-fraud-protection-studio#fpsのモード)モードを選択できます。適用またはタグ付けを選択できます。
* [現在の検知状況](/docs/beta-fraud-protection-studio#現在の検知状況)：当日を除く過去14日間のデータに基づき、リエンゲージメントハイジャック検知を適用した場合に、インストールと関連イベントにどのような影響があったかを表示します。  
  **注意：** リエンゲージメントハイジャック検知はポストアトリビューションで行うため、直近7日間のデータは未確定の場合があり、過去にさかのぼって更新されます。  

  このセクションは、さらに次の項目に分かれています。
  * リエンゲージメントハイジャック検知のウィジェット
    * 検知件数：リエンゲージメントハイジャックの判定ロジックのみで検知した件数。
    * 検知率：リエンゲージメントの検知全体に占める、リエンゲージメントハイジャックの検知の割合。
  * リエンゲージメント総検知件数のウィジェット：すべての判定ロジックによるリエンゲージメントの検知総数。
  * リエンゲージメントのアトリビューション数のウィジェット
    * アトリビューション数：対象期間のリエンゲージメントのアトリビューション件数。
    * 総アトリビューション数に占める割合：アプリのすべてのアトリビューションに占める、リエンゲージメントのアトリビューションの割合。
  * メディアソース別のリエンゲージメント検知：検知件数が多いメディアソースについて、リエンゲージメントハイジャックの検知件数を表示します。

<Image align="center" alt="" src="https://files.readme.io/bab73f39f3792401dd8795a78c64d88c26d075cdb7d693a5871bba668495f8d1-35682380370321.png" width="624px" />

</Accordion>

<div id="inapp-based-detection" />

<Accordion title="アプリ内の行動に基づく不正検知">

アプリ内の行動に基づく不正検知は、アプリ内の行動の異常を分析し、ポストアトリビューションでインストールを不正と確定的に判定します。実際のユーザーの行動を模倣しながら、インストール後のイベントの流れや発生タイミングに異常が見られるボットなど、高度な不正手法を特定します。

<div id="how-to-access-1" />

#### アクセス方法

1. AppsFlyerにログインします。
2. 左側のメニューから、**設定 > Protect360 > Fraud Protection Studio**に移動します。
3. ページ上部のアプリのドロップダウンから、設定するアプリを選択します。
4. 左側のメニューから、**アプリ内の行動に基づく不正検知**のカードを選択します。

<div id="the-in-app-based-detection-page" />

#### アプリ内の行動に基づく不正検知のページ

このページは、2つのセクションで構成されています。

* [検知ステータス](/docs/beta-fraud-protection-studio#クリック洪水の画面を開く方法)：[検知](/docs/beta-fraud-protection-studio#fpsのモード)モードを選択できます。適用またはタグ付けを選択できます。
* [現在の検知状況](/docs/beta-fraud-protection-studio#現在の検知状況)：当日を除く過去14日間のデータに基づき、アプリ内の行動に基づく不正検知を適用した場合に、インストールにどのような影響があったかを表示します。   

  注意：アプリ内の行動に基づく不正検知はポストアトリビューションで行うため、直近7日間のデータは未確定の場合があり、過去にさかのぼって更新されます。

このセクションは、さらに次の項目に分かれています。

* **アプリ内の行動に基づく判定ロジックによる新たな検知**
  * 検知件数：アプリ内の行動に基づく判定ロジックで検知したインストール数。
  * 追加検知率：アプリ内の行動に基づく不正検知件数を、アプリの総インストール数で割った割合。
* **偽と判定されたインストール**
  * 検知件数：偽と判定されたデータの総数。
  * 検知率：偽と判定されたデータの件数を、アプリの総インストール数で割った割合。
* **総インストール数**

* **メディアソース別のアプリ内の行動に基づく不正検知**：上位のメディアソース別にインストール数を表示します。

<Image align="center" alt="" src="https://files.readme.io/63eedf0c4aa28471d4044a8896e349612fb9d8e9f06aed6b1efbaa825330d150-36947287654033.png" width="624px" />

</Accordion>

<div id="h_01K0ASM01ADVSECMOD01" />

<Accordion title="Advanced Security Moduleのデータ">

Androidアプリで、Advanced Security Module（高度なセキュリティ機能）が検知した、インストール候補データへのサイバー攻撃をリアルタイムで確認できます。これにより、検証済みのトラフィックのみがアプリに届くようにすることができます。

<div id="how-to-access-2" />

#### アクセス方法

1. AppsFlyerにログインします。
2. 左側のメニューから、**設定 > Protect360 > Fraud Protection Studio**に移動します。
3. ページ上部のアプリのドロップダウンから、設定するアプリを選択します。
4. 左側のメニューから、**Advanced Security Module**のカードを選択します。

<div id="the-advanced-security-module-page" />

#### Advanced Security Moduleのページ

Advanced Security Moduleのページには、次の情報が表示されます。

* **上位のアプリバージョン**：インストール数の多い上位5つのアプリバージョンを表示し、偽装されたトラフィックが集中しているバージョンを把握できます。

検知結果は、次のいずれかで表示されます。

* **ブロック**：アトリビューション前に、リアルタイムでブロックされたトラフィック。
* **タグ付け**：不審なトラフィックとして目印が付けられても、アトリビューションは維持されるため、適用前に確認できます。これがデフォルトの検知モードです。
* **タグなし**：この機能で目印が付けられなかったインストール候補データ。

<div id="note-4" />

> 📘 **注意**
>
> 設定方法、要件、レポートの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/beta-advanced-security-protect360-module">［ベータ版］Protect360のAdvanced Security Module</Anchor>をご覧ください。

</Accordion>

<div id="faqs" />

## よくある質問

<div id="can-i-tag-detection-for-specific-partnersmedia-sources" />

<Accordion title="パートナーやメディアソース別に、検知結果のタグ付けを設定できますか？">

検知の種類によって異なります。例えば、判定の偏りを防ぐため、ハイジャックの検知ではパートナー単位のタグ付けを利用できません。

<div id="what-happens-when-the-tagging-period-ends" />

<Accordion title="タグ付け期間が終了すると、どうなりますか？">

検証期間が終了すると、タグ付けモードは自動的に適用モードに切り替わります。

</Accordion>

<div id="where-can-i-see-tagged-installs" />

<Accordion title="タグ付けされたインストールはどこで確認できますか？">

**ローデータレポート**の次のレポートで、タグ付けされたデータを確認できます。

* タグ付けされたインストール
  * リアルタイム
* タグ付けされたインストール
  * ポストアトリビューション
* タグ付けされたアプリ内イベント
  * リアルタイム
* タグ付けされたアプリ内イベント
* ポストアトリビューション

**Data Locker**でも、次のタグ付けレポートを利用できます。

* タグ付けされたインストール
  * リアルタイム
* タグ付けされたアプリ内イベント
  * リアルタイム

</Accordion>

<div id="can-tagged-detection-be-adjusted-for-appspecific-settings" />

<Accordion title="タグ付けの設定は、アプリごとに変更できますか？">

はい。クリック洪水のタグ付けは、アプリ単位で設定できます。

</Accordion>

<div id="can-i-see-tagged-inapp-events" />

<Accordion title="タグ付けされたアプリ内イベントも確認できますか？">

はい。タグ付けされたインストールと同じAppsFlyer IDに紐づくアプリ内イベントも、タグ付けされます。

</Accordion>

<div id="who-can-change-set-up-or-view-fps" />

<Accordion title="FPSの変更、設定、閲覧を行えるのは誰ですか？">

FPSの設定を変更できるのは、管理者のみです。 FPSの閲覧権限については、<Anchor target="_blank" href="/marketers/ja/docs/manage-data-access-permissions">権限の説明ページ</Anchor>をご覧ください。

</Accordion>

<div id="are-tagged-installs-credited-back-to-the-consumption-plan" />

<Accordion title="タグ付けされたインストールは、従量課金プランの計測件数から差し引かれますか？">

いいえ。タグ付けされた検知結果は、従量課金プランの計測件数から差し引かれません。

</Accordion>

<div id="are-tagged-installs-considered-as-fraud" />

<Accordion title="タグ付けされたインストールは、不正として扱われますか？">

タグ付けされたインストールは、Protect360で検知されたものです。ただし、お客様の設定に基づいてタグ付けされています。そのため、概要ダッシュボードとProtect360ダッシュボードの両方で、アトリビューションされたデータの指標に含まれます。

</Accordion>

<div id="can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />

<Accordion title="クリック洪水のタグ付けのみでタグ付けされたインストールの件数を確認できますか？">

はい。このデータは、レポート出力ページの新しい専用レポートと、Protect360ダッシュボードで確認できます。

</Accordion>

</Accordion>

<div data-zendesk-anchors="why-flexible-protection=fraud-protection-studio%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01JEQR86DC1CK03DKCZH760N4M=fraud-protection-studio%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01JK3BGVNMYFQYQGRPJBVN2A7Z=%E9%87%8D%E8%A6%81 how-flexible-protection-works=fraud-protection-studio%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF 01JEQR86DEG7RTRNYFP02WHJGQ=fraud-protection-studio%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF 01JETRN5S347ZXV8CGZJDHQH56=key-concepts fps-modes=fps%E3%81%AE%E3%83%A2%E3%83%BC%E3%83%89 h_01JEWZEBBA9VAPCKR87NJ5AK3C=fps%E3%81%AE%E3%83%A2%E3%83%BC%E3%83%89 01JEWZQ7PBD6W4J15W0HE2Q4MJ=%E6%B3%A8%E6%84%8F where-is-tagged-detection-reflected=%E3%82%BF%E3%82%B0%E4%BB%98%E3%81%91%E3%81%97%E3%81%9F%E6%A4%9C%E7%9F%A5%E7%B5%90%E6%9E%9C%E3%81%AF%E3%81%A9%E3%81%93%E3%81%AB%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%81%BE%E3%81%99%E3%81%8B 01JEWZT9N34FZ9SE8H7EGCMPBZ=%E3%82%BF%E3%82%B0%E4%BB%98%E3%81%91%E3%81%97%E3%81%9F%E6%A4%9C%E7%9F%A5%E7%B5%90%E6%9E%9C%E3%81%AF%E3%81%A9%E3%81%93%E3%81%AB%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%81%BE%E3%81%99%E3%81%8B how-to-use-flexible-protection=fraud-protection-studio%E3%81%AE%E5%88%A9%E7%94%A8%E6%96%B9%E6%B3%95 01JEQR86ECSYTM7RN3YPYRSAGE=fraud-protection-studio%E3%81%AE%E5%88%A9%E7%94%A8%E6%96%B9%E6%B3%95 01JETF4NJX02APNK1TDV91JQAB=general 01JETF4NJZ7P5M5RTCEFFD0WEP=click-flood-detection 01JFSPDB630RE494JG1W618TKR=%E9%87%8D%E8%A6%81-1 adjust-detection-status=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E6%B4%AA%E6%B0%B4%E3%81%AE%E7%94%BB%E9%9D%A2%E3%82%92%E9%96%8B%E3%81%8F%E6%96%B9%E6%B3%95 01JEQVJS6YTQD299X39Q8E3506=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E6%B4%AA%E6%B0%B4%E3%81%AE%E7%94%BB%E9%9D%A2%E3%82%92%E9%96%8B%E3%81%8F%E6%96%B9%E6%B3%95 click-flood-page=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E6%B4%AA%E6%B0%B4%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 h_01JJKE1ZKE5WDRSPKS8JE9MRRG=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E6%B4%AA%E6%B0%B4%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 detection-status=%E6%A4%9C%E7%9F%A5%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9 h_01JZQ81MW4HMY9B782Y7PWVE8Y=%E6%A4%9C%E7%9F%A5%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9 h_01JJKE1ZKEJ4QM2HTT37FERA92=%E6%A4%9C%E7%9F%A5%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%81%AE%E5%A4%89%E6%9B%B4%E6%96%B9%E6%B3%95 current-detection-status=%E7%8F%BE%E5%9C%A8%E3%81%AE%E6%A4%9C%E7%9F%A5%E7%8A%B6%E6%B3%81 01JEQVZCNSTXY4V8H2Y1QP224C=%E7%8F%BE%E5%9C%A8%E3%81%AE%E6%A4%9C%E7%9F%A5%E7%8A%B6%E6%B3%81 01JETF4NK2KT4MY2G6WMWGMVKB=new-releases 01JFQPRZ5NGEAFBWB1FS0D6DCT=%E6%B3%A8%E6%84%8F-1 how-this-works=%E4%BB%95%E7%B5%84%E3%81%BF h_01JEXC0ABSTCEA939DGQ5SDJBJ=%E4%BB%95%E7%B5%84%E3%81%BF how-to-set-the-tagged-mode-time-period-for-future-packages=%E6%96%B0%E3%81%97%E3%81%84%E6%A4%9C%E7%9F%A5%E6%A9%9F%E8%83%BD%E3%81%AE%E7%94%BB%E9%9D%A2%E3%82%92%E9%96%8B%E3%81%8F%E6%96%B9%E6%B3%95 h_01JEXC2HAR2S6BWK28N8W3HHSZ=%E6%96%B0%E3%81%97%E3%81%84%E6%A4%9C%E7%9F%A5%E6%A9%9F%E8%83%BD%E3%81%AE%E7%94%BB%E9%9D%A2%E3%82%92%E9%96%8B%E3%81%8F%E6%96%B9%E6%B3%95 new-releases-page=%E6%96%B0%E3%81%97%E3%81%84%E6%A4%9C%E7%9F%A5%E6%A9%9F%E8%83%BD%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 h_01JJKE1ZKE0K1W2VE3KHQ639B1=%E6%96%B0%E3%81%97%E3%81%84%E6%A4%9C%E7%9F%A5%E6%A9%9F%E8%83%BD%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 h_01JJKE1ZKE13D7EC6BMN3JJNGW=%E4%BB%8A%E5%BE%8C%E3%81%AE%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%81%AE%E3%82%BF%E3%82%B0%E4%BB%98%E3%81%91%E6%9C%9F%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 01JF50BVZ75ZSXTJEKAV4HVSTZ=%E6%B3%A8%E6%84%8F-2 how-to-evaluate-and-implement-current-active-packages=%E7%8F%BE%E5%9C%A8%E3%81%AE%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%81%AE%E6%A4%9C%E8%A8%BC%E9%81%A9%E7%94%A8%E6%96%B9%E6%B3%95 h_01JEXC3DESR10WVV34ED30B7BH=%E7%8F%BE%E5%9C%A8%E3%81%AE%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%81%AE%E6%A4%9C%E8%A8%BC%E9%81%A9%E7%94%A8%E6%96%B9%E6%B3%95 to-implement-the-current-package-if-in-tagged-status=%E3%82%BF%E3%82%B0%E4%BB%98%E3%81%91%E4%B8%AD%E3%81%AE%E7%8F%BE%E5%9C%A8%E3%81%AE%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%82%92%E9%81%A9%E7%94%A8%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01JF505FK4NP88WYXP8PVQRYDS=%E3%82%BF%E3%82%B0%E4%BB%98%E3%81%91%E4%B8%AD%E3%81%AE%E7%8F%BE%E5%9C%A8%E3%81%AE%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%E3%82%92%E9%81%A9%E7%94%A8%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF 01JF50BVZ9QPT5W41P8KQAREKV=%E6%B3%A8%E6%84%8F-3 h_01JQXFMBGXWKXMFFAPHN5V66Q7=app-detection-evaluation h_01JQXPVD4MXPYQQZXNTM2H9BNA=%E9%87%8D%E8%A6%81-2 how-to-access-app-detection-evaluation=%E3%82%A2%E3%83%97%E3%83%AA%E5%8D%98%E4%BD%8D%E3%81%AE%E4%B8%8D%E6%AD%A3%E6%A4%9C%E7%9F%A5%E3%81%AE%E6%A4%9C%E8%A8%BC%E3%81%AE%E7%94%BB%E9%9D%A2%E3%82%92%E9%96%8B%E3%81%8F%E6%96%B9%E6%B3%95 h_01JQXG4GJ2DB8HM26K3E1WA3A1=%E3%82%A2%E3%83%97%E3%83%AA%E5%8D%98%E4%BD%8D%E3%81%AE%E4%B8%8D%E6%AD%A3%E6%A4%9C%E7%9F%A5%E3%81%AE%E6%A4%9C%E8%A8%BC%E3%81%AE%E7%94%BB%E9%9D%A2%E3%82%92%E9%96%8B%E3%81%8F%E6%96%B9%E6%B3%95 app-detection-evaluation-page=%E3%82%A2%E3%83%97%E3%83%AA%E5%8D%98%E4%BD%8D%E3%81%AE%E4%B8%8D%E6%AD%A3%E6%A4%9C%E7%9F%A5%E3%81%AE%E6%A4%9C%E8%A8%BC%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 h_01JQXG6QDSTAPCJDMQVQMXS86W=%E3%82%A2%E3%83%97%E3%83%AA%E5%8D%98%E4%BD%8D%E3%81%AE%E4%B8%8D%E6%AD%A3%E6%A4%9C%E7%9F%A5%E3%81%AE%E6%A4%9C%E8%A8%BC%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 how-to-adjust-the-detection-status=%E6%A4%9C%E7%9F%A5%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%81%AE%E5%A4%89%E6%9B%B4%E6%96%B9%E6%B3%95-1 h_01JQXG6QEAM0Y67G504JV2SA5R=%E6%A4%9C%E7%9F%A5%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%81%AE%E5%A4%89%E6%9B%B4%E6%96%B9%E6%B3%95-1 h_01JWAVMSW1K6R4FJ8J9AYYNHQW=reengagement-hijacking-detection how-this-works::a0e9054=%E4%BB%95%E7%B5%84%E3%81%BF-1 h_01JWAVPAVKM9RSXFMZN9CM36ER=%E4%BB%95%E7%B5%84%E3%81%BF-1 how-to-access=%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95 h_01JWAVPAVK7ZT471AQAFKAS64K=%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95 reengagement-hijacking-page=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 h_01JWAVPAVKKB4JSP41P967EESS=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 h_01JZMAX35E1KT04VTKAFB8FAF3=inapp-based-detection how-to-access::db81debe=%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-1 h_01JZMAZET0JXYEDGKE0B797TQ7=%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-1 the-inapp-based-detection-page=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%81%AE%E8%A1%8C%E5%8B%95%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E4%B8%8D%E6%AD%A3%E6%A4%9C%E7%9F%A5%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 h_01JZMB0NET3Y8CFVZ1WP0WDPMJ=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%81%AE%E8%A1%8C%E5%8B%95%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E4%B8%8D%E6%AD%A3%E6%A4%9C%E7%9F%A5%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 advanced-security-module=h_01K0ASM01ADVSECMOD01 h_01K0ASM02ADVSECMOD02=%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95-2 h_01K0ASM07ADVSECMOD07=advanced-security-module%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 the-advanced-security-module-page=advanced-security-module%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8 h_01K0ASM13ADVSECMOD13=%E6%B3%A8%E6%84%8F-4 faqs=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01JEQR86EMZQFNSZ5NWZ08F5YQ=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01JETRQMEJHZMHAKHHX5SZ028N=can-i-tag-detection-for-specific-partnersmedia-sources 01JETRQMEKJ27S5GGVR73H6WZB=what-happens-when-the-tagging-period-ends 01JETRQMEMKV8K7EQMS1BJB989=where-can-i-see-tagged-installs 01JETRQMEM6BMEXGYJM6WVE313=can-tagged-detection-be-adjusted-for-appspecific-settings 01JF79M50ZZ7HP0XCW1F4YJH7R=can-i-see-tagged-inapp-events 01JF79M50ZTMM1Y2YW8ARTYVTN=who-can-change-set-up-or-view-fps 01JF79M510HGEVC1WTWXAHSAQH=are-tagged-installs-credited-back-to-the-consumption-plan 01JF79M510B5WW067Q4T4FDVSC=are-tagged-installs-considered-as-fraud 01JF79M5105Z9AH95K6VVANANM=can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />
