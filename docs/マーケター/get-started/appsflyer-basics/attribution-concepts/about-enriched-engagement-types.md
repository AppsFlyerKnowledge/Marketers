---
title: 拡張エンゲージメントタイプについて
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-01-21T13:45:23Z'
  edited_at: '2026-10-28T09:07:21Z'
  id: 21837486015889
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/21837486015889
---
> **概要：** 広告の種類が高度化・複雑化する一方、レポートの対象は依然として限定的で、ビュースルーとクリックスルーのアトリビューションにとどまっていました。拡張エンゲージメントタイプは、広告の閲覧や操作を通じてユーザーが示す、さまざまな関わり方や関心の強さを計測に反映し、この課題を解消します。

## はじめに

近年、プレイアブル広告、スキップ可能な広告、短尺動画広告など、新たなクリエイティブ形式が登場し、ユーザーとの接点が広がっています。これらは従来の静止画バナーや簡素な動画広告とは大きく異なり、広告主が利用できる機能やフォーマットの幅を広げています。

しかし、広告の種類が高度化・複雑化し、双方向性が高まっているにもかかわらず、レポートの対象は依然として限定的で、ビュースルーとクリックスルーのアトリビューションにとどまっています。広告接触の種類によって重要度、ユーザーの関心の強さ、効果は異なりますが、従来の計測方法では、こうした変化を十分に捉えられていません。アドネットワークは、それぞれの方法でユーザーの関心やエンゲージメントの度合いをできる限り適切に反映しようとしているため、業界全体で基準が統一されていない状況です。その結果、広告主は広告費に対する成果を部分的にしか把握できていません。

AppsFlyerは、主要なアドネットワークと協力し、業界全体の信頼性と透明性を高めるため、エンゲージメントの共通基準を導入します。拡張エンゲージメントタイプは、一瞬の広告表示から直接的な反応まで、広告の閲覧や操作を通じてユーザーが示す、さまざまな関わり方や関心の強さを反映します。この仕組みにより、AppsFlyerのパートナーエコシステムとその枠を超えた領域で、共通基準の維持を図ります。広告主は拡張エンゲージメントタイプを通じて、広告費に対する成果を統一された基準で詳しく把握し、その知見を予算配分の改善やROASの向上に活用できます。

## 拡張エンゲージメントタイプとは

拡張エンゲージメントタイプ（EET）は、関心を伴う広告閲覧（例：スキップボタンの表示後もスキップ可能な動画広告を5秒以上視聴する場合）や、アプリ起動・アプリストアへの移動以外につながるクリックを区別し、ユーザージャーニーの細かな違いを可視化する仕組みです。マーケターはユーザーの行動をより深く理解し、予算配分の最適化やROIの改善につなげられます。

拡張エンゲージメントタイプの一覧は以下のとおりです。

| engagement\_type | 説明 |
| --- | --- |
| <span id="preload"></span>preload | OEMが工場でアプリをプリロードするか、デバイスの初回有効化時にプロバイダーがプリロードします。または、デバイスの初回有効化時に、ウィザードがアプリのダウンロードを促します。 |
| <span id="click_to_download"></span>click\_to\_download | ユーザーが広告に反応すると、アプリストアを経由せずにアプリが自動的にダウンロードされ、デバイスにインストールされます。 |
| <span id="click_to_app"></span>click\_to\_app | 広告クリック、QRコードのスキャン、ディープリンクなど、アプリへの移動や、アプリをダウンロードするためのアプリストアへの移動につながるクリックです。 |
| <span id="engaged_click"></span>engaged\_click | アプリストアに移動したりアプリを起動したりせず、同じ画面やコンテンツ内で広告を操作するクリックです。 |
| <span id="engaged_view"></span>engaged\_view | スキップ可能な動画、リワード動画、StoreKitで表示される広告で、関心を示す閲覧が行われた場合にエンゲージビューとして計測されます。たとえば、スキップ可能な動画広告で、スキップボタンの表示後も5秒以上視聴する場合です。 |
| <span id="view"></span>view | 広告が画面に表示され、インプレッションが発生した状態です。 |
| <span id="listening"></span>listening | ポッドキャスト広告などの音声広告をユーザーが聴くことです。 |

## **EETのアトリビューションの優先順位とルックバック期間**

拡張エンゲージメントタイプは、エンゲージメントタイプごとのアトリビューションの優先順位を変更するものではありません。そのため、EETの導入によって、インストールやコンバージョン率への影響が生じることは想定されていません。

各エンゲージメントタイプの<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#アトリビューション方法の判定優先順位">アトリビューションの優先順位</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows#ルックバック期間">ルックバック期間</Anchor>を以下の表に示します。

<table><thead><tr><th>エンゲージメント</th><th>エンゲージメントタイプ</th><th>アトリビューションの優先順位\*</th><th>ルックバック期間\*\*</th></tr></thead><tbody><tr><td rowspan="2">ダウンロード</td><td>preload</td><td>1</td><td>1時間～180日｜デフォルト：90日</td></tr><tr><td>click_to_download</td><td>2</td><td>1時間～30日｜デフォルト：7日</td></tr><tr><td rowspan="2">クリック</td><td>click_to_app</td><td>2</td><td>1時間～30日｜デフォルト：7日</td></tr><tr><td>engaged_click</td><td>2</td><td>1時間～7日｜デフォルト：2日 </td></tr><tr><td rowspan="3">インプレッション</td><td>engaged_view</td><td>2</td><td>1時間～7日｜デフォルト：2日</td></tr><tr><td>view</td><td>3</td><td>1～24時間｜デフォルト：24時間</td></tr><tr><td>listening</td><td>3</td><td>1～24時間｜デフォルト：24時間</td></tr></tbody></table>

*エンゲージメントタイプが報告されない場合は、デフォルトの優先順位（クリックは2、インプレッションは3）が適用されます。

**`engaged_click`と`engaged_view`のルックバック期間を個別に設定できるのは、非SRNのアドネットワークのみです。 SRNでは、`engaged_click`と`engaged_view`にクリックと同じルックバック期間が適用されるため、**Install Click-Through Attribution Lookback**のスライダーで設定します。

## エンゲージビューとエンゲージクリックを報告できるアドネットワーク

以下は、`engaged_clicks`と`engaged_views`の報告について、AppsFlyerの認定を受けたアドネットワークの一覧です。  一覧への追加を希望するアドネットワークは、AppsFlyerサポートにお問い合わせください。

| **アドネットワーク** | **エンゲージビュー** | **エンゲージクリック** |
| --- | --- | --- |
| facebook\_int | はい |  |
| googleadwords\_int | はい |  |
| tiktokglobal\_int* | はい | はい |
| twitter\_int | はい | はい |
| snapchat\_int | はい | はい |
| bytedanceglobal\_int | はい | はい |
| aarki\_int | はい | はい |
| adjoe\_int |  | はい |
| appier\_int | はい | はい |
| appnext\_int | はい |  |
| bidease\_int | はい | はい |
| bigabid\_int | はい | はい |
| inmobidsp\_int | はい | はい |
| ironsource\_int | はい |  |
| lap\_int | はい |  |
| liftoff\_int | はい | はい |
| mdsp\_int | はい | はい |
| mintegral\_int | はい | はい |
| onedigitalturbine\_int | はい |  |
| personalyrtb\_int | はい | はい |
| pinterest\_int | はい |  |
| remerge\_int | はい | はい |
| revx\_int | はい | はい |
| rtbhouse\_int | はい | はい |
| smadex\_int | はい | はい |
| trademob\_int | はい | はい |
| unityads\_int | はい | はい |
| vungle\_int | はい |  |
| yahoojapan\_int | はい |  |
| yandexdirect\_int | はい | はい |
| youappi\_int | はい | はい |
| jampp\_int | はい | はい |

* TikTokは拡張エンゲージメントタイプに対応していますが、現在、エンゲージビューがレポートに正しく反映されていません。 AppsFlyerはTikTokと協力して、この問題の解決に取り組んでいます。

> 📘 **注意**
>
> 。特定の認定済みアドネットワークが、実際に`engaged_clicks`と`engaged_views`に対応しているかを確認するには、そのアドネットワークが報告した広告接触を含むローデータレポートを開き、`engagement_type`パラメータに上記の値が入力されているかを確認してください。

## エンゲージクリックとエンゲージビューのルックバック期間の設定

**エンゲージクリックとエンゲージビューのルックバック期間を設定するには、以下の手順を実施します。**

1. AppsFlyerのサイドメニューで、**連携**＞**有効な連携**を選択します。
2. 連携済みパートナーを選択します。
3. エンゲージビューおよびエンゲージクリックによるアトリビューションのルックバック期間を設定します。

   > 📘 **注意**
   >
   > ビュースルーやクリックスルーのルックバック期間は計測リンクでも設定できますが、エンゲージクリックとエンゲージビューのルックバック期間は、必ずパートナーの**連携タブ**で設定します。
   >
   > SRNでは、クリックスルーのルックバック期間を設定すると、エンゲージクリックとエンゲージビューにも同じ期間が適用されます。

4. ［**連携を保存**］をクリックします。

## EETデータの確認と分析

### ローデータレポート

アドネットワークが`engagement_type`を報告すると、その値がローデータレポートに反映されます。貢献元のデータでも確認できます。

> 📘 **注意**
>
> ビュースルーアトリビューションが無効な場合も、エンゲージビューは常にローデータレポートに含まれます。

プリロードやディープリンクなど、クリックが記録されない場合、AppsFlyerはローデータレポートの`engagement_type`フィールドに該当する値（preload、またはディープリンクの場合は`click_to_app`）を設定します。

以下の場合、ローデータレポートの`engagement_type`フィールドに、`click_unspecified`または`impression_unspecified`が設定されます。

* 広告接触（クリック／インプレッション）とエンゲージメントタイプが一致しない場合。
* `af_engagement_type`が送信されていない、または値が空の場合。

ローデータレポートでエンゲージメントタイプを確認するには、使用するローデータ製品で該当フィールドを選択する必要があります。エンゲージメントタイプと貢献元のエンゲージメントタイプは、デフォルトでは選択されていません。

### ダッシュボード

ダッシュボードに、エンゲージメントタイプのディメンションが追加されます。

[![eet-dashboard.png](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)

> 📘 **注意**
>
> ビュースルーアトリビューションが無効な場合も、エンゲージビューは常にダッシュボードに表示されます。

### **インプレッション1,000回あたりのインストール数**（IPM）の算出方法

総インプレッション数には、エンゲージビューと通常のビューの両方が含まれます。 IPMの算出時は、**総インプレッション数からエンゲージビューを差し引く**必要があります。エンゲージビューはインプレッションの一部であり、重複して数えるとインプレッション数が過大になるためです。

## よくある質問

<div id="what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types" />

<Accordion title="拡張エンゲージメントタイプはどの種類のキャンペーンに対応していますか？">

アドネットワークによって異なりますが、拡張エンゲージメントタイプはUAとリターゲティングの両方のキャンペーンに適用できます。リターゲティングキャンペーンへの対応状況は、そのアドネットワークのローデータレポートで、リターゲティングキャンペーンの`engagement_type`に値が入力されているかを確認してください。

</Accordion>

<div id="are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard" />

<Accordion title="Overview dashboardのクリック数とインプレッション数の集計に、エンゲージクリックとエンゲージビューは含まれますか？">

非SRNでは含まれ、広告接触の種類に応じて計上されます。エンゲージクリックはクリック、エンゲージビューはインプレッションとして数えられます。 SRNでは、API側の対応待ちのため、現在は集計に含まれていません。

</Accordion>

<div id="why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions" />

<Accordion title="Metaのgp_referrerによるコンバージョンでエンゲージメントタイプが表示されないのはなぜですか？">

Metaがengagement\_type=engaged\_viewを報告するのは、SRN APIのみです。 gp\_referrerを含む、それ以外のコンバージョンではengagement\_typeの値を取得できません。

</Accordion>

<div id="why-cant-i-see-the-engagement-type-i2" />

<Accordion title="ビュースルーのトグルを無効にしても、 attributed_touch_type = impression のインストールやリエンゲージメントが表示されるのはなぜですか？">

**ビュースルー**のトグルが無効な場合も、エンゲージビューは計測・報告されます。該当のインプレッションがエンゲージビューかを確認するには、`attributed_touch_type`だけで判断せず、ダッシュボードやローデータレポートの`engagement_type = engaged_views`を使用してください。

</Accordion>

## 仕様と制限事項

| 項目 | 備考 |
| --- | --- |
| <span id="cross-platform-engaged-view-support"></span>クロスプラットフォームでのエンゲージビューへの対応 | 拡張エンゲージメントタイプは、クロスプラットフォームでの利用にはまだ対応していません。インプレッションURLで`engaged_view`を送信しても、パートナーと広告主のアトリビューションデータには`view`と表示されます。 |
| <span id="owned-media-support"></span>オウンドメディアへの対応 | 現在、オウンドメディアには対応していません。オウンドメディアで使用するリンクに、`af_engagement_type`パラメータを含めないでください。 |

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HNCNA03SZ0MJFQ9XHDFXNTA1=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB enriched-engagement-types=%E6%8B%A1%E5%BC%B5%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%BF%E3%82%A4%E3%83%97%E3%81%A8%E3%81%AF h_01HNCNBR7KMT1KQBG5CPZY8YQY=%E6%8B%A1%E5%BC%B5%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%BF%E3%82%A4%E3%83%97%E3%81%A8%E3%81%AF eet-attribution-priority-and-lookback-window=eet%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%84%AA%E5%85%88%E9%A0%86%E4%BD%8D%E3%81%A8%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HNCVYDH17NGA8SH5XNWR4P9X=eet%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%84%AA%E5%85%88%E9%A0%86%E4%BD%8D%E3%81%A8%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 allowed-networks=%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%93%E3%83%A5%E3%83%BC%E3%81%A8%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%92%E5%A0%B1%E5%91%8A%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF h_01J00XFV136HPEHVQNPD934409=%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%93%E3%83%A5%E3%83%BC%E3%81%A8%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%92%E5%A0%B1%E5%91%8A%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF 01JENXRAMPFXTMF7SKDN2Y0E5M=%E6%B3%A8%E6%84%8F set%C2%A0engaged-enrichment-attribution=%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%81%A8%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J5B6EVM9P3M1SVR3K7WWK02J=%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%81%A8%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J5B97RCQQG6GN4PCKTQWVF54=%E6%B3%A8%E6%84%8F-1 reporting=eet%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D%E3%81%A8%E5%88%86%E6%9E%90 h_01J00XFV13YN8QNFZJTGM78EG2=eet%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D%E3%81%A8%E5%88%86%E6%9E%90 raw-data=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01J00XFV132M8TM6EGFZ7A7C3A=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01JFCPX6WKCWY9RM470H23EDQ0=%E6%B3%A8%E6%84%8F-2 dashboards=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89 h_01J00XFV13W0SD4MD7H4BT1RC9=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89 01JFCPX6WNCFC0R0N90G4HFYZX=%E6%B3%A8%E6%84%8F-3 how-to-calculate-installs-per-mille-ipm=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B31000%E5%9B%9E%E3%81%82%E3%81%9F%E3%82%8A%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E6%95%B0ipm%E3%81%AE%E7%AE%97%E5%87%BA%E6%96%B9%E6%B3%95 h_01JHG3EQN6FNJAHX1S91JE3MPT=%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B31000%E5%9B%9E%E3%81%82%E3%81%9F%E3%82%8A%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E6%95%B0ipm%E3%81%AE%E7%AE%97%E5%87%BA%E6%96%B9%E6%B3%95 faqs=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01JFCKK7FK0B5Z7QCZNSX14WF2=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HNFTS74KF3YFA0SWRGEQAGYQ=what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types h_01HNYY1S6YQ6YNR6RSY7B8H4EM=are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard h_01HQG5Y4JVNCB60AXR9K2GGD0H=why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions h_01JJP3TT2QMH5Y94C4Q7V6HFP1=why-cant-i-see-the-engagement-type-i2 cross-platform-traits-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
