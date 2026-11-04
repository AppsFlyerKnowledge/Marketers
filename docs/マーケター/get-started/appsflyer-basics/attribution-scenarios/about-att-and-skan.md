---
title: ATTとSKANについて
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2026-10-21T18:43:07Z'
  id: 360011890298
  locale: ja
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ja/articles/360011890298
---
> **概要**：iOS 14.5以降、Appleは<Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">AppTrackingTransparency</Anchor>（ATT）の実装と、その利用条件の遵守を求めています。 ATTでは、*アプリがユーザーのデータを収集し、アプリやWebサイトをまたいだトラッキングを目的として他社と共有する場合*、ATTの同意確認画面を使用し、広告を掲載するアプリと広告主のアプリの両方で、ユーザーの同意を得る必要があります。トラッキングを行わない場合は、同意確認画面を表示する必要はありません。

<div id="attribution-measurement-in-an-att-environment" />

## ATTが適用される環境でのアトリビューション計測

AppsFlyerは、さまざまなニーズに対応する複数のアトリビューション計測方法を提供しています。 [ATT](/docs/about-att-and-skan#att-principles)による同意取得の要件は、アプリ内広告から別のアプリへのインストールを促す有料キャンペーンのアトリビューション計測に影響します。そのため、広告主は複数の計測・レポートソリューションを組み合わせて利用する必要があります。

アプリ内広告から別のアプリへのインストールを促す有料キャンペーンでは、[SKAN](/docs/about-att-and-skan#skan-solution-principles)によって確定的なアトリビューション結果が得られます。オウンドメディア、Webからアプリへの誘導、Apple Adsなど、その他の種類のキャンペーンでは、AppsFlyerの従来のアトリビューション計測ツールを使用します。従来のツールでは長期的なLTVを計測できますが、SKANではインストール後の短い期間におけるユーザーの行動や成果を計測します。

計測の全体像を把握するには、互いに補完し合うSKANとAppsFlyerの従来のソリューションを併用してください。

この記事では、広告主向けにSKANとATTの概要を説明します。 AppsFlyerの基本的な使い方をご存じの広告主を対象としています。

<div id="skan-solution-principles" />

<Accordion title="SKANソリューションの仕組み">

AppsFlyerは、iOSからのSKANポストバックを利用して、iOSのアトリビューション結果を集計データとして提供します。これらのポストバックは、iOSからアドネットワークに送信され、アドネットワークからAppsFlyerに転送されます。ポストバックには、匿名化されたアトリビューションの記録に加えて、広告主が設定したコンバージョン値（CV）が含まれます。 CVは、インストール直後の計測期間におけるユーザーの質を表す指標です。

AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKANソリューション</Anchor>は、広告主に次の機能を提供します。

* すべてのアドネットワークから受信したポストバックを集計し、コストなどの情報を加えたSKANデータを、ダッシュボードとレポートで確認できます。
* アプリのコードを変更することなく、AppsFlyer Conversion StudioでCVの計測対象を設定できます。 CVは、収益、ユーザーの行動、コンバージョンイベントの計測に使用できます。

**SKANの制限事項**

* **キャンペーン：** 自社アプリ間での相互送客キャンペーンと、モバイルWeb経由のインストールには対応していません。
* **計測期間：** 実際に計測できる期間は数日間に限られます。

**SKANの処理の流れ**

1. 広告主が、AppsFlyer Conversion StudioでSKANの計測設定を行います。
2. ユーザーがアプリを初めて起動します。
3. 各計測期間中に、AppsFlyerがユーザーの行動と定義済みのCV設定ルールに基づいて、CVを設定します。
4. 計測期間が終了すると、iOSはアドネットワークにポストバックを送信し、AppsFlyerにもそのコピーを送信します。ポストバックの到着には、次の遅延が生じます。
   * SKAN 4の計測期間1：24〜48時間
   * SKAN 4の計測期間2・3：24〜144時間
   * SKAN 3：CVが最後に増加してから24〜48時間後
5. iOSデバイスからAppsFlyerに直接送信されたポストバックのコピーは、広告主が指定したエンドポイントに転送されます。 <Anchor target="_blank" href="/marketers/ja/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">SKANポストバックのコピーをAppsFlyerに送信する方法</Anchor>を参照してください。
6. アドネットワークが追加情報を含めたポストバックをAppsFlyerに転送します。または、SRNがAPI経由でポストバックデータを送信します。
7. AppsFlyerがCVを検証し、設定ルールに基づいてその値を解釈します。解釈したデータを記録してアトリビューションを行い、AppsFlyerのダッシュボード、レポート、APIで利用できるようにします。

</Accordion>

<div id="att-principles" />

<Accordion title="ATTの仕組み">

ATTの同意確認画面は、広告主がユーザーデータを収集・共有することについて、ユーザーから明示的な同意を得るための仕組みです。 iOS 14.5以降、IDFAを利用できるのは、ユーザーが同意確認画面で同意した場合に限られます。

広告を掲載するアプリと広告主のアプリの両方で、同意確認画面を表示します。ユーザーが両方のアプリで同意すると、*トラッキング*に同意したことになり、広告主は、異なる企業が所有するアプリ間でそのユーザーをトラッキングすることをAppleから許可されます。

**ATTの状態**

ATTには、次の表に示すいずれかの状態が設定されます。 初期状態では、iOSによって「未選択（Not determined）」または「制限あり（Restricted）」に設定されます。

同意確認画面を表示して、ユーザーの状態を*未選択（Not determined）*から*許可（Authorized）*に変更するかどうかは任意です。ただし、同意確認画面を表示しない場合は、*許可を得ることはできません。 0>*

| ATTの状態 | 同意の有無  <br />（IDFAの利用可否） | 説明 |
| --- | --- | --- |
| 制限あり（Restricted） | いいえ | <ul><li>ユーザーの年齢などの基準に基づいてAppleが決定します。デバイスのユーザーは変更できません。</li><li>これらのユーザーには、同意確認画面を表示できません。</li></ul> |
| 未選択（Not determined、iOS 14.4まで） | はい | デフォルトの状態 |
| 未選択（Not determined）<br /><br />（iOS 14.5以降） | いいえ | デフォルトの状態 |
| 拒否（Denied） | いいえ | 次のいずれかの場合に設定されます。<ul><li>同意確認画面の表示後に設定された場合</li><li>ユーザーが*［Appからのトラッキング要求を許可］*（デバイス全体に適用される設定）をオフにした場合</li><li>デバイスにiOS 14をインストールする前に、LAT（追跡型広告の制限）がオンになっていた場合</li></ul> |
| 許可（Authorized） | はい | 同意確認画面の表示後に設定されます |

**ATTによる影響**

ATTが適用される環境では、ユーザーが同意した場合にのみIDFAを利用できます。そのため、広告主は集計データによるアトリビューション計測と、同意を得たユーザーのユーザー単位のレポートを併用することで、より多くの情報を把握できます。 <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">AppsFlyerのアトリビューションモデル</Anchor>を参照してください。

アプリのアトリビューションに関するデータは、複数の情報源から取得されます。それぞれの情報源で利用できる識別子と、実際に使用する識別子は異なります。大部分のデータは、従来のアトリビューション計測ツールで確認できます。ただし、SKANで計測されたインストールは、SKANダッシュボードで確認します。

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="インストールはどのダッシュボードに表示されますか？">

iOS 14では、同じインストールが従来のダッシュボードとSKANダッシュボードの両方で計測される場合があります。また、メディアソースの状況によっては、一方のダッシュボードではオーガニック、もう一方では非オーガニックとして計測される場合があります。

</Accordion>

<div id="ios-attribution-and-privacy-important-knowledge" />

## iOSのアトリビューションとプライバシーに関する重要事項

<div id="ios-attribution-skan-and-privacy-articles-and-links" />

#### iOSのアトリビューション、SKAN、プライバシーに関する記事とリンク

| 分野 | 記事 | 主な関連情報：よくある質問、計測結果の差異、比較 |
| --- | --- | --- |
| SKAN | SKANローデータの項目 | did\_winとSKAN 3.0に対応する追加のSKANローデータ項目 |
| SKAN | SKANソリューション | <ul><li>アプリのインストールからダッシュボード更新までの時間</li><li>SKANにおけるオーガニックの指標</li><li>AppsFlyerとSKANのアトリビューションの比較</li><li>SKANの計測結果の差異に関するよくある質問</li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/ja/docs/skan-interoperation">SKANのパートナー連携</Anchor>（記事セクション） | SKAN連携済みパートナー一覧 |
| SKAN | Meta広告とAppsFlyerのSKAN連携 | <ul><li>トラブルシューティングと計測結果の差異</li><li>計測方法とデータ反映タイミングの違い</li></ul> |
| SKAN | SnapchatとAppsFlyerのSKAN連携 | 計測結果の差異に関するガイド |
| プライバシー | Aggregated Advanced Privacy（AAP） | <ul><li>AAPの影響を受ける機能</li></ul> |
| プライバシー | データ提供が制限されるメディアソース | 提供が制限されるローデータ項目 |
| iOS 14 | App Storeのプライバシー情報と審査に向けた準備 |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">アプリでのATTの設定</Anchor>（開発者向けSDKガイド） |  |
| iOS 14 | GoogleやMeta広告などのセルフレポーティングネットワーク（SRN）について | SRNのインストールはどこで確認できますか？ |
| 請求 | iOSアプリの請求 |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="IDFAの利用可否がアトリビューションと計測に与える影響">

<div id="metrics" />

#### **指標**

IDFAを利用できない場合は、次の指標に影響が生じる可能性があります。

| 指標 | 増加 | 減少 | 説明 |
| --- | --- | --- | --- |
| 非オーガニックとオーガニック | オーガニック | 非オーガニック |  |
| 再インストールとインストール | インストール | 再インストール |  |
| リターゲティング | オーガニックインストールとアプリ内イベント | リエンゲージメント、リアトリビューション |  |
| Apple Ads | -- | -- | 変更なし。 IDFAの利用可否にかかわらず、正しくアトリビューション計測されます。 |

<div id="deep-linking" />

#### **ディープリンク**

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy">onConversionDataSuccessを使用する従来の方法</Anchor>でディファードディープリンクを実行する場合、IDFAを利用できないと機能しない可能性があります。この方法では、プライバシー設定によって提供が制限される可能性のあるアトリビューションデータが必要となるためです。

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_overview">統合ディープリンク（UDL）</Anchor>の使用を推奨します。 UDLはiOS 14.5以降のプライバシー基準に準拠しており、ディープリンクとディファードディープリンクに関連するパラメータである`deep_link_value`と`deep_link_sub1`のみを返します。 `media_source`、`campaign`、`af_sub1-5`などのアトリビューションパラメータはnullを返すため、ディープリンクには使用できません。

</Accordion>

<div id="faqios-attribution-and-att" />

## iOSのアトリビューションとATTに関するよくある質問

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="V6より前のSDKを使用するアプリには、どのような影響がありますか？">

V6.0より前のSDKを使用するアプリでは、次の影響があります。

* SKAdNetworkとApple Adsが機能しません。
* App Storeにアプリを申請しても、審査で却下されることが想定されます。

V6.10より前のSDKを使用するアプリでは、SKAN 4が機能しません。

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="ATTの同意確認画面の表示は必須ですか？">

いいえ。 ATTの同意を求める必要があるのは、ユーザーの*トラッキング*、IDFAの収集、またはその両方を行う場合のみです。

</Accordion>

<div id="faqskan" />

## SKANに関するよくある質問

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="ポストバックが届くタイミングと、SKAN 3・SKAN 4のどちらになるかを確認するには、どうすればよいですか？">

受信するSKANポストバックの種類は、Conversion Studioで使用するモード、アドネットワーク、ユーザーのiOSバージョンなど、さまざまな要因によって決まります。

これらの要因は、次の項目に影響します。

* ポストバックのバージョン：SKAN 3またはSKAN 4です。<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#principles-and-flow">詳細はこちら</Anchor>
* 計測期間1（AW）：SKAN 4では48時間です。 SKAN 3では、アクティビティ計測期間に基づきます。注意：Conversion StudioがSKAN 4モードではなく、アドネットワークの署名がSKAN 4の場合、計測期間はアクティビティ計測期間と48時間のうち、短い方になります。
* ポストバックの遅延：インストールからSKANポストバックの到着までの時間です。この時間は、計測期間が終了するタイミングによって異なります。<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update">詳細はこちら</Anchor>
* 計測期間を延長するタイマー：SKAN 3では、アクティビティ計測期間を最大63日間まで延長できます。ポストバックは、計測期間の終了後にのみ届きます。

詳しくは、次のフローチャートを参照してください。

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="SKANでは、アドネットワークごとにソース識別子やキャンペーンIDの数に上限がありますか？">

はい。以前は、キャンペーンIDの上限は100でした。 SKAN 4以降では、キャンペーンIDは「階層型ソース識別子」と呼ばれ、上限は10,000になっています。ソース識別子は4桁の整数です。

アドネットワークは、SKANのソース識別子を自社のキャンペーンIDに紐づけます。

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="SKANローデータは、どのような用途に使えますか？">

* 集計APIでは取得できない分析軸で、ローデータを集計できます。
* 既存のローデータの取り込み処理を調整することで、SKANローデータも容易に取り込めます。

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="受信したコンバージョン値が、AppsFlyer Conversion Studioの設定と一致しないのはなぜですか？">

多くの場合、アプリに組み込まれた別のSDKがコンバージョン値を設定し、AppsFlyer SDKおよびAppsFlyerで設定したコンバージョン値と競合していることが原因です。コンバージョン値を設定する別のSDKが、アプリに組み込まれていないことを確認してください。

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="SKANダッシュボードの集計データが、SKANのData Lockerレポートのローデータの数値と一致しないのはなぜですか？">

多くの場合、この差異は、確認しているData Lockerレポートが適切でないことによって生じます。 Googleからのデータの受信には、最大13日かかる場合があります。また、ローデータレポートには、データを受信した日にそのデータが記録されます。累積データとして記録されるわけではありません。そのため、特定の日付に発生したインストールの指標を正しく把握するには、その日から13日後までのすべてのレポートを確認する必要があります。

例：6月12日のレポートに、6月11日に発生したGoogle経由のインストールが100件表示されています。 6月24日のレポートには、6月11日に発生したインストールがさらに100件記録されています。 6月11日に発生したインストールの合計200件を正しく把握するには、13日間（6月12日〜6月24日）のすべてのレポートを確認し、インストール時刻またはアドネットワークのタイムスタンプに基づいて集計する必要があります。

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * AppsFlyerの利用開始手順

<div data-zendesk-anchors="attribution-measurement-in-an-att-environment=att%E3%81%8C%E9%81%A9%E7%94%A8%E3%81%95%E3%82%8C%E3%82%8B%E7%92%B0%E5%A2%83%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC h_01HE0C8YXSXSX003X0671Z97KZ=att%E3%81%8C%E9%81%A9%E7%94%A8%E3%81%95%E3%82%8C%E3%82%8B%E7%92%B0%E5%A2%83%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=ios%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E9%87%8D%E8%A6%81%E4%BA%8B%E9%A0%85 h_01HE0C8YXS3BH109DF1Y1KNK5P=ios%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E9%87%8D%E8%A6%81%E4%BA%8B%E9%A0%85 ios-14-and-skan-articles-and-links=ios%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3skan%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E8%A8%98%E4%BA%8B%E3%81%A8%E3%83%AA%E3%83%B3%E3%82%AF h_01HE0C8YXSPZKBWXC51Z2636R0=ios%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3skan%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E8%A8%98%E4%BA%8B%E3%81%A8%E3%83%AA%E3%83%B3%E3%82%AF h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement metrics=%E6%8C%87%E6%A8%99 h_01HE0C8YXSJMYN81FKPCA8ATK7=%E6%8C%87%E6%A8%99 deep-linking=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01HE0C8YXS6ADG1SQCMVP0W69B=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF faq%E2%80%94ios-14=ios%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8att%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HE0C8YXSV9VSK1NPG9RCTQW1=ios%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A8att%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=skan%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=skan%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
