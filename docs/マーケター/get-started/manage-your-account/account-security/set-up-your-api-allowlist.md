---
title: API許可リストの設定
metadata:
  keywords:
    - OneLink
    - API Policy
    - fraud
    - Advertisers
    - Agencies
    - API access
    - attribution link
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
  created_at: '2021-08-22T13:50:14Z'
  edited_at: '2026-10-28T09:14:20Z'
  id: 4406016140817
  locale: ja
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ja/articles/4406016140817
---
> **概要：** API許可リストを設定し、AppsFlyerアカウントを保護します。

## [<Image alt="API許可リスト" src="https://files.readme.io/05f8c46f81b679e2881bf72255ae835a70d1cb3be1ea862b90053c2c259f25b6-4423224122385.png" width="609px" />](https://files.readme.io/05f8c46f81b679e2881bf72255ae835a70d1cb3be1ea862b90053c2c259f25b6-4423224122385.png)

## 概要

API許可リストで、AppsFlyerアカウントへのAPI呼び出しを許可するIPアドレスを指定し、データへの不正アクセスを防ぎます。許可リストを有効にすると、指定したIPアドレスからのAPI呼び出しのみが許可され、ほかのIPアドレスからの呼び出しはすべて拒否されます。

> 📘 **注意**
>
> * 許可リストにアクセスして管理できるのは、管理者のみです。
> * 許可リストの利用は任意で、デフォルトでは無効です。
> * 有効化はアカウント単位で行い、アカウント内のすべてのアプリに適用されます。

## API許可リストの設定

<div id="set-up-the-api-allowlist" />

<Accordion title="許可リストの設定">

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) API許可リストを設定して有効にするには、次の手順に従います。**

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. ［API許可リスト］セクションで、<strong>［API許可リストを管理］</strong>をクリックします。
3. 標準の形式で、IPアドレスまたはIPアドレスの範囲を入力します。
   * 例：`192.168.1.1`、`185.114.120.140`
   * IPアドレスの範囲は、次の形式で入力します：`185.114.120.1/32`（`185.114.120.1`が範囲の開始アドレス、`185.114.120.32`が終了アドレス）。
4. <strong>［適用］</strong>をクリックします。
5. ［任意］IPアドレスや範囲を追加するには、<strong>［＋追加］</strong>をクリックします。
6. <strong>［リストを保存］</strong>ボタンをクリックします。
7. 許可リストを<strong>［有効］</strong>にします。

   **注意：** 保存して有効にするには、IPアドレスまたは範囲を少なくとも1件登録する必要があります。

</Accordion>

<div id="edit-the-api-allowlist" />

<Accordion title="許可リストの編集">

許可リストの有効・無効にかかわらず、IPアドレスはいつでも追加・削除できます。

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) IPアドレスまたは範囲を追加するには、次の手順に従います。**

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. ［API許可リスト］セクションで、<strong>［API許可リストを管理］</strong>をクリックします。
3. <strong>［＋追加］</strong>をクリックし、IPアドレスまたは範囲を追加します。
4. IPアドレスまたは範囲を入力します。
5. <strong>［適用］</strong>をクリックします。
6. 必ず<strong>［リストを保存］</strong>ボタンをクリックして、変更を保存してください。

   **注意：** リストを保存しても、有効・無効の状態は変わりません。<strong>［有効］</strong>のオン／オフを確認し、必要に応じて切り替えてください。

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) IPアドレスまたは範囲を削除するには、次の手順に従います。**

1. 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［セキュリティセンター］</strong>を選択します。
2. ［API許可リスト］セクションで、<strong>［API許可リストを管理］</strong>をクリックします。
3. 削除するIPアドレスの横にあるごみ箱アイコンをクリックします。
4. 確認ポップアップで<strong>［削除］</strong>をクリックします。
5. 必ず<strong>［リストを保存］</strong>ボタンをクリックして、変更を保存してください。

</Accordion>

<div id="api-allowlist-specifications" />

<Accordion title="許可リストの仕様">

* 不正なAPI呼び出しからアカウントを保護するには、IPアドレスまたは範囲を少なくとも1件登録し、許可リストを<strong>［有効］</strong>にする必要があります。
* 許可リストは、<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#api-v2トークンの用途">V2.0トークンを使用するすべてのAppsFlyer API</Anchor>**に適用されます。** V1.0 APIトークンを使用するAPI呼び出しは、すべてのAPIアドレスから許可されます。
* 許可リストには、IPアドレスまたは範囲を最大20件追加できます。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 overview::6f3684c7=%E6%A6%82%E8%A6%81 h_01HZCCCTT52ZQB9VAF6Q7RRKES=%E6%A6%82%E8%A6%81 h_01HZCD0681XNKR2HSNCN4GWGA0=%E6%A6%82%E8%A6%81 h_01HJR00RGQX0CQEHDS9BHBGJD4=%E6%B3%A8%E6%84%8F set-up-your-api-allowlist=api%E8%A8%B1%E5%8F%AF%E3%83%AA%E3%82%B9%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HZCCW4XYJ72Z6KKJPCXQB947=api%E8%A8%B1%E5%8F%AF%E3%83%AA%E3%82%B9%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HJR00RGRQ54R71HY0ZBRM1PM=set-up-the-api-allowlist h_01HJR00RGRD7PK2HR5VS1JENWQ=edit-the-api-allowlist h_01HJR00RGRESGGEW3D6NHHF7VY=api-allowlist-specifications" />
