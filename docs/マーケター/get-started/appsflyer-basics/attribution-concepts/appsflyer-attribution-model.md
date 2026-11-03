---
title: AppsFlyerのアトリビューションモデル
metadata:
  keywords:
    - Attribution
    - NativeTrack
    - Look-Back
    - Twiiter
    - Multi-Channel
    - Re-Install
    - Facebook
    - media source
    - Advertisers
    - Ad Networks
    - reinstall
    - branch
    - attribution determination
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T10:54:37Z'
  edited_at: '2026-10-28T09:07:38Z'
  id: 207447053
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/207447053
---
> **概要：** AppsFlyerは、アプリのインストールやリエンゲージメントにつながったメディアソースを特定し、AppsFlyerのアトリビューションモデルに基づいて、そのユーザー行動を当該メディアソースに紐付けます。

[![](https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png)](https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png)

## アトリビューションとは

**アトリビューション**とは、ユーザーがアプリをインストールしたきっかけや、インストール後にリエンゲージメント・リアトリビューションなどの行動を取ったきっかけを特定することです。アトリビューションの結果は、以下のいずれかに分類されます。

* **ノンオーガニックのメディアソース**：ユーザーがメディアソースに接触した場合です。通常は、広告の表示やクリックによる接触を指します。
* **オーガニック**：ユーザーがメディアソースに接触していない場合です。注意：説明を分かりやすくするため、ユーザーを*オーガニックとして計測した*と表現することがあります。ただし、厳密には正確な表現ではありません。オーガニックでインストールしたユーザーは、どのメディアソースにも紐付けられていないためです。

アトリビューションは、ユーザー獲得やリエンゲージメント施策と、その成果を最適化するために不可欠です。

## アプリのインストールとは

**アトリビューションモデル**とは、コンバージョンに至る経路の各接点に、イベントへの貢献をどのように割り当てるかを定めたルールです。アプリマーケティングに関わる各事業者は、それぞれ独自のアトリビューションモデルを持っています。Google Play、App Store、Apple、CTV・PC・コンソールのプラットフォーム、Meta adsやX Adsなどのアドネットワーク、モバイル計測事業者などが該当します。インストールやイベントの集計方法も、それぞれ異なります。

重要なのは、モデル間の違いよりも、ルールが明確で、公平に適用されていることです。これにより、広告主はキャンペーンを最適化し、獲得したユーザーの行動や成果の質を比較できます。

連携先の事業者が採用しているモデルとルールを理解することが重要です。特に、AppsFlyerがサポートするモデルと、各計測方法の細かな違いを理解することが大切です。

AppsFlyerでアトリビューションの対象となるのは、以下のイベントです。

* ユーザー獲得の場合：ユーザーがアプリをダウンロードして起動すると、**インストール**を記録し、その流入元を判定します。つまり、AppsFlyerでは、**アプリのインストール日時は初回起動の日時**を指します。一方、アドネットワークでは広告接触の日時、アプリストアではダウンロードの日時が使用されます。
* [リターゲティング](/docs/appsflyer-attribution-model#retargeting-attribution)の場合：
  * **リエンゲージメント**
  * **リアトリビューション**

## アトリビューション方法

AppsFlyerは、以下の表に示す複数のアトリビューション方法を使用しています。

<table><tbody><tr><td>方法</td><td>デバイスIDの使用</td><td>計測方式</td><td>アトリビューションの判定元</td><td>Android（Google Playおよびサードパーティのストア）</td><td>iOS</td><td>ユニバーサルWindowsプラットフォーム（UWP）</td><td>CTV・PC・コンソールのプラットフォーム（3）</td></tr><tr><td> <a href="#install-referrer-android-only">リファラ</a>（1）</td><td>いいえ</td><td>決定論的</td><td>AppsFlyer</td><td>はい（2）</td><td>いいえ</td><td>はい</td><td>いいえ</td></tr><tr><td> <a href="#device-id-matching">Device ID Matching</a>（1）</td><td>はい</td><td>決定論的</td><td>AppsFlyer</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td></tr><tr><td> <a href="#probabilistic-modeling">確率論的モデリング</a>（1）</td><td>いいえ</td><td>確率論的</td><td>AppsFlyer</td><td>はい</td><td>はい</td><td>いいえ</td><td>はい</td></tr><tr><td> <a href="#preload-campaigns">プリロード</a>（1）</td><td>いいえ</td><td>決定論的</td><td>AppsFlyer</td><td>はい</td><td>いいえ</td><td>はい</td><td>いいえ</td></tr><tr><td><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork (SKAN)</a></td><td>いいえ</td><td>決定論的</td><td>Apple</td><td>いいえ</td><td>はい</td><td>いいえ</td><td>いいえ</td></tr><tr><td> <a href="./apple-ads-integration-setup" target="_blank">Apple Search Ads</a> (1)</td><td>いいえ</td><td>決定論的</td><td>Apple</td><td>いいえ</td><td>はい</td><td>いいえ</td><td>いいえ</td></tr><tr><td> <a href="#deep-link">ディープリンク</a>（1）</td><td>いいえ</td><td>決定論的</td><td>AppsFlyer</td><td>はい</td><td>はい</td><td>はい</td><td>いいえ</td></tr><tr><td colspan="8">（1）AppsFlyerのダッシュボードやレポートでは、「Classic」のアトリビューション方法と表記されることがあります。<br/>（2）一部のサードパーティのストアで対応しています。<br/>（3）<a href="./ctv-pc-and-console-platform-attribution-concepts#サポートされているプラットフォーム" target="_blank">CTV・PC・コンソールのプラットフォーム一覧</a>をご覧ください。</td></tr></tbody></table>

### アトリビューション方法の判定優先順位

新規インストールに対して、有効な広告接触が複数ある場合、**AppsFlyerはインプレッションよりもクリックを、確率論的計測よりも決定論的計測を優先します**。各アトリビューション方法は、図に示す優先順位に従って適用されます。

[<Image alt="watefall.png" src="https://files.readme.io/8110571047a972a247d21d5b34d64c3afd010fd733f625ca1321cff93061e374-37555863998865.png" width="1378px" />](https://files.readme.io/8110571047a972a247d21d5b34d64c3afd010fd733f625ca1321cff93061e374-37555863998865.png)

以下では、AppsFlyerの各アトリビューションモデルについて詳しく説明します。

<div id="install-referrer-android-only" />

<Accordion title="インストールリファラ（Androidのみ）">

* AppsFlyerは、Google Playや一部のアプリストアからダウンロードされたAndroidアプリの流入元を、インストールリファラで判定します。リファラには、Androidのアプリストアにリダイレクトされる前にクリックされた元のURLが含まれます。これは、Androidのアトリビューションで主に使用される方法です。現在、Google Play、Huaweiのアプリストア、Samsung Galaxy Store、Xiaomi GetApps Storeが、インストールリファラによるアトリビューションに対応しています。<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">リファラを使用したサードパーティのアプリストアのアトリビューション</Anchor>をご覧ください。
* <Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#Meta_install_referrer_anchor">Metaインストールリファラ：AppsFlyer</Anchor>は、デバイスのローカルストレージから広告キャンペーンのメタデータを受け取ることで、AndroidアプリのMeta adsのアトリビューションに対応しています。このデータは、アトリビューション計測（Metaのオンデバイスアトリビューション）に使用されます。

</Accordion>

<div id="device-id-matching" />

<Accordion title="Device ID Matching">

従来のアトリビューション方法の一つです。ユーザーのデバイスにアクセスできるアドネットワークが、クリックURLにデバイスIDを含めてAppsFlyerに送信するか、インプレッションの配信をAppsFlyerに通知する際にデバイスIDを送信します。これにより、AppsFlyerはクリック時のデバイスIDと、AppsFlyer SDKが取得したデバイスIDをマッチングできます。

Device ID Matchingは、iOSのアトリビューションで主に使用される方法ですが、ATTへの同意が必要です。

使用できるIDは、以下のとおりです。

* **iOSデバイス**：IDFA、IDFV
* **Google Play開発者サービスを搭載したAndroidデバイス：** GAID
* **Google Play開発者サービスを搭載していないAndroidデバイス：** OAID、Android ID、IMEI、Fire ID

計測リンク内のデバイスIDは、SHA1またはMD5を使用してハッシュ化できます。

</Accordion>

<div id="device-id-matching-for-selfreporting-networks" />

<Accordion title="Self-Reporting NetworkのDevice ID Matching">

従来のアトリビューション方法の1つです。アプリの初回起動時に、AppsFlyerはアプリ設定を確認し、Meta広告、Snapchat、Google広告などの<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srn媒体">Self-Reporting Network</Anchor>（SRN）からのトラフィックが想定されるかを判断します。

デバイスIDを取得でき、iOSではATTへの同意が得られている場合、AppsFlyerは新規インストールの一意のデバイスIDを使用して、該当するSRNに問い合わせます。この問い合わせには、SRNが定義するモバイル計測パートナー（MMP）向けAPIを使用します。 AppsFlyerは、応答に基づいて新規ユーザーをSRNに紐付ける場合があります。

</Accordion>

<div id="probabilistic-modeling" />

<Accordion title="確率論的モデリング">

AppsFlyerは、アプリ開発者のマーケティングキャンペーンの成果をレポートするために、プライバシーを保護する統計的な手法として確率論的モデリングを使用しています。アプリ開発者向けに、キャンペーン単位で集計したパフォーマンスレポートを作成します。

**仕組みと特徴**

* 統計を使用し、一意のIDには依存しません。
* 広告、Webサイトのリンク、メール、QRコード、SMS、その他のオウンドメディアなど、開発者が自社アプリ向けに実施したマーケティングキャンペーンの後に、どれだけのインストールやエンゲージメントが発生したかを推定します。
* 集計レポートの作成に必要なシグナルのみを使用します。
* 出力されるのはキャンペーンのパフォーマンスレポートであり、個々のデバイスやユーザーを識別するものではありません。
* ルックバック期間内にリファラまたはIDマッチングを伴うクリックが発生した場合は、これらの決定論的なアトリビューション方法が優先されます。

</Accordion>

<div id="preload-campaigns" />

<Accordion title="プリロードキャンペーン">

工場出荷時またはデバイスのアクティベーション時に、プリロードパートナーがユーザーのデバイスにアプリをインストールするキャンペーンを対象とした、従来のアトリビューション方法です。プリロードパートナーには、以下のような事業者が含まれます。

* デバイスメーカー（OEM）
* アプリ発見プラットフォーム
* 携帯通信事業者

プリロードキャンペーンのアトリビューション方法は3種類あります。 3種類とも同時に使用でき、互いの仕組みに干渉することはありません。

以下の表では、3種類の方法と主な仕様をまとめています。各プリロード方法の詳細は、リンクをクリックしてご確認ください。

<table><thead><tr><th>プリロードのアトリビューション方法</th><th>利用シーン</th><th>デバイスのアクティベーションからアプリ起動までの情報\*</th><th>ルックバック期間\*\*</th><th>ローデータのマッチタイプ</th></tr></thead><tbody><tr><td> <a href="./set-up-appsflyer-preload-referrer-attribution" target="_blank">AppsFlyerリファラ</a>\*</td><td><ul><li>工場出荷時のプリロード</li><li>デバイスのアクティベーション時のプリロード</li></ul></td><td>はい</td><td><ul><li>最大180日</li><li>デフォルトは90日</li></ul></td><td><ul><li>プリロード：preload_rfr</li><li>クリックによるダウンロード：af_referrer</li></ul></td></tr><tr><td> <a href="./measure-preload-campaigns-with-google-play-install" target="_blank">Google Playの自動インストール</a>\*\*</td><td>デバイスのアクティベーション時のプリロード（Google Playのアプリ）</td><td>いいえ</td><td><ul><li>最大180日</li><li>デフォルトは90日</li></ul></td><td>preload_pai</td></tr><tr><td> <a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">システムプロパティまたはマニフェストによる工場出荷時のプリロード（Android）</a>\*\*</td><td><ul><li>工場出荷時のプリロード</li><li>デバイスのアクティベーション時のプリロード</li></ul></td><td>いいえ</td><td>制限なし</td><td>preload_conf</td></tr><tr><td colspan="5"><p>\* AppsFlyerリファラによるプリロードソリューションでは、デバイスの初回アクティベーションからアプリの初回起動までの状況を把握し、計測できます。これにより、特定のパートナーがアプリをプリロードした状態でアクティベーションされたデバイスの台数と、そのアプリが初めて起動されたタイミングを確認できます。</p><p>他の2種類の方法では、ユーザーがアプリを初めて起動した後にのみアトリビューションが確定するため、初回起動前にアプリがインストールされていたデバイスの台数は確認できません。</p><p>\*\* ユーザーが初めてデバイスの電源を入れてから、プリロードされたアプリを初めて起動するまでに、数日から数週間かかる場合があります。このため、AppsFlyerはプリロードキャンペーンのルックバック期間を長く設定し、アトリビューションの判定で最優先に扱います。</p></td></tr></tbody></table>

</Accordion>

<div id="deep-link" />

<Accordion title="ディープリンク">

リエンゲージメントのみを対象とした従来のアトリビューション方法です。この場合、ユーザーはアプリをダウンロードするためにアプリストアへリダイレクトされません。そのため、URL内の情報をクリックと、その後のアプリ起動に直接紐付けることができます。リエンゲージメントのアトリビューションに使用する情報がディープリンクURLに含まれているため、この方法は「ディープリンク」と呼ばれます。

</Accordion>

### メディアソースとAppsFlyerの機能別のアトリビューション方法

対応しているアトリビューション方法は、以下の条件によって異なります。詳細は、以降のセクションをご覧ください。

* メディアソース：オウンドメディアまたは有料媒体
* 使用するAppsFlyerの機能
* ユーザーのデバイス：AndroidまたはiOS

<div id="owned-media" />

<Accordion title="オウンドメディア">

<table><thead><tr><th rowspan="2">メディアソース</th><th rowspan="2">機能</th><th colspan="2">アトリビューション方法</th></tr><tr><th>Android</th><th>iOS</th></tr></thead><tbody><tr><td>オウンドメディア：メール（メール配信サービスを含む）、SMS、ソーシャルメディアへの投稿、インフルエンサー／アフィリエイト、印刷物など。</td><td><a href="./onelink-guide" target="_blank"><span>OneLink</span></a></td><td><ul><li>インストールリファラ</li><li>確率論的モデリング</li></ul></td><td>確率論的モデリング</td></tr><tr><td rowspan="2">有料またはオーガニックの流入がある、自社のモバイル向けWebサイト／ランディングページ</td><td><a href="./smart-banners-mobile-web-to-app-for-marketers" target="_blank">Smart Banners</a></td><td><ul><li>インストールリファラ</li><li>確率論的モデリング</li></ul></td><td>確率論的モデリング</td></tr><tr><td><a href="./onelink-smart-script-overview" target="_blank">OneLink Smart Script</a></td><td><ul><li>インストールリファラ</li><li>確率論的モデリング</li></ul></td><td>確率論的モデリング</td></tr><tr><td rowspan="2">自社のモバイルアプリ</td><td><a href="./user-invite-attribution" target="_blank">ユーザー招待／紹介</a></td><td><ul><li>インストールリファラ</li><li>確率論的モデリング</li></ul></td><td>確率論的モデリング</td></tr><tr><td><a href="./cross-promotion-attribution-for-marketers" target="_blank">クロスプロモーション</a></td><td><ul><li>インストールリファラ</li><li>Device ID Matching</li></ul></td><td>Device ID Matching（ATTへの同意が必要）</td></tr></tbody></table>

</Accordion>

<div id="paid-media" />

<Accordion title="有料媒体">

<table><thead><tr><th rowspan="2">メディアソース</th><th colspan="3">アトリビューション方法</th></tr><tr><th>Android</th><th>iOS</th><th><strong>CTV・PC・コンソールのプラットフォーム</strong></th></tr></thead><tbody><tr><td><a href="./self-reporting-networks-srns" target="_blank">SRNs</a></td><td>Device ID Matching</td><td><ul><li>Device ID Matching（ATTへの同意が必要）</li><li>SKAdNetwork（iOS 14以降）</li></ul></td><td>Device ID Matching</td></tr><tr><td><ul><li> <a href="./set-up-an-integrated-partner#attribution-link-tab" target="_blank">パートナー向け計測リンク</a>を使用するアドネットワーク（SRN以外） </li><li><span>CTV・PC・コンソールのプラットフォーム</span></li></ul></td><td><ul><li>インストールリファラ</li><li>Device ID Matching</li><li>確率論的モデリング</li></ul></td><td><ul><li>Device ID Matching（ATTへの同意が必要）</li><li>確率論的モデリング </li><li>SKAdNetwork（iOS 14以降）</li></ul></td><td> </td></tr><tr><td><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">デバイスにプリインストールされたアプリ</a></td><td>プリインストール</td><td>--</td><td> </td></tr></tbody></table>

</Accordion>

## ユーザーの広告接触に基づくアトリビューションの種類

AppsFlyerの各種キャンペーン計測方法を使用して、クリックスルーやビュースルーの広告接触に基づくアトリビューションを行います。

<div id="clickthrough-attribution" />

<Accordion title="クリックスルー計測">

多くのインストールは、バナー広告、動画広告、インタースティシャル広告などをユーザーがクリックした結果として発生します。

広告がクリックされると、クリックのルックバック期間が開始します。デフォルトの期間は7日です。ルックバック期間内のインストールはノンオーガニックとして、そのメディアソースに紐付けられます。ルックバック期間を過ぎてから発生したインストールは、オーガニックインストールとして扱われます。この状態を、オーガニックとして計測されると表現することもあります。

* クリックのルックバック期間を7日とすることが、業界標準とされています。メディアソースとの合意内容に合わせて、期間を設定してください。
* SRNのルックバック期間は、そのSRNが定めた期間に合わせてください。

<table><thead><tr><th rowspan="2"> <strong>アトリビューションの種類</strong> </th><th rowspan="2"> <strong>アトリビューション方法</strong> </th><th rowspan="2">設定範囲</th><th rowspan="2">デフォルト</th></tr></thead><tbody><tr><td rowspan="2"><p>クリックスルー</p><p>（すべての連携済みパートナー）</p></td><td>リファラ、IDマッチング</td><td>1～30日</td><td>7日</td></tr><tr><td>確率論的モデリング</td><td>0～24時間</td><td><ul><li>状況に応じて自動調整</li><li>AppsFlyerが決定</li></ul></td></tr></tbody></table>

<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">ルックバック期間の詳細</Anchor>

</Accordion>

<div id="viewthrough-attribution" />

<Accordion title="ビュースルー計測">

広告が表示されたもののクリックしなかったユーザーも、その広告を配信したアドネットワークの成果として計測できる場合があります。

ビュースルー計測のルックバック期間には、以下の特徴があります。

* クリックスルー計測の期間よりも短くなります。
* 期間を設定できます。

これは、動画広告のクリック率（CTR）が低い傾向にある動画アドネットワークで特に有用ですが、通常の広告を配信する従来のアドネットワークでも活用できます。

クリックとインプレッションの両方が発生した場合は、クリックがユーザーの能動的な接触であるため、**常にクリックが優先されます**。

<table><thead><tr><th><strong>アトリビューションの種類</strong></th><th><strong>アトリビューション方法</strong></th><th><strong>設定範囲</strong></th><th> <strong>デフォルト</strong><br/> </th></tr></thead><tbody><tr><td rowspan="2"><p>ビュースルー（<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">対応している一部の連携済みパートナー</a>）</p></td><td>IDマッチング</td><td>0～24時間</td><td>1日</td></tr><tr><td>確率論的モデリング</td><td>0～24時間</td><td><ul><li>状況に応じて自動調整</li><li>AppsFlyerが決定</li></ul></td></tr></tbody></table>

**ビュースルー計測を有効にするには、以下を設定します。**

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#ビュースルー計測のルックバック期間">設定画面</Anchor>でルックバック期間を設定します。

<Anchor target="_blank" href="/marketers/ja/docs/measure-view-through-engagements">ビュースルー計測の詳細</Anchor>

</Accordion>

<div id="engaged-click-attribution" />

<Accordion title="エンゲージクリック計測">

エンゲージクリックは、ユーザーが広告をクリックした後、アプリストアにリダイレクトされたりアプリが起動したりせず、同じ画面やコンテンツ内で広告への操作を続ける場合に発生します。例えば、プレイアブル広告内にとどまる、広告内の要素を操作する、広告の表示領域内でコンテンツの閲覧を続ける、といった行動が含まれます。詳細は、「<Anchor target="_blank" href="/marketers/ja/docs/about-enriched-engagement-types">拡張エンゲージメントタイプについて</Anchor>」をご覧ください。

* IDマッチングによるアトリビューションでは、エンゲージクリックのルックバック期間は1～7日です。デフォルトは2日です。
* 確率論的モデリングのルックバック期間は0～24時間です。デフォルトでは、状況に応じて自動調整されます。
* メディアソースとの合意内容に合わせて、期間を設定してください。
* エンゲージクリックは、一部の連携済みパートナーに対応しています。
* エンゲージクリックは、click-to-downloadおよびclick-to-appと同じアトリビューションの優先順位です。

| アトリビューションの種類 | アトリビューション方法 | 設定範囲 | デフォルト |
| --- | --- | --- | --- |
| エンゲージクリック（対応している一部の連携済みパートナー） | IDマッチング | 1～7日  <br />1～23時間 | 2日 |
|  | 確率論的モデリング | 0～24時間 | <ul><li>状況に応じて自動調整</li><li>AppsFlyerが決定</li></ul> |

<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">ルックバック期間の詳細</Anchor>

</Accordion>

<div id="engaged-view-attribution" />

<Accordion title="エンゲージビュー計測">

エンゲージビューは、ユーザーが広告をクリックせずに、一定時間を超えて動画を視聴したり、広告ユニットを操作したりするなど、所定の条件を満たす行動を取った場合に発生します。これらの行動はユーザーの意向を示すものであり、インストールのアトリビューションに使用されます。詳細は、「<Anchor target="_blank" href="/marketers/ja/docs/about-enriched-engagement-types">拡張エンゲージメントタイプについて</Anchor>」をご覧ください。

* エンゲージビューのルックバック期間は、決定論的アトリビューションと確率論的アトリビューションのどちらも0～24時間です。
* 決定論的計測のルックバック期間のデフォルトは2日です。
* エンゲージビューは、一部の連携済みパートナーに対応しています。
* エンゲージビューは、エンゲージクリックおよびclick-to-appと同じアトリビューションの優先順位です。

| アトリビューションの種類 | アトリビューション方法 | 設定範囲 | デフォルト |
| --- | --- | --- | --- |
| エンゲージビュー（対応している一部の連携済みパートナー） | IDマッチング | 1～7日  <br />1～23時間 | 2日 |
|  | 確率論的モデリング | 0～24時間 | <ul><li>状況に応じて自動調整</li><li>AppsFlyerが決定</li></ul> |

**エンゲージビュー計測を有効にするには、以下を設定します。**

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#ビュースルー計測のルックバック期間">設定画面</Anchor>でルックバック期間を設定します。

<Anchor target="_blank" href="/marketers/ja/docs/measure-view-through-engagements">ビュースルー計測の詳細</Anchor>

</Accordion>

## アトリビューションに関する詳細

<div id="in-app-events" />

<Accordion title="アプリ内イベント">

AppsFlyerは、アプリのインストール、再インストール、リアトリビューションの計測に使用したデバイスIDまたは一意のAppsFlyer IDを使い、**アプリ内イベントをメディアソースに紐付けます**。広告主は、この情報を使用して、アプリのローデータでユーザージャーニーを確認できます。集計データでは、デバイスIDまたはAppsFlyer IDを使用して、アプリ内イベントを実行したユニークユーザー数などを算出します。

イベントのアトリビューションの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview?query=in%20app%20event#how-does-appsflyer-attribute-events">こちら</Anchor>をご覧ください。

</Accordion>

<div id="assisted-installs" />

<Accordion title="アシストインストール">

AppsFlyerは、インストール1件につき1つのメディアソースのみに成果を紐付けます。通常は、最後の広告クリック、またはクリックがない場合は最後の広告インプレッションを使用します。

アシストインストール（マルチタッチアトリビューションとも呼ばれます）とは、最後の接点ではないものの、アトリビューションのルックバック期間内にユーザーに接触し、インストールに貢献したメディアソースやキャンペーンがあるインストールです。

アシストしたアドネットワークは、AppsFlyerでインストールの貢献元として表示されます。

詳細は、<Anchor target="_blank" href="/marketers/ja/docs/measure-assisted-installs">こちら</Anchor>をご覧ください。

</Accordion>

<div id="reinstalls" />

<Accordion title="再インストール">

再インストールとは、ユーザーがアプリをインストールし、アンインストールした後に、再度インストールすることです。再インストールのアトリビューションは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>に基づいて、以下のように判定されます。

* リアトリビューション期間の終了後に再インストールした場合：新規インストールとして記録されます。
* リアトリビューション期間内に再インストールした場合：以下のいずれかが適用されます。
  * 再インストール前にリターゲティングキャンペーンに接触していた場合：<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティングによる再インストール</Anchor>（リアトリビューションとも呼ばれます）として記録されます。
  * キャンペーンに接触していない場合、またはユーザー獲得（UA）キャンペーンに接触していた場合：インストールは記録されません。これらのユーザーによる再インストール後のアプリ内イベントは、<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#overview">**再インストール後のイベントのアトリビューション**</Anchor>の設定に応じて、オーガニックまたは元のインストールに紐付けられます。

デバイスのテストや複数回のインストールを行う場合は、AppsFlyerにデバイスを<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">登録</Anchor>してください。デバイスを登録しない場合は、最初のインストールのみが記録されます。

AppsFlyerでは、広告IDがないiOSの再インストールについても、アトリビューションの精度を高められます。この機能は、<Anchor target="_blank" href="/marketers/ja/docs/app-settings#reinstall-detection-using-ondevice-storage-ios-only">アプリ設定ページ</Anchor>で有効にできます。

#### iCloudにバックアップされたiOSアプリの再インストール

iCloudにバックアップされたアプリを、同じデバイスまたは別のデバイスに復元した場合、AppsFlyerは新規インストールや再インストールとして集計しません。 iCloudからアプリを復元したユーザーのAppsFlyer IDとアトリビューションデータは維持されます。

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="リターゲティング計測">

![Retargeting_-_Flow__2_.png](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>内（デフォルトは90日）にアプリを再インストールしたユーザーは、リアトリビューションとして扱われます。リターゲティングキャンペーンへの接触後にこのインストールが発生した場合は、リターゲティングによる再インストール（リアトリビューション）として記録され、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティング</Anchor>のレポートに表示されます。

</Accordion>

<div id="app-updates" />

<Accordion title="アプリのアップデート">

* AppsFlyerですでに計測している既存ユーザーがアプリを新しいバージョンにアップデートしても、新たなアトリビューションイベントとしては数えません。注意：他のMMPからAppsFlyerに移行した場合、既存ユーザーによる移行後の初回アプリ起動は、オーガニックとして計測されます。
* アプリのバージョン別ユーザー数に関する指標は、<Anchor target="_blank" href="/marketers/ja/docs/sdk-information-version-consent-dashboard">SDK情報ダッシュボード</Anchor>で確認できます。

</Accordion>

<div data-zendesk-anchors="what-is-attribution=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8%E3%81%AF 01H8GG9XPSS8KA9CHPD6ECNR2J=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8%E3%81%AF what-is-an-app-install=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%81%AF 01EDRHGMTXK94Y97DPKFAMCJ5B=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%81%AF attribution-methods=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%96%B9%E6%B3%95 01EDRHGMTXCRNVXS9JGHQ1JAQT=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%96%B9%E6%B3%95 attribution-waterfall=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%96%B9%E6%B3%95%E3%81%AE%E5%88%A4%E5%AE%9A%E5%84%AA%E5%85%88%E9%A0%86%E4%BD%8D h_01JBC8582ABTE00W29PM5Y5X0B=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%96%B9%E6%B3%95%E3%81%AE%E5%88%A4%E5%AE%9A%E5%84%AA%E5%85%88%E9%A0%86%E4%BD%8D 01H8GG9XPS6P3CXX5AN2KY8WN4=install-referrer-android-only 01H8GG9XPSGVK90FV0K9HZARH7=device-id-matching 01H8GG9XPSV247F3JRCR870JK0=device-id-matching-for-selfreporting-networks 01EDRHGMTXHAKWZK99Q2X86BND=probabilistic-modeling 01H8GG9XPSZ5CPKNSCV7NF1MKW=preload-campaigns h_01K0XWKWQ7TJ2DBT1JZPY5Q4F6=deep-link attribution-methods-per-media-source-and-appsflyer-feature=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A8appsflyer%E3%81%AE%E6%A9%9F%E8%83%BD%E5%88%A5%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%96%B9%E6%B3%95 01H8GG9XPTXDR41QANF4XVSZMM=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A8appsflyer%E3%81%AE%E6%A9%9F%E8%83%BD%E5%88%A5%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%96%B9%E6%B3%95 01H8GG9XPT65G88DE8548HZREE=owned-media 01H8GG9XPTADWMQ37WBB6P9WVS=paid-media user-engagement-attribution-types=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E5%BA%83%E5%91%8A%E6%8E%A5%E8%A7%A6%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E7%A8%AE%E9%A1%9E 01EDRHGMTX7851H14R20F9KNAN=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E5%BA%83%E5%91%8A%E6%8E%A5%E8%A7%A6%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E7%A8%AE%E9%A1%9E 01EDRHGMTXJ7WKTWQXFCHTD9AV=clickthrough-attribution 01EDRHGMTXN0Y0ZRVBX7HHW7NN=viewthrough-attribution h_01K0XYZWBVPSXT0T6XGPQT20X8=engaged-view-attribution advanced-attribution-topics=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E8%A9%B3%E7%B4%B0 01EDRHGMTYYXBSCDPKXCDK1641=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E8%A9%B3%E7%B4%B0 01EDRHGMTYMH3SVNBTQ28D4F42=in-app-events h_01K0XWKWQ7J20YKEND9A43DRNR=assisted-installs 01EDRHGMTY2CF0B70T3RAGPCJ1=reinstalls reinstalling-ios-apps-that-are-backed-up-in-icloud=icloud%E3%81%AB%E3%83%90%E3%83%83%E3%82%AF%E3%82%A2%E3%83%83%E3%83%97%E3%81%95%E3%82%8C%E3%81%9Fios%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB 01EDRHGMTYDSNJKQNPNYFXJPAZ=icloud%E3%81%AB%E3%83%90%E3%83%83%E3%82%AF%E3%82%A2%E3%83%83%E3%83%97%E3%81%95%E3%82%8C%E3%81%9Fios%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB 01EDRHGMTYYB9XVM5CBWSPJGMN=retargeting-attribution 01EDRHGMTYTQRMG1W7ZBW4G6W4=app-updates" />
