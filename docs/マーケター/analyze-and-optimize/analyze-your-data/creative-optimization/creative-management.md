---
title: Creative Management
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2025-09-17T12:01:55Z'
  edited_at: '2026-10-28T08:55:53Z'
  id: 39137008313105
  locale: ja
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/ja/articles/39137008313105
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Creative Managementは、クリエイティブの一元管理、確認、配信開始までの作業を効率化します。ストレージからクリエイティブを同期し、メディアソースを横断して配信状況を把握できます。目的のクリエイティブを簡単に見つけ、対応するメディアソースのキャンペーンへ直接アップロードできます。

<div id="about-creative-management" />

## Creative Managementについて

Creative Managementは、ストレージとの同期からメディアソースへのアップロードまで、クリエイティブアセットのライフサイクル全体を一元管理するハブです。

Creative Managementでは、以下のことができます。

* クリエイティブを保存しているストレージから同期します。
* 一元化されたギャラリーで、クリエイティブを簡単に検索・確認します。
* メディアソースを横断して、クリエイティブの配信状況を把握します。
* 配信開始前のAIスコアに基づき、クリエイティブの優先順位を決めます。
* 各メディアソースのキャンペーンへ、クリエイティブを直接アップロードします。
* アップロード結果を確認し、どのクリエイティブが成功・失敗したかを把握します。

大規模な運用に対応したCreative Managementは、マーケティングチームやクリエイティブチームの手作業を削減し、配信開始までの時間を短縮して、キャンペーンのパフォーマンス向上を支援します。

<div id="get-started" />

## まずはじめに

**前提条件：**

<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-guide">Creative Optimization</Anchor>のサブスクリプションが有効なAppsFlyerアカウントである必要があります。また、Creative Managementへの申し込みは、CSMにご連絡いただくか、[hello@appsflyer.com](mailto:hello@appsflyer.com)までお問い合わせください。無料トライアルを利用できる場合もあります。

**Creative Managementの利用を開始するには、以下の手順に従ってください。**

<div id="sync-creatives-from-the-creative-storage" />

<Accordion title="ストレージからのクリエイティブの同期">

Creative Managementでは、接続したストレージからクリエイティブを同期できます。接続を保存すると、Creative Managementが接続先のストレージからクリエイティブを取得します。その後も新しいクリエイティブの追加に合わせて、ライブラリを最新の状態に保ちます。

Creative Managementは現在、Google DriveとDropboxに対応しています。接続手順は、ストレージごとに異なります。

**接続に対応しているストレージは以下のとおりです。**

* [Google Drive](#google-driveへの接続)
* [Dropbox](#dropboxへの接続)

<div id="connect-google-drive" />

#### Google Driveへの接続

**Google Driveのフォルダに接続するには：**

1. AppsFlyerで、**最適化> Creative Management**に移動します。

**<Image alt="Click Creative Management New.png" src="https://files.readme.io/c4ae98a4409b0766c9bd41e2f153d67c3d6168d31af82dadd1f43f345678878e-40988213459217.png" width="35.83%" />**

2. **クリエイティブの接続設定**をクリックします。

<Image alt="click Creative connection.png" src="https://files.readme.io/a1ba600e90389351dc119bb00a358d14909eb92a3fc0b8391e3efa7650992ae2-small-48939135740689.png" width="150%" />

3. **接続を追加**をクリックします。
4. **Google Drive**を選択します。
5. Google Driveで、クリエイティブを保存しているフォルダをAppsFlyerのサービスアカウント（`creative-google-account-drive@creative-prod.iam.gserviceaccount.com`）に閲覧者権限で共有し、AppsFlyerがアクセスできるようにします。
   * Creative Managementは、選択したフォルダとそのサブフォルダからクリエイティブを同期します。
6. Creative Managementに戻り、フォルダのURLを入力します。
7. 対象のアプリを選択します。この手順は任意ですが、クリエイティブを正しく整理・マッチングするため、設定をお勧めします。
8. **URLを追加**をクリックします。
9. 複数のフォルダを一度に接続する場合は、直前の2つの手順を繰り返します。

<Image alt="image (49).png" src="https://files.readme.io/c29dab5dc76470b5e99e8efd8accaec7bfd1c6878f3bcfe8d58d7b650063065b-48939152741393.png" width="92.07%" />

10. **接続**をクリックします。

<div id="connect-dropbox" />

#### Dropboxへの接続

Dropboxに接続する前に、対象のクリエイティブフォルダにアクセスできるアカウントでDropboxにログインしていることを確認してください。

**Dropboxのフォルダに接続するには：**

1. AppsFlyerで、**最適化> Creative Management**に移動します。
2. **クリエイティブの接続設定**をクリックします。
3. **接続を追加**をクリックします。
4. **Dropbox**を選択します。
5. Dropboxのログインポップアップで、対象のDropboxアカウントに接続します。
6. 接続ダイアログで**フォルダを選択**をクリックし、接続するフォルダを選択します。
   * Creative Managementは、選択したフォルダとそのサブフォルダからクリエイティブを同期します。

<Image alt="click Choose folders.png" src="https://files.readme.io/13d62001deedecfb95a202aa54d36a1d7948d36aa76ac2a93b056be54d2ffe01-48939135745937.png" width="84.64%" />

7. フォルダごとに対象のアプリを選択します。この手順は任意ですが、クリエイティブを正しく整理・マッチングするため、設定をお勧めします。
8. **接続**をクリックします。

接続が作成されると、Creative Managementがクリエイティブの取得と処理を開始します。処理が完了すると、クリエイティブタイプ、同期日、初回配信日、ステータス、利用可能なバージョンなどのメタデータとともに、クリエイティブがギャラリーに表示されます。

</Accordion>

<div id="browse-and-select-creatives" />

<Accordion title="クリエイティブの閲覧と選択">

Creative Managementのギャラリーでは、クリエイティブの確認・検索・絞り込み・選択を行えます。

各クリエイティブカードは、1つのクリエイティブを表します。 1つのクリエイティブに、解像度や形式が異なる複数のバージョンが含まれる場合があります。カードでは、メディアソースを横断してクリエイティブが新規・配信中・配信停止中のいずれかをすばやく把握できます。初回配信日やCreative Managementへの同期日など、主なメタデータも確認できます。新しいクリエイティブはそれぞれ自動的に分析・スコアリングされ、配信開始前に最適なものを選ぶ際の判断材料になります。スコアはC（成果につながる可能性が低い）からA（配信拡大の準備ができている）までの範囲で付与され、高いパフォーマンスが見込めるクリエイティブを優先する際の判断に役立ちます。

<Image alt="image (52).png" src="https://files.readme.io/a295ed00e01564b04bd32a7ce515cf41012a62324a8fcd350d1b4b9113e0cacb-small-48939135746577.png" width="150%" />

<div id="filter-creatives" />

#### クリエイティブの絞り込み

検索バーとフィルターを使用して、以下の条件でクリエイティブを絞り込めます：

* **検索バー**：IDまたは名前でクリエイティブを検索します。
* **アプリ**：特定のアプリに関連するクリエイティブに絞り込みます。
* **メディアソース**：特定のアドネットワークで現在配信中、または過去に配信されていたクリエイティブを検索します。
* **クリエイティブタイプ**：画像、動画、HTMLで絞り込みます。
* **クリエイティブのステータス**：新規、配信中、配信停止中で絞り込みます。
* **クリエイティブスコア**：特定のAIスコアが付いた新しいクリエイティブに絞り込みます。
* **同期日**：特定の期間中にCreative Managementへ追加されたクリエイティブを検索します。
* **初回配信日**：特定の期間中に初めて配信されたクリエイティブを検索します。
* **解像度**：特定のバージョンが利用可能なクリエイティブを検索します。

デフォルトでは同期日順に並び、最近追加されたクリエイティブが先に表示されます。初回配信日やクリエイティブ名で並べ替えることもできます。

</Accordion>

<div id="upload-creatives-to-media-sources" />

<Accordion title="メディアソースへのクリエイティブのアップロード">

クリエイティブを配信する準備ができたら、ギャラリーで1つ以上選択し、**メディアソースにアップロード**をクリックします。

Creative Managementが現在アップロードに対応しているのは、アプリのプロモーションキャンペーンのみです。アドネットワークごとに要件やアップロード先の構成が異なるため、選択したメディアソースによってアップロード設定が変わります。

対応するすべてのメディアソースで、複数のアップロード先へ一度にクリエイティブをアップロードできます。

**対応するメディアソースは以下のとおりです。**

* [Google Ads](#google-ads)
* [Meta Ads](#meta-ads)
* [TikTok Ads](#tiktok-ads)
* [Mintegral](#mintegral)
* [Unity Ads](#unity-ads)
* [AppLovin](#applovin)

#### Google Ads

Google Adsでは、既存のアプリプロモーション用広告グループにクリエイティブをアップロードできます。

1. ギャラリーからクリエイティブを選択します。
2. **メディアソースにアップロード**をクリックします。
3. Google Adsを選択します。
4. アップロード先の詳細として、Googleアカウントと広告グループを選択します。
   * キャンペーンフィルターを使用して、特定の広告グループに絞り込めます。
   * YouTubeチャンネルを追加する必要はありません。
5. アップロード対象に動画が含まれる場合は、その動画が子ども向けかどうかを選択します。
6. **すべてのクリエイティブ**セクションからクリエイティブを選択し、広告グループに割り当てます。
7. クリエイティブに複数のバージョンがある場合は、アップロードするバージョンを選択します。
8. 設定内容と、検証に関するメッセージがあればその内容を確認します。
9. **Google Adsにアップロード**をクリックします。

<Image alt="click Upload to Google Ads.png" src="https://files.readme.io/5280a1a396584e6874d8a2c24882fb9be4b25747d322fab607944da57a8fcdc9-48939152742545.png" width="100%" />

<div id="note" />

> 📘 **注意**
>
> 初めて大量にアップロードする前に、1つのクリエイティブでテストし、選択したメディアソースで正しく表示されることを確認するようお勧めします。

#### Meta Ads

Metaでは、既存の広告セット内に広告を作成できます。

1. ギャラリーからクリエイティブを選択します。
2. **メディアソースにアップロード**をクリックします。
3. Meta Adsを選択します。
4. アップロード先の詳細として、Metaの広告アカウントと広告セットを選択します。
   * キャンペーンフィルターを使用して、広告グループを絞り込めます。
5. 必要な数の新しい広告を作成します。
   * 複数の広告セットを選択した場合、各広告がそれぞれの広告セットに作成されます。
6. **すべてのクリエイティブ**セクションからクリエイティブを選択し、広告に割り当てます。
7. クリエイティブに複数のバージョンがある場合は、アップロードするバージョンを選択します。

<Image alt="Meta Ads.png" src="https://files.readme.io/56c387af74f4904921770abdee23e0d27a92e8f26c40d2d4fa46a4c42a4e2bb0-48939152743441.png" width="1838px" />

8. 設定内容と、検証に関するメッセージがあればその内容を確認します。
9. **次へ**をクリックします。
10. 広告単位の項目として、Facebookページ、Instagramプロフィール、メインテキスト、見出し、CTA、配信開始時のステータス、クリエイティブへのMetaのエンハンス機能の適用を許可するかどうかを設定します。
    * デフォルトでは、この設定は作成するすべての新しい広告に適用されます。**特定の広告をカスタマイズ**ドロップダウンから広告を選択すると、個別に編集できます。
11. **Metaで広告を作成**をクリックします。

<Image alt="image (55).png" src="https://files.readme.io/95125f551e731428a8d18a7ba1162246a867cdff4e0d34aee3950e08446c5eeb-48939152744209.png" width="1840px" />

#### TikTok Ads

TikTok Adsでは、既存のアプリプロモーション広告にクリエイティブをアップロードできます。

1. ギャラリーからクリエイティブを選択します。
2. **メディアソースにアップロード**をクリックします。
3. TikTokを選択します。
4. アップロード先の詳細として、TikTokの広告アカウントと広告を選択します。
   * キャンペーンと広告グループのフィルターを使用して、特定の広告に絞り込めます。
   * YouTubeチャンネルを追加する必要はありません。
5. **すべてのクリエイティブ**セクションからクリエイティブを選択し、広告に割り当てます。
6. クリエイティブに複数のバージョンがある場合は、アップロードするバージョンを選択します。
7. 設定内容と、検証に関するメッセージがあればその内容を確認します。
8. **TikTokにアップロード**をクリックします。

#### Unity Ads

<div id="note-1" />

> 📘 **注意**
>
> Unity Adsでは現在、Unityのクリエイティブライブラリへのアップロードにのみ対応しています。キャンペーンへの直接アップロードには、近日中に対応予定です。

1. ギャラリーからクリエイティブを選択します。
2. **メディアソースにアップロード**をクリックします。
3. **Unity Ads**を選択します。
4. クリエイティブを関連づけるアプリと、クリエイティブの言語（任意）を選択します。
5. クリエイティブに複数のバージョンがある場合は、アップロードするバージョンを選択します。
6. **Unity Adsにアップロード**をクリックします。

#### Mintegral

<div id="note-2" />

> 📘 **注意**
>
> Mintegralでは現在、Mintegralのクリエイティブライブラリへのアップロードにのみ対応しています。キャンペーンへの直接アップロードには、近日中に対応予定です。

1. ギャラリーからクリエイティブを選択します。
2. **メディアソースにアップロード**をクリックします。
3. **Mintegral**を選択します。
4. クリエイティブを関連づけるMintegralアカウントを選択します。
5. クリエイティブに複数のバージョンがある場合は、アップロードするバージョンを選択します。
6. **Mintegralにアップロード**をクリックします。

#### AppLovin

<div id="note-3" />

> 📘 **注意**
>
> AppLovinのキャンペーン管理APIを利用できるのは、一部の広告主に限られます。利用申請や対象条件の詳細については、AppLovinの担当者にお問い合わせください。

AppLovinでは、既存のクリエイティブセットにアップロードするか、新しいクリエイティブセットを作成できます。

1. ギャラリーからクリエイティブを選択します。
2. **メディアソースにアップロード**をクリックします。
3. AppLovinを選択します。
4. 新しいクリエイティブセットを作成するか、既存のセットにアップロードするかを選択します。

**新しいクリエイティブセットを作成するには：**

1. AppLovinアカウントを選択します。
2. クリエイティブセットを作成するキャンペーンを選択します。
3. クリエイティブセット名を入力します。
4. 配信開始時のステータスを選択します。
5. **追加**をクリックします。必要な数のクリエイティブセットを作成できます。
6. **すべてのクリエイティブ**セクションからクリエイティブを選択し、クリエイティブセットに割り当てます。
7. クリエイティブに複数のバージョンがある場合は、アップロードするバージョンを選択します。
8. 設定内容と、検証に関するメッセージがあればその内容を確認します。
9. **AppLovinにアップロード**をクリックします。

**既存のクリエイティブセットにアップロードするには：**

1. AppLovinアカウントを選択します。
2. アップロード先のクリエイティブセットを選択します。
   * キャンペーンフィルターを使用して、特定のクリエイティブセットに絞り込めます。
3. **すべてのクリエイティブ**セクションからクリエイティブを選択し、クリエイティブセットに割り当てます。
4. クリエイティブに複数のバージョンがある場合は、アップロードするバージョンを選択します。
5. 設定内容と、検証に関するメッセージがあればその内容を確認します。
6. **AppLovinにアップロード**をクリックします。

</Accordion>

<div id="review-upload-results" />

<Accordion title="アップロード結果の確認">

アップロードを開始すると、アップロードウィンドウは自動的に閉じます。その後もCreative Managementがバックグラウンドで処理を続けるため、ほかの作業を継続できます。

アップロード結果を確認するには、Creative Managementのギャラリーで**アップロード履歴**をクリックします。

アップロード履歴には、過去のアップロード処理と、その結果に関する以下の情報が表示されます。

* メディアソースとアップロード先。
* アップロードのステータス：成功、一部成功、失敗。
* 選択したクリエイティブの総数に対する、アップロード済みの数。
* アップロード完了時刻。
* 失敗したクリエイティブの詳細。

アップロードが一部成功または失敗で完了した場合、Creative Managementはアップロード履歴に通知を表示し、後から問題を確認できるようにします。詳細ビューには、失敗したクリエイティブとその理由が表示されます。

</Accordion>

<div id="creative-activity-status" />

<Accordion title="クリエイティブの配信状況">

クリエイティブのステータスによって、接続済みのメディアソースのどこで使用されているかを把握できます。

ギャラリーでは、各クリエイティブについて以下の状態を確認できます。

* **新規**：まだ配信されていないクリエイティブです。
* **配信中**：現在配信されているクリエイティブです。
* **配信停止中**：過去に配信されていましたが、現在は配信されていないクリエイティブです。

Creative Managementでは、配信中のクリエイティブが現在どこで使用されているかも把握できます。クリエイティブカードをクリックすると右側のパネルが開き、現在配信されているキャンペーンや広告グループを具体的に確認できます。

ステータス情報を使用して、以下のような点を判断できます。

* 次にアップロードすべき新しいクリエイティブはどれか。
* あるメディアソースで配信中で、別のメディアソースでもテストできるクリエイティブはどれか。
* 過去にテスト済みで、再配信する価値がありそうなクリエイティブはどれか。
* テストキャンペーンで配信中で、さらに多くのキャンペーンに展開すべきクリエイティブはどれか。

</Accordion>

<div id="traits-and-limitations" />

## 特性と制限

| 項目 | 説明 |
| --- | --- |
| 対象キャンペーン | Creative Managementは現在、アプリのプロモーションキャンペーンにのみ対応しています。 |
| 対応するストレージ | 現在、Google DriveとDropboxの保存先との同期に対応しています。 |
| アドネットワークごとに異なるアップロード先 | 対応するアップロード先と必須項目は、メディアソースごとに異なります。 |
| アドネットワークごとに異なるアップロード方法 | アップロード方法は、アドネットワークごとに異なります。  <br />Google Ads、Meta Ads、TikTokは、キャンペーンへの直接アップロード（広告またはクリエイティブセットとして）に対応しています。Unity AdsとMintegralは現在、各アドネットワークのクリエイティブライブラリへのアップロードにのみ対応しています。 |
| アセットの要件 | クリエイティブのファイル形式、寸法、再生時間、ファイルサイズは、各アドネットワークの要件を満たす必要があります。 |
| アップロード履歴の対象範囲 | アップロード履歴はアップロード結果を示すものであり、その後のクリエイティブの配信状況や審査状況は反映しません。 |

<div id="see-also" />

> 📄 **関連記事**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-guide">Creative Optimizationガイド</Anchor>

<div data-zendesk-anchors="about-creative-management=creative-management%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 get-started=%E3%81%BE%E3%81%9A%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01KXDN2V1R9SRPFSRGZZ4ZA62S=sync-creatives-from-the-creative-storage connect-google-drive=google-drive%E3%81%B8%E3%81%AE%E6%8E%A5%E7%B6%9A h_01KXDN2V1RGCDYJ074FV4KJY8T=google-drive%E3%81%B8%E3%81%AE%E6%8E%A5%E7%B6%9A connect-dropbox=dropbox%E3%81%B8%E3%81%AE%E6%8E%A5%E7%B6%9A h_01KXDN2V1R75971RE5ECTDM8TM=dropbox%E3%81%B8%E3%81%AE%E6%8E%A5%E7%B6%9A h_01KXDN2V1RAA882M55HK9152D6=browse-and-select-creatives filter-creatives=%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%81%AE%E7%B5%9E%E3%82%8A%E8%BE%BC%E3%81%BF h_01KXDN2V1RHJJZC67ZM84TNT0Y=%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%81%AE%E7%B5%9E%E3%82%8A%E8%BE%BC%E3%81%BF h_01KXDN2V1R8CXZ4XGTX656XRWF=upload-creatives-to-media-sources h_01KXDN2V1RE8748NWSCJP824PD=google-ads h_01KXDN2V1R31MABH1A3G0T9B84=%E6%B3%A8%E6%84%8F h_01KXDN2V1RG25RR7BXYAFVEAT7=meta-ads h_01KXDN2V1RBANB482286YP1QSY=tiktok-ads h_01KXDN2V1R52Y91AZNVGPPWW44=unity-ads h_01KXDN2V1RF9TZ25DFYQ91RVRC=%E6%B3%A8%E6%84%8F-1 h_01KXDN2V1REED32CRW83W7MMC9=mintegral h_01KXDN2V1SVWASV4KGJJ2VC162=%E6%B3%A8%E6%84%8F-2 h_01KXDN2V1RSFB2GHDPN95S90EJ=applovin h_01M1H2RMVW2CYMV7KBBSHJ9686=%E6%B3%A8%E6%84%8F-3 h_01KXDN2V1S8NZP8F4QN51NS3XP=review-upload-results h_01KXDN2V1SC0PHRY810NJG6QY3=creative-activity-status traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01KXDN2V1SDNR1Z5FTKEJNDZF3=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />
