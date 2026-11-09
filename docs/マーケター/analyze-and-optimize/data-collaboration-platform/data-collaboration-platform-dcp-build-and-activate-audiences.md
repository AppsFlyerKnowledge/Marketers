---
title: データコラボレーションプラットフォーム（DCP） - オーディエンスの構築とアクティブ化
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-04-25T12:55:13Z'
  edited_at: '2026-10-14T09:26:14Z'
  id: 24522739719057
  locale: ja
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ja/articles/24522739719057
---
> **概要：** 共有データを使用してDCPコラボレーションで値の高いオーディエンス構築し、メディアパートナーサイトまたはクラウドサービスでオーディエンスを活性化することで、キャンペーンインパクト最大化できます。

<div id="about-dcp-audiences" />

## DCP オーディエンスについて

データセットを組み合わせて充実したオーディエンスセグメントを作成し、特定の消費者グループにリーチすることで、DCPコラボレーションでオーディエンスを構築します。オーディエンスは、ソース所有者が定義した権限に基づいて、1人の共同編集者のデータに基づいて作成することも、両方の共同編集者のデータセットにわたる交差するユーザーに基づいて作成することもできます。オーディエンスを構築したら、メディアパートナーに送信してアクティベーションを行ったり、クラウドストレージバケットに送信したりできます。

<div id="build-an-audience" />

## 視聴者を増やす

オーディエンスの構築には、次のツールが利用できます。

* [ビジュアルオーディエンスビルダー](/docs/data-collaboration-platform-dcp-build-and-activate-audiences#visual-audience-builder)-ビジュアルオーディエンスビルダーはユーザーフレンドリーなツールで、技術に詳しくないユーザーでも SQL スキルがなくてもオーディエンスセグメントを作成できます。グラフィカルインターフェイスを使用して、高度なオーディエンスセグメンテーションが可能です。
* [SQL オーディエンスビルダー](#sql-audience-builder) (SQL の専門知識が必要)-制限なくデータをクエリできる SQL クエリ。SQLの専門知識が必要です。

<div id="key-features" />

#### 主な機能

| ビジュアルオーディエンスビルダー | SQLオーディエンスビルダー |
| --- | --- |
| <span id="supports-using-one-source-from-each-collaborating-party"></span>各コラボレーターからの1つのソースまたは1人のコラボレーターからの複数のソースの使用をサポート | 双方の複数のソースをサポート |
| <span id="supports-using-overlapping-data-only"></span>各コラボレーターの1つのソースについて、重複データのみの使用をサポート | すべてのデータのクエリをサポート |
| <span id="supports-retrieving-values-within-the-selected-attribute-range"></span>選択した属性範囲内の値の取得をサポートします。 | 属性範囲を超えた値のクエリをサポート |

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">共同作業者のデータセット間の一致率を最大化するためにソースデータを準備する方法を学びましょう</Anchor>。

<div id="visual-audience-builder" />

<Accordion title="ビジュアルオーディエンスビルダー">

**Visual Audience Builder を使用してオーディエンスを構築する手順は、次のとおりです。**

<div id="note" />

> 📘 **注意**
>
> オーディエンスを作成するには、オーディエンス<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-sharing-permissions">作成する権限があることを確認してください</Anchor>。

1. AppsFlyer管理画面 左メニュー **連携** > **データクリーンルーム**へ移動します。

   <Image align="center" alt="「データクリーン Room.png」をクリックします" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="245px" />
2. **コラボレーション**タブから、関連するコラボレーションをクリックします。

   <Image align="center" alt="関連する collaboration.png をクリックします。" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. コラボレーションで、[**New audience]** > [**Visual audience builder**] をクリックします。  
   **注：オーディエンスを構築する前に、少なくとも1つのソースを関連付ける必要**があります。

   <Image align="center" alt="New Aud Visual audience builder.png" src="https://files.readme.io/31458edec870140b9c4eb0805aef0175ca5f3c698b6faa380f979398046eb58b-32455804445201.png" width="355px" />
4. 次の**オーディエンスビルダー**のウォークスルー手順に進みます。

<div id="step-1-details-and-sources" />

#### ステップ1：詳細とソース

オーディエンスは、単一のコラボレーターからのデータを使用して作成するか、各コラボレーターから1つのソースをマージして結合されたデータソースを有効にすることで作成できます。

<Image align="center" alt="New aud.png" src="https://files.readme.io/c110dcda7524ddcb4ce255ac5eb1f33ffec61103219e35f54f1d5687135cf915-35683488156433.png" />

1. オーディエンス名オーディエンス・コラボレーション名
2. ソースを選択ドロップダウンリストからソースを選択します。
   * 一方的なコラボレーションの場合：独自のソースまたはコラボレーターのソースのいずれかを選択します。
   * 双方向コラボレーションの場合：独自のソースとコラボレーターのソースのいずれかを選択します。

     <div id="note-1" />

     > 📘 **注意**
     >
     > * 両方のソースが交差するユーザーを共有している場合、右側のペインにはソースの交差の概要が表示され、両方のソースに共通するユーザーの推定数が表示されます。
     > * トランザクションデータソースは、ソースドロップダウンでは使用できません。以下の「[トランザクションデータソースの操作](#トランザクションデータソースでの作業)」を参照してください。

3. **データの組み合わせ方法：** オーディエンスを構築したいデータを選択してください：
   * **交差するユーザー** - 両方のソース （自分とコラボレーター） に表示されるユーザーのみが含まれます。
   * **Users from my source only** - ソースに固有のユーザーのみが含まれます。コラボレーターのソースに表示されているすべてのユーザーを除外します。
   * **Users from the collaborator's source only** (コラボレーターのソースからのユーザーのみ) - コラボレーターに紐づくソースに固有のユーザーのみが含まれます。ソースに含まれるすべてのユーザーを除外します。  

     **注：** 3つのオプションはすべて、ソース権限で「**Build Audiences**」>「**Can use all data** - **Universal dataset**」が有効になっている場合にのみ利用できます。<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#共有権限">ソース権限の詳細</Anchor>  

     <Image align="center" alt="arrow.png で有効になっているすべてのデータ権限を使用できます" src="https://files.readme.io/6f386c2383c75bf42da6cfdc4d662be0fdf7d623588480825e4a70f453d1f94c-46848627186065.png" width="1556px" />
4. **次へ**をクリックします。

<div id="step-2-define-the-audience" />

#### ステップ2：オーディエンスを定義

データソースを選択したら、このステップではオーディエンスに含める属性と値を選択します。

1. **［Select］ 列**をクリックして、ソースからの属性リストを表示します。
2. 属性、演算子、属性値を選択します。
   * **数値と日付**の属性は、次の演算子でフィルタできます。  
     Equals, Not equals, Greater than, Lower than, Greater than or equals,  
     Lower than or equals, Between, Last "X" days (現在の日を含めることもできます)
   * **テキスト属性**は、次の演算子でフィルタできます。  
     等しい、または等しくない

     <div id="note-2" />

     > 📘 **注意**
     >
     > * 属性が選択されていない場合、デフォルトですべての属性が含まれます。
     > * 属性値を選択すると、オーディエンスサイズが調整されます。

3. [オプション] [**+ 条件**] をクリックして別の属性を追加し、その値を選択します。  
   必要に応じて繰り返します。
4. **次へ**をクリックします。
5. 次のステップに進みます [オーディエンスを送信](#オーディエンスを送信してアクティベーションを行う)してオーディエンスを有効にします 。

<Image align="center" alt="Definetheaudience.png" src="https://files.readme.io/70c93dbb737563f7b62e8a8ba111e7d5e7e1a0fa2697a2be69d5caa579bbf3dc-34588602544017.png" width="75.57%" />

<div id="summary-right-side-preview-pane" />

#### 概要 (右側のプレビューペイン)

概要パネルは、対象者を定義するとリアルタイム更新されます。選択したデータソースで使用可能な識別子とその重複に基づいて、**アクティブ化できるユニークユーザーの推定範囲が表示されます**。  
オーディエンスのアクティベーションは、メディアパートナーが実行時に使用する識別子によって異なるため、オーディエンスのサイズは単一の数値ではなく範囲として表示されます。

**ソース行とユニークユーザー**

ソースデータには、ユーザーごとに複数の行が含まれる場合があります。  
たとえば、次のような理由で同じ人が複数回現れることがあります。

* 複数のイベント
* 複数のデバイス
* 複数の識別子 (CUID、電子メール、電話など)

  DCPのオーディエンスサイズの見積もりは、未加工の行ではなく、常にユニークユーザー数に基づいています。

**識別子と推定ユーザー範囲**

メディアパートナーごとに異なる識別子サポートされており、DCP はアクティベーション時にどの識別子が使用されるかを予測できないため、1 つのソースに同じユーザーの複数の識別子 (たとえば、CUID とハッシュされたメールの両方) が含まれる場合があります。

DCP では、オーディエンスサイズを最小から最大までの範囲として推定しています。

* **最小値:** 識別子間の重複が可能な限り強いものと仮定します
* **最大値:** 識別子は異なるユーザーを表していると仮定します

実際にアクティブ化されたオーディエンスは、パートナーの能力と識別子の照合にもよりますが、この範囲内のどこかに収まるでしょう。

**概要パネルの理解:**

**合計ユーザー**  
重複が適用される前に、選択したすべてのソースで利用可能なユニークユーザーの最大数が表示されます。

**ソースコントリビューション**  
各ソースが投稿したユニークユーザーの数と、他のソースとの重複箇所が表示されます。

**推定データプール:**  
ソース間で共有されているユニークユーザーの推定数を表し、次のように表します。

* ユーザー範囲
* ソースコントリビューションのパーセンテージ

このプールによって、同時にアクティベートできる最大オーディエンスが決まります。

**推定オーディエンスサイズ**  
推定オーディエンスサイズは、オーディエンスの定義と一致し、アクティベートできるユニークユーザーの予想範囲を反映しています。範囲:

* 識別子の重複に関するアカウント
* ソース間の重複の勘定 (該当する場合)
* フィルター、ソース、またはルールの変更に応じて動的に調整

<Image align="center" alt="image (20).png" src="https://files.readme.io/0ba94f26978e2d3f984bd0c8c2fa8e60159420f5765cff358cdd80d6f05e271c-43432443225489.png" />

<div id="note-3" />

> 📘 **注意**
>
> メディアパートナーによってマッチ率が異なるため、メディアパートナー側のアクティブオーディエンスは、送信するオーディエンスよりも少ない場合があります。

<div id="working-with-transactional-data-sources" />

#### トランザクションデータソースでの作業

ユーザーごとに複数のレコードを含む購入、注文、イベントなどのトランザクションデータソースは、ビジュアルオーディエンスビルダーで直接使用することはできません。これは、集計を行わずにトランザクションデータを使用すると、オーディエンス数が不正確になり、オーディエンスサイズが膨張し、予期しないセグメンテーション結果が生じる可能性があるためです。

オーディエンス作成にトランザクションデータを使用するには、まずデータビューツールを使用してデータをユーザーレベルデータセットに集約する必要があります。**集計するには:**

1. <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-customized-data-views">**データビューツールを開き**</Anchor>、トランザクションソースデータビューを作成します。
2. 集計関数 (Count、Sum、Average など) を適用して、ユーザーごとに 1 行を生成します。
3. 集約されたデータビューをコラボレーションに関連付けます。
4. 集計されたデータビューをオーディエンスビルダーソースとして使用します。

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-customized-data-views#transactional-data-sources">データビューを使用してトランザクションデータを集計する方法を学ぶ</Anchor>

</Accordion>

<div id="sql-audience-builder" />

<Accordion title="SQLオーディエンスビルダー">

**SQL オーディエンスビルダーを使用してオーディエンスを構築するには、以下の手順に従います。**

<div id="note-4" />

> 📘 **注意**
>
> オーディエンスを作成するための<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">オーディエンス作成</Anchor>権限があることを確認してください。

1. AppsFlyer管理画面 左メニュー **連携** > **データクリーンルーム**へ移動します。

   <Image align="center" alt="「データクリーン Room.png」をクリックします" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="40.57%" />
2. **コラボレーション**タブから、関連するコラボレーションをクリックします。

   <Image align="center" alt="関連する collaboration.png をクリックします。" src="https://files.readme.io/6a23e891cad8929b084759a83773943905fda8d6d0ef262ac6d8f0c3475eb062-32455804434449.png" width="947px" />
3. コラボレーションで、[**New audience]** > [**SQL audience builder**] をクリックします。

   <Image align="center" alt="New Aud SQL audience builder.png" src="https://files.readme.io/e955bdd8a90a92dff5bb695cd64621860e79413f42ac8a8efaefc3cb80d061a5-32455799682193.png" width="355px" />
4. **オーディエンスビルダー**のウォークスルー手順に進みます。

<div id="set-details" />

#### 詳細の設定

オーディエンスに名前を付け、**[Next**]をクリックします。

<div id="build-query" />

#### クエリを作成

1. エディタをクリックして開きます [SQL ビルダー](#sql-audience-builder)。
2. SQLクエリを作成してオーディエンスを構築します。を利用できます 結合ソースまたは片側ソース。

<div id="note-5" />

> 📘 **注意**
>
> クエリにトランザクションソースが含まれている場合、 COUNT、SUM、AVG などの集計ロジックを含める必要があります。 MIN または MAX (データを 1 行あたり 1 行に減らす) オーディエンスの作成に使用できるようになる前のユーザー。クエリ 集計なしでトランザクションデータを使用するものはそうではありません サポートされています。参照： [サポートされているクエリパターンとサポートされていないクエリパターン](#sql-クエリのトランザクションデータ) を参照してください。

3. 「**テスト**」をクリックして、クエリの結果を確認します。 （オーディエンスサンプル）はクエリステートメントの下に表示されます。
4. [**続行**] をクリックし、[**次へ**] をクリックします to **オーディエンスビルダーの次のステップに進む** チュートリアル、**または下書きとして保存して履歴書** 後で
5. 続けて [聴衆を送ってください](#オーディエンスを送信してアクティベーションを行う)。

<div id="the-sql-audience-builder" />

#### SQLオーディエンスビルダー

SQL ビルダーを使用してデータをクエリし、オーディエンスを作成します。次の表は、ビルダーのセクションの概要を示しています。

| セクション | 説明 |
| --- | --- |
| <span id="left-pane"></span>左のセクション： | オーディエンスの作成に利用できるすべてのソースが表示されます。これには、あなたのソースとあなたと共有されたものが含まれる場合があります。<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#grant-permissions-for-your-source">**オーディエンスの構築**</Anchor>権限を持つソースのみを表示できます。<br /><br />ソースを選択すると、対応する列が表示されるように展開されます。 |
| <span id="topmiddle-section-text-editor"></span>上部中央セクション（クエリエディタ） | SQL ステートメントを記述するためのクエリエディタ。 |
| <span id="bottommiddle-section-context-panel"></span>下部中央セクション（コンテキスト パネル） | このセクションでは、左側のペインから選択したオブジェクトに基づいて、詳細が動的に表示されます。<ul><li>**ソースの選択時：** 列名 ("Field name") とそれに対応する型 ("Type") を表示します。</li><li>**列が選択されている場合：** 列の値（"Distinct values"）と各値（"Count"）の行数を表示します。</li><li>**次のクエリ実行：** クエリ結果のサンプルを表示します。<br />**注：** プライバシー保護のため、結果表には電子メールや ID などのハッシュ値は表示されません。これらの値は「制限付き」として表示されます。</li></ul> |
| <span id="right-pane"></span>右のセクション： | このセクションでは、選択したオブジェクトに基づいて詳細が動的に表示されます。<ul><li>**ソースの選択時：** ソースに付与された権限を表示します。</li><li>**SQLクエリの書き込み中：**<ul><li>ページの右上にクエリの有効性ステータスを表示します。これには、次のいずれかのステータスが含まれます。</li><li>**実行する準備はできましたか：** 問題は見つかりませんでした。クエリをテストして、次のステップに進むことができます。</li><li>**構文エラー：** 構文エラーと、その解決に関するガイダンスが検出されました。</li><li>**権限エラー:** 必要な権限がないことを示し、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#view-permissions-for-collaborator%E2%80%99s-source">ソースに提供されているアクセス</Anchor>の詳細を示すツールチップが表示されます。</li><li>ページの右上に [**テスト**] ボタンを表示します。クエリの作成が完了したら、クエリテストして、対象読者の正確さを確認する必要があります。<br />**［Test］** をクリックしてクエリをテストし、結果を検証します。</li></ul></li></ul> |

<div id="transactional-data-in-sql-queries" />

#### SQL クエリのトランザクションデータ

SQL ビルダーでトランザクションデータソースを操作する場合、次のクエリパターンが適用されます。

**サポート対象のクエリパターン**

| パターン | 説明 |
| --- | --- |
| <span id="single-transactional-source-with-aggregation"></span>集約機能を備えた単一のトランザクションソース | トランザクションソースをユーザーごとに 1 行に集約するクエリ。たとえば、購入レコードを集約して、ユーザーごとの合計購入数を算出します。 |
| <span id="transactional-source-joined-to-a-profileuserlevel-source"></span>トランザクションソースをプロファイル/ユーザーレベルソースに結合 | ジョイン前にトランザクション側が集約されている場合に許可されます。たとえば、ユーザーごとに購入履歴を集約し、その結果顧客プロファイルデータセットに結合します。 |
| <span id="aggregated-transactional-output-in-downstream-joins"></span>ダウンストリーム結合の集約されたトランザクション出力 | ユーザーレベルに集約された出力は、その後の結合やオーディエンス構築ワークフローで使用でき、プロファイルレベルのデータセットと同様に扱われます。 |

**サポートされていないクエリパターン**

| パターン | 説明 |
| --- | --- |
| <span id="transactional-source-joined-directly-to-another-transactional-source"></span>トランザクションソースを別のトランザクションソースに直接結合 | 2 つのトランザクションデータセット間の直接結合 (購入と注文の結合など) はサポートされていません。これらの結合は、レコードが増えたり、オーディエンス結果が不正確になったり、トランザクションが拡大したりする可能性があるため、実行前にブロックされます。 |
| <span id="nonaggregated-transactional-query"></span>非集計トランザクションクエリ | トランザクションレコードを集約せずに直接使用するクエリはサポートされていません。 |

</Accordion>

<div id="send-an-audience-for-activation" />

## オーディエンスを送信してアクティベーションを行う

オーディエンスを構築したら、結果を出すことができる場所でオーディエンスをアクティブにします。<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#共有権限">キャンペーンターゲティング用のメディアパートナーやダウンストリーム用のクラウドストレージバケットなどの宛先を選択すると、DCPは最新のソースデータと権限に基づいてオーディエンスを毎日更新して配信します。</Anchor>

* [**オーディエンスをメディアパートナーにつなげる**](#connect-an-audience-to-media-partners)-メディアパートナーのプラットフォームには、Meta 広告、Google 広告などがあります。有料キャンペーン、リマーケティング、類似キャンペーンを実施する際に、オーディエンスをメディアパートナーに接続します。
* [**オーディエンスをクラウドストレージにエクスポート**](#export-to-cloud-storage)-ビジネスインテリジェンスモデル、CDP、または内部エンリッチメントパイプラインでファイルが必要なときに、オーディエンスをクラウドストレージに接続します。

<div id="note-6" />

> 📘 **注意**
>
> * オーディエンスは、ユーザー ID のリストとしてアクティベーションに送信されます。このリストは継続的に更新され、毎日選択した宛先に送信されます。
> * ソースデータが更新されるたびに、オーディエンスは自動的に更新され、選択した宛先に送信されます。

<div id="connect-an-audience-to-media-partners" />

<Accordion title="オーディエンスをメディアパートナーに連携">

Meta 広告や <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10010286?hl=en">Google 広告など</Anchor>、お好みのメディアパートナープラットフォームにオーディエンスを直接送信してアクティベーションを行います。システムは、パートナーが必要に応じて自動的にハッシュ化されたユーザーIDのCSVを転送します。

<div id="note-7" />

> 📘 **注意**
>
> * コラボレーターのソースデータを使用してオーディエンスを構築する場合、表示されるアクティベーションオプションは、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-sharing-permissions">コラボレーターが付与した権限によって異なります</Anchor>。アクティベーション中は、そのソースに対して許可されたアクティベーションパートナーのみを使用できます。
> * コラボレーターがオーディエンス公開またはエクスポートする権限を付与していない場合でも、アクティベーションリクエストを送信できます。この場合、アクティベーションリクエストがコラボレーターに送信され、コラボレーター側でアクティベーションが行われます。

**オーディエンスをメディアパートナーに連携する方法：**

1. オーディエンスビルダー内で、**オーディエンスをメディアパートナー**に接続をオンにします。  

   <Image align="center" alt="オーディエンスをメディアパートナーに連携.png" src="https://files.readme.io/d1e6558183eed8f239f1d61efd81cd71db7a2c7f6acfdef7e1c029dea51af172-37184169230097.png" />
2. **+パートナー接続を追加**をクリックしてください。
3. パートナー接続が確立されていない場合は、新しいパートナー接続を作成します。
   1. **接続の追加**をクリックします。
   2. 関連するメディアパートナー (Meta 広告、Google 広告、Pinterest、TikTok、DV360、またはトレードデスク) を選択してください。
   3. 接続の名前を入力します。
   4. [**Login with [partner name]**] をクリックします。パートナーログインページに移動します。オーディエンスを受信するアカウントを選択します。その後、ダイアログウィンドウに戻ります。
   5. [**アカウント ID を選択**] をクリックし、該当するアカウント ID を選択します。
   6. **保存**をクリックしてください。
4. **Save & send** をクリックします。

<Image align="center" alt="image (21).png" src="https://files.readme.io/bb7785936d3e79e18adffe31ca8121b5c0a65392508ef0aea76c7dc75e9ce9eb-43432561109777.png" />

</Accordion>

<div id="export-to-cloud-storage" />

<Accordion title="クラウドストレージへエクスポート">

オーディエンスをクラウドストレージバケットに直接送信します。オーディエンスが更新されるたびに、DCP は選択した宛先に最新バージョンを自動的にエクスポートします。また、オーディエンスはいつでもCSVファイルとしてダウンロード。

<div id="note-8" />

> 📘 **注意**
>
> エクスポートする前に、クラウドストレージバケットが設定され、DCP に接続されていることを確認してください。手順については、「<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">クラウドサービスのセットアップ</Anchor>」と「<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-add-connections">接続の追加</Anchor>」を参照してください。

**オーディエンスをクラウドストレージにエクスポートするには:**

1. オーディエンスビルダーで、「**クラウドストレージにエクスポート**」をオンにします。
2. **クラウドストレージ接続ドロップダウンから**、既存の接続を選択します。
   * まだ接続していない場合は、[**+ 新しいクラウド接続**] をクリックします。接続ダイアログは、DCP を離れることなくこのページに直接開きます。セットアップを完了し、[**保存**] をクリックします。新しい接続が自動的に選択されます。
3. **Save & send** をクリックします。

</Accordion>

<div id="manage-audiences" />

## オーディエンスの管理

コラボレーションに関連するオーディエンス表示および管理します。

<div id="access-audience-management" />

<Accordion title="アクセスオーディエンス管理">

**コラボレーションに関連するオーディエンス表示および管理するには:**

1. DCP で、[**コラボレーション**] タブに移動し、関連するコラボレーションクリック。
2. **オーディエンスセクションをクリックします**。  
   <Image align="center" alt="オーディエンスセクション新規 UI.png" src="https://files.readme.io/8f8170d6848da0158c7db76938bdb4fa64cb3a9702218fe549e6b6e859d64140-small-43777994824977.png" width="2836px" />

**このページからできること：**

* **オーディエンスの検索：** ソース名またはオーディエンス名のいずれかで検索します。
* **オーディエンスソート:** 列見出しのいずれかをクリックしてオーディエンスソートします。
* **オーディエンスの詳細の表示：** コラボレーターの名前、重複ユーザーの統計、[オーディエンスのステータス](#view-audience-statuses)、アクティベーション場所などの詳細を確認できます。
* **その他のアクション：** オーディエンスカードの3つのドットのメニューアイコンをクリックすると、追加のアクションが開きます。
  * 編集するオーディエンスの有効化先を変更します。
  * 複製オーディエンスの新しい独立したコピーを作成します。
    * 新しいオーディエンスのソースとデータの組み合わせ方法は引き継がれます（変更不可）。フィルターとアクティベーション先は事前入力されていますが、完全に編集可能です。
    * SQL オーディエンスビルダーのオーディエンスおよびステータスが「無効」のオーディエンスでは、複製は無効になっています。
  * **履歴の表示**：オーディエンスのアクティベーションのすべてのインスタンスを、接続やアクティベーションステータスなどの詳細とともに確認できます。
  * 削除オーディエンスを削除します
  * オーディエンスを一時停止データソースが変更されたときにオーディエンスが更新され、再度アクティブ化されるのを防ぎます 。

</Accordion>

<div id="edit-the-audience-activation-destination" />

<Accordion title="オーディエンスの有効化先を編集する">

オーディエンスの作成中に、下書きとして保存し、その下に戻って有効化先を編集できます（権限によって異なります）。

**オーディエンスの有効化先を編集するには：**

1. **コラボレーション**タブから、関連するコラボレーションをクリックします。
2. **オーディエンス** セクションをクリックし、関連するオーディエンスを検索します。
3. オーディエンス > **[編集]** にカーソルを合わせたときに表示される3つのドットのメニューアイコンをクリックします。
4. 「**接続してエクスポート**」（オーディエンスページの下部）で、該当するトグルをオンに切り替えます。

   * [メディアパートナーとつながる](#connect-an-audience-to-media-partners)
   * [クラウドストレージへエクスポート](#export-to-cloud-storage)

</Accordion>

<div id="delete-an-audience" />

<Accordion title="オーディエンスを削除する">

アカウントで作成したオーディエンスを削除できます。これにより、アカウントから完全に削除されます。

**オーディエンスを削除する方法：**

1. **コラボレーション**タブから、関連するコラボレーションをクリックします。
2. **オーディエンス** セクションをクリックし、関連するオーディエンスを検索します。
3. オーディエンス > **削除** にカーソルを合わせたときに表示される3つのドットのメニューアイコンをクリックします。
4. 削除の確認

</Accordion>

<div id="view-audience-statuses" />

<Accordion title="オーディエンスのステータスを表示する">

コラボレーションに関連するオーディエンス**スの最終アップロードステータスを表示できます**。

<Image align="center" alt="image (33).png" src="https://files.readme.io/5659a3e30aac91226ecf8d1cf08618b698f063d1412522f2c231459fdfc7fb03-43541066537105.png" width="860px" />

オーディエンスにはさまざまなステータスがあります。

* **アクティブ：** オーディエンスは宛先プラットフォームに正常に送信され、キャンペーンで使用できるようになりました。
* 下書きオーディエンスは下書きとして保存されました（接続、エクスポート、配信は行われませんでした）。
* **無効**：対象ユーザーに使用されているソースまたはデータビューの有効期限が切れているか、削除されたか、コラボレーションから削除されているか、有効な権限がなくなったことを示します。
* **配信保留中：** オーディエンスはアクティベーションのためにコラボレーターに送られ、アクティベーションを保留中です。
* 一時停止されましたオーディエンスは手動で一時停止されており、新しいデータが使用可能になった時点で送信されません。
* 一時停止中コラボレーションと関連するオーディエンスは一時停止されています。

オーディエンスの**アップロード履歴**ステータスも表示できます。

**アップロード履歴を表示するには:**

特定のオーディエンスの横にあるドロップダウンをクリックし、**View history** を選択します。

<Image align="center" alt="View history Doctored .png" src="https://files.readme.io/7840f05fd8f6a98445c29e5a59813776378d842dd54fab4e3f66111c34dd89dd-36573637043089.png" />

**アップロード履歴のステータスは次のとおりです。**

* 処理中聴衆は現在準備中です。
* SUCCESSオーディエンスはすべての接続に正常に送信されました。
* 一部失敗オーディエンスを1つ以上の接続に送信できませんでした。
* 失敗オーディエンスの処理に問題が発生しました（例：データの不一致、プラットフォームの制限、プラットフォームのエラーなど）。
* N/Aオーディエンスはドラフトまたは保留中です。アップロード履歴ステータスは適用されません。

</Accordion>

<div data-zendesk-anchors="overview=dcp-%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HWG1P909NHBXC5VF23BDVVPH=dcp-%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 key-features=%E8%A6%96%E8%81%B4%E8%80%85%E3%82%92%E5%A2%97%E3%82%84%E3%81%99 h_01HWG5B2MEJH7M8E9BWA3FQFQ2=%E8%A6%96%E8%81%B4%E8%80%85%E3%82%92%E5%A2%97%E3%82%84%E3%81%99 01KFDX0R4BYSTE1V5G7ATQ6FZS=%E4%B8%BB%E3%81%AA%E6%A9%9F%E8%83%BD h_01HWG62BA9X4VRRDXAEKA07FTJ=visual-audience-builder h_01HZMBFKV40PHFN1B8PVVCMWQQ=%E6%B3%A8%E6%84%8F step-1-join-sources=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E8%A9%B3%E7%B4%B0%E3%81%A8%E3%82%BD%E3%83%BC%E3%82%B9 h_01HWFRRGP99KKGBSQ6QB10RD26=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E8%A9%B3%E7%B4%B0%E3%81%A8%E3%82%BD%E3%83%BC%E3%82%B9 h_01KT94AC4N81MBE0DAT7TX2QA7=%E6%B3%A8%E6%84%8F-1 step-2-build-audiences=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%82%92%E5%AE%9A%E7%BE%A9 h_01HWFRRPFTCFGEHY1AW8G4VMY4=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%82%92%E5%AE%9A%E7%BE%A9 h_01JSEPSRF3FFJJ4S20GJJPJVWF=%E6%B3%A8%E6%84%8F-2 summary-rightside-preview-pane=%E6%A6%82%E8%A6%81-%E5%8F%B3%E5%81%B4%E3%81%AE%E3%83%97%E3%83%AC%E3%83%93%E3%83%A5%E3%83%BC%E3%83%9A%E3%82%A4%E3%83%B3 h_01KBMPR7BHCTTVE8DR1TCRYAHJ=%E6%A6%82%E8%A6%81-%E5%8F%B3%E5%81%B4%E3%81%AE%E3%83%97%E3%83%AC%E3%83%93%E3%83%A5%E3%83%BC%E3%83%9A%E3%82%A4%E3%83%B3 h_01KBMPK2HXMZ6YNQMJTST9BD8Y=%E6%B3%A8%E6%84%8F-3 h_transactional-data-visual-builder=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A7%E3%81%AE%E4%BD%9C%E6%A5%AD working-with-transactional-data-sources=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A7%E3%81%AE%E4%BD%9C%E6%A5%AD h_01HWG62BAAD46MTK385756T4AQ=sql-audience-builder h_01HZM8X9RZ1A9CKWYNM61QW515=%E6%B3%A8%E6%84%8F-4 step-1-set-details=%E8%A9%B3%E7%B4%B0%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HWG9VX0QB3GFZDARAT5QKHV0=%E8%A9%B3%E7%B4%B0%E3%81%AE%E8%A8%AD%E5%AE%9A step-2-build-query=%E3%82%AF%E3%82%A8%E3%83%AA%E3%82%92%E4%BD%9C%E6%88%90 h_01HWG9Y6B9X3T1FFM9ZR8TVBVC=%E3%82%AF%E3%82%A8%E3%83%AA%E3%82%92%E4%BD%9C%E6%88%90 h_01KT6SCS53699DZXE4EF92WC44=%E6%B3%A8%E6%84%8F-5 the-sql-audience-builder=sql%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%83%93%E3%83%AB%E3%83%80%E3%83%BC h_01HZM9P2GNCPGJDEA51HCV1Y99=sql%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%83%93%E3%83%AB%E3%83%80%E3%83%BC h_transactional-data-sql-patterns=sql-%E3%82%AF%E3%82%A8%E3%83%AA%E3%81%AE%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF transactional-data-in-sql-queries=sql-%E3%82%AF%E3%82%A8%E3%83%AA%E3%81%AE%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF send-audience-for-activation=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%82%92%E9%80%81%E4%BF%A1%E3%81%97%E3%81%A6%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%99%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E8%A1%8C%E3%81%86 h_01HZMCHKMVXRWK7RXZ7NN65JQX=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%82%92%E9%80%81%E4%BF%A1%E3%81%97%E3%81%A6%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%99%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E8%A1%8C%E3%81%86 h_01HZMCRJBBXFEV6JXEHGFXZDZW=%E6%B3%A8%E6%84%8F-6 h_01KFG12R13ADFBY4XBDRGE956V=connect-an-audience-to-media-partners h_01HZMDXEEABQRQE8XMZNE86SRF=%E6%B3%A8%E6%84%8F-7 h_01KFG12R13R9B6ATHTBTKAVAMX=export-to-cloud-storage h_01KY2FJV90NYBVTQBN6K63K9DS=%E6%B3%A8%E6%84%8F-8 manage-audiences=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%AE%E7%AE%A1%E7%90%86 h_01HZPWTG23YQ5Y1GAPXT65DK07=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%AE%E7%AE%A1%E7%90%86 h_01KFBA379S9ZZAKN7FC7X2S297=access-audience-management h_01KFB4HVDZZ0MA4Q69DXKH4YY7=edit-the-audience-activation-destination h_01KFB4HVDZJ08STDXGA7ZP8MM3=delete-an-audience h_01KFB4HVDZFCJNYG6VVWTWVAQ8=view-audience-statuses" />
