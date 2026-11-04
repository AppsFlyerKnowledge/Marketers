---
title: リターゲティング向けの休眠期間
metadata:
  keywords:
    - Agencies
    - Ad Networks
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
  created_at: '2020-05-31T13:56:38Z'
  edited_at: '2026-10-14T09:38:18Z'
  id: 360009305817
  locale: ja
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/ja/articles/360009305817
---
> **概要：** 概要：休眠（非アクティブ）ユーザーをリターゲティングすることで、キャンペーン効果を向上させます。メディアソースごとに休眠期間を設定しましょう。
>
> ![](https://files.readme.io/1029124dc36a3881628f870cc725315afc262a20dc8652e5ff6cdd47653e7984-51910196789521.png)

<div id="inactivity-period" />

## 休眠期間

リターゲティングによって休眠ユーザーを取り戻すことができます。通常これらのキャンペーンでは、良好なコンバージョン率とROAS（広告費回収率）が見込めますが、アクティブユーザーを除外しないことが原因で、リターゲティングキャンペーンであまり効果的な成果を出せないことも多々あります。リターゲティングキャンペーンの効果を高めるには、**休眠期間**を設定して、アクティブユーザーを除外することをおすすめします。

最短休眠時間を設定することで、アクティブユーザーのアトリビューションを防ぐことができます。例えば、最短の休眠期間が3日間の場合、過去0&#126;3日間にアクティブなユーザーは成果計上対象に含まれません。4日間以上休眠しているユーザーが成果対象になります。なお、休眠期間の設定はリアトリビューションとリエンゲージメントの両方の計測に適用されます。リアトリビューションの場合、アプリをアンインストールする前に行った最後のアプリ起動が最後にアクティブだったタイミングとして処理されます。

**休眠期間のルール**

* 成果が計測される場合成果が紐づけられるユーザー： 設定された休眠期間を超えてアプリを使用していない休眠ユーザーリターゲティングのリエンゲージメントと再インストールが計測されます。
* 成果が計測されない場合：設定された休眠期間中にアプリを起動したアクティブユーザーのコンバージョンは無視され、リターゲティングキャンペーンの成果として計測されません。

<div id="retargeting-inactivity-terminology" />

### リターゲティングの休眠期間に関する用語

| 用語 | 定義 |
| --- | --- |
| 最大値 | 30日間 |
| デフォルト値 | 0日間（設定なし）  <br />メディアソース毎に設定する **休眠期間**の機能は、デフォルトでは無効になっています。 |
| ユーザーアクティビティ | SDKまたはS2S経由でレポートされたインストールまたはセッション。 |
| (他社SDKから)移行されたデバイス | 移行された時刻が最後にアクティブだった時刻と見なされます。 |

<div id="scenarios" />

## シナリオ

次のシナリオでは、メディアソースに対して休眠期間が定義されています。

<div id="reattribution" />

<Accordion title="リアトリビューション">

前提条件は以下の図に記載の通りで、ユーザー：

* ユーザーはアプリを既にアンインストールしており、アクティブではない状態
* ユーザーが該当メディアのリターゲティング広告に接触
* アプリを再インストール

[![re-attribution_1_en-us.png](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)

| シナリオ | 設定された休眠期間 | ユーザーの休眠期間 | 結果 |
| --- | --- | --- | --- |
| A | 7日 | 8日間。<br /><br />設定された休眠期間を超えて**ユーザーは休眠状態**です。 | <ul><li>**リアトリビューション**を計測（リターゲティングの再インストール）</li><li>リターゲティングメディアソースAに成果が計測される</li></ul> |
| B | 14日間 | 5日間<br /><br />＝ユーザーはアクティブな状態 | <ul><li>**オーガニックの再インストール**</li><li>**非オーガニックの再インストール：** ユーザーが新規獲得媒体の広告に接触した場合</li><li>リターゲティング媒体Aへは、設定された休眠期間により成果は計測されない</li></ul> |

</Accordion>

<div id="reengagement" />

<Accordion title="リエンゲージメント">

前提条件は以下の図に記載の通りで、ユーザー：

* アプリをインストール
* その後、数日間休眠の状態
* リターゲティング広告に接触し、アプリを起動

[![Re-engagement_scenarios_en-us.png](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)

| シナリオ | 媒体Aで設定された休眠期間 | ユーザーの休眠期間 | 結果 |
| --- | --- | --- | --- |
| A | 7日 | 8日間<br /><br />設定された休眠期間を超えて**ユーザーは休眠状態**です。 | <ul><li>媒体Aに**リエンゲージメント**成果が計測される</li></ul> |
| B | 7日 | 4日間<br /><br />＝ユーザーは設定された休眠期間内に**アプリを使用しておりアクティブな状態** | <ul><li>**通常のセッションとして計測**</li><li>リターゲティング媒体Aには成果が計測されない</li></ul> |

</Accordion>

<div id="partner-setup" />

## パートナー設定

<div id="zd-srn" />

<Accordion title="SRN">

休眠期間をサポートしているSRN媒体は、この機能の設定が [連携] タブに表示されます。

**リターゲティングをサポートしているセルフレポーティングネットワーク (SRN) の休眠期間を定義する方法：**

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**を選択します。
2. SRN媒体を選択します。
3. **連携** タブにて、スクロールダウンします。**リターゲティングCVの計測対象からアクティブユーザーを除外する**設定を有効にする
4. **休眠期間**を設定します（1-30日間）。
5. **連携を保存**をクリックします。

[![Inactivity_window_SRN.png](https://files.readme.io/29e80edb6f42ae129b24b05280e9c1605ef5b089ccecf1c0a7f2888b1a4f593a-51910208455057.png)](https://files.readme.io/29e80edb6f42ae129b24b05280e9c1605ef5b089ccecf1c0a7f2888b1a4f593a-51910208455057.png)

</Accordion>

<div id="nonsrn-click-ad-networks" />

<Accordion title="SRN以外（クリック計測のアドネットワーク）">

**リターゲティングをサポートしているアドネットワーク (非SRN) の休眠期間を定義する方法：**

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**を選択します。
2. アドネットワークを選択します。
3. [**計測リンク**] タブを開き、スクロールダウンし [**リターゲティングの対象からアクティブユーザーを除外する**] を有効にします。
4. **休眠期間**を設定します（1-30日間）。  
   この機能が無効の場合、計測リンクには追加されません。

[![Inactivity_window_non-SRN.png](https://files.readme.io/6670efad2795ddb22197506d8d98050f23c9d515375d99b012a6e7426de9470f-51910208455953.png)](https://files.readme.io/6670efad2795ddb22197506d8d98050f23c9d515375d99b012a6e7426de9470f-51910208455953.png)

</Accordion>

<div id="agencies" />

<Accordion title="代理店">

#### SRN

代理店（広告主から権限を付与された場合）

**休眠期間設定にアクセスするには：**

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**を選択します。
2. SRN媒体を選択します。
3. 連携タブにて、以下の表に記載されているように設定を実行してください。

| SRN | 代理店 |
| --- | --- |
| DoubleClick | <ul><li>リターゲティングを有効／無効にします</li><li>休眠期間を設定します</li></ul> |
| Google Ads | <ul><li>リターゲティングを有効／無効にできません</li><li>代理店が権限を付与されている場合、休眠期間を設定できます</li></ul> |
| Meta ads/X Ads/Snapchat | リターゲティングと**休眠期間**の設定にアクセスできません |

<div id="traits-and-limitations" />

<div id="non-srn" />

#### 非SRN

パートナー（リターゲティングをサポートしている）

**リターゲティングをサポートしているアドネットワーク (非SRN) の休眠期間を定義する方法：**

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**を選択します。
2. **計測リンク**タブで SRN以外の媒体を選択します。

</Accordion>

<div data-zendesk-anchors="inactivity-period=%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93 h_01H9JS3QKW5S7VP9YW05CB6STR=%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93 retargeting-inactivity-terminology=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E7%94%A8%E8%AA%9E h_01H9JS3QKXMBS95RG06A9JXGT0=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E7%94%A8%E8%AA%9E scenarios=%E3%82%B7%E3%83%8A%E3%83%AA%E3%82%AA h_01H9JS3QKXWDX8Y58GX1G5HNYY=%E3%82%B7%E3%83%8A%E3%83%AA%E3%82%AA h_01H9JS3QKXN0E0MGD35173C9FR=reattribution h_01H9JS3QKXNS77EFYBZP94YQMT=reengagement partner-setup=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E8%A8%AD%E5%AE%9A h_01H9JS3QKXGNFM8499G52458B2=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E8%A8%AD%E5%AE%9A srn=zd-srn h_01H9JS3QKXCAHG91VS6VSVJTTT=zd-srn h_01H9JS3QKX8R8AXHQWKX7FR9GZ=nonsrn-click-ad-networks h_01H9JS3QKXSDXA5Z7TWN2A7S5K=agencies srn::bd853114=srn h_01H9JS3QKX88HQYJ5881W7VXF2=srn nonsrn=%E9%9D%9Esrn h_01H9JS3QKXRJ8W9H89JBVSZ3R3=%E9%9D%9Esrn" />
