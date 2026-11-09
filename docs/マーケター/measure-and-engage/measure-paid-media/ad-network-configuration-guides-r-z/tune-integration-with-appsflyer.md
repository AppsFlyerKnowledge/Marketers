---
title: AppsFlyerとTUNEを連携する
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-08-25T08:58:17Z'
  edited_at: '2026-10-14T09:31:27Z'
  id: 4406153487505
  locale: ja
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ja/articles/4406153487505
---
> **概要：** 概要： AppsFlyerの連携パートナーであるTUNEは、パートナー向けマーケティングプラットフォームです。  
> TUNEと連携し、流入経路の計測やアプリへのディープリンクを可能にします。

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hasoffers.png" width="79px" />

<div id="setting-up-tune-integration" />

## TUNEとの連携設定

AppsFlyerとTUNEの連携でクリックアトリビューションに対応します。

**前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer管理画面左メニュー **コラボレーション** > **Partner Marketplace**を選択します。  
   **編集するには：** AppsFlyer管理画面 左メニュー 連携 > **連携済みパートナー**を選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、 連携の設定ページに移動します。
4. **連携**タブにて、**パートナーを有効にする**トグルをオンにしてください。  
   **注: このトグルは、このパートナーの連携を続ける限り、オン（有効）のままにしておく必要があります。**
5. 次のセクションで説明されている関連タブを使用して設定を完了します。
6. 連携の保存をクリックします。

| 設定タブ | 備考 |
| --- | --- |
| **統合** | 必要に応じて、追加の <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">連携</Anchor> 設定をします。<br /><br />Custom\_TUNE\_tracking\_domain 項目は、エンドポイントURL を設定するために使用されます。  <br />https://greatapp.go2cloud.org/aff_Isr?<br /><br />アプリ内イベントのカスタムトラッキングドメインと同じ名前を使用してください。 |
| **計測リンク** | <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">計測リンク</Anchor>を生成します。 |
| **コスト** | 必要に応じて<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#cost-tab">コストデータ</Anchor>を取得します。 |
| **広告収益** | このパートナーは利用できません。 |
| **権限** | 必要に応じて広告媒体 <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">権限</Anchor> を設定します。 |

<div id="enabling-deep-linking-into-your-app" />

## アプリへのディープリンクを可能にする

AppsFlyerで生成可能な <Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">OneLinkブランドリンク</Anchor> を使用して、TUNEでクリックを計測します。以下の手順で、アプリ内の特定のページにユーザーをディープリンクさせることができます。

<div id="prerequisite" />

### 前提条件

AppsFlyer SDKのバージョンを確認します。

* iOS:
* Android:

<div id="step-1-configure-links-for-your-campaigns" />

### ステップ1:ステップ1: キャンペーンの計測リンクを設定する

* <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLink テンプレート</Anchor> を作成し、メールキャンペーンに利用してください。
* <Anchor target="_blank" href="/marketers/ja/docs/brand-onelink-with-your-domain">ブランドリンクを作成します。</Anchor>  
  `ブランドリンクを作成してください。`ドメインにCNAMEを追加するように要求されたら、 ブランドリンク作成ページで提供されたURLの代わりに、yourdomain.esplinks.appsflyer.com を使用してください。例：  
  **例：**

  * **CNAME:** `example.appsflyer.com`

    <Image align="center" alt="branded-link-esp-new-en_us.png" src="https://files.readme.io/a7433ac0e3b343195bac9b4be49d22c18534ec1c145189198c5ec467fea510bb-21323417936145.png" />

    **Verify** (認証) をクリックしてブランドドメインを確認する際、AppsFlyer CNAMEに関する失敗メッセージが表示されます。  

    <Image align="center" alt="branded-link-esp-cname-fail-message.png" src="https://files.readme.io/94f159a089152437111fc6e4308464bc48512ee18f5e249460006bfda05252c2-21323447961105.png" />

    このメッセージを無視して、上記の指示通りにCNAMEを変更してください。

<div id="step-2-set-up-the-attribution-link" />

### ステップ2:

1. 計測リンクタブを開き、以下のように **計測リンク** をクリックし、リンクパラメータのみをコピーしてください。[![](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)
2. コピーしたパラメータをブランドリンクに追加します。

   <div id="example" />

   > 📄 **例**
   >
   > <Image align="center" alt="TUNE-link-example2-en_us.png" src="https://files.readme.io/58f38eb0bb724b66d0c958454651e0950a54f6fd990220f2ac24f93ca89ba344-small-4410086650769.png" />

3. 設定を完了するには、TUNEのヘルプセンターにある <Anchor target="_blank" href="https://support.tune.com/hc/en-us/articles/1500008336641-Managing-Mobile-Offers-with-Appsflyer">Managing Mobile Offers with Appsflyer ガイド</Anchor> の 'Universal Links via OneLink' までスクロールダウンし、指示に従って操作してください。

<div data-zendesk-anchors="setting-up-tune-integration=tune%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01HJZRGVZ1VQF4N93THDRT5YCJ=tune%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A enabling-deep-linking-into-your-app=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E5%8F%AF%E8%83%BD%E3%81%AB%E3%81%99%E3%82%8B h_01HJZRGVZ1KJ80ZA1THKFZ535P=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E5%8F%AF%E8%83%BD%E3%81%AB%E3%81%99%E3%82%8B prerequisite=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HJZRGVZ1ZC9G7M72V2HW4XDS=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 step-1-configure-links-for-your-campaigns=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E3%82%B9%E3%83%86%E3%83%83%E3%83%971-%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HJZRGVZ1GPR3NQQAXRBXV09Z=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E3%82%B9%E3%83%86%E3%83%83%E3%83%971-%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B step-2-set-up-the-attribution-link=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972 h_01HJZRGVZ2F83PHABEWJXMMJ22=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972 h_01HJZRGVZ2435CGWY4FZ5FKKHV=%E4%BE%8B" />
