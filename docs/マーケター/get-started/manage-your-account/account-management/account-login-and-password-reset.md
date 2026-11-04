---
title: アカウントへのログインとパスワードのリセット
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
  created_at: '2025-03-03T09:04:23Z'
  edited_at: '2026-10-28T09:12:55Z'
  id: 33114514624273
  locale: ja
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/ja/articles/33114514624273
---
> **概要：** AppsFlyerへのログイン、複数アカウントの追加、ユーザーパスワードのリセットについて説明します。

<div id="log-in-instructions" />

## ログイン方法

初めて利用するユーザーと、すでに利用しているユーザーのログイン方法を説明します。新規アカウントの作成、新しいユーザーの招待、既存ユーザーとしてのログインが対象です。

**注意**：ユーザーの作成手順は、<Anchor target="_blank" href="/marketers/ja/docs/user-management#creating-users">こちら</Anchor>を参照してください。


<div id="logging-in-for-the-first-time" />

<Accordion title="初回ログイン">

AppsFlyerに新規登録した場合も、招待された場合も、有効化リンクが記載されたメールが届きます。

AppsFlyerにログインするには、次の手順に従います。

1. AppsFlyerから届いた有効化メールを開きます。
2. **アカウントで最初のユーザーの場合**：
   1. メール本文の有効化リンクをクリックします。  
      **注意**：アカウント開設時に作成されたユーザーが「アカウント所有者」となり、デフォルトで<Anchor target="_blank" href="/marketers/ja/docs/user-management#アカウント所有者">Adminロールが割り当てられます。</Anchor>
3. **招待されたユーザーの場合**：
   1. メール本文の認証コードをコピーします。
   2. メール本文の<strong>［AppsFlyerログインページ］</strong>ボタンをクリックします。
   3. 認証コードを入力します。  
      **注意：** 認証コードの有効期間は15分です。認証コードの有効期限が切れた場合は、<strong>［コードを再送信］</strong>をクリックして、新しいコードを取得します。
4. パスワードを作成します。

</Accordion>

<div id="existing-users" />

<Accordion title="既存ユーザー">

既存ユーザーは、<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">ログインページ</Anchor>からAppsFlyerにログインできます。

次のいずれかの方法でログインできます。

* ユーザー名とパスワード
* Googleアカウントでログイン
* <Anchor target="_blank" href="/marketers/ja/docs/sso-authentication">シングルサインオン</Anchor>

**注意**：管理者がアカウントに<Anchor target="_blank" href="/marketers/ja/docs/implementing-and-using-2fa-login">2要素認証（2FA）</Anchor>を設定している場合は、別の認証方法による追加確認が求められます。

</Accordion>

<div id="twofactor-authentication-2fa" />

<Accordion title="2要素認証（2FA）">

［セキュリティ管理］設定で2FAが有効になっている場合、初回ログイン後に適用されます。

[ユーザーの2FAをリセットする手順は、こちらを参照してください](/docs/account-login-and-password-reset#resetting-twofactor-authentication-2fa)。

</Accordion>

<div id="password-login-or-2fa-reset" />

## パスワード・ログイン・2FAのリセット

既存ユーザーと、初回登録や招待後の手続きが完了していないユーザー向けに、パスワードのリセット方法を説明します。

<div id="existing-users-and-invited-users-who-have-not-activated-yet" />

<Accordion title="既存ユーザーと、有効化が完了していない招待済みユーザー">

パスワードをリセットするには、次の手順に従います。

1. AppsFlyerの<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">ログインページ</Anchor>で、<strong>［パスワードを忘れた場合］</strong>をクリックします。
2. ワンタイム認証コードがメールで届きます。
3. メール本文の認証コードをコピーします。
4. メール本文の<strong>［AppsFlyerログインページ］</strong>ボタンをクリックします。
5. 認証コードを入力します。  
   **注意：** 認証コードの有効期間は15分です。  
   有効期限が切れた場合は、<strong>［コードを再送信］</strong>をクリックして、新しいコードを取得します。
6. 新しいパスワードを作成します。

</Accordion>

<div id="users-who-have-not-completed-the-initial-registration" />

<Accordion title="初回登録が完了していないユーザー">

AppsFlyerへの新規登録時に、招待メールが送信されています。メールに記載された有効化リンクの有効期間は7日間です。次の手順で登録を完了してください。

1. メールを開きます。
2. メール本文の<strong>［AppsFlyer新規登録ページ］</strong>ボタンをクリックして有効化します。  
   **注意**：アカウント開設時に作成された「アカウント所有者」には、デフォルトで<Anchor target="_blank" href="/marketers/ja/docs/user-management#アカウント所有者">Adminロールが割り当てられます。</Anchor>
   1. リンクの有効期限が切れている場合は、新規登録を最初からやり直してください。
3. パスワードを作成します。

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="ユーザーの2要素認証（2FA）のリセット">

アカウントで2FAを使用している場合、ユーザーの2FA設定をリセットする必要が生じることがあります。次の手順でリセットします。

1. <strong>［ユーザー］</strong>タブで、対象ユーザーの行の右端にある<strong>［操作］</strong>ボタン<Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />をクリックします。
2. メニューから<strong>［2FAをリセット］</strong>を選択します。

**注意：** 管理者は、自分以外のユーザーの2FAをリセットできます。アカウント所有者の2FAをリセットするには、AppsFlyerサポートチームにお問い合わせください。

</Accordion>

<div data-zendesk-anchors="log-in-instructions=%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3%E6%96%B9%E6%B3%95 h_01JNDM4M03F0T16ZHY2V1BSRQH=%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3%E6%96%B9%E6%B3%95 h_01JNDJFMRHCS20TABKNSHQ2MMW=logging-in-for-the-first-time h_01JNDM9HN8K396432TQ5MEVYCZ=existing-users h_01JNDS7ZT2TMX5315587CHBDY5=twofactor-authentication-2fa password-login-or-2fa-reset=%E3%83%91%E3%82%B9%E3%83%AF%E3%83%BC%E3%83%89%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B32fa%E3%81%AE%E3%83%AA%E3%82%BB%E3%83%83%E3%83%88 h_01JNDSMFB1YAWA340BAEYFXRES=%E3%83%91%E3%82%B9%E3%83%AF%E3%83%BC%E3%83%89%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B32fa%E3%81%AE%E3%83%AA%E3%82%BB%E3%83%83%E3%83%88 h_01JNDSJPQ4GNV0PD16GE7G9FY6=existing-users-and-invited-users-who-have-not-activated-yet h_01JNDTHN2B6VCH38ER68D3RNFS=users-who-have-not-completed-the-initial-registration h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
