---
title: 高プライバシー一括設定のフレームワークの適用
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
  created_at: '2021-03-15T11:32:31Z'
  edited_at: '2026-10-14T09:31:34Z'
  id: 360018515798
  locale: ja
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ja/articles/360018515798
---
> **概要：** iOS 14.5以降のAppleによるATT施行により、広告主は高プライバシー一括設定（AAP）を使用して、プラットフォームからのユーザーレベルのアトリビューションデータの利用を制御することができます。

<div id="aggregated-advanced-privacy-aap-framework" />

## 高プライバシー一括設定（AAP）

AppsFlyerの高プライバシー一括設定は、異なる企業間の広告主アプリとWebサイトにわたるトラッキングを防止し、個人または端末を特定できないようにします。高プライバシー一括設定は、プライバシー保護しきい値の最小ベンチマークとして、Appleアプリ追跡の透明性プライバシーレベルを利用しています。

このフレームワークにより、広告主はAppsFlyerプラットフォームを介してユーザーレベルのアトリビューションデータの可用性を制御できます。

iOS 14.5の一般提供およびATTの適用開始以降、AAPが有効な場合、iOS 14.5以上を利用する非同意ユーザーのユーザーレベルのアトリビューションデータは、広告主およびパートナーに提供されません。

AAPは、集計されたアトリビューションデータおよび分析レポートの利用可否には影響しません。

<div id="aap-impacted-features" />

### AAPが影響する機能

AAPがオンの場合、ローデータによって提供されるデータが影響を受け、一部の項目が制限されているか、使用できません。これは、次のツールによって提供されるデータに影響します：

* Data Locker
* Pull API ローデータ
* Push API
* 管理画面からのローデータ出力
* アドネットワークへのポストバック
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">コンバージョンデータ取得 (GCD) API</Anchor>（クライアント側でのユーザーレベルデータAPI）

AAPがオンの場合、データの可用性は次のように影響を受けます：

* **アトリビューションデータと不正（Protect360）：** <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">一部のアトリビューション項目は制限されているか、利用できません。</Anchor>
* **クリック、インプレッション、ブロックされたクリック（不正）データ：** ユーザーおよびデバイス関連の識別子は利用できません。
* **ディファードディープリンク**：有料メディアでディファードディープリンクを実装する場合は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unifieddeeplink">Unified Deep Linking API (UDL API)</Anchor>を使用してください。GCDを使用する旧APIは、非同意ユーザーの文脈では利用できません。オウンドメディアの場合、GCDおよび最新のディファードディープリンクAPIの両方が利用可能です。

<div id="data-availability-principles-in-aggregated-advanced-privacy" />

## 高プライバシー一括設定におけるデータ可用性の原則

特定のユーザーのデータにAAPが適用される場合、データの可用性は、そのユーザーのATTステータスとユーザーをもたらすメディアソースによって異なります。

**定義：**

* **ユーザーレベルのアトリビューションデータ：** デバイスレベルの識別子を含むデータレコードは、ユーザーレベルでのアトリビューションに紐付けられています。
* **広告主向けの制限付き計測データ：**
  * 利用可能：デバイスレベル識別子（IDFA：ユーザーがATT許諾した場合には利用可）
  * 利用不可：パブリッシャーの計測リンク経由で取得されるパラメータ（例：`pid`や`c`）。<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">これらは「制限されたメディアソース」に該当します。</Anchor>
* **パートナー向けの限定的な計測データ：**
  * 利用可能： 集約データ
  * 利用不可：ユーザー特定につながるユーザーレベルデータ（AppsFlyer ID、カスタムデータ、CUID、Click ID、IDFA、IDFV、IMEI、User-agent、IPアドレスなど）

定義された用語は、広告主およびパートナーが利用できるデータを説明するために、図および後続のセクションで使用されます。

![高度なプライバシーフレームワーク - 広告主 (4).png](https://files.readme.io/0291fe2eea5f6efc41f2338824a0017be3e265f502e0d3999d52ac87b1ee7719-35847850634897.png)

高プライバシーポストバックは、ウェブ上で配信される場合は動作が異なり、af\_media\_type=web または af\_media\_type=app パラメータを使用する必要があります。詳細は <Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web面での広告配信">こちら</Anchor>を確認してください。

<div id="paid-and-owned-media-data-availability" />

### 有料メディアとオウンドメディアのデータの可用性

<div id="paid-media" />

<Accordion title="有料メディア">

有料メディアには、AppsFlyerと連携しているモバイル広告ネットワークが含まれます。

<div id="paid-media-data-availability-by-att-status" />

#### ATTステータス別 広告媒体データの可用性

<table><thead><tr><th rowspan="2">Media type</th><th colspan="2">ATTステータス</th><th colspan="2">利用できるデータ：</th></tr><tr><th>広告掲載アプリ</th><th>広告主アプリ</th><th>広告主</th><th>アドネットワーク</th></tr></thead><tbody><tr><td rowspan="4">アプリ</td><td>承認</td><td>承認</td><td>ユーザーレベルの計測データ</td><td>ユーザーレベルの計測データ</td></tr><tr><td>許可されていません</td><td>承認</td><td>広告主向けの限定的な計測データ </td><td>パートナー向けの限定的な計測データ</td></tr><tr><td>承認</td><td>許可されていません</td><td>広告主向けの限定的な計測データ </td><td>パートナー向けの限定的な計測データ</td></tr><tr><td>許可されていません</td><td>許可されていません</td><td>広告主向けの限定的な計測データ </td><td>パートナー向けの限定的な計測データ</td></tr><tr><td> </td><td colspan="4"> </td></tr><tr><td rowspan="2"><p>Web</p></td><td>N/A</td><td>承認</td><td>ユーザーレベルの計測データ</td><td>ユーザーレベルの計測データ</td></tr><tr><td>N/A</td><td>許可されていません</td><td>広告主向けの限定的な計測データ </td><td>パートナー向けの限定的な計測データ</td></tr></tbody></table>

</Accordion>

<div id="owned-media" />

<Accordion title="オウンドメディア">

AppleのAppTrackingTransparencyフレームワークは、異なる会社から収集されたデータのみに適用されます。したがって、ユーザーATT同意ステータスに関わらず、広告主はオウンドメディアのユーザーレベル計測データを利用できます。

オウンドメディアには、広告主が顧客にリーチするために使用するデジタルマーケティングキャンペーンが含まれます。これには、メールキャンペーン、クロスプロモーション、プッシュ通知などが含まれます。AppsFlyerでは、アドネットワークを使用するキャンペーンはオウンドメディアと見なされません。

</Accordion>

<div id="controlling-advanced-aggregated-privacy" />

## 高プライバシー 一括設定のコントロール

<div id="aap-central-switch" />

<Accordion title="高プライバシー 一括設定（AAP）—アプリレベルの設定">

高プライバシー一括設定（AAP）は、選択したアプリのすべてのパートナーのプライバシーの詳細設定を制御するアプリレベルの制御です。「高プライバシー一括設定」トグルは**アプリの設定**画面にあります。高プライバシー一括設定トグルがオンの場合、選択したアプリのすべてのパートナーの **高プライバシーポストバック**トグルが自動的にオンになり、媒体毎にオンオフの変更はできません。高プライバシー一括設定をオフにすると、広告主は各パートナー連携画面に個別に移動し、 **高プライバシーポストバック**を有効・無効に設定できます。

![AAPcontrol.png](https://files.readme.io/ddc8140ada9278eab447ecdfa4d88c56e07a0ed54b10b71de1cc2352f9590d40-35847850639121.png)

<div id="aap-enabled" />

#### 高プライバシー一括設定（AAP）が有効の場合

* 集約式アトリビューション：利用可能 ー これには、オーバービューダッシュボードやコホート、マスターAPIなどのレポートツールが含まれます。
* [高プライバシーポストバックのトグル](#partner-advanced-privacy-switch)は常にオンになり、変更できません。注意：トグルはオンで固定されており変更できません。
* [以前のセクション](/docs/apply-aggregated-advanced-privacy-framework#高プライバシー一括設定におけるデータ可用性の原則)で定義したとおり、広告主とパートナー向けのユーザーレベルデータの可用性は制限されます。

<div id="aap-disabled" />

#### 高プライバシー一括設定（AAP）が無効の場合

* 広告主はユーザーレベルのアトリビューションデータを利用できます。
* パートナーごとに高プライバシーポストバックを個別に設定できます。

*AAPをオフにする前に、ユーザーレベルのアトリビューションデータを第三者が利用できるようにするかどうか、および第三者がそのデータをどのように使用するかを検討してください。Appleがトラッキングをどのように定義するかに関して、法律顧問やその他の専門アドバイザーと緊密に連携する必要があります。 ここに記載されていることは、一切法的な助言ではありません。これらは情報提供と便宜上の目的でのみ提供されています。*

**高プライバシー一括設定の設定方法**：

1. AppsFlyerのサイドメニューから **設定** > **アプリ設定**を選択します。
2. 必要に応じて**高プライバシー一括設定**をオンまたはオフに切り替えます。
3. **保存**をクリックしてください。

</Accordion>

<div id="partner-advanced-privacy-switch" />

<Accordion title="高プライバシーポストバック — パートナーレベルの設定">

AAPが無効の場合、アドネットワークごとに個別で広告主は高プライバシーポストバックを設定できます。

![APControl.png](https://files.readme.io/8e5a005cbadb5665cf255d39d6fa425298510f719b166c2013a2dfe57d4e982b-35847865312657.png)

**パートナーの高プライバシーポストバックを無効にする方法：**

1. **アプリ設定**画面で、高プライバシー一括設定のトグルがオフになっていることを確認します。
2. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー** へ移動します。
3. アドネットワークを選択します。
4. **連携タブ**で、**高プライバシーポストバック**をオフにします。

**AAP設定の変更とパートナーの高プライバシーポストバック設定への影響**

前述のように、設定はパートナーレベルの高プライバシーポストバック（AP）を上書きします。ただし、後からAAP（高プライバシー一括設定）をオフにすると、個別のパートナーレベルでの高プライバシーポストバックを以前のステータスに戻すことができます。詳細は以下を参照してください：

* 過去に、AAPをオフにし、一部のパートナーのAP設定をオフに設定しました。
* 後にAAPをオンに設定しました。AAPがオンの場合、AAPはパートナー設定をオーバーライドし、すべてのパートナーがオンであると見なされます。
* 次に、AAPを再びオフにします。つまり、個々のパートナー設定が適用されます。そのため、一部のパートナーではこの設定がすでにオフになっています。

</Accordion>

<div id="advanced-aggregated-privacy-implications-for-your-partners" />

## 高プライバシー一括設定のパートナーへの影響

<div id="ad-networks" />

<Accordion title="アドネットワーク">

<div id="postbacks-to-ad-network-partners" />

#### **アドネットワークパートナーへのポストバック**

<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高プライバシー一括設定（AAP）は、アドネットワークと共有されるデータに関連してアドネットワークに影響</Anchor>し、アドネットワークのコンテキストで広告主に適用されるAAPの原則に準拠しています。アドネットワークと共有されるデータは、成果が付与されるアドネットワークと成果が付与されないアドネットワークで異なるポストバックを介して行われます。

説明されているデータ共有ルールは、次のスイッチのいずれかがオンになっている場合に、特定のアドネットワークに適用されます：

* 高プライバシー一括設定（AAP）：アプリ全体への適用
* 高プライバシーポストバック設定（AP）：特定媒体への適用

<div id="postbacks-for-attributed-ad-networks" />

#### **成果が紐づくアドネットワークへのポストバック**

成果が紐づくネットワークの場合、データ共有に使用されるポストバックの種類は、次のようにユーザーの同意の有無によって異なります：

* **同意ユーザー：** 識別子を含むユーザーレベルのアトリビューションデータを含む通常のポストバック。
* **同意ユーザー：** 高プライバシーポストバック（AP）には、限られたアトリビューションデータが含まれています。これには、識別子などは含まれず、キャンペーンの詳細のみが含まれています。
  * **前提条件：** アドネットワークが高プライバシーポストバックを取得するには、AppsFlyerと高プライバシー連携されている必要があります。連携がまだの場合は、同意のないユーザーに関してはポストバックは送信されません。
  * **例外：** Apple Search Ads (ASA) に紐づくインストールの場合、高プライバシーポストバックをサポートしていない広告ネットワークがインストールポストバックを **すべてのメディアソース、オーガニックを含む** に設定しても、Apple Search Ads (ASA) は広告主側の高プライバシーポストバック設定の状態に関係なく、広告ネットワークにインストールポストバックを送信します。

さまざまなユーザーの同意シナリオと、使用されるポストバックの種類を次の図に示します。

![AAP - 属性付けされた広告ネットワーク.png](https://files.readme.io/d776c77115beb4c6b6ada1850077f186aa2feb809a8b69af8cf0ec760cd02b39-35847865314961.png)

高プライバシーポストバックは、ウェブ上で配信される場合は動作が異なり、af\_media\_type=web または af\_media\_type=app パラメータを使用する必要があります。詳細は <Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web面での広告配信">こちら</Anchor>を確認してください。

<div id="postbacks-for-unattributed-partners" />

#### **成果の紐づかないパートナーへのポストバック**

次の図に示すように、連携パートナーの連携タブの送信オプションが*オーガニックを含むすべてのメディアソース*に設定され、そのパートナーがイベントの成果に紐づかない場合、成果に紐づかないポストバックがネットワークに送信されます。

![InAppEventAll.png](https://files.readme.io/e24037f75b2b82797031eb13d5e063b8c2006812491e69674ff066ac830919f7-35847850644881.png)

さまざまなユーザーの同意シナリオと、使用されるポストバックの種類を次のフローチャートに示しています。

![AAP - 無名広告ネットワーク.png](https://files.readme.io/bb8a5d192e2120f8df90b9be044c0b4abf48c2250f5128fbbce76c60c89718cc-35847850645649.png)

高プライバシーポストバックは、ウェブ上で配信される場合は動作が異なり、af\_media\_type=web または af\_media\_type=app パラメータを使用する必要があります。詳細は <Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web面での広告配信">こちら</Anchor>を確認してください。

</Accordion>

<div id="analytics-partners" />

<Accordion title="アナリティクスパートナー">

高プライバシー一括設定（AAP）は、アナリティクスパートナーと共有されるデータに関連してアドネットワークに影響し、アナリティクスパートナーのコンテキストで広告主に適用されるAAPの原則に準拠しています。  パートナーと共有されるデータはポストバックを介して行われます。

説明されているデータ共有ルールは、次のスイッチのいずれかがオンになっている場合に、特定のパートナーに適用されます。

* 高プライバシー一括設定（AAP）：アプリ全体への適用
* 高プライバシーポストバック設定（AP）：特定媒体への適用

同意済みのユーザーに関しては、ユーザー識別子を含むユーザーレベルのアトリビューションデータを含むポストバックが送信されます。同意していないユーザーに関しては、ポストバックは送信されません。

さまざまなユーザーの同意シナリオと、使用されるポストバックの種類を次の図に示しています。

![AAP - Analytics partner.png](https://files.readme.io/4bb77720f9e0be093e325f989987f5b5ba2dba5aa26e2f32df5f1bd5b99161eb-35847865320593.png)

高プライバシーポストバックは、ウェブ上で配信される場合は動作が異なり、af\_media\_type=web または af\_media\_type=app パラメータを使用する必要があります。詳細は <Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web面での広告配信">こちら</Anchor>を確認してください。

</Accordion>

<div id="agencies" />

<Accordion title="代理店">

**データの可用性：** 代理店へのAAPの影響は、広告主の影響と似ています。広告代理店が所定のアプリのローデータを利用でき、AAPが特定のユーザーのデータに適用される場合、広告主向けの[限定的な計測データのルール](/docs/apply-aggregated-advanced-privacy-framework#高プライバシー一括設定におけるデータ可用性の原則)に従ってデータが利用できます。

**代理店がアドネットワークの高プライバシーポストバック設定を変更する場合：**

* 高プライバシー一括設定 (AAP) がオフの場合、各連携パートナーの高プライバシーポストバックを設定できます。
* デフォルトでは、広告主のみが高プライバシーポストバック設定を変更できますが、広告主が代理店に、アドネットワークの高プライバシーポストバック設定を有効にする権限を明示的に付与することができます。

**代理店に高プライバシーポストバックを設定する権限を付与する**

![agency_advanced_privacy.png](https://files.readme.io/ac4a1aae41e9e39b9759006db84ea14df7495d0a14c02df7dbfb8dd93a2d2c23-35847865322129.png)

**代理店に高プライバシーポリシーの設定を許可する方法**：

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー** へ移動します。
2. 代理店を選択します。
3. **権限**タブで、**高プライバシーポストバック設定をオンにします。**
4. **保存**をクリックしてください。

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高プライバシーポストバック & ポストバックマクロ：アドネットワーク向け</Anchor>

<div data-zendesk-anchors="aggregated-advanced-privacy-framework=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9Aaap h_01HDPDE0H3SYFWBHK59HBV2P6N=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9Aaap aapimpacted-features=aap%E3%81%8C%E5%BD%B1%E9%9F%BF%E3%81%99%E3%82%8B%E6%A9%9F%E8%83%BD h_01HDPDE0H339BPACN235V70MWW=aap%E3%81%8C%E5%BD%B1%E9%9F%BF%E3%81%99%E3%82%8B%E6%A9%9F%E8%83%BD data-availability-principles-in-aggregated-advanced-privacy=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9A%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E5%8F%AF%E7%94%A8%E6%80%A7%E3%81%AE%E5%8E%9F%E5%89%87 h_01HDPDE0H3QBE60DVBZ1MWNB9N=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9A%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E5%8F%AF%E7%94%A8%E6%80%A7%E3%81%AE%E5%8E%9F%E5%89%87 paid-and-owned-media-data-availability=%E6%9C%89%E6%96%99%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%81%A8%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HDPDE0H326EXNCQHPVJWXK3H=%E6%9C%89%E6%96%99%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%81%A8%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HDPDE0H3TBDSXCNW5Q3E1Q7P=paid-media paid-media-data-availability-by-att-status=att%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E5%88%A5-%E5%BA%83%E5%91%8A%E5%AA%92%E4%BD%93%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HDPDE0H3SACYAV19WQD9TCQ3=att%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E5%88%A5-%E5%BA%83%E5%91%8A%E5%AA%92%E4%BD%93%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HDPDE0H4M4XPE1C54K284BGW=owned-media controlling-aap=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC-%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9A%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%AB h_01HDPDE0H4VQC2DWAV68Q9VDVQ=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC-%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9A%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%AB h_01HDPDE0H4BHG114REGTWCDBP9=aap-central-switch aap-enabled=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9Aaap%E3%81%8C%E6%9C%89%E5%8A%B9%E3%81%AE%E5%A0%B4%E5%90%88 h_01HDPDE0H4SC810EBK7ZGQ02K0=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9Aaap%E3%81%8C%E6%9C%89%E5%8A%B9%E3%81%AE%E5%A0%B4%E5%90%88 aap-disabled=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9Aaap%E3%81%8C%E7%84%A1%E5%8A%B9%E3%81%AE%E5%A0%B4%E5%90%88 h_01HKHPGQ1R6HZEXSRTX7ATVWE9=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9Aaap%E3%81%8C%E7%84%A1%E5%8A%B9%E3%81%AE%E5%A0%B4%E5%90%88 h_01HDPDE0H4FRDXWRCYAWTPZZWE=partner-advanced-privacy-switch 01HKHPEBBFGQ5ZX4J6G50GEN64=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E4%B8%80%E6%8B%AC%E8%A8%AD%E5%AE%9A%E3%81%AE%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF h_01HDPDE0H4PDJ4TC02TED0DB8P=ad-networks postbacks-to-ad-network-partners=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%B8%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HDPDE0H47ENYTWRVFPX0VTZC=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%B8%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF postbacks-for-attributed-ad-networks=%E6%88%90%E6%9E%9C%E3%81%8C%E7%B4%90%E3%81%A5%E3%81%8F%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HDPDE0H4B01YG577QZCG7TA7=%E6%88%90%E6%9E%9C%E3%81%8C%E7%B4%90%E3%81%A5%E3%81%8F%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%B8%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF postbacks-for-unattributed-partners=%E6%88%90%E6%9E%9C%E3%81%AE%E7%B4%90%E3%81%A5%E3%81%8B%E3%81%AA%E3%81%84%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%B8%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HDPDE0H63ZMV255SN7EKDRMV=%E6%88%90%E6%9E%9C%E3%81%AE%E7%B4%90%E3%81%A5%E3%81%8B%E3%81%AA%E3%81%84%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%B8%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HDPDE0H67T1XFTEB2N0NN6YN=analytics-partners h_01HDPDE0H6AM91W49W2G2Z94DM=agencies h_01HDPDMX05ZZCAMW4TTWF4M4YN=%E5%8F%82%E7%85%A7" />
