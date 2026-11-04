---
title: XsollaとAppsFlyerの連携
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2024-03-25T06:20:28Z'
  edited_at: '2026-10-28T09:04:05Z'
  id: 23593013687185
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/23593013687185
---
> **概要：** AppsFlyerの連携済みパートナーであるXsollaは、従来のアプリプラットフォームを介さない決済処理を専門とする、ゲームコマースのテクノロジーパートナーです。 XsollaとAppsFlyerを連携すると、Xsolla Web Shopの購入・収益データをAppsFlyerに自動送信できます。Web Shopでの購入も含めた、ゲーム全体のROASとLTVを把握できます。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="integration-types" />

## 連携方式

Xsollaとの連携には、次の2つの方式があります。

* [テクノロジーパートナー連携](#テクノロジーパートナー連携の設定)：Web Shopの購入と収益を、モバイルのアプリ内イベントとしてXsollaから送信します。通常のアプリストアでの購入に加え、これらのデータもモバイルアプリのキャンペーンのROASとLTVに反映できます。
* [PBA Web SDK連携](#pba-web-sdk連携の設定)：Web Shopの購入と収益を、WebイベントとしてXsollaから送信します。これにより、ゲームユーザーをWeb Shopに直接誘導するWebキャンペーンの成果をAppsFlyerで計測できます。

**前提条件：**

* 連携の設定を始める前に、<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに問い合わせて</Anchor>アカウントを作成してください。
* 連携を正しく動作させるには、カスタマーユーザーID（CUID）をAppsFlyerに共有し、Xsollaに共有するユーザーIDと一致させてください。 IDを一致させることで、ユーザーがXsolla Web Shopにログインでき、ユーザーデータがAppsFlyerに正確に送信されます。

<div id="setting-up-the-tech-partner-integration" />

## テクノロジーパートナー連携の設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   **注意：** パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携</Anchor>を参照してください。

設定で使用するのは、<strong>［連携］</strong>タブのみです。

<div id="integration-tab" />

<Accordion title="連携タブ">

<div id="activate-partner" />

#### パートナーを有効化

初回の設定時は、［**パートナーを有効化**］をオンにして、連携を設定できるようにします。 Xsollaと連携している間は、オンにしておく必要があります。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>を参照してください。

#### Advanced Privacy

iOSアプリでは、［<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">Advanced Privacy</Anchor>］のトグルが表示されます。オンにすると、パートナーとのユーザー識別子の共有が制限されます。アプリ設定で［<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor>］がオンの場合、［**Advanced Privacy（iOS 14.5以降）**］はデフォルトでオンになり、変更できなくなります。

<div id="default-postbacks" />

#### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にXsollaへデフォルトポストバックを送信します。このセクションで、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">ポストバックを設定</Anchor>します。

* **オフ：** インストールポストバックはXsollaに送信されません。  
  **注意：** XsollaとAppsFlyerの連携では、インストールポストバックを送信する必要はありません。そのため、オフに設定することを推奨します。
* **オーガニックを含むすべてのメディアソース：** すべてのパートナーの成果として計測されたイベントと、オーガニックのイベントのインストールポストバックを送信します。

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

<div id="in-app-event-postbacks" />

#### アプリ内イベントポストバック

このセクションでは、ポストバックを介してAppsFlyerのイベントをパートナーのイベントに対応付けます。

![xsolla-af-login-3.jpg](https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg)

1. ［**アプリ内イベントポストバック**］をオンにします。
2. ［**イベントを追加**］をクリックし、SDKまたはサーバー間（S2S）のイベントをリストに追加します。
3. 以下のパラメータを設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | アプリに組み込んだSDK、またはサーバー間イベントからAppsFlyerが受信したイベント名です。<br /><br />**注意：**<ul><li>Xsollaでは、上のスクリーンショットのように、`af_login`またはモバイルアプリへのログインを示す別のイベントを必ず追加してください。</li></ul> |
| **パートナー側のイベント名／ID** | Xsollaに送信するイベントの対応する名前を入力します。 Xsollaではイベント名を自由に設定できるため、このフィールドには任意の名前を使用できます。 |
| **対象ユーザーの流入元** | すべてのパートナーの成果として計測されたイベントとオーガニックのイベントを送信するには、［**オーガニックを含むすべてのメディアソース**］を選択します。 |
| **送信するデータ** | <ul><li>**値も収益も送信しない**：パラメータ（値や収益）を含めず、イベント自体のみを送信します。</li><li>**値のみ送信し、収益は送信しない**：収益値を**除く**すべてのパラメータを送信します。</li><li>**値と収益を送信する**：収益値を**含む**すべてのイベントパラメータを送信します（イベントに収益値がある場合）。</li></ul>注意：XsollaとAppsFlyerの連携では、値や収益の送信は必須ではありません。そのため、どのオプションを選択してもかまいません。 |

4. ［**連携を保存**］をクリックします。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Xsollaでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

Xsollaとの連携では、コストデータには対応していません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

Xsollaとの連携では、広告収益データには対応していません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

Xsollaでは、権限の設定は利用できません。

</Accordion>

<div id="setting-up-the-pba-web-sdk-integration" />

## PBA Web SDK連携の設定

この連携により、PBAダッシュボードにLTV（顧客生涯価値）のデータと分析結果を表示し、アプリの成果を分析できます。

**連携を設定するには、以下の手順を実施します。**

1. **AppsFlyerでの操作：** <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer?query=adding%20an%20app">Xsollaのアプリを追加</Anchor>します。プラットフォームに<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#web-pba">Web (PBA)</Anchor>を選択し、次の情報を入力します。
   * WebアプリのURLには、Web Shopのドメインを使用します。たとえば、Web Shopのドメインが[www.webshop.com](http://www.webshop.com,)の場合、それをWebアプリのURLに使用します。
   * アプリ名には任意の値を使用します。
2. **AppsFlyerでの操作：** 次の情報で<Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings#add-brand-bundle">Xsollaのバンドルを追加</Anchor>します。
   1. バンドル名には任意の名前を入力します。
   2. バンドルのWebアプリとして、前の手順で作成したWebアプリを選択します。
3. **Xsolla側の設定：** XsollaのPublisher AccountにAppsFlyerを接続します。
   1. <Anchor target="_blank" href="https://publisher.xsolla.com/">Publisher Account</Anchor>でプロジェクトを開きます。
   2. サイトを選択し、**Configure**をクリックします。
   3. **Site settings**タブで、**Apps**セクションに移動します。
   4. **AppsFlyer**ブロックで、**Connect**をクリックします。  
      [![xsolla-connect.jpg](https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg)](https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg)
   5. **AppsFlyer Dev Key**フィールドに、AppsFlyerのWeb用Devキーを入力します。 [AppsFlyerでこのキーを確認する方法](/docs/xsolla-integration-with-appsflyer#appsflyerでのweb用devキーの確認)は、以下を参照してください。
   6. **Connect**をクリックします。

<div id="finding-the-web-dev-key-in-appsflyer" />

#### AppsFlyerでのWeb用Devキーの確認

1. <strong>［マイアプリ］</strong>ページで、<strong>［ブランドバンドルを表示］</strong>をクリックします。
2. Xsollaのバンドル行にあるコピーアイコンをクリックします。

![xsolla-brand-bundle2.jpg](https://files.readme.io/9cb6a9e872e482f7e426aea7e615afb1f91017c569e7cd67286cdb946d9d2445-26923253273361.jpg)

<div id="identifying-xsollas-events-in-appsflyer" />

## AppsFlyerでのXsollaイベントの識別

<div id="tech-partner-s2s-integration" />

### テクノロジーパートナー（S2S）連携：

Xsollaは、次の2つのアプリ内イベントをAppsFlyerに送信します。

* **xsolla-billing-payment**：商品の購入
* **xsolla-billing-refund**：商品購入の返金

どちらもモバイルアプリのアプリ内イベントとして扱われます。

<div id="web-sdk-integration" />

### Web SDK連携：

Xsollaは、広告主の施策に合わせてカスタマイズした、複数のWebイベントをAppsFlyerに送信します。最も重要なイベントは、収益データを含む「PURCHASE」です。  
XsollaのWebイベントは、PBAのWebアトリビューションとData Lockerのローデータ「Webイベント」レポートに表示されます。

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

PC／コンソールへの対応：AppsFlyerとXsollaの連携は、現時点ではPC／コンソールアプリに対応していません。

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="https://developers.xsolla.com/solutions/web-shop/analytics/appsflyer/">Xsollaのドキュメント</Anchor>

<div data-zendesk-anchors="h_01HST42K52VQDWCWGP7TQVFB2X=%E9%87%8D%E8%A6%81 integration-types=%E9%80%A3%E6%90%BA%E6%96%B9%E5%BC%8F h_01J3DB8MCNQKKKCV1M39KN7Q0H=%E9%80%A3%E6%90%BA%E6%96%B9%E5%BC%8F setting-up-xsolla=%E3%83%86%E3%82%AF%E3%83%8E%E3%83%AD%E3%82%B8%E3%83%BC%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HST42K52JKQ70F7Y5PHDZAZ5=%E3%83%86%E3%82%AF%E3%83%8E%E3%83%AD%E3%82%B8%E3%83%BC%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HST42K52RCTSGRNRCJ1C70NP=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HST42K52BBJ6JS5KM0WCN6CF=advanced-privacy default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HST47F5BXWV5W8BNHS9M2MTN=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKEAV3GG6X17X3NCCSWJAS=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab setting-up-the-pba-web-sdk-integration=pba-web-sdk%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J3DEZZHDPSRZRXDV6FD4HY6Q=pba-web-sdk%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A finding-the-web-dev-key-in-appsflyer=appsflyer%E3%81%A7%E3%81%AEweb%E7%94%A8dev%E3%82%AD%E3%83%BC%E3%81%AE%E7%A2%BA%E8%AA%8D h_01J3F247QEAFGRW7CEP941KZE9=appsflyer%E3%81%A7%E3%81%AEweb%E7%94%A8dev%E3%82%AD%E3%83%BC%E3%81%AE%E7%A2%BA%E8%AA%8D identifying-xsollas-events-in-appsflyer=appsflyer%E3%81%A7%E3%81%AExsolla%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%AD%98%E5%88%A5 h_01JMHXRGB60RVZ399FNHS18ZHZ=appsflyer%E3%81%A7%E3%81%AExsolla%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%AD%98%E5%88%A5 tech-partner-s2s-integration=%E3%83%86%E3%82%AF%E3%83%8E%E3%83%AD%E3%82%B8%E3%83%BC%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BCs2s%E9%80%A3%E6%90%BA h_01JMHXS5MZ7B781WNNVYMDGGFY=%E3%83%86%E3%82%AF%E3%83%8E%E3%83%AD%E3%82%B8%E3%83%BC%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BCs2s%E9%80%A3%E6%90%BA web-sdk-integration=web-sdk%E9%80%A3%E6%90%BA h_01JMHXX7VBPPS7GQ0VBGWRPT7X=web-sdk%E9%80%A3%E6%90%BA h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations h_01J1C78W0MP8KXFB4251FKWJBX=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
