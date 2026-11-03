---
title: Meta広告｜iOSの合算イベント測定（AEM）
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-10-09T16:40:55Z'
  edited_at: '2026-10-28T09:16:45Z'
  id: 19228737402129
  locale: ja
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ja/articles/19228737402129
---
> **概要：** Meta広告でiOSのコンバージョンやアプリ内イベントを最適化し、iOSのリエンゲージメントを計測するAEMソリューションについて説明します。

## 概要

AppsFlyerは、<Anchor target="_blank" href="https://www.facebook.com/business/help/721422165168355">Meta広告の合算イベント測定（AEM）</Anchor>に対応しています。このソリューションでは、以下のアトリビューション方法を使用して、iOS 14以降のデバイスのWebイベントとアプリイベントを計測できます。

* [リエンゲージメント向けアプリAEM](#リエンゲージメント向けアプリaem)
* [アプリの宣伝向けアプリAEM](#アプリの宣伝向けアプリaem)

AEMソリューションでは、イベントがAEMの要件を満たす場合、Metaは広告主からのコンバージョンとアプリ内イベントのポストバックを受信します。イベントがAEMの要件を満たしているかどうかは、以下を参照してください。

* [アプリイベントのAEM利用要件の確認](#アプリイベントのaem利用要件の確認)

## リエンゲージメント向けアプリAEM

Meta広告はAEMを使用して、広告IDを取得できないiOSユーザーについて、ディープリンクによるリエンゲージメントアトリビューションを提供します。

### アトリビューションの流れ

Meta広告は、AEMの`campaign_ids`識別子とともに、アトリビューションデータをディープリンクに追加します。 AppsFlyerは、ディープリンクURLに含まれるキャンペーンパラメータを受信して処理し、以下を行います。

* 集計レポートデータをMeta広告に提供します。
* Meta広告が追加したディープリンク情報に基づいてアトリビューションを行います。
* ディープリンクのアトリビューションデータを、ローデータレポートと集計データレポートに含めます。

### アトリビューションデータのパラメータ

Meta広告から共有される以下のアトリビューションデータのパラメータが、レポートに含まれます。

* `ad_id`
* `adgroup_id`
* `campaign_id`
* `campaign_group_id`
* `account_id`

> 📘 **注意**
>
> リマーケティングにAEMを利用するため、AppsFlyer SDKはディープリンクを開いた際に`campaign_ids`文字列を取得します。デフォルトでは、SDKはすべてのドメインのディープリンクを共有します。連携をカスタマイズしている場合は、AppsFlyerのドメインだけでなく、Metaのドメインを含むすべてのドメインのディープリンクを共有するよう設定されていることを確認してください。

### ディープリンクによるリエンゲージメントアトリビューションのよくある質問

<div id="what-must-the-advertiser-do-to-enable-this-attribution" />

<Accordion title="このアトリビューションを有効にするため、広告主側で必要な対応はありますか？">

アトリビューション用のパラメータを受信するために、広告主側で**対応する必要はありません**。

ただし、ディープリンクによるリエンゲージメントを計測するには、<strong>［リエンゲージメントアトリビューション］</strong>を**オンにする必要があります**。

**注意：** Meta広告のAEMに関する利用規約に基づき、リエンゲージメント計測を有効にすると、Meta広告へのポストバックに、アトリビューションデータの一部としてIPアドレスの一部が含まれる場合があります。

</Accordion>

<div id="what-about-agencies-and-meta-campaign-management-partners" />

<Accordion title="代理店とMetaキャンペーン管理パートナーへの対応はどうなっていますか？">

現時点では、代理店とMetaキャンペーン管理パートナーへのアトリビューションはサポートされていません。そのため、すべてのトラフィックはMeta広告にアトリビューションされます。これは一時的な制限であり、近日中に変更される予定です。

</Accordion>

<div id="are-there-any-restrictions-on-data-from-this-attribution" />

<Accordion title="このアトリビューションのデータに制限はありますか？">

ディープリンクによるアトリビューションのデータは、レポートの制限対象ではありません。そのため、すべてのデータが集計レポートとユーザーレベルのローデータレポートの両方に表示されます。

</Accordion>

## アプリの宣伝向けアプリAEM

### AEMの利用要件

アプリがMeta広告のAEM利用要件を満たしている場合、広告セットの作成時に、デフォルトで<strong>［合算イベント測定］</strong>が選択されます。この場合、キャンペーンでAEMとSKANを併用できます。代わりに<strong>［AppleのSKAdNetwork］</strong>を選択すると、キャンペーンに適用されるのはSKANのみになります。その場合、AppsFlyerでMeta広告のアプリ内アクティビティを計測できる範囲が限られます。

<Image alt="aem_meta_ads_platform.png" src="https://files.readme.io/9ce9735024294967545fee9e9fc44cc49834ffcb5b3496febd50f8466c1bd397-46192072798737.png" width="563px" />

> 📘 **注意**
>
> AEMの利用要件に関して問題がある場合は、[アプリイベントのAEM利用要件の確認](#アプリイベントのaem利用要件の確認)を参照してください。

### AEMのデータ共有

**拡張データ共有**を使用すると、広告IDを取得できないユーザーのイベントも含め、要件を満たすすべてのコンバージョンイベントを、Meta広告での計測に利用できるようになります。

* 拡張データ共有がオフの場合、対象は広告IDを取得できるユーザーのコンバージョンイベントに限られます。広告IDのないユーザーのイベントは、共有もアトリビューションもされません。
* 拡張データ共有がオンの場合、広告IDを取得できないユーザーも含め、すべてのユーザーのコンバージョンイベントをMeta広告で利用できるようになります。 AppsFlyerは、これらのイベントをアトリビューションします。提供するデータには、デバイスID以外の追加のデバイス関連情報が含まれる場合があります。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#advanced_data_sharing">拡張データ共有</Anchor>を参照してください。

![AEM](https://files.readme.io/77e44d893994581dbe1a058fb5bebbf9b5e8bf167abe6e9d35ea8aa809ceca4b-46192056604305.png)

> 📘 **注意**
>
> * ここでいうイベントには、インストール、アプリ起動、アプリ内イベントがすべて含まれます。
> * **拡張データ共有**を有効にする前に、第三者によるデータの利用も含め、これらのデータをMeta広告に提供することが、適用されるプラットフォームのポリシーや規制に準拠していることを確認してください。提供するデータには、IPアドレス、anon\_ids（取得できる場合）、vendor\_id、ユーザーエージェントが含まれる場合があります。
> * サーバー間（S2S）で送信するアプリ内イベントについて、Meta広告は、イベントペイロードに**IPアドレス**と<strong>ベンダー識別子（IDFV）</strong>の両方を含めることを求めています。これらの識別子がないイベントは、Meta広告のAEMによるアトリビューションの対象になりません。
> * アプリの宣伝向けのMeta AEMには、非確定的なビュースルーのアトリビューション申告が含まれる場合もあります。 Meta AEMの非確定的なビュースルーアトリビューションに対応するには、アプリ単位の［キャンペーン計測モデリングによるビュースルーアトリビューションを有効にする］がオンになっていることを確認してください。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">確率論的モデリングによるビュースルーアトリビューション</Anchor>を参照してください。

## アプリイベントのAEM利用要件の確認

Metaイベントマネージャで、アプリイベントがAEMの利用要件を満たしているか確認できます。アプリイベントが要件を満たすと、選択したAEMキャンペーンの成果を広告マネージャで確認できます。確認方法の詳細は、<Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">Metaのドキュメント</Anchor>を参照してください。

## AEMの有効化手順のまとめ

AppsFlyerでMeta広告のAEMを有効にする際のチェックリストとして、以下の表を使用してください。

| **ソリューション** | **トグル** | **トグルの場所** | **効果** |
| --- | --- | --- | --- |
| **リマーケティング向けAEM（リエンゲージメント）** | リエンゲージメントアトリビューション | パートナー連携（Meta広告） | リマーケティング向けのAEM（リエンゲージメントアトリビューション）を有効にします。 |
| **アプリの宣伝向けAEM（インストール）** | 拡張データ共有 | パートナー連携（Meta広告） | アプリの宣伝向けのAEMを有効にします。広告IDを取得できないユーザーのイベントもMetaで計測できるようにし、該当する場合は非確定的なアトリビューション申告も受け入れます。 |
| **アプリの宣伝向けAEM（インストール）** | 確率論的モデリングによるビュースルーアトリビューションを有効にする | アプリ設定 | 非確定的なアトリビューション申告によるビュースルーアトリビューションを有効にします。 |

## トラブルシューティング

<div id="troubleshooting-ineligible-events-in-meta-aem" />

<Accordion title="Meta AEMの利用要件を満たさないイベントのトラブルシューティング">

Meta広告でアプリイベントが要件を満たさないと判定され、<strong>「Missing opt-out events」</strong>などのAEM関連エラーが表示される場合、通常はデータの欠落や設定不備が原因です。以下のチェックリストを使用して、よくある問題を特定し、解決してください。

> 🚧 **重要！**
>
> 以下の手順を完了した後、変更が反映されるまで時間を置いてください。変更の適用後、Meta広告でAEMの利用可否が反映されるまでに、最大**2～3日**かかる場合があります。

<div id="step-1-advanced-data-sharing-is-enabled" />

<Accordion title="ステップ1：拡張データ共有が有効か確認">

1. **［連携］**>**［連携済みパートナー］**><strong>［Meta広告］</strong>に移動します。
2. <strong>［拡張データ共有］</strong>がオンになっていることを確認します。

</Accordion>

<div id="step-2-ip-masking-is-disabled" />

<Accordion title="ステップ2：IPマスキングが無効か確認">

IPアドレスをマスキングしたイベントは、AEMの対象になりません。

* <strong>［アプリ設定］</strong>に移動します。
* <strong>［IPマスキング］</strong>がオフになっていることを確認します。

</Accordion>

<div id="step-3-servertoserver-s2s-events-include-required-parameters" />

<Accordion title="ステップ3：サーバー間（S2S）イベントに必須パラメータが含まれているか確認">

すべてのS2Sイベントに、以下を含める必要があります。

* **IPアドレス**
* **IDFV**（ベンダー識別子）

</Accordion>

<div id="step-4-review-att-consent-rate" />

<Accordion title="ステップ4：ATTの同意率を確認">

Metaは、IDFAがない、または値がすべて0になっているイベントの受信件数に上限を設けています。アプリがこの上限を超えると、次のエラーが表示される場合があります：**Advertiser Tracking Enabled parameter volume out of range.**

</Accordion>

<div id="step-5-postback-mapping-configuration" />

<Accordion title="ステップ5：ポストバックのマッピング設定を確認">

イベントポストバックで<strong>［すべて送信（オーガニックを含む）］</strong>が設定されていることを確認します。

</Accordion>

<div id="step-6-check-reengagement-settings-if-relevant" />

<Accordion title="ステップ6：必要に応じてリエンゲージメント設定を確認">

リエンゲージメントキャンペーンの場合：

* <strong>［アプリ設定］</strong>と**Metaの連携済みパートナーページ**の両方で、<strong>［リエンゲージメントアトリビューション］</strong>を有効にします。

</Accordion>

#### それでも解決しない場合

特定のイベントが引き続き要件を満たさない場合は、以下を行ってください。

1. Metaのイベントマネージャに移動し、画面の案内に従います。
2. 対象のアプリイベントを選択します。
3. 優先する接続方法として<strong>［MMP traffic］</strong>を設定します。

#### サポートが必要な場合

問題が解決しない場合は、以下を行ってください。

* サポートチケットを作成します。
* Meta広告で要件を満たさないと判定されたイベントが分かるスクリーンショットを添付します。

</Accordion>

<div id="i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible" />

<Accordion title="キャンペーンはAEMの利用要件を満たしていますが、ダッシュボードやレポートでAEMデータを確認できません">

Metaは次のように回答しています。「この更新は、MMPと連携して今後数か月かけて段階的に提供します。提供が完了するまで、一部の広告主は利用できない場合があります。」

</Accordion>

<div id="why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />

<Accordion title="AMMに同意した後も、AEMで計測されたインストールがローデータレポートに表示されないのはなぜですか？">

AAPが有効な場合、Metaの合算イベント測定（AEM）でアトリビューションされたインストールは、ローデータレポートから除外されます。これは、AMMに同意済みの場合も同様です。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HCAM4CEVRCG13CA32B0GM9QS=%E6%A6%82%E8%A6%81 app-aem-for-reengagement=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E5%90%91%E3%81%91%E3%82%A2%E3%83%97%E3%83%AAaem 01H88ZM20H99W37M0H6XXQVMQA=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E5%90%91%E3%81%91%E3%82%A2%E3%83%97%E3%83%AAaem attribution-flow=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%B5%81%E3%82%8C 01H7YJVNMV7QSZJWKZZA9042K6=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%B5%81%E3%82%8C attribution-data-parameters=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF 01H7YJVNMVPPCD08Z2R0V5GCMY=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_attribution_deeplink_note=%E6%B3%A8%E6%84%8F faqs-on-deep-link-reengagement-attribution=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AB%E3%82%88%E3%82%8B%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7YJVNMV4ZKMWKD06RC6GKFW=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AB%E3%82%88%E3%82%8B%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01H7YJVNMVSGMNJ3K84MCENXYG=what-must-the-advertiser-do-to-enable-this-attribution 01H7YJVNMVP7ZRCKXDRRH7GZBY=what-about-agencies-and-meta-campaign-management-partners are-there-any-restrictions-on-data-from-this%20attribution=are-there-any-restrictions-on-data-from-this-attribution 01H7YJVNMVQF0B0DV2NQYQVYHK=are-there-any-restrictions-on-data-from-this-attribution app-aem-for-app-promotion=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E5%AE%A3%E4%BC%9D%E5%90%91%E3%81%91%E3%82%A2%E3%83%97%E3%83%AAaem 01H88ZM20HQFMG962AZGYA98FR=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E5%AE%A3%E4%BC%9D%E5%90%91%E3%81%91%E3%82%A2%E3%83%97%E3%83%AAaem aem-eligibility=aem%E3%81%AE%E5%88%A9%E7%94%A8%E8%A6%81%E4%BB%B6 01H7YJVNMVPB054VFS60KH9N7W=aem%E3%81%AE%E5%88%A9%E7%94%A8%E8%A6%81%E4%BB%B6 h_01HR886Q0KPM99FCQXD6RDPSBK=%E6%B3%A8%E6%84%8F-1 aem-data-sharing=aem%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89 01H88ZM20HK2HY32M4BKZ4N0B9=aem%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89 01H7YK9CHHNARCD7M2VZRMEW6S=%E6%B3%A8%E6%84%8F-2 check-eligibility=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AEaem%E5%88%A9%E7%94%A8%E8%A6%81%E4%BB%B6%E3%81%AE%E7%A2%BA%E8%AA%8D 01JBHQSHF8NA4SGVJ3WYPRN9B3=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AEaem%E5%88%A9%E7%94%A8%E8%A6%81%E4%BB%B6%E3%81%AE%E7%A2%BA%E8%AA%8D enable-aem-toggles-summary=aem%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96%E6%89%8B%E9%A0%86%E3%81%AE%E3%81%BE%E3%81%A8%E3%82%81 h_01KJ28ETP9GK6TBTJK8SBZ5PFW=aem%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96%E6%89%8B%E9%A0%86%E3%81%AE%E3%81%BE%E3%81%A8%E3%82%81 faqs-and-troubleshooting=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 01H7YK9CHHZN78CBHFTQ7E9RKQ=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01K720W9MYXFTYG18368SKHGGC=troubleshooting-ineligible-events-in-meta-aem h_01K720W9MYDKK5Q2J1M8VT9JFP=%E9%87%8D%E8%A6%81 h_01K722GQSB92J5KFFYQNP5WR29=step-1-advanced-data-sharing-is-enabled h_01K722GQSBV3GY2ZNN29ENG7Q2=step-2-ip-masking-is-disabled h_01K722GQSBVTSC09EPPCZQ6WN3=step-3-servertoserver-s2s-events-include-required-parameters h_01K722GQSBSX06A56ZX8RJ6YKT=step-4-review-att-consent-rate h_01K722GQSB26TN65JVJD6R7BAV=step-5-postback-mapping-configuration h_01K722GQSBTD4J9TZHBRGYS1XV=step-6-check-reengagement-settings-if-relevant still-not-working=%E3%81%9D%E3%82%8C%E3%81%A7%E3%82%82%E8%A7%A3%E6%B1%BA%E3%81%97%E3%81%AA%E3%81%84%E5%A0%B4%E5%90%88 h_01K722GQSB8CXSSCVZPA3R3CJX=%E3%81%9D%E3%82%8C%E3%81%A7%E3%82%82%E8%A7%A3%E6%B1%BA%E3%81%97%E3%81%AA%E3%81%84%E5%A0%B4%E5%90%88 need-help=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%8C%E5%BF%85%E8%A6%81%E3%81%AA%E5%A0%B4%E5%90%88 h_01K722GQSBBB8KS8JNRBJZ4WWT=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%8C%E5%BF%85%E8%A6%81%E3%81%AA%E5%A0%B4%E5%90%88 01JCX7SKJ76KGW9SN7RCFA18E6=i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible why-can%27t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01K4ADBT26D2KD5MH568542XSV=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />
