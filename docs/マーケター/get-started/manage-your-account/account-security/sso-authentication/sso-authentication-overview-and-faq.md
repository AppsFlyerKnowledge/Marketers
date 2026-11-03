---
title: SSO認証｜概要とよくある質問
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-08-11T07:54:46Z'
  edited_at: '2026-10-28T09:13:51Z'
  id: 27434547337617
  locale: ja
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ja/articles/27434547337617
---
> **概要：** シングルサインオン（SSO）認証の仕組みと、IDプロバイダー（IdP）を経由してAppsFlyerにログインする手順を説明します。 SSOログインについてのよくある質問も確認できます。

## SSO認証とは

SSOは、IDプロバイダー（Okta、Azure AD、OneLoginなど）で一度ログインすることで、複数の独立したアプリ、システム、プラットフォームにアクセスできる認証方式です。 IdPにAppsFlyerを追加すると、ユーザーはシングルサインオン（SSO）により、IdPからAppsFlyerへ直接ログインできます。 1組のログイン情報だけで、より**安全に認証**して自動ログインできます。

## SSO認証の仕組み

AppsFlyerは、SAML 2.0プロトコルを使用したSSO認証に対応しています。 SAML 2.0対応のIdPにAppsFlyerの認証証明書を設定すると、IdPは認証済みユーザーのデータを含むトークンを生成します。 IdP側からAppsFlyer側にも同様の設定を行い、IdPのトークンをAppsFlyerに登録します。

## AppsFlyer（サービスプロバイダー）の認証証明書

AppsFlyerは、データの暗号化とSSOリクエストの署名に使用する暗号化証明書を提供しています。使用する証明書は、次のいずれかを選択できます。

* **AppsFlyer署名証明書：** <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">AppsFlyerのメタデータURL</Anchor>から作成する、AppsFlyerの証明書
* **CA署名証明書：Amazonが署名した**AppsFlyerの証明書。

> 📘 **注意**
>
> AppsFlyerは、シリアル番号が負の値の証明書には対応していません。

## トラブルシューティングとよくある質問

<div id="can-users-log-in-using-both-sso-and-2fa-methods" />

<Accordion title="SSOと2FAの両方でログインできますか？">

セキュリティを強化するログイン方法として、SSOまたは2FAのいずれか一方のみを使用できます。

* **SSOが有効な状態で2FAを有効にするには：** 先にSSOを無効にしてから、2FAを有効にします。
* **2FAが有効な状態でSSOを有効にするには：** 先に2FAを無効にしてから、SSOを有効にします。

</Accordion>

<div id="why-cant-some-users-connect-using-sso" />

<Accordion title="一部のユーザーがSSOで接続できないのはなぜですか？">

IdPとAppsFlyerの両方に、すべてのユーザーのメールアドレスが登録されていることを確認してください。これが原因でない場合は、担当CSMに原因と解決方法をお問い合わせください。解決するまでの間は、CSMが<strong>［SSOログインを必須にする］</strong>を一時的に無効にし、ユーザーがメールアドレスとパスワードでログインできるように設定できます。

</Accordion>

<div id="do-i-need-a-test-environment-to-test-setup-before-pushing-to-production" />

<Accordion title="設定前にテストするための環境は必要ですか？">

テスト環境は不要です。手順3に従って、IdPまたはサービスプロバイダー（AppsFlyer）からのSSOログインをテストしてください。

</Accordion>

<div id="what-should-i-do-before-the-appsflyer-certificate-expires" />

<Accordion title="AppsFlyerの証明書の有効期限が近づいたら、どうすればよいですか？">

AppsFlyerのSSO証明書の有効期限が近づくと、管理画面にアラートが表示されます。次の手順で、新しいAppsFlyerの証明書を設定してください。

1. [更新した暗号化キーを使って、新しい証明書ファイルを作成します](#how-to-create-the-appsflyer-certificate-file)。
2. IdPに移動し、新しいAppsFlyerの証明書を設定します。
3. 設定後、<strong>［シングルサインオン（SSO）］</strong>セクションに戻り、<strong>［証明書の設定を確認］</strong>をクリックして、最新のAppsFlyer証明書に更新したことを確認します。

</Accordion>

<div id="how-can-i-unselect-the-force-sso-login-option" />

<Accordion title="［SSOログインを必須にする］が操作できません。有効にするにはどうすればよいですか？">

<strong>［SSOログインを必須にする］</strong>を選択して設定を保存すると、この項目は操作できなくなります。 <strong>［SSOログインを必須にする］</strong>を再び操作できるようにするには、SSO設定の<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">手順2</Anchor>を最初からやり直す必要があります。

> 📘 **注意**
>
> より安全にログインできるよう、<strong>［SSOログインを必須にする］</strong>を選択した状態にしておくことを推奨します。この設定では、ログインするユーザーはIdPで認証され、ユーザー名とパスワードだけではログインできなくなります。

</Accordion>

<div id="is-it-required-to-use-the-appsflyer-certificate-in-my-idp" />

<Accordion title="IdPにAppsFlyerの証明書を設定することは必須ですか？">

IdPへのAppsFlyer証明書の設定は**強く推奨されます**が、必須ではありません。 Google WorkspaceやMicrosoft Entra IDなど、一部のIdPは、デフォルトではサービスプロバイダーの証明書を必要としません。

</Accordion>

<div id="what-happens-when-i-deactivate-sso-and-how-do-i-do-it" />

<Accordion title="SSOを無効にするとどうなりますか？また、どのように無効にしますか？">

SSO認証を無効にすると、AppsFlyerのユーザー名とパスワードや<Anchor target="_blank" href="/marketers/ja/docs/implementing-and-using-2fa-login">2FA</Anchor>など、ほかの方法でログインできるようになります。

1. 上部のバーでアカウントメニュー（管理者のメールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. <strong>［ログインセキュリティの強化］</strong>で、<strong>［ログイン方法を設定］</strong>を選択します。
3. <strong>［シングルサインオン（SSO）］</strong>セクションで、<strong>［シングルサインオン］</strong>をオフにします。

</Accordion>

<div id="can-i-have-negative-serial-numbers-in-the-certificate" />

<Accordion title="証明書のシリアル番号に負の値を使用できますか？">

いいえ。 AppsFlyerは、シリアル番号が負の値の証明書には対応していません。

</Accordion>

<div data-zendesk-anchors="what-is-sso=sso%E8%AA%8D%E8%A8%BC%E3%81%A8%E3%81%AF h_01J5QR4DE5EBSVWHXXENZTRPWQ=sso%E8%AA%8D%E8%A8%BC%E3%81%A8%E3%81%AF how-does-sso-authentication-work=sso%E8%AA%8D%E8%A8%BC%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01HCHG901WVRX1MKNB0KF02PSJ=sso%E8%AA%8D%E8%A8%BC%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF the-authentication-certificate=appsflyer%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%83%97%E3%83%AD%E3%83%90%E3%82%A4%E3%83%80%E3%83%BC%E3%81%AE%E8%AA%8D%E8%A8%BC%E8%A8%BC%E6%98%8E%E6%9B%B8 h_01HCHG901WG05TP2NJBJRDRWPN=appsflyer%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%83%97%E3%83%AD%E3%83%90%E3%82%A4%E3%83%80%E3%83%BC%E3%81%AE%E8%AA%8D%E8%A8%BC%E8%A8%BC%E6%98%8E%E6%9B%B8 h_01JJH8DC3AHNC6GST0S41X8MFV=%E6%B3%A8%E6%84%8F faq=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A8%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HCHG901XSAQ7HSGM0ZVT7B70=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A8%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HCHG901XJ77NQFVX01YZPGT2=can-users-log-in-using-both-sso-and-2fa-methods h_01HCHG901XH0ED40MK2YM1NGRP=why-cant-some-users-connect-using-sso h_01HCHG901X942E0WCBC00KRFSE=do-i-need-a-test-environment-to-test-setup-before-pushing-to-production h_01HCHG901XNNT8GA3TSP5XJC3B=what-should-i-do-before-the-appsflyer-certificate-expires h_01HCHG901XSKPTTRECJPNA09XR=how-can-i-unselect-the-force-sso-login-option h_01HCHG901XPKMP7HSJ04PY9KHW=%E6%B3%A8%E6%84%8F-1 h_01HYDBV18S924FNRCBSPR56CTR=is-it-required-to-use-the-appsflyer-certificate-in-my-idp h_01J5QRR54JNC5YNZHQ463KS7BS=what-happens-when-i-deactivate-sso-and-how-do-i-do-it h_01JJH8F3VFTQA1AANNNS85YBF8=can-i-have-negative-serial-numbers-in-the-certificate" />
