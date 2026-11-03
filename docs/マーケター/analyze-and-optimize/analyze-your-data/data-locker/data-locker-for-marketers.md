---
title: Data Locker — マーケティング担当者向け
metadata:
  keywords:
    - Reports
    - Data Locker
    - Advertisers
    - Raw Data
    - Developers
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2019-02-03T12:20:08Z'
  edited_at: '2026-10-14T09:27:52Z'
  id: 360000877538
  locale: ja
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/ja/articles/360000877538
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Data Lockerを使用することで、レポートデータをクラウドストレージに送信し、自社の分析基盤（BIシステム）に読み込むことができます。AppsFlyerでは、多様なデータ保存先を提供しています：AppsFlyerが所有するAWS S3バケット、または広告主保有のAWS、GCS、Yandex、BigQuery、Snowflakeのお客様が所有するストレージ。なお、Data Lockerは、[複数の接続](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination)をサポートしています。つまり、すべてのデータを複数の宛先に送信したり、宛先ごとにデータを分離したり、またはその両方の組み合わせを行ったりすることができます。

## 概要

![6133DataLockerForAdvertisers.png](https://files.readme.io/820fee89515ccdcdfac2043bcb9fde722ddc8ec852a140ec250378c581d9c375-32966274469649.png)

Data Locker設定画面で、クラウドストレージに格納するAppsFlyerから配信するデータに含めたいアプリ、メディアソース、イベント、レポートを柔軟に選択することができます。その後、ストレージから自社システムへプログラムで読み込ませる形で自社データなどと連携します。

<div id="data-locker-features" />

<Accordion title="Data Locker—機能">

| 機能 | 説明 |
| --- | --- |
| [ストレージオプション（クラウド）](/docs/data-locker-for-marketers#storage-options) | Data Lockerは、次のクラウドサービスプロバイダーへデータを送信できます：<ul><li>AppsFlyer所有のAWS S3ストレージ</li><li>次のいずれかの<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup">広告主所有のストレージ</Anchor>：<ul><li>AWS</li><li>GCS</li><li>Azure Blob</li><li>[Beta] Yandex</li><li>BigQuery</li><li>Snowflake</li></ul></li></ul>Data Lockerでは複数のストレージを設定できます。つまり、全てまたは一部のデータを[複数のストレージ](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination)に送信することができます。<br /><br />**例**<ul><li>レポートタイプ別にデータを分割：ローデータをGCSへ、集約データをSnowflakeへ送信できます。</li><li>アプリごとにデータを分離：アプリグループごとにデータを異なるバケットに送信できます。</li></ul> |
| 複数アプリ | アカウント内の1つ、複数、または全てのアプリのデータを送信連携します。アカウントにアプリを追加したときに、それらを自動的に含めることができます。 |
| 利用可能なデータ期間 | 14日間 |
| [データの分離](/docs/data-locker-for-marketers#app-segregation) | 利用可能なデータ分離オプション（バケットクラウドストレージに関連)：<ul><li>[デフォルト] **統合：** すべてのアプリを合わせたデータ。データファイル内のアプリを特定するために、行レベルでアプリID項目が使用されます。</li><li>**アプリごとに分離：** 各アプリのデータは別々のフォルダに格納されます。フォルダ名はアプリIDで構成されます。</li></ul> |
| データ形式のオプション | <ul><li>バケットクラウドストレージの場合：<ul><li>CSV</li><li>Parquet</li><li><Anchor target="_blank" href="/marketers/ja/docs/adobe-experience-platform-aep-integration-with-appsflyer-data-locker">Adobe</Anchor></li></ul></li><li>データウェアハウス</li></ul> |
| データ更新頻度 | 更新頻度はレポートタイプによって異なります。<ul><li>**毎時：** データは継続的に生成されます。例えば、インストールとアプリ内イベントデータは、イベントがAppsFlyerに到着してから数時間以内に書き込まれます。</li><li>**毎日：アンインストールなどのレポートは毎日生成され、翌日に利用できます。**</li><li>**バージョン管理済み：** 同じレポートが同じ期間に複数回生成される場合、バージョン管理の仕組みが適用されます。</li></ul> |

</Accordion>

<div id="reports-available-via-data-locker" />

<Accordion title="Data Lockerで取得できるレポート">

<Anchor target="_blank" href="/marketers/ja/docs/data-locker-advertiser-reports">Data Lockerで取得できるレポート</Anchor>

</Accordion>

## Data Lockerのレポート設定

データロッカーを設定するには、クラウドサービスに接続し、エクスポート設定を定義し、レポート内容をカスタマイズするために、次の手順に従ってください：

<div id="1-set-up-your-cloud-service" />

<Accordion title="1. クラウドサービスの設定">

1つ以上のクラウドサービスプロバイダーに接続できます。Data Lockerと連携するための設定方法については、以下を参照してください：

* <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>バケット
* <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>バケット
* <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
* [Beta] <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>バケット
* <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>データウェアハウス
* <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>データウェアハウス

<strong>注意！</strong>Data Lockerのご契約がなく、コホート分析または SKANデータを取得する場合でも、広告主様が所有するクラウドストレージサービスの手順を完了する必要があります。

</Accordion>

<div id="2-add-a-connection-to-your-cloud-service" />

<Accordion title="2. クラウドサービスへの接続を追加">

データロッカーで動作するようにクラウドサービスアカウントを設定した後（上記の「クラウドサービスの設定」を参照）、アカウントの資格情報を使用してデータロッカーで接続を作成します。最大2つの接続を作成できます。

> 📘 **注記**
>
> デフォルトでは、各アカウントは最大で**2 データロッカー接続**を開くことができます。追加の接続が必要な場合は、カスタマーサクセスマネージャー（CSM）にお問い合わせください。

クラウドプロバイダーとの接続を作成するには、次の手順を実行してください：

1. AppsFlyer管理画面 左メニュー **エクスポート** > **Data Locker**へ進みます。
2. 画面右上の、**新しい接続**をクリックします。
3. **接続名**に接続の名前を入力してください。英字の小文字と数字、ハイフンのみを使用してください。
4. 接続したいクラウドサービスのアイコンをクリックしてください。
5. 選択したサービスに応じて、以下の接続情報を入力してください。

   <div id="aws-cloud-bucket-connection" />

   <Accordion title="AWSクラウドバケット接続">

   AWS接続を設定する前に、AWSバケットを作成してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#aws-storage">こちら</Anchor>を参照してください。

   接続を設定するには：

   1. AWS S3バケット名を入力します。プレフィックス `af-` は必須であり、手動で入力する必要があります。
   2. **接続テスト**をクリックしてください。
   3. バケットパスが無効であることを示すエラーメッセージなどが表示されないことを確認します。
   4. **この接続をAdobe Experience Platformと互換性を持たせる**かどうかを選択します。選択した場合は、**保存**をクリックして、[グローバルレベルのフィルターを選択](#select-global-level-filters)へ続きます。
   5. **保存**をクリックします。

   </Accordion>

   <div id="gcs-cloud-bucket-connection" />

   <Accordion title="AWSクラウドバケット接続">

   GCS接続を設定する前に、GCSにバケットを作成してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#gcs-storage">こちら</Anchor>を参照してください。

   接続を設定するには：

   1. **GCSバケット名**を入力します。
   2. **接続テスト**をクリックしてください。
   3. バケットパスが無効であることを示すエラーメッセージなどが表示されないことを確認します。
   4. **この接続をAdobe Experience Platformと互換性を持たせる**かどうかを選択します。 選択した場合は、**保存**をクリックして、[グローバルレベルのフィルターを選択](#select-global-level-filters)へ続きます。
   5. **保存**をクリックします。

   </Accordion>

   <div id="azure-cloud-bucket-connection" />

   <Accordion title="Azureクラウドバケット接続">

   Azure接続を設定する前に、Azureでストレージアカウントを開いてください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#beta--azure-storage">こちら</Anchor>を参照してください。

   接続を設定するには：

   1. **接続名**、**ストレージアカウント名**、**キー**を入力します。
   2. バケットパスが無効であることを示すエラーメッセージなどが表示されないことを確認します。
   3. **この接続をAdobe Experience Platformと互換性を持たせる**かどうかを選択します。 選択した場合は、**保存**をクリックして、[グローバルレベルのフィルターを選択](#select-global-level-filters)へ続きます。
   4. **保存**をクリックします。

   </Accordion>

   <div id="yandex-cloud-bucket-connection" />

   <Accordion title="Yandexクラウドバケット接続">

   AWS接続を設定する前に、Yandexでサービスアカウントを作成してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#yandex">こちら</Anchor>を参照してください。

   接続を設定するには：

   1. **バケット名**、**アクセスキー**、**シークレットキー**を入力します。
   2. バケットパスが無効であることを示すエラーメッセージなどが表示されないことを確認します。
   3. **この接続をAdobe Experience Platformと互換性を持たせる**かどうかを選択します。 選択した場合は、**保存**をクリックして、[グローバルレベルのフィルターを選択](#select-global-level-filters)へ続きます。
   4. **保存**をクリックします。

   </Accordion>

   <div id="bigquery-data-warehouse-connection" />

   <Accordion title="BigQueryデータウェアハウス接続">

   BigQuery接続を設定する前に、BigQueryにデータセットを作成してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#bigquery">こちら</Anchor>を参照してください。

   接続を設定するには：

   1. BigQueryプロジェクトIDとデータセット名を入力します。
   2. **接続テスト**をクリックしてください。
   3. バケットパスが無効であることを示すエラーメッセージなどが表示されないことを確認します。
   4. 選択した場合は、**保存**をクリックして、[グローバルレベルのフィルターを選択](#select-global-level-filters)へ続きます。

   </Accordion>

   <div id="snowflake-data-warehouse-connection" />

   <Accordion title="Snowflakeデータウェアハウス接続">

   Snowflake接続を設定する前に、Snowflakeでアカウントを開設してください。詳細は<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#snowflake">こちら</Anchor>を参照してください。

   接続を設定するには：

   1. Snowflake地域とアカウントIDを入力します。
   2. **接続テスト**をクリックしてください。
   3. バケットパスが無効であることを示すエラーメッセージなどが表示されないことを確認します。
   4. 選択した場合は、**保存**をクリックして、[グローバルレベルのフィルターを選択](#select-global-level-filters)へ続きます。

   </Accordion>

6. **保存**をクリックします。**レポート出力設定セクション**が表示されます。

> 📘 **注記**
>
> 接続が作成、更新、または削除されたかどうか、そして誰が変更を行ったかを確認するには、[監査ログ](#track-connection-changes-in-the-audit-log)を使用できます。

</Accordion>

<div id="3-set-the-report-output-settings" />

<Accordion title="3. レポート出力の設定">

クラウドサービスとの接続を設定した後、データロッカーのレポート出力の一般設定を続けることができます。**クラウドサービスがBigQueryまたはSnowflakeである場合、このステップはスキップします**。

1. **レポート出力設定** セクションで、フォルダ構造 ([データ分離](/docs/data-locker-for-marketers#app-segregation)) を選択します。
   * **統一**（デフォルト）：レポートファイルには、すべてのアプリからの記録が含まれています。
   * **アプリごとに分離：** 各レポートファイルは1つのアプリの専用ファイルです。
2. レポートのファイル形式を選択します：パーケット（デフォルト）またはCSV。
3. レポートのファイル圧縮タイプを選択してください：
   * Snappy（Parquetファイルでのみ使用可能）
   * GZIP
4. ファイルに希望する最大行数を選択してください：1万、2万5千、5万、10万、20万、50万のいずれか。 ファイル内の行数が多いほど、ファイルは少なくなりますが、各ファイルサイズは大きくなります。

   > 📘 **注記**
   >
   > の下で、レポートのパスパターンを表示します。注記：表示されているものとは異なる実際のパスがあるかもしれません。


</Accordion>

<div id="select-global-level-filters" />

<Accordion title="4. グローバルレベルのフィルターを選択">

グローバルレベルのフィルターを使用すると、**アプリやメディアソースでレポートをフィルター**できます。これらのフィルターは、あなたのデータロッカーアカウント内のほとんどのレポートに適用されますが、レポートレベルでも設定できます（下記 [7. レポートレベルのフィルター選択](#select-the-report-level-filters)を参照してください）。両方のレベルに同じフィルターが適用される場合、レポートレベルのフィルターが優先されます。

フィルターを適用するには、次の手順を実行します：

1. **レポート**セクションで、フィルターをクリックし、レポートに含める項目を選択します。 例： <Image alt="Untitled.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" /> **アプリ**フィルターをクリックして、レポートに含めるアプリを選択します。
2. 次に、Enter (⏎) ボタンをクリックします。

</Accordion>

<div id="5-select-the-report" />

<Accordion title="5.レポートグループを選択します">

クラウドサービスで取得したいレポートを選択してください。レポートはグループごとにリストされています。レポートグループ名をクリックすると、グループが展開または折りたたまれます。

* レポートを選択するには、<Image alt="down.png" src="https://files.readme.io/3f59bcc54434374270c0099394a740cc650a3b4a1be0f3f34d298be1ebcad40c-34623601355409.png" width="20px" />をクリックしてレポートグループを展開します。グループ内の各レポートには、以下の情報が提示されます：
  * **Report Name：** レポートのタイトル
  * **Dataset Name：** レポートの記録を含むデータセットの名前。
  * **Data Freshness：** レポートが新しいレコードでどのくらいの頻度で更新されるか（例：毎時、毎日、またはバージョン管理）。
  * **Fields：** レポートのために選択したフィールド（または列）の数と、選択可能なフィールドの総数を比較します。

</Accordion>

<div id="customize-or-duplicate" />

<Accordion title="6.レポートをカスタマイズまたは複製します">

レポートグループから1つ以上のレポートを選択した後、**元のレポートをカスタマイズする**か**別のカスタマイズされたコピーを作成する**のいずれかを選択できます。これにより、元のバージョンに影響を与えることなく、レポートのフィールドとフィルターを特定のニーズに合わせて調整できます。

**オプションA:元のレポートをカスタマイズする**

1. レポート名の隣にある<Image alt="customize.png" src="https://files.readme.io/35f4653b944cd5dc81c6de76f8dcacd9c3413ea49915ba2b5865a244ede3c4b6-35437232722833.png" width="20px" /> **カスタマイズ**ボタンをクリックします。
2. レポートエディタが開き、フィールドを選択し、フィルターを適用できます。
3. 変更は元のレポート構成に保存されます。

*注：これにより、レポートがクラウドストレージに配信される方法が変更されます。*

**オプションB:レポートを複製します**

* レポート名の隣にある<Image alt="Untitled 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="5px" />をクリックします。
* ドロップダウンメニューから<Image alt="duplicate2.png" src="https://files.readme.io/d8fbf09b3a8e3839f80a0a4fec90e0360dc1c2a4a066bf58438364c0d8a15c65-35439088509073.png" width="17px" /> **複製**を選択します。
* レポートのコピーが作成され、プレフィックス`copy_of_`が付けられます。
* 複製されたレポートは、さらなるカスタマイズのために編集モードで開きます。

　 / *ヒント：複製は、異なる使用ケースのためにレポートのバリエーションを作成するのに最適です。*

カスタマイズするか複製するかを選択した後、次のステップで説明されているようにレポートフィールドを構成します。

</Accordion>

<div id="6-select-the-report-fields" />

<Accordion title="7. レポート項目の選択">

レポートをカスタマイズするか複製することを選択したら、次のステップはどのデータフィールドを含めるかを定義することです。各レポートは利用可能なフィールドの完全なセットを提供し、分析や統合に関連するものだけを含めるように選択をカスタマイズできます。デフォルトでは、すべてのフィールドが選択されていますが、特定のフィールドを手動で選択することでレポートを絞り込むことができます。

レポートに含めるフィールドを選択するには：

1. 選択したレポートダイアログの**フィールド**タブの下で、任意のフィールドにカーソルを合わせると、その説明が表示されます。HQ1\_2024-08-26\_15.44.23.png

   [![HQ1_2024-08-26_15.44.23.png](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)
2. レポートに含めたいフィールドをチェックするか、レポートから除外したいフィールドのチェックを外してください。
3. **適用**をクリックして設定を保存します。

**別のレポートからフィールド選択をコピー**

他のレポートからフィールドの選択をコピーして出発点とし、その後、レポートを微調整するためにフィールドを選択または選択解除し続けることができます。

1. **フィールド** タブで、任意のランダムフィールドの選択を解除します。
2. レポートからスキーマを**取得**クリックします。
3. フィールド選択をコピーしたいレポートを選択してください。
4. フィールドの選択または選択解除を続けてください。
5. レポートの元のフィールド選択を復元するには、 <Image alt="無題 4.png" src="https://files.readme.io/dda26e3d18c52049cf92d7862a87ce7a46e6a00c349afd70dfe6d1809e00b89e-34623601369361.png" width="15px" /> **更新**をクリックしてください。

</Accordion>

<div id="7-select-the-reportlevel-filters" />

<Accordion title="8. レポートレベルのフィルター選択">

レポートレベルのフィルターを使用すると、**アプリ、メディアソース、またはその他のディメンションによって単一のレポートをフィルター**できます。アカウント内のすべてのレポートに適用されるフィルターを設定することもできます。参照：[グローバルレベルのフィルターを選択](#select-global-level-filters)デフォルトでは、レポートレベルのフィルターはグローバルレベルのフィルター設定に設定されていますが、選択したレポートにのみ適用されるカスタム設定に更新することができます。

指定されたレポートに適用するフィルターを選択するには：

1. 特定のレポートにカーソルを合わせてカスタマイズします。
2. アクションメニューを開くには、<Image alt="Untitled 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="6px" /> をクリックし、<Image alt="Untitled 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="20px" /> **レポートの編集** を選択します。
3. **フィルター**タブを開きます。フィルターはグローバルレベルのフィルター設定に設定されています。
4. フィルターをクリックして、レポートに含めるアイテムを選択します。例： <Image alt="Untitled.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" /> **アプリ**フィルターをクリックして、レポートに含めるアプリを選択します。
5. Enter (⏎) ボタンをクリックします。この選択はグローバルレベルの設定を上書きします。
6. （オプション） **アプリ内イベント**レポートについては、**アプリ内イベント**フィルターを設定できます。名前を正確に入力して選択してください。
7. **適用**をクリックして設定を保存します。

</Accordion>

<div id="8-remove-legacy-fields" />

<Accordion title="9.レガシーフィールドを削除する">

未使用のフィールドとは、以前はレポートスキーマに含まれていたが、現在は除外されているフィールドのことです。これらのフィールドを削除して、レポートに関連する情報のみが含まれるようにすることをお勧めします。変更を加える前に、ワークフローや統合がそれに依存していないことを確認してください。

**特定のレガシーフィールドを削除する**

1. **レガシーフィールド**タブを開きます。
2. オンに設定する：**レポートにレガシーフィールドを含める**。
3. 除外したいフィールドの選択を解除します。
4. **適用**をクリックします。
5. 接続設定を保存します。

**すべてのレガシーフィールドを削除するには：**

1. レガシーフィールドタブを開きます。
2. オフに設定する：**レポートにレガシーフィールドを含める**。

> 📘 **注記**
>
> 未使用のフィールドをレポートに含めたいが、未使用フィールドのリストがグレーアウトしてロックされているためできない場合は、カスタマーサクセスマネージャーにお問い合わせください。

#### 非空のレガシーフィールド

ほとんどのレガシーフィールドは空であるか、`null`です。しかし、それらのいくつかは値を含んでいますが、次の理由から未使用と見なされます：

* 別の名前（改名された）でレポートに表示されます。
* レポートスキーマから除外（非推奨）されました。

[非空のレガシーフィールドリストをダウンロードする（CSV）。](https://docs.google.com/spreadsheets/d/e/2PACX-1vRzJr2IgKTHKq_6IFX-PFFv6_89ixtlbGZ9RNH134TniGlWa_M-85D1L2E7LhzQrDjictnSnNNnN2mm/pub?output=csv)

</Accordion>

<div id="9-save-the-connection" />

<Accordion title="10. 接続の保存">

**保存**をクリックすると、最初のダンプデータが3時間以内に接続されたクラウドサービスに書き込まれます。次のデータ更新スケジュールは、各レポートに特有のものです。

> 🚧 **重要！**
>
> Data Locker設定への変更が有効になるには、最大3時間かかります。

</Accordion>

## ユーザー権限

適切な権限を持つ管理者とチームメンバーがData Lockerにアクセスできます。

* 管理者はData Lockerページへのアクセス、すべての接続の作成と管理、編集者の追加、既存の接続への所有者の割り当てを行うことができます。
* チームメンバーは、Data Lockerページへのアクセス、所有する既存の接続の編集、新規接続の作成を行うことができます。彼らは、たとえアカウントの所有者であっても、所有権（所有者や編集者の設定）を**管理できません**。

### Data Lockerのアクセス権と所有権の管理（管理者）

#### Data Lockerのアクセス権を付与する

* チームメンバーにData Lockerへのアクセス権を付与するには、**管理**に設定されたData Lockerの役割を割り当てます。

#### 所有権と編集者の管理

既存の接続の所有権を譲渡したり、チームメンバーを編集者として追加したりするには：

1. 接続内の3点オプションメニュー<Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="1.18%" />をクリックします。
2. **所有権の管理**を選択します。
3. 接続の所有者を変更するか、編集者を追加します。

#### 所有権変更後のフィルターの確認

Data Locker接続の所有者をデータアクセス制限のあるユーザー（アプリ、メディアソース、代理店、国などによる制限があるユーザー）に変更した場合、既存の[グローバルレベル](#select-global-level-filters)または[レポートレベルのフィルター](#7-select-the-reportlevel-filters)が、新しい所有者の権限に合わせてリセットされる可能性があります。

所有権を譲渡した後は、フィルターを確認し、接続が意図したデータ範囲を反映していることを確認してください。

データアクセス制限の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/user-management#データへのアクセス">ユーザー管理 > データアクセス</Anchor>を参照してください。

> 📘 **注記**
>
> AF AWS接続では、管理者であっても**所有権の管理**オプションはありません。なぜなら、管理者のみがAF AWS接続を編集、削除、または新規作成できるからです。この予防措置は、バケットの資格情報の露出を防ぐために取られています。

## データストレージのアーキテクチャ

<div id="overview" />

<Accordion title="概要">

ストレージ内のデータ構造は、データが送信されるクラウドストレージまたはデータウェアハウスによって異なります。ここで説明するフォルダの構成は、ストレージ（バケット）に適用されるものです。データウェアハウスストレージの場合は、フォルダーへの参照がビューに適用されることを考慮してください。

各種データは、選択したストレージオプションに書き込まれます。クラウドストレージの場合、ストレージはAppsFlyerが所有しているAWSか、お客様が保有しているAWS、GCS、またはYandexのいずれかもしくは複数を選択できます。ストレージオプションはいつでも切り替えたり、データの一部またはすべてを複数のストレージオプションに送信したりできます。

クラウドバケットストレージ内のデータは、レポートタイプ、日付、時刻に従って階層フォルダ構造に編成されます。次の図は、この構造の例を示しています：

![DLFolderOVerview.png](https://files.readme.io/78f360ec1df72253e5b2cd725f3eecf4e17548a7f06b544a94a75a2c319d77a0-18107910420369.png)

特定のレポートのデータは、そのレポートに紐付けられた時間 (h) フォルダに格納されます。

* 時間フォルダの数は、レポートデータの更新頻度（毎時、毎日、またはバージョン別）によって異なります。
* データは、Snappy または GZIP圧縮ファイル、もしくはParquet 形式またはCSV形式の非圧縮ファイルで提供されます。
* データファイルは列（項目）で構成されています。
* <Anchor target="_blank" href="/marketers/ja/docs/data-locker-advertiser-reports#user-journey">ユーザージャーニーレポート</Anchor>のスキーマ（フィールド）構造は互いに同一であり、選択した項目によって異なります。その他のレポートは、それぞれ独自の明示的な項目を持つ、別名スキーマレスレポートです。利用できるレポートとレポートの仕様へのリンクについては、<Anchor target="_blank" href="/marketers/ja/docs/data-locker-advertiser-reports#user-journey">マーケター向けのData Lockerレポート</Anchor>を参照してください。

</Accordion>

<div id="folder-structure" />

<Accordion title="フォルダの構成">

| フォルダ | 説明 |
| --- | --- |
| サブスクリプションID | <Image alt="DataLockerFolders.png" src="https://files.readme.io/0cda5728e48dab772878cad13ed3b81168f152e1bf01604ac45b700af804dd16-32966264039185.png" width="439px" /><ul><li>バケットの上階層のフォルダはストレージ所有者とプロバイダーによって異なります。一般的に、最上位フォルダはサブスクリプションIDですが、Cyberduckを使用する場合、IDがブックマークに設定され、フォルダ構造に表示されない場合があります。</li><li>*data-locker-hourly* フォルダにはレポートトピックが含まれています。これより上層部のフォルダ階層は、バケット所有者とクラウドサービスプロバイダによって異なります。</li></ul>**バケット所有者とクラウドプロバイダーに基づくフォルダの構成の例**<ul><li>**AppsFlyer保有のAWS S3バケット**: &lt;af-ext-reports>/&lt;unique\_identifier>/&lt;data-locker-hourly></li><li>**広告主保有のAWSバケット**: *&lt;af-datalocker-your bucket prefix>/&lt;generated-home-folder>&lt;subscription-id>*</li><li>**広告主保有のGCSバケット:** &lt;your bucket name>/&lt;generated-home-folder>/&lt;subscription-id></li></ul> |
| Topic (t) | レポートタイプはレポートの主題に関連します。 |
| Date (dt) | これはデータの日付に関連します。ローデータの場合、これはイベントが発生した日を意味します。集計データの場合、レポート日が入ります。 |
| Time (h or version) | 日付フォルダは、レポートの種類によって、**hourly (h)** または **version** フォルダに分かれています。<br /><br />**<span id="hourly-folders"></span>Hourly（時間別）フォルダ**<br /><br />h フォルダは、AppsFlyerがデータを受信した時刻に関連します。例えば、インストールイベントを 14:00-15:00 UTC に受信した場合、h=14 ファイルに書き込まれます。注！AppsFlyerにデータが到着してから、h フォルダがData Lockerに書き込まれるまで、約1-3時間のタイムラグがあります。例えば、h=14 フォルダは1時間後の15:00 UTC に書き込まれます。<br /><br />**Hourly フォルダの特性**：<ul><li>0–23の番号が付いた24のhフォルダがあります。例えば、h=0, h=1などです。</li><li>h=late という遅延フォルダには、深夜以降に到着した前日のイベントが含まれています。つまり翌日の 00:00–02:00 UTC に到着したイベントを指します。例えば、ユーザーが月曜の朝 08:00 UTC にアプリをインストールし、イベントが火曜日の深夜 01:00 UTCに到着した場合、このイベントは月曜の遅延フォルダに書き込まれます。</li><li>UTCの深夜 02:00以降に到着したデータは、実際の到着日時のフォルダに書き込まれます。</li><li>h=late フォルダ内のデータが取り込まれていることを確認してください。これらのデータは他の h フォルダには含まれていません。</li><li>\_temporary フォルダ：場合によっては、hフォルダ内に一時的なフォルダを生成する場合があります。一時フォルダとサブフォルダは無視してください。例： /t=impressions/dt=2021-04-11/h=18/**\_temporary**</li></ul>Daily Report（日次レポート）<ul><li>h=23フォルダには、毎日更新されるローデータレポートが保存されています。アンインストールレポートは、通常 h=2 フォルダに格納されますが、それ以外のフォルダに入るケースもあります。</li><li>コホートとIncrementalityのレポートは、直接 dt フォルダに保存されます。</li><li>バージョン管理されたレポートは、このセクションで説明する別の慣例に従い保存されます。</li></ul>**UTCタイムゾーンを使用しないアプリでの毎時レポートに関する検討事項**<br /><br />その日の全てのデータを確実に取得するには、次に説明するとおり、アプリのタイムゾーンで定義された日に合わせてフォルダを消費する必要があります：<ul><li>**東半球のタイムゾーン（日本）**：指定されたカレンダーの日付のすべてのデータを取得するには、UTC時間と日付に従ってフォルダを消費する必要があります。例：アプリのタイムゾーンがUTC+9（日本時間）の場合、日本時間の火曜に関連する全ての時間ごとのデータを取得するには、以下のフォルダを確認する必要があります：月曜日 h=15–23 と late、火曜日 h=0–14 と h=15-16（なぜ火曜日の h=14-15 を消費する必要があるのか？ -火曜日の h=15-16 も確認した方がよい理由は、一部のデータは遅れて到着する場合があるためです。そのため、h=14-15のフォルダには、遅延のあったイベントが含まれることがあります。）そのため、データ取得後にevent\_time でフィルタをかけ、UTCでの時間表記を考慮しながら火曜のデータを拾う必要があります。</li><li>**西半球のタイムゾーン：** 指定されたカレンダーの日付のすべてのデータを取得するには、UTC時間と日付に従ってフォルダを消費する必要があります。例：アプリのタイムゾーンはUTC- 7（ロサンゼルス）です。ロサンゼルスでの火曜に関連する全ての時間ごとのデータを取得するには、以下のフォルダを確認する必要があります：火曜h=7-23と後半、水曜h=0-6と7-8。（水曜日の h=7-8 も確認した方がよい理由は、火曜日の h=15-16 も確認した方がよい理由は、一部のデータは遅れて到着する場合があるためです。そのため、h=7-8のフォルダには、遅延のあったイベントが含まれることがあります。）そのため、データ取得後にevent\_time でフィルタをかけ、UTCでの時間表記を考慮しながら火曜のデータを拾う必要があります。</li></ul>**<span id="version-folders"></span>Versionフォルダ**<br /><br />一部のレポートにはバージョン指定のオプションがあります。つまり、ある日の最新データが複数回提供されます。データは、到着が遅れたり、より正確なデータによって更新され続けることがあるため、同じレポートには複数のバージョンがあり、最新のバージョンが最も正確なものとなります。<br /><br />ある日のレポートは、その日のバージョンフォルダーに含まれています。各バージョンは、レポートを一意に識別するEpochタイムスタンプを使用して名前が設定されている別のフォルダに格納されています。<br /><br />データのインポート処理では、データが過去にさかのぼって書き込まれる可能性があることを考慮する必要があります。例えば、1月14日に、1月1日フォルダにデータが書き込まれることがあります。広告主がバケットを所有している場合、インポート処理のトリガーとしてクラウドサービスの通知を使用することを検討してください。 (<Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html">AWS</Anchor> \| <Anchor target="_blank" href="https://cloud.google.com/storage/docs/pubsub-notifications">GCS</Anchor>) |

</Accordion>

<div id="app-segregation" />

<Accordion title="アプリ毎のデータ分割">

バケットクラウドストレージの場合、データは、アプリごとにフォルダーに選択または分離されたすべてのアプリのデータを含む統合データファイルで提供されます。アプリごとの分離は、次の表で示すとおり、hフォルダ内で行われます。

| 分離タイプ | 説明 |
| --- | --- |
| [デフォルト] 統合 | 全てのアプリのデータは、統合されたデータファイルにて提供されます。データを取り込む際に、行レベルで app\_id 項目を使用してアプリを区別してください。<br /><br />**データファイルの例は、h=2 フォルダをご覧ください**<br /><br />![UnifiedByApp.png](https://files.readme.io/dbc39c2ce99c1ff607fd553b9c9034e55728c102f31fd18a501cc00910267b28-18107874522513.png)<br /><br />データファイルの命名規則は、unique\_id.gz です。<ul><li>データの取り込みプロセスでは、以下のことに注意してください：<ul><li>\_SUCCESS フラグが設定された後にデータを取り込んでください。</li><li>フォルダの全てのファイルに *.gz*拡張子が付いた状態でデータを取り込んでください。パート番号のロジックを使用したインポートプロセスは構築しないでください。</li></ul></li></ul> |
| アプリごとに分離 | フォルダにはアプリごとのサブフォルダが含まれています。特定のアプリのデータファイルは、アプリフォルダ内に含まれています。次の図では、h=19 フォルダにアプリフォルダが含まれています。各アプリフォルダには関連するデータファイルが含まれています。注！データファイルには app\_id が含まれていないため、フォルダを使用して app\_id を特定する必要があります。<br /><br />![DLSegregateByApp.png](https://files.readme.io/90639507da82f7dafacfa5bfb67fa96a8277747cd0eee226d74498bf5ff16869-32966264040977.png)<br /><br />各アプリのフォルダでの命名規則は、unique\_id.gz です。<ul><li>データの取り込みプロセスでは、以下のことに注意してください：<ul><li>\_SUCCESS フラグが設定された後にデータを取り込んでください。</li><li>フォルダの全てのファイルに *.gz*拡張子が付いた状態でデータを取り込んでください。パート番号のロジックを使用したインポートプロセスは構築しないでください。</li></ul></li></ul>制限事項：このオプションはPeople-Based Attributionレポートでは利用できません。 |

</Accordion>

<div id="data-files" />

<Accordion title="データファイル">

データファイルはセグメンテーションタイプにより異なります。

<table><thead><tr><th>コンテンツ</th><th colspan="2">詳細</th></tr></thead><tbody><tr><td>完了フラグ</td><td colspan="2"><p>最終ファイル（完了）フラグは、対象の h フォルダの全てのデータが書き込まれたあとに設定されます。 </p><ul><li>_SUCCESS フラグが存在していることを確認してから、h フォルダ内のデータを読み込んでください。</li><li>_SUCCESS フラグは、特定のフォルダに書き込むデータがなく、フォルダが空である場合にも設定されます。</li><li>注！アプリごとの分離オプションでは、フラグは各アプリフォルダごとではなく、h フォルダ内で設定されます。前のセクションの図を参照してください。 </li></ul></td></tr><tr><td>ファイルの種類</td><td colspan="2"><ul><li>データは、Snappy または GZIP圧縮ファイル、もしくはParquet 形式またはCSV形式の非圧縮ファイルで提供されます。</li><li>解凍後のデータファイルは、設定に応じてParquetまたはCSV形式で出力されます。</li></ul></td></tr><tr><td>列の並び（CSVファイル） </td><td colspan="2"><p>CSVファイルの場合、レポート項目の順序は常に同じです。新しい項目が追加される場合は、既存項目の右側に追加されます。 </p><p>この点に関して： </p><ul><li>ユーザー経路レポートの列の構成は同じです。つまり、異なるレポートタイプに対して同様のデータ読み込み手順を実行できます。レポートに含める項目を選択してください。各項目の詳細・定義：<a href="./raw-data-field-dictionary" target="_blank">ローデータ項目の手引き</a> </li><li>レポート可用性セクションで、FFと表示されているレポートは、共通の列構造ではありません。 </li></ul></td></tr><tr><td>項目入力に関する考慮事項</td><td colspan="2"><p><strong>空白または空のフィールド：</strong> 一部の項目は <em>null</em> または空白になります。これは、特定のレポートのコンテキストでは、レポートするデータがないことを意味します。通常、<em>null</em> は、特定のレポートおよびアプリタイプのコンテキストでこの項目に値が入力されないことを意味します。空白（""）は、この項目がこのコンテキストに関連しているものの、入力するデータが見つからなかったことを意味します。 </p><p>制限付きメディアソースの場合、制限された項目の内容は null になります。  </p><p>一般的に、nullとブランクは同じものであり、利用可能なデータはありません。  </p><p><strong>タイムゾーンと通貨</strong></p><p>アプリ固有のタイムゾーンと通貨設定は、Data Locker に書き込まれるデータには影響しません。次のことが当てはまります。 </p><ul><li> <strong>time_zone</strong>日付と時間のデータはUTCです。</li><li> <strong>通貨：</strong>event_revenue_usd フィールドは USD です。</li></ul><p><strong>カンマで区切られた値</strong>：これらのカンマは二重引用符 `"` の間に含まれます。例：<code>`"iPhone6,1"`</code></p></td></tr></tbody></table>

</Accordion>

<div id="storage-options" />

<Accordion title="ストレージオプション">

> ❗️ **警告！**
>
> 広告主所有のストレージオプションを使用する場合：
>
> * GDPR等のデータプライバシー規制とアドネットワーク／SRNのデータ保持ポリシーに準拠していることをご確認ください。
> * 広告主所有のストレージソリューションを使用して第三者にデータを送信しないでください。

* データは、選択したストレージ所有者に次のように書き込まれます。
  * AppsFlyer所有のAWS S3ストレージ
  * 広告主所有のストレージ — AWS, GCS, Azure, Yandex, BigQuery, Snowflake
* ストレージの選択はいつでも変更できます。
* ストレージを変更すると、次のことが起こります：
  * 新しく選択したストレージへの書き込みは1時間以内に開始します。
  * 7日間の移行期間中、既存のストレージへの書き込みを続行します。移行期間の有効期限がユーザーインターフェイスに表示されます。移行期間を使用して、データ読み込みプロセスを更新してください。必要に応じて移行期間を再開したり、AppsFlyerのバケットに戻したりすることができます。
  * **ストレージの変更**：複数のストレージオプションを使用して複数の宛先に同時にデータを送信することで、あるストレージオプションから別のストレージオプションに移行できます。移行とテストが完了したら、不要になったストレージオプションを削除してください。

|  | AppsFlyer所有ストレージ (AWS) | 広告主所有のストレージ（GCS, AWS, Azure, Yandex, BigQuery, Snowflake） |
| --- | --- | --- |
| バケット名 | AppsFlyerが設定します | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#gcs-storage">GCS：</Anchor>制限なし</li><li><Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#aws-storage">AWS：</Anchor>広告主が設定します（プレフィックス af- が必要です）。</li></ul>例： `af-datalocker-your-bucket-name` |
| ストレージの所有権 | AppsFlyer | マーケティング担当者 |
| ストレージプラットフォーム | AWS | AWS, GCS, Azure, Yandex, BigQuery, Snowflake |
| データへアクセスするための認証情報 | AppsFlyerアカウントの管理者がData Lockerのユーザーインターフェイスで利用できます。 | AppsFlyerには開示されません。クラウドプロバイダーから提供された認証情報を使用してください。 |
| データ保持期間 | データは14日後に削除されます。 | マーケティング担当者の責任 |
| データ削除リクエスト | AppsFlyerの責任 | マーケティング担当者の責任 |
| セキュリティ | AppsFlyerがストレージを管理します。広告主は読み込み専用アクセスがあります。 | マーケターがストレージを管理します。<ul><li>**AWS：** AppsFlyerでは、バケットへのGetObject、ListBucket、DeleteObject、PutObject 権限が必要です。バケットはAppsFlyer専用にする必要があります。他の用途には使用しないでください。</li><li>**GCS：** 参照 - <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup">GCS設定に関する記事</Anchor></li></ul> |
| ストレージ容量 | AppsFlyerが管理します | マーケターが管理 |
| バケットポリシーでVPCエンドポイントを使用したアクセスコントロール | 不適用 | [オプション] AWSで、バケット単位でVPCエンドポイントセキュリティを実装している場合、AppsFlyerサーバーを許可リストに追加する必要があります。 |

#### **セキュリティご担当者への連絡事項（お客様が管理するストレージの場合）**

注意事項：

* バケットまたはストレージ先は、AppsFlyer専用です。この宛先には他のシステムからのデータを送らないでください。
* データを書き込まれた後25時間後に、ストレージ内のデータを削除できます。
* ストレージに書き込まれるデータは、当社のサーバーに既に存在しているデータのコピーです。データは、当社の保持ポリシーに従って引き続き当社のサーバーに格納されます。
* 技術的な理由により、データを削除したり書き換えたりすることがあります。このため、削除とリストのパーミッションが必要です。どちらのパーミッションも、広告主にとってセキュリティリスクにはなりません。リストの場合、我々はバケットに書き込む唯一の存在です。削除された場合は、データを再生成することができます。
* 詳細については、[hello@appsflyer.com](mailto:hello@appsflyer.com) 経由でセキュリティチーム、またはCSMにご連絡ください。

</Accordion>

<div id="multipleconnections-principles-more-than-one-destination" />

<Accordion title="複数連携の原則（2つ以上の接続先設定）">

Data Lockerでは、データの一部またはすべてを2つの接続先（接続設定箇所で定義）に送信できます。例えば、アプリAのデータをAWSへ、アプリBのデータをGCSへ送信できます。

各連携に対して、ディスティネーションを含むData Lockerの設定を全て実行する必要があります。連携設定は互いに独立しています。

連携管理について、以下の点を考慮してください。

* Data Locker設定では、連携はタブに表示されます。各連携には独自の設定タブがあり、そこから連携を管理できます。各タブのアイコンはストレージの種類を示しています。
* 連携の詳細の確認、連携の複製、連携の削除を行うには、⋮ (オプション) をクリックしてください。

</Accordion>

## 追加情報

<div id="track-connection-changes-in-the-audit-log" />

<Accordion title="監査ログで接続の変更を確認する">

データロッカーの接続変更を監査ログで表示できるようになりました。これは、AppsFlyerダッシュボードのセキュリティセンターから利用可能です。変更が行われたかどうか、いつ行われたか、誰が行ったかを確認するには、監査ログを使用してください。これにより、サポートに連絡することなく、データの欠落や予期しない接続の変更などの問題を解決するのに役立ちます。

次の接続ライフサイクルイベントがモニターされます：

* 新しい接続の作成
* 既存の接続内容の更新
* 接続の解除
* 接続の削除

**監査ログへアクセスする方法：**

1. 上部のナビゲーションバーで、アカウントメニュー <Image alt="HQ1 2025-05-05 10.48.04.png" src="https://files.readme.io/b7020f3b633fb66e0e2d4988c7903426509b1fa871693cee602a39b8eb9d69d1-34955489919889.png" width="4.24%" /> を開きます。
2. **セキュリティセンター**を選択します。
3. **監査ログ**セクションで、**監査ログの確認**をクリックします。
4. サービスでフィルター：**Datalocker**の関連エントリを表示します。

詳細については、以下を参照してください：<Anchor target="_blank" href="/marketers/ja/docs/audit-log">監査ログ</Anchor>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特徴と制限">

| **特性** | 備考 |
| --- | --- |
| アドネットワーク | アドネットワークは使用できません。 |
| 代理店 | 代理店アカウントでは使用できません。 |
| アプリ固有のタイムゾーン | 適用されません。Data Lockerフォルダは、UTCを使用して時間に分割されます。実際のイベントは、UTCで時刻が刻まれます。必要に応じて、他のタイムゾーンに時刻を変換します。アプリのタイムゾーンに関係なく、イベント発生からData Lockerに記録されるまでの遅延時間は同じです。 |
| アプリ固有の通貨 | サポートされておらず、計測対象外です |
| サイズ制限 | 不適用 |
| データ更新頻度 | データは、この記事内に記載されている個々のレポートデータの更新頻度に従って更新されます。 |
| 過去データ | 対応していません過去のデータが必要な場合、すべてではありませんが、一部のレポートはPull APIを介して利用可能です。 |
| 制限付きデータ | 一部のレポートの項目は、プライバシーの制限により制限されています。<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">詳細はこちら</Anchor> |
| ユーザーアクセス | Data Lockerを設定できるのは、<Anchor target="_blank" href="/marketers/ja/docs/user-management">必要な権限を持つアカウントユーザーのみ</Anchor>です。 |
| 単一アプリ / 複数アプリ | 複数アプリのサポート。複数のアプリをサポートしています。 |
| 最大接続数 | デフォルトでは、各アカウントは最大で**2データロッカー接続**を開くことができます。追加の接続をリクエストするには、**CSMに連絡してください**。 |

</Accordion>

<div id="troubleshooting" />

<Accordion title="トラブルシューティング">

* **症状**：AWS CLIを使用してデータを取得できない
* **エラーメッセージ：** ListObjectsV2 オペレーションの呼び出し時にエラーが発生しました（AccessDenied）：アクセス拒否
* **要因：** 使用されているAWS認証情報が、AppsFlyerバケットの正しい認証情報ではありません。これは、複数または無効な資格情報が原因の可能性があります。
* **解決法：**
  1. [Cyberduck](/docs/data-locker-for-marketers#cyberduck)などの別の方法、つまりCLI以外を使用してバケットにアクセスしてください。これにより、使用している資格情報が機能していることを確認してください。Cyberduckを使用して接続できる場合は、資格情報キャッシュに問題があることを示しています。
  2. <Anchor target="_blank" href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html">AWS認証情報キャッシュを更新</Anchor>してください。   
     **Screenshot from AWS** ![mceclip0.png](https://files.readme.io/e6608b196c39cb71e0a02e0eabe95378f24659a1578a16fd381bfd0053ca309e-32966264043537.png)

</Accordion>

## AWSデータの取得

AWS CLIや次のセクションで説明するツールのいずれかのAWSデータ取得ツールを使用してください。注！正確な手順は、AppsFlyerが所有するバケットに適しています。独自のバケットに接続する場合は、必要に応じて手順を調節してください。

<div id="aws-cli" />

<Accordion title="AWS CLI">

**はじめに：**

* コンピューターにAWS CLIをインストールします。
* AppsFlyerで、Data Lockerに移動し、認証情報パネルに含まれる情報を取得します。

**AWS CLIを使用する：**

1. ターミナルを開きます。Windowsでこれを行うには、&lt;Windows>+&lt;R> を押し、**OK** をクリックします。   
   コマンドラインウィンドウが開きます。
2. **aws configure** を入力してください。
3. 認証情報パネルに表示されるAWS Access Keyを入力します。
4. 認証情報パネルに表示されるAWS Secret Keyを入力します。
5. **eu-west-1**を入力してください。
6. Enterキー（None）を押します。

必要に応じて、以下のCLIコマンドを使用してください。

以下のコマンドで、`{home-folder}`の値を見つけることができる。

**バケット内のフォルダーを一覧表示する方法：**

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/
```

### ファイルとフォルダーの一覧表示

Data Lockerバケットには3種類のフォルダがあります。

* Report Type: `t=`
* Date: `dt=`
* Hour: `h=`

特定のレポートタイプのすべてのレポートを一覧表示するには：

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/
```

特定の日の特定のレポートタイプのすべてのレポートを一覧表示するには：

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17
```

特定の日の特定の時間の特定のレポートのすべてのレポートを一覧表示するには：

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17/h=23
```

特定の日付のファイルをダウンロードする方法：

```bash
aws s3 cp s3://af-ext-reports/<home-folder>/data-locker-hourly/t=installs/dt=2020-08-01/h=9/part-00000.gz ~/Downloads/
```

</Accordion>

<div id="cyberduck" />

<Accordion title="Cyberduck">

**はじめに：**

* Cyberduckクライアントをインストールしてください。
* AppsFlyerで、Data Lockerに移動し、認証情報パネルに含まれる情報を取得します。

**Cyberduckの設定方法**：

1. Cyberduckで、[Action]をクリックしてください。
2. **New Bookmark** を選択します。以下の画面が表示されます：
3. 最初のフィールド（下のスクリーンショットでは[1]となっている）で**Amazon S3**を選択します。[![DataDuckSmall2.png](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)
4. 次のフィールドを入力します：
   * **Nickname:** 自由入力欄
   * **Server:** s3.amazonaws.com
   * **Access key ID: AppFlyerの認証情報パネルに表示されるAWSアクセスキーをコピーしてください**
   * **Secret access key:** AppsFlyer の資格情報パネルに表示されているバケットシークレットキーをコピーします。
   * **Path:** `{Bucket Name}/{Home Folder}` / 例：**af-ext-reports/1234-abc-ffffffff**
5. ウィンドウを閉じます。画面の右上にある X をクリックしてください。
6. 接続を選択します。   
   データディレクトリが表示されます。

</Accordion>

<div id="amazon-s3-browser" />

<Accordion title="Amazon S3ブラウザー">

**はじめに：**

* Amazon S3ブラウザをインストールします。
* AppsFlyerで、Data Lockerに移動し、認証情報パネルに含まれる情報を取得します。

**Amazon S3ブラウザを設定するには** ：

1. S3 ブラウザにて、**Accounts** > **Add** **New Account** をクリックします。  
   新しいアカウントの追加ウィンドウが開きます。 [![mceclip0.png](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)
2. 次のフィールドを入力します：
   * **Account Name** ：フリーテキスト
   * **Access Key ID** ：認証情報パネルに表示されるAWS Access Keyをコピーします。
   * **Secret Access Key**：資格情報パネルに表示される Bucket Secret Key をコピーします。
   * パスワードで **Encrypt Access Keys** を選択し、パスワードを入力します。このパスワードを覚えておいてください。
   * **Use secure transfer** を選択します。
3. **変更を保存**をクリックします。
4. Buckets **> Add External Bucket**をクリックします。   
   「外部バケットの追加」ウィンドウが開きます。   
   <Image alt="mceclip2.png" src="https://files.readme.io/88dd43f62dbd68d0295b52a7f7b9b09449bd915e6a6d52703c24a50583e05a6e-32966264054929.png" width="433px" />
5. <strong>バケット名を入力します。</strong>バケット名は以下の形式です： `{Bucket Name}/{Home Folder}`.バケット名とホームフォルダに必要な値は認証情報ウィンドウに表示されます。
6. **Add External bucket**をクリックします。バケットが作成され、ウィンドウの左側のパネルに表示されます。   
   これで、Data Lockerファイルにアクセスできます。

</Accordion>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/data-locker-advertiser-reports">Data Lockerで取得できるレポート</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">適切なローデータ抽出ツールの選択</Anchor>

<div data-zendesk-anchors="data-locker=%E6%A6%82%E8%A6%81 h_01HE2S6FANNTNB580CMHNX34YA=%E6%A6%82%E8%A6%81 data-locker%E2%80%94features=data-locker-features h_01HE2S6FANQH2GZ11S8S87H0YH=data-locker-features h_01HE2S6FAN6BFPJSZJBEE9P5VK=reports-available-via-data-locker set-data-locker-report-settings=data-locker%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E8%A8%AD%E5%AE%9A h_01JS45N2DNWZBHP5PH8ZG6FBTF=data-locker%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E8%A8%AD%E5%AE%9A h_01JS45N2DNEZZJRF2RKG1RM9NK=1-set-up-your-cloud-service h_01JS45N2DNVA0SHBA49G42GNFE=2-add-a-connection-to-your-cloud-service h_01K22P5FWJ96CPFJPW0XDCHNNJ=%E6%B3%A8%E8%A8%98 h_01JS4ASE6J6X1DD33PEGQAPXPA=aws-cloud-bucket-connection h_01JS4ASE6J587JPHAMCSBA2Z92=gcs-cloud-bucket-connection h_01JS4ASE6J4NC7M0TRFDT7F2X7=azure-cloud-bucket-connection h_01JS4ASE6JKFTM3FYAEKFHRW2M=yandex-cloud-bucket-connection h_01JS4ASE6JKV8WJG68RMHKVCE5=bigquery-data-warehouse-connection h_01JS4ASE6JBNE5BK04QDRM7CW4=snowflake-data-warehouse-connection h_01JTFRHNRRJB76JBXXT1TBNRBY=%E6%B3%A8%E8%A8%98-1 h_01JS45N2DN8JTMQCK76PDBBWA4=3-set-the-report-output-settings h_01JSBTCZ5569RCV6W6QWT400R7=%E6%B3%A8%E8%A8%98-2 h_01JS45N2DNMQAGFVHDDD5JGF2M=select-global-level-filters h_01JS45N2DN388YVP29DDBBBFBP=5-select-the-report h_01JVPJ9CG45JREBKP3ZQXKZWRZ=customize-or-duplicate h_01JS45N2DP4FK9EZYNTY2GX2GK=6-select-the-report-fields h_01JS45N2DPN7B73X0TRC82JW87=7-select-the-reportlevel-filters h_01JS45N2DPYYABS9NXFXP23ARA=8-remove-legacy-fields h_01JS45N2DPYNBG9VPCZJ481DFE=%E6%B3%A8%E8%A8%98-3 nonempty-legacy-fields=%E9%9D%9E%E7%A9%BA%E3%81%AE%E3%83%AC%E3%82%AC%E3%82%B7%E3%83%BC%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01JSCC6KZNKJAVYSFCDDSE80YW=%E9%9D%9E%E7%A9%BA%E3%81%AE%E3%83%AC%E3%82%AC%E3%82%B7%E3%83%BC%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01JS45N2DPH1QAREYGN5H20T8R=9-save-the-connection h_01JS45N2DPNPXAEZ74J0ETP7BS=%E9%87%8D%E8%A6%81 set-user-permissions=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%A8%A9%E9%99%90 h_01KH8D60TDTNS4EWNXJ4JPGXZ2=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%A8%A9%E9%99%90 manage-data-locker-access-and-ownership-admins=data-locker%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E3%81%A8%E6%89%80%E6%9C%89%E6%A8%A9%E3%81%AE%E7%AE%A1%E7%90%86%E7%AE%A1%E7%90%86%E8%80%85 h_01KH8D60TEFX2MCW00JT94F9AQ=data-locker%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E3%81%A8%E6%89%80%E6%9C%89%E6%A8%A9%E3%81%AE%E7%AE%A1%E7%90%86%E7%AE%A1%E7%90%86%E8%80%85 give-data-locker-access=data-locker%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E3%82%92%E4%BB%98%E4%B8%8E%E3%81%99%E3%82%8B h_01KH8D60TE541XMXWCVK0HZTJA=data-locker%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E3%82%92%E4%BB%98%E4%B8%8E%E3%81%99%E3%82%8B manage-ownership-and-editors=%E6%89%80%E6%9C%89%E6%A8%A9%E3%81%A8%E7%B7%A8%E9%9B%86%E8%80%85%E3%81%AE%E7%AE%A1%E7%90%86 h_01KH8D60TF69FN7KMBPMZHBW27=%E6%89%80%E6%9C%89%E6%A8%A9%E3%81%A8%E7%B7%A8%E9%9B%86%E8%80%85%E3%81%AE%E7%AE%A1%E7%90%86 review-filters-after-changing-ownership=%E6%89%80%E6%9C%89%E6%A8%A9%E5%A4%89%E6%9B%B4%E5%BE%8C%E3%81%AE%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KH8D60TFYMEY8FEPR4YKJRYJ=%E6%89%80%E6%9C%89%E6%A8%A9%E5%A4%89%E6%9B%B4%E5%BE%8C%E3%81%AE%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KH8D60TGVN75TMS9QES0G6CQ=%E6%B3%A8%E8%A8%98-4 architecture=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%81%AE%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%81%E3%83%A3 data-storage-architecture=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%81%AE%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%81%E3%83%A3 h_01HE2S6FAN4H9DQ5HBTKSNJ72B=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%81%AE%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%81%E3%83%A3 h_01HE2S6FANY1FWEY6Y34T85GHM=overview h_01HE2S6FANDJ65MZ2H2FBAZYJR=folder-structure h_01HE2S6FAN7PBZ8M86FQVSN5KQ=hourly-folders h_01HE2S6FAN366V8HNCY4PFNTFG=version-folders h_01HE2S6FANHFZMCY3WZBZB9QMP=app-segregation h_01HE2S6FANVDFH9S9JN8E9J7ES=data-files h_01HE2S6FAN8ZDF5N4ECKKN1D1H=storage-options h_01HE2S6FAN2HY7V3G9NS9XCVE1=%E8%AD%A6%E5%91%8A notice-to-security-officers-in-the-case-of-customercontrolled-storage=%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%81%94%E6%8B%85%E5%BD%93%E8%80%85%E3%81%B8%E3%81%AE%E9%80%A3%E7%B5%A1%E4%BA%8B%E9%A0%85%E3%81%8A%E5%AE%A2%E6%A7%98%E3%81%8C%E7%AE%A1%E7%90%86%E3%81%99%E3%82%8B%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%81%AE%E5%A0%B4%E5%90%88 h_01HE2S6FANRVGYPRWWFA50JAQ4=%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%81%94%E6%8B%85%E5%BD%93%E8%80%85%E3%81%B8%E3%81%AE%E9%80%A3%E7%B5%A1%E4%BA%8B%E9%A0%85%E3%81%8A%E5%AE%A2%E6%A7%98%E3%81%8C%E7%AE%A1%E7%90%86%E3%81%99%E3%82%8B%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%81%AE%E5%A0%B4%E5%90%88 h_01HE2S6FANBRXA0NS4E8SP3618=multipleconnections-principles-more-than-one-destination additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HE2S6FAP4SA77B0SX7R8JMTY=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01JTFQMKN0046SNBB4YSRJMQG9=track-connection-changes-in-the-audit-log h_01HE2S6FAP6FKAJCW92JVWD828=traits-and-limitations h_01HE2S6FAPJC20G7YZSRWP5E34=troubleshooting aws-data-retrieval=aws%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97 h_01HE2S6FAPJMKX567HSAR16TCN=aws%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97 h_01HE2S6FAPB5MW09Y4HKFV3RM8=aws-cli listing-files-and-folders=%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%A8%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E3%81%AE%E4%B8%80%E8%A6%A7%E8%A1%A8%E7%A4%BA h_01HE2S6FAP31H9NK6V870FGXZF=%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%A8%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC%E3%81%AE%E4%B8%80%E8%A6%A7%E8%A1%A8%E7%A4%BA h_01HE2S6FAP2E2TW4F5PJ4226Q0=cyberduck h_01HE2S6FAP74NG5VNEWKWXXJX2=amazon-s3-browser h_01HE7RB5N99WJ3XP69Z69H81AD=%E5%8F%82%E7%85%A7" />
