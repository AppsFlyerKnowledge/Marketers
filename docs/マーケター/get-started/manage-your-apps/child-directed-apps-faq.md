---
title: 子ども向けアプリ - FAQ
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2023-09-05T19:02:32Z'
  edited_at: '2026-10-14T09:29:36Z'
  id: 18324823209745
  locale: ja
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ja/articles/18324823209745
---
**概要：** 概要： 子ども向けアプリに関するよくあるご質問（FAQ）の回答をご覧ください。

<div id="overview" />

## 概要

子ども向けアプリには、子どものプライバシーを保護するための多くのポリシー、法律、規制があります。主要なものは [COPPA](https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa)と[GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN#d1e2029-1-1)です。近年、iOSやAndroidなどのプラットフォームでは、子どものプライバシーを向上させるための施策が実装されています。アプリを作成するときに最初に行うべきことの一つは、アプリの対象を子どものみとするか、全年齢（子どもと大人の両方）とするかを決定することです。この記事から、子ども向けアプリにコンプライアンスに準拠したアトリビューションソリューションを実装する方法を学んでください。

<div id="if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later" />

<div id="adding-a-child-directed-app" />

## 子ども向けアプリの追加

<div id="what-steps-do-i-need-to-take-when-adding-a-childdirected-app" />

<Accordion title="子ども向けアプリを追加する場合に必要なステップとは？">

1. <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">アプリ追加のウィザードに従います</Anchor>。
2. ウィザードのステップ２では、<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#アプリのユーザー層を定義する">子ども向けアプリに関する手順</Anchor>をご覧ください。
3. アプリが追加されたら、次の操作を行います：
   * SDKに <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#アプリへのdevキーの組み込み">Devキー</Anchor>を実装します。
   * 適切な<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">プライバシーコントロール</Anchor>を含めます。

  詳しくは[アドネットワークへのコンプライアンスツールの実装](#appsflyerのコンプライアンスツールの導入)をご覧ください。

</Accordion>

<div id="when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children" />

<Accordion title="新しいアプリを追加する場合、子ども向けアプリに指定した後に起こることとは？">

アプリを追加してから2週間後に、子供向けアプリのプライバシーコントロールを実装したことを確認するよう通知が届きます。確認後、確認メッセージが表示されます。通知センターから確認メッセージにいつでもアクセスでき、監査ログで確認の詳細を確認できます。

</Accordion>

この段階では、アプリが子ども向けかどうかを選択すると元に戻すことはできません。これは、アプリの追加時にのみ選択できます。


<div id="how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps" />

<Accordion title="チームメンバーがアプリを子ども向けと指定したかどうかを確認する方法は？">

アプリが子ども向けと指定されていることが確認されたら、次の2つの方法で確認することができます：

* 通知設定
* **監査ログ**

  2. セキュリティセンターを選択します。
  3. 監査ログセクションにて、**監査ログを表示**をクリックしてください。  
     マイアプリ/strong>サービスで確認の詳細を確かめることができます。

</Accordion>

<div id="implementing-appsflyer-compliance-tools" />

## AppsFlyerのコンプライアンスツールの導入

<div id="how-do-i-know-which-tool-to-use" />

<Accordion title="使用すべきツールを知る方法は？">

アプリが子ども、あるいは全年齢（子どもと大人）を対象としている場合、この記事の法的要件に沿った推奨ツールを使用できます。その他のSDKリソースについては、このページの下部を参照してください。

<div id="examples-of-compliance-tools-and-their-use" />

#### コンプライアンスツールとその使用例

<table><thead><tr><th>ツール</th><th>iOS</th><th>Android</th><th>データの可用性</th></tr></thead><tbody><tr><td><span id="strict-sdk"></span><p><a href="./additional-sdk-integration-guide#strictmode-sdk" target="_blank">StrictモードSDK</a>：  </p><p>IDFAがAppsFlyerに送信されないようにします。これは通常、子ども向けアプリに推奨されます。</p></td><td><span><span>✓</span></span></td><td>- </td><td>広告主のみ利用可能</td></tr><tr><td><span id="standard-sdk-using-the-setdisableadvertisingidentifiers-api"></span><p><a href="./android-oaid-implementation-in-the-sdk#opting-out-of-oaid-collection" target="_blank"><kbd>setDisableAdvertisingIdentifiers</kbd>API</a>を使用した標準のSDK：</p><p>AAID（GoogleのAndroidの広告ID）がAppsFlyerに送信されないようにします。これは通常、子ども向けアプリに推奨されます。</p></td><td>- </td><td><span><span>✓</span></span></td><td>広告主のみ利用可能</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-specific-ad-networks"></span><p><a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank">特定の</a>アドネットワーク向けの<kbd><strong>setSharingFilterForPartners</strong>ファンクション</kbd>を使用した、年齢ゲート付きの標準のSDK </p><p>ユーザーが年齢ゲート\*を下回った場合に、そのようなアドネットワークがデータにアクセスできないようにします。</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>特定のアドネットワークに限定</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks"></span><p> <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank">すべての</a>アドネットワーク向けの<kbd><strong>setSharingFilterForPartners</strong>ファンクション</kbd>を使用した、年齢ゲート付きの標準のSDK</p><p>ユーザーが年齢ゲート\*を下回った場合に、すべてのアドネットワークがデータにアクセスできないようにします。</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>広告主のみ利用可能</td></tr><tr><td><span id="skan-only"></span><p><a href="./skadnetwork-skan-solution-guide" target="_blank">SKANのみ</a>：</p><p>広告IDが他のアドネットワークに共有されないようにします。</p></td><td><span><span>✓</span></span></td><td>- </td><td>広告主のみ利用可能</td></tr><tr><td><span id="sdkless-solutions-less-recommended"></span><p>SDK-lessソリューション（あまり推奨されません）：</p><p><span>SDK</span><span>経由でデータを送信しない代わりに、AppsFlyerにデータを送信するように独自のサーバーを設定します。</span></p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>設定に応じて</td></tr><tr><td><span id="aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners"></span><p>高プライバシー一括設定のフレームワーク </p><p>Apple ATTのプライバシーレベルを適用し、ユーザーレベルデータを<span>広告主やアドネットワークが</span><span>利用できない</span>ようにします。</p></td><td><span><span>✓</span></span></td><td>- </td><td>広告主やアドネットワークではご利用いただけません。</td></tr><tr><td colspan="4"><span id="-when-applying-an-age-gate-block-userlevel-data-that-doesnt-fall-under-the-age-gate-is-available-in-raw-data-reports"></span><p>\* 年齢ゲートのブロックを適用すると、年齢ゲートに該当しないユーザーレベルデータがローデータレポートで利用できます。</p></td></tr></tbody></table>

</Accordion>

<div id="how-does-using-the-tools-in-the-guide-affect-attribution" />

<Accordion title="この記事のツールを使用すると、アトリビューションにどのような影響がありますか？">

<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">AppsFlyerのコンプライアンスソリューションガイド</Anchor>には、それぞれ[異なるレベルのコントロール](#how-do-i-know-which-tool-to-use)を持つさまざまなツールが用意されています。アトリビューションへの影響は、実装する特定のツールによって異なります。

デバイスIDなどのユーザーデータの送信を制限するツールを使用する場合、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#probabilistic-modeling">確率論的モデリング</Anchor> や<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#install-referrer-android-only">インストールリファラー（Android向け）</Anchor>などの他のアトリビューション方法が使用されます。

ユーザーレベルデータを送信しないツールはプライバシーが保護されていると見なされ、集計されたキャンペーンデータを受信できます。

</Accordion>

<div id="i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do" />

<Accordion title="利用しているアドネットワークがコンプライアンスに準拠しているか分からない場合、どうすれば良いですか？">

多くの場合、連携しているアドネットワークが関連する法律に準拠しているかどうかは不明です。この質問は、アドネットワークに照会することができます。アドネットワークが準拠していない場合、あるいは確信が持てない場合は、データの共有を控えることができます。<strong><Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners`ファンクション</Anchor></strong>を使用して、アプリデータの受信をブロックするアドネットワークを指定できます。また、このファンクションを使用してすべてのアドネットワークをブロックすることも可能です。その他のコンプライアンスツールの例を参照してください。

</Accordion>

<div id="do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant" />

<Accordion title="アドネットワークがコンプライアンスに準拠している場合、AppsFlyerのコンプライアンスツールを実装する必要はありますか？">

AppsFlyerのコンプライアンスツールは、常に実装する必要があります。どれがニーズに適しているかは、アプリのオーディエンスによって異なります。連携しているアドネットワークがCOPPA、GDPR、適用される法律や規則、またはそれを必要とするその他のプラットフォーム規則で許可されている限られた目的のために、適切な同意を得てデータプロセッサーとしてのみ共有したデータを取り扱うことを約束している場合は、**<Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners`ファンクション</Anchor>**（メディアソース名）を使用できます。

これは、連携している各アドネットワークに適用されます。

</Accordion>

<div id="what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this" />

<Accordion title="どのデータをアドネットワークに共有していますか？ これに対してどのようなコントロールを持っていますか？">

<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">SRN</Anchor>ではないアドネットワークは、ポストバックを介してデータを受信します。このアドネットワークは、ポストバックに含めるイベントを定義することができます。インストールポストバックはデフォルトでアトリビューションに送信されますが、アプリ内イベントのポストバックは特定のイベントが送信されるように設定した場合にのみ送信されます。 ポストバックがSDKによってブロックまたは制限されていない限り、アプリのユーザーエンゲージメント（インストール、アプリ内イベント、リエンゲージメント）に関連するユーザーレベルデータが含まれる可能性があります。

ポストバックを除き、アドネットワークと代理店は<Anchor target="_blank" href="/marketers/ja/docs/manage-data-access-permissions">プラットフォームを経由したデータへのアクセスが制限されています</Anchor>。

**ポストバックを介してアドネットワークに送信されたデータを確認するには：**

* レポート > <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview#postbacks">ローデータ出力</Anchor>メニューから、**ポストバックレポート**をダウンロードします。

**送信するデータをコントロールするには：**

* 特定のデータの送信をブロック、または制限するために、<Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">setSharingFilterForPartners</Anchor> などのSDKのコンプライアンス ツールを使用します。
* デフォルトのポストバックと <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">アプリ内イベントのポストバック</Anchor>の送信先を、イベントがアトリビュートされたアドネットワーク、またはオーガニックを含むすべてのメディアソースのどちらかから選択します。

**iOSユーザーのユーザーレベルのアトリビューション データの可用性をコントロールするには：**

* Apple ATTのプライバシーレベルを適用するために、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高プライバシー一括設定のフレームワーク</Anchor>を使用します。

</Accordion>

<div id="do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked" />

<Accordion title="アプリが子ども向けで、すべてのアドネットワークがブロックされている場合、SDKは必要ですか？">

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">SDK実装の概要</Anchor>
> * SDKSDK：プライバシー保護の方法
> * SDKSDK：ユーザーのプライバシー設定
> * <Anchor target="_blank" href="https://www.appsflyer.com/trust/privacy/">AppsFlyerのプライバシー対策</Anchor>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HA20EGWDBSNAFZ7WNXJFFRRV=%E6%A6%82%E8%A6%81 general-questions=%E5%AD%90%E3%81%A9%E3%82%82%E5%90%91%E3%81%91%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%BF%BD%E5%8A%A0 h_01H9ZK2THJVFYQ49HHRYKZZNEK=%E5%AD%90%E3%81%A9%E3%82%82%E5%90%91%E3%81%91%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E8%BF%BD%E5%8A%A0 h_01HHCE11YQX4DKV5BEW6QHKN55=what-steps-do-i-need-to-take-when-adding-a-childdirected-app when-adding-a-new-app-what-happens-after-i%E2%80%99ve-indicated-my-app-is-directed-towards-children=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children h_01H9ZK2THJ225P38Q9CHQSTNY4=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children h_01H9ZK2THJK5Q5EE3K38GTCCT7=how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps implementing-compliance-tools=appsflyer%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%97%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%82%B9%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AE%E5%B0%8E%E5%85%A5 h_01HGZ5VAJHNJVM2ENFZ3DEAK42=appsflyer%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%97%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%82%B9%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AE%E5%B0%8E%E5%85%A5 h_01HGZ4VWDBZJE8RWM05EJNH0S9=how-do-i-know-which-tool-to-use examples-of-compliance-tools-and-their-use=%E3%82%B3%E3%83%B3%E3%83%97%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%82%B9%E3%83%84%E3%83%BC%E3%83%AB%E3%81%A8%E3%81%9D%E3%81%AE%E4%BD%BF%E7%94%A8%E4%BE%8B h_01HHEED2AQTW7G0MJJZDZV2B09=%E3%82%B3%E3%83%B3%E3%83%97%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%82%B9%E3%83%84%E3%83%BC%E3%83%AB%E3%81%A8%E3%81%9D%E3%81%AE%E4%BD%BF%E7%94%A8%E4%BE%8B standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function%C2%A0for-all-ad-networks=standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks aggregated-advanced-privacy-framework%C2%A0%0Aenforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners=aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners h_01HKHX0GBS9EWMXMY387FQ95X1=how-does-using-the-tools-in-the-guide-affect-attribution h_01HH9EAB8T4Z6RMT8MVS77Q6BP=i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do h_01HKHWSQQKEDZBCDH0P8H760K6=do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant h_01HHEEQ4AAEZSA0YB6V2DSRYXK=what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this h_01HKJ843208PMQF1MCYCWMJC3H=do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked h_01HE7TQV7VDSEX3E7RTKAHBMNN=%E5%8F%82%E7%85%A7" />
