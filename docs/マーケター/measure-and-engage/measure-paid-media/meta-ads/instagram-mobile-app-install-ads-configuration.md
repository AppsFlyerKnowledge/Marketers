---
title: Instagram｜モバイルアプリインストール広告の設定
metadata:
  keywords:
    - Facebook
    - Instagram
    - install ads
    - integrated partner
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-09T01:10:44Z'
  edited_at: '2026-10-28T09:16:31Z'
  id: 207034066
  locale: ja
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ja/articles/207034066
---
> **概要：** Meta広告アカウントで、Instagram経由のモバイルアプリのインストールを計測できるようにします。

<Image alt="instagram_logo.jpg" src="https://files.readme.io/55ab80e2b1ba9d164d978116f3aaaacb9fe7e4571f71e0130a40e1ded16679db-360000492725.jpg" width="101px" />

## Instagramの設定

Instagramの設定は、AppsFlyerの［連携済みパートナー］にあるMeta広告の連携設定から行います。

Metaのドキュメントは、<Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/guides/instagramads/">こちら</Anchor>と<Anchor target="_blank" href="https://www.facebook.com/business/help/1634705703469129">こちら</Anchor>を参照してください。

1. InstagramアカウントをMetaビジネスマネージャにリンクします。  

   ![link-inst-with_fb-account.png](https://files.readme.io/c6c7fe17274f0b9af008c4452b4b7ea2233cc5bca8773307fef6afaeb7d06015-11212956311441.png)
2. ビジネスマネージャに追加したら、Instagramアカウントに広告アカウントを割り当てます。  

   <Image alt="assign-inst-ad-to-fb.png" src="https://files.readme.io/658dc57d0056a2217a9f0f5c785b87e24c297158b75c5815eddb64930d00ea17-11213052873745.png" width="550px" />
3. ［連携済みパートナー］のMeta広告の連携設定で、FacebookアプリIDを追加します。
4. FacebookアプリIDがない場合は、<Anchor target="_blank" href="https://developers.facebook.com/apps">こちら</Anchor>から作成してください。  
   [![facebook_app_id.png](https://files.readme.io/2e497e1e00c22d0006aebd540b24c47ba4f2907ee9de061dc04ab50bbbe2cc67-14069602144273.png)](https://support.appsflyer.com/hc/article_attachments/51444627540625)

## ディープリンク用のInstagramランディングページ

現在、カタログを使用しない静的広告では、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">ユニバーサルリンクを使用したInstagramからiOSアプリへのディープリンクがサポートされています</Anchor>。 iOSのユニバーサルリンクとAndroidのアプリリンクは、遷移先として<strong>［アプリ］</strong>を選択したキャンペーンでのみサポートされます。

Instagramで、遷移先に<strong>［アプリ］</strong>を選択できないキャンペーンにディープリンク付きのカスタムリンクを使用したい場合は、注意が必要です。たとえば、Metaの認知度キャンペーンでは遷移先に<strong>［アプリ］</strong>を選択できないため、iOSのユニバーサルリンクとAndroidのアプリリンクはサポートされません。このような場合は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Instagram向けランディングページを設定できます</Anchor>。これにより、Instagramでユニバーサルリンク付きのOneLinkを使ってユーザーをアプリ内に誘導し、ユーザー体験を向上できます。

ダイナミック広告では、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads">こちら</Anchor>の説明に従って、iOSのユニバーサルリンク、Androidのアプリリンク、URIスキームを使用できます。

<div data-zendesk-anchors="setting-up-instagram=instagram%E3%81%AE%E8%A8%AD%E5%AE%9A instagram-landing-page-for-deep-linking=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E7%94%A8%E3%81%AEinstagram%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8" />
