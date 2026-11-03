---
title: CTV、PC、コンソールプラットフォームのアトリビューションの概念
metadata:
  keywords:
    - Attribution
    - Advertisers
    - Developers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-15T11:30:45Z'
  edited_at: '2026-10-14T09:27:16Z'
  id: 4404083608849
  locale: ja
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ja/articles/4404083608849
---
> **概要：** CTV、PC、コンソールプラットフォームでアトリビューションがどのように機能するかを学び、AppsFlyer がこれらのクロスプラットフォームデバイスでキャンペーンのアトリビューションとイベントデータを受信できるようにします。

<Image alt="7435_CTV_image.png" src="https://files.readme.io/7fc57fd80ad86bb173bcf81581b9fe8b4625ed2a044d302a6d72194560019e81-4410336840977.png" width="471px" />

## AppsFlyerのクロスプラットフォームソリューション

多くのがマーケターは、今日のデジタル環境において 複数のデバイスやプラットフォームで消費者にリーチするという課題に直面しています。従来の計測アプローチでは、複数のプラットフォームにまたがるユーザージャーニーの全容を十分に捉えることができません。クロスプラットフォームの計測は、マーケティング活動の影響を理解し、情報に基づいた意思決定を行うために不可欠です。

AppsFlyerは、従来のモバイルアトリビューションツールを補完する広範なクロスプラットフォームソリューションを提供しています。これは、ユーザーが複数のプラットフォームやデバイスを用いる際に、グロースの専門家がマーケティング活動を正確に測定し、属性付けるのに役立ちます。このソリューションは、CTV、PC、およびコンソールプラットフォームに焦点を当てています。

広告主は、広告が表示される同一の、または異なるプラットフォーム上でアプリをプロモーションできます。例えば、広告主はSteamのプラットフォーム上でSteamアプリの広告を表示することができます。または、デスクトップのウェブ（Google Adsなど）に Steamアプリの広告を配信することもできます。<span id="tv-screens"></span>CTVキャンペーンでは、特にテレビの画面やテレビのようなディスプレイで広告を配信します。

マーケティング戦略が何であれ、CTV、PC、コンソールプラットフォームのアプリインストールとインストール後のイベントを促進するソース（非オーガニックまたはオーガニック）とキャンペーンに関するアトリビューションデータとパフォーマンスの計測を受信するために、広告主はAppsFlyerと連携します。マーケターはこれらのインサイトを使用して LTV（顧客生涯価値）を計算し、マーケティング活動を測定および最適化します。<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">AppsFlyer のアトリビューションについて詳しくはこちらをご覧ください</Anchor>

### サポートされているプラットフォーム

<table><thead><tr><th>プラットフォーム</th><th colspan="2">AppsFlyerとの連携方法</th></tr><tr><th> </th><th>S2S</th><th>SDK</th></tr></thead><tbody><tr><td>Android TV</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>tvOS (Apple TV)</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>MacOS</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Amazon Fire TV</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Chromecast</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Roku</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Vizio</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Samsung</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>LG</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>PlayStation</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Vidaa</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Steam</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Native PC</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Meta Quest (Oculus)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Epic Games</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Nintendo Switch</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Xbox</td><td><span>✓</span></td><td><span>-</span></td></tr></tbody></table>

### **クロスプラットフォームアトリビューションをサポートするアドネットワークを選択**

CTV、PC、コンソールのプラットフォームに広告を表示し、クロスプラットフォームアトリビューション（CTVからモバイルアプリなど）をサポートしているアドネットワークの一覧は、 <Anchor target="_blank" href="https://hq1.appsflyer.com/partner-marketplace/explore?integrationLevels=CROSS_PLATFORM">AppsFlyerパートナーマーケットプレイス</Anchor>で確認できます。

確認するには：

1. AppsFlyer管理画面左メニュー **連携** > **パートナーマーケットプレイス**へ移動します。
2. **対応機能**フィルターをクリックし、**クロスプラットフォーム**を選択します。

### 特定のCTV / PC / コンソールプラットフォームに対応するアドネットワークを選択

特定のCTV、PC、コンソールプラットフォームに広告を表示できるアドネットワークのリストは、 <Anchor target="_blank" href="https://hq1.appsflyer.com/partner-marketplace/explore?supportedPlatforms=EPIC%2CNATIVEPC%2CPLAYSTATION%2CQUEST%2CSTEAM%2CSWITCH%2CXBOX">AppsFlyerパートナーマーケットプレイス</Anchor>をご覧ください。

確認するには：

1. AppsFlyer管理画面左メニュー **連携** > **パートナーマーケットプレイス**へ移動します。
2. **対応機能**フィルターをクリックし、CTV / PC / コンソール を選択します。

## クロスプラットフォームのアトリビューション計測フロー

CTV、PC、コンソールプラットフォーム上でアプリをマーケティングする場合、—広告の表示（インプレッションまたはクリック）からAppsFlyerのアトリビューションまで—、すべてのプラットフォームに適用されるいくつかのフローがあります：

* ダイレクト計測リンク
* クロスプラットフォームのOneLinkリンク
* SRN（セルフレポーティングネットワーク、またはSAN：セルフアトリビューションネットワーク）
* クロスプラットフォームのランディングページ

各アプリ、広告主、プラットフォームには、同時に実行されるフローが1つ以上あります。以下のセクションでは、様々なフロータイプと、各フローがいつ使用されるかについて説明します。

<div id="direct-attribution-link" />

<Accordion title="ダイレクト計測リンク">

ダイレクト計測リンクは、一度に１つのプラットフォーム上の１つのリンク先を持つアプリに対するリダイレクトとアトリビューションをサポートする、AppsFlyer のリンクです。これらは通常、次の目的で使用されます：

* 同じプラットフォームから同じプラットフォームへの広告。つまり、広告を表示するプラットフォームとアプリをサポートするプラットフォームは同一です。例えば、広告主はSamsung TV アプリの広告を Samsung TV に表示できます。
* リンク先・プラットフォームが事前に決定された、あるプラットフォームからあるプラットフォームへの広告。例えば、デスクトップのウェブランディングページには、特定のプラットフォームストア・マーケットプレイスにリダイレクトされている１つ以上のボタンを含む広告が表示されます。

ダイレクト計測リンクは、確率論的モデリングと決定論的マッチング（リンクにIDが提供されている場合）の両方の計測方法をサポートしており、1人のユーザーによる1つのインストールが広告のクリックまたはインプレッションと照合されます。アトリビューションフローを次の図で説明します。

![CTV attribution flow - Direct attribution link flow.png](https://files.readme.io/2af32b096faa381843040314c9c183056256d03a7e2e6095e72a59bb7211727f-19374976446225.png)

ダイレクト計測リンクは、特定の事前に決められたプラットフォーム上のアプリ用であり、１つの特定のリンク先に繋がるため、URLには常にアプリIDとプラットフォームの情報が含まれています。

ダイレクト計測リンクのサンプル：`https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/1234561?&af_media_source=game_media_source&af_campaign=campaign_yellow&af_campaign_id=1234&af_ad=game_ad_name&af_adset=game_adset_name&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F1176160%2FSpace_Wars%2F`

<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links#計測リンク">ダイレクト計測リンク設定の方法はこちら</Anchor>。

</Accordion>

<div id="crossplatform-onelink" />

<Accordion title="クロスプラットフォームのOneLinkリンク">

クロスプラットフォームの OneLink リンクは、広告プラットフォームとリンク先プラットフォームが異なる場合のリダイレクトとアトリビューションに対応しています。これらは、様々なプラットフォームが選択肢に挙がる場合に使用されます。例えば、CTV からモバイルへのフローでは、広告は Roku プラットフォーム・デバイス上に表示されますが、リンク先は Android・iOS アプリにすることができます。別の例として、デスクトップのウェブからコンソールへのフローでは、広告はデスクトップウェブ上に表示されますが、ゲームは PC や PlayStation、Xbox、Steam などの複数のコンソールプラットフォームで利用できます。

クロスプラットフォームの OneLink リンクは、確率論的モデリングアトリビューション方法（IPアドレスに基づく）のみに対応しています。このため、複数のユーザーによる複数のインストールは、同一のインプレッションとして計測される可能性があります。アトリビューションフローを次の図で説明します。

![CTV attribution flow - Cross-platform Onelink link attribution flow (1).png](https://support.appsflyer.com/hc/article_attachments/51909661153809)

可能なすべてのアプリのリンク先・プラットフォームは、OneLink テンプレートで設定されます。そのため、クロスプラットフォームの OneLink リンクには、URL に特定のアプリIDや特定のプラットフォーム情報が含まれていません。代わりに、可能なすべてのアプリのリンク先・プラットフォームが設定されているテンプレート ID が、URL に含まれています。

クロスプラットフォーム OneLink リンクのサンプル：`https://impressions.onelink.me/ch/AG7A?pid=game_media_source&c=game_landing_page&af_ad=game_ad_name&af_adset=game_adset_name&af_xplatform=true`

<Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns">クロスプラットフォームの OneLink リンクの設定方法はこちら</Anchor>

</Accordion>

<div id="srn" />

<Accordion title="SRN （サーバー連携媒体）">

ダイレクト計測リンクとクロスプラットフォームのOneLinkリンクを使用して、AppsFlyerではURLに含まれるデータを介してインストール数がアトリビューションされます。対照的に SRNs （セルフレポーティングネットワーク、または SANs：セルフアトリビューティングネットワーク）は、AppsFlyer からインストールが通知されるとデバイス ID を使用して自己アトリビューションします。

SRNへのアトリビューションは、決定論的マッチングによって行われます。広告主が SRN と連携すると、アトリビューションは次の図のように機能します。

![CTV attribution flow - SRN attribution flow (1).png](https://files.readme.io/ba0d84643aefd6a20e95c8aca9424affea8169c95ccc428ddf3d35bb8787a67c-19374961372945.png)

現時点で SRN アトリビューションは、同じプラットフォームから同じプラットフォームへの広告でのみ機能します。つまり、タッチポイント（クリックまたはインプレッション）がインストールと同じプラットフォームで発生する場合です。例えば、Roku CTVのインストールが Roku Endemic Media（RokuのSRN）で確認され、Roku デバイスでインプレッションが発生していることが判明した場合です。インプレッションがモバイルなど別のプラットフォームで発生した場合、アトリビューションの対象にはなりません。

将来的には、SRN アトリビューションがあらゆるプラットフォームからあらゆるプラットフォームへの広告で利用できるようになり、より包括的なクロスプラットフォームアトリビューションが可能になるかもしれません。

</Accordion>

<div id="landing-page" />

<Accordion title="クロスプラットフォームのランディングページ">

クロスプラットフォームのランディングページは、一般的なクロスプラットフォームのユーザージャーニーとマーケティングフローに対応するように設計されています。これらは、ゲームアプリで最も一般的に使用されます。ランディングページは、AppsFlyer のスマートスクリプトを実行して、Web からアプリへのアトリビューションを実行します。つまり、あらゆるプラットフォーム（CTV、PC、コンソール、モバイルプラットフォームなど）でのインストールを、ウェブに表示される広告にアトリビューションします。

クロスプラットフォームのランディングページにおけるスマートスクリプトは、受信リンク（ウェブ広告上のリンク）を使用して、元のメディアソースとウェブ広告がインストールにアトリビューションされるように、次の2つのことを実行します：

* AppsFlyerにインプレッションを送信するクロスプラットフォームのOneLinkリンクを作成します。これにより、AppsFlyerはインプレッションを記録して、後でユーザーインストールのアトリビューションに使用することができます。インプレッションは、ランディングページが開いたときに送信されます。ユーザーがどのボタンもクリックせずにランディングページを離れ、自分でアプリをダウンロードしてインストールした場合でも、インプレッションはアトリビューションされます。
* アプリ・プラットフォームごとにダイレクト計測リンクを作成します。ユーザーがこれらのリンクをクリックすると、正しいプラットフォーム・アプリストアに移動します。その後、ユーザーがアプリをダウンロードしてインストールすると、インストールはクリックに結び付けられます。

ランディングページは、確率論的モデリングと決定論的マッチング（リンクでIDが指定されている場合）の両方のアトリビューション方法に対応しています。確率論的モデリングでは、複数のユーザーによる複数のインストールを同じインプレッションに結び付けることができます。アトリビューションフローを次の図で説明します。

![CTV attribution flow - Landing page attribution flow.png](https://files.readme.io/28e4d14d14532332027e5d429ac3f95c8d4d451d94125e399cfb9ad04727b278-19374961376529.png)

例：

1. デスクトップ、モバイル、Epic、またはSteam プラットフォームでダウンロードしてプレイできるゲームアプリがあるとします。
2. ウェブ上で広告を掲載します。
3. ユーザーは、 有料検索結果やソーシャルメディアのプロモーションなど、ウェブ上で広告を目にします。
4. ユーザーが広告をクリックすると、個々のプラットフォーム（デスクトップ、モバイル、Epic、Steam）ごとにダウンロードボタンがあるランディングページにリダイレクトされます。
5. ランディングページでは AppsFlyer のスマートスクリプトが実行され、以下の機能が実行されます：
6. 受信リンク（ユーザーをウェブからランディングページに誘導するリンク）から、メディアソース、キャンペーン、広告などを識別するクエリや UTM パラメーター、デフォルト値などの重要なデータポイントを取得します。
7. 上記のデータポイントを使用してインプレッションを生成し、AppsFlyer に送信します。
8. 各プラットフォームのダウンロードボタンの発信リンクを生成します。
9. ユーザーがダウンロードボタンの1つをクリックすると、プラットフォームアプリストアに移動し、アプリをダウンロードして開きます。
10. アプリのインストール数や初回起動数はインプレッション数と照合され、ウェブ上で元の広告を表示したメディアソースに関連付けられます。

追加情報：

* <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">クロスプラットフォームのランディングページの例を確認する</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/cross-platform-landing-pages-with-smart-script">スマートスクリプトでクロスプラットフォームのランディングページを設定する方法はこちら</Anchor>

</Accordion>

## データの可用性

CTV、PC、コンソールプラットフォームのデータには、非オーガニックユーザーおよびオーガニックユーザーのLTV（顧客生涯価値）に関するインサイトを広告主に提供するインストールデータとアプリ内イベントデータが含まれており、これらはサブスクリプション、アプリ内購入、広告収益化に基づいています。 LTV指標は、アトリビューション日から現在までの期間で計算されます。

データは次のように利用できます：

* 集計データ - オーバービュー経由
* ローデータ：
  * <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-data-via-data-locker">Data Locker</Anchor>
  * <Anchor target="_blank" href="/marketers/ja/docs/raw-data-export-page">ローデータ出力画面</Anchor>
  * <Anchor target="_blank" href="/marketers/ja/docs/pull-api-raw-data">Pull API</Anchor>
* **クロスプラットフォームのインプレッション**は、アプリレベルのダッシュボードには表示されません。ただし、Data Lockerの<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-data-via-data-locker">クロスプラットフォームエンゲージメントレポート</Anchor>で使用できます。

**注：** Android および iOS オペレーティングシステムを搭載したプラットフォームでは、<Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">集計</Anchor>および<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータ</Anchor>レポートを利用できるかどうかはモバイルアプリの場合と同じです。

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| リアトリビューション期間 | CTV、PC、コンソールプラットフォームの場合、リアトリビューション期間は決められた非アクティブ期間（デフォルトは90日間）に基づきます。 |
| 再インストール後のイベント | 初回インストールのメディアソースに紐づきます。<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#attributed-to-the-first-install">詳細はこちら</Anchor> |
| リターゲティング | <ul><li>リアトリビューション：クロスプラットフォームからモバイルまでサポートしています。他のプラットフォームには対応していません。</li><li>リエンゲージメント：サポートされていません</li></ul> |
| アトリビューション方法 | <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#アトリビューション方法">CTV、PC、コンソールプラットフォームのアトリビューション方法</Anchor> |
| 通貨設定 | USDまたは「アプリ設定」画面で設定された通貨 |
| タイムゾーン | UTC |
| コストデータ | CTV、PC、コンソールプラットフォーム上のアプリの場合、コストデータは、メールによるファイルのアップロードを使用して、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">コストインポート</Anchor>機能経由で送信する必要があります。 |

</Accordion>

<div data-zendesk-anchors="about-ctv-attribution=appsflyer%E3%81%AE%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 01H7ZRK7PCNZG54ZQ0804HMR38=appsflyer%E3%81%AE%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 list-of-supported-ctv-and-gaming-device-types=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0 01H7ZRK7PCP1KWRX1A5K81F4KR=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8B%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0 list-of-supporting-ad-networks=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%82%92%E9%81%B8%E6%8A%9E h_01J2XT3HFBYD7KX47E6NRP2XZ2=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%82%92%E9%81%B8%E6%8A%9E list-of-specified-platforms=%E7%89%B9%E5%AE%9A%E3%81%AEctv--pc--%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AB%E5%AF%BE%E5%BF%9C%E3%81%99%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%82%92%E9%81%B8%E6%8A%9E h_01JMA8F9F6M2MZFNRXFQWJF8B8=%E7%89%B9%E5%AE%9A%E3%81%AEctv--pc--%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AB%E5%AF%BE%E5%BF%9C%E3%81%99%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%82%92%E9%81%B8%E6%8A%9E crossplatform-attribution=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%83%95%E3%83%AD%E3%83%BC 01H8EHHJNBA8NKMX2C8RSV7P31=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%83%95%E3%83%AD%E3%83%BC 01H8EQ4KS75Q62Z7WVNSTDXBZX=direct-attribution-link 01H8EQ4KS7C6HADNKQZYNTTFMF=crossplatform-onelink 01H8EQ4KS7NVYAD6MQ6MM26AVW=srn h_01JMA8F9F62BQ0P90RJ3EECS13=landing-page data-availability=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01H9G52NKMQG9QD9S3N537BM7N=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E7%94%A8%E6%80%A7 01H7ZRK7PCJ6BRQZ2AKQTV5Q5E=traits-and-limitations" />
