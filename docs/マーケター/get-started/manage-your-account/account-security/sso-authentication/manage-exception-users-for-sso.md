---
title: SSOの適用除外ユーザーの管理
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
  created_at: '2026-05-27T08:43:46Z'
  edited_at: '2026-10-28T09:13:46Z'
  id: 47096696016529
  locale: ja
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ja/articles/47096696016529
---
> **概要：** SSOの適用除外ユーザーとは、SSOでのログインが必須ではないユーザーです。アカウント全体では引き続きSSOでのログインが必須ですが、管理者は特定のユーザーに別のログイン方法を割り当てることができます。

<div id="about-exception-users" />

## **適用除外ユーザーについて**

SSO以外の方法でログインする必要があるユーザーに、管理者がアクセスを許可する仕組みです。たとえば、緊急時のログイン手段を確保する場合や、アカウントのIDプロバイダーを利用できないユーザーがいる場合に、適用除外ユーザーとして登録できます。

適用除外ユーザーは、SSO、または割り当てられた代替ログイン方法でログインできます。適用除外ユーザーとして登録されていないユーザーは、SSOでログインする必要があります。

SSOの初期設定時に、信頼できる管理者を少なくとも1名、適用除外ユーザーに追加することを推奨します。 SSOの設定に誤りがあっても、その管理者が割り当てられた代替方法でログインし、設定を修正できます。

<div id="prerequisites" />

## **前提条件**

* アカウントでSSOが設定されている必要があります。
* SSOと適用除外ユーザーを管理するには、<strong>［ログインセキュリティ］</strong>の権限が<strong>［管理］</strong>に設定されている必要があります。

<div id="add-exception-users-during-sso-setup" />

<Accordion title="SSO設定時に適用除外ユーザーを追加する">

**推奨：** SSOを有効にする前に、信頼できる管理者を少なくとも1名、適用除外ユーザーに追加してください。 SSOの設定に誤りがあっても、アカウントにログインできなくなる事態を防げます。

適用除外ユーザーを追加するには、次の手順に従います。

1. <strong>［適用除外ユーザーの追加］</strong>の手順で、<strong>［適用除外ユーザーを追加］</strong>をクリックします。
2. 氏名またはメールアドレスでユーザーを検索します。
3. 追加するユーザーを選択します。
4. <strong>［代替ログイン方法］</strong>のドロップダウンリストで、次のいずれかを選択します。
   * **ユーザー名とパスワード**
   * **認証アプリ**
5. 追加するユーザーごとに、手順2～4を繰り返します。
6. <strong>［適用除外ユーザーを追加］</strong>をクリックします。
7. <strong>［SSOを有効化］</strong>をクリックします。

適用除外ユーザーを追加しなかった場合、有効化後はアカウントの全ユーザーにSSOでのログインが必須となります。

</Accordion>

<div id="add-login-methods-for-multiple-users" />

<Accordion title="複数のユーザーにログイン方法をまとめて設定する">

複数のユーザーに同じ代替ログイン方法を設定するには、次の手順に従います。

1. 設定を変更するユーザーのチェックボックスを選択します。
2. <strong>［選択したユーザーのログイン方法を設定］</strong>をクリックします。
3. 次のいずれかを選択します。
   * **選択したすべてのユーザーにユーザー名とパスワードを適用**
   * **選択したすべてのユーザーに認証アプリを適用**

</Accordion>

<div id="edit-exception-users-after-sso-activation" />

<Accordion title="SSO有効化後に適用除外ユーザーを編集する">

SSOの有効化後も、適用除外ユーザーの追加・削除や、代替ログイン方法の更新ができます。

適用除外ユーザーを編集するには、次の手順に従います。

1. **［セキュリティセンター］**＞<strong>［ログインセキュリティ］</strong>に移動します。
2. <strong>［SAMLシングルサインオン（SSO）］</strong>セクションで、<strong>［編集］</strong>アイコンをクリックします。
3. <strong>［適用除外ユーザー］</strong>セクションを開きます。
4. <strong>［適用除外ユーザーを編集］</strong>をクリックします。
5. ユーザーの追加・削除、または代替ログイン方法の更新を行います。
6. **Save**をクリックします。
7. <strong>［変更を保存しますか？］</strong>ダイアログで、<strong>［変更を保存］</strong>をクリックします。

登録済みの適用除外ユーザーには、現在の代替ログイン方法が表示されます。

</Accordion>

<div id="delete-exception-users" />

<Accordion title="適用除外ユーザーの削除">

適用除外ユーザーを削除するには、次の手順に従います。

［適用除外ユーザーを編集］ダイアログで、削除するユーザーを探します。

削除アイコンをクリックします。

そのユーザーは、リストからすぐに削除されます。

</Accordion>

<div id="alternative-login-methods" />

<Accordion title="代替ログイン方法">

| **ログイン方法** | **説明** |
| --- | --- |
| ユーザー名とパスワード | 適用除外ユーザーが、AppsFlyerのユーザー名とパスワードでログインできます。 |
| 認証アプリ | 適用除外ユーザーが、認証アプリを使用してログインできます。 SMSには対応していません。 |

</Accordion>

<div id="handle-partial-activation-failures" />

<Accordion title="一部のユーザーを追加できなかった場合の対応">

SSOの有効化は完了していても、一部の適用除外ユーザーが追加されない場合があります。

この場合の動作は、次のとおりです。

* SSOは有効のままです。
* 適用除外ユーザーとして追加されなかったユーザーは、SSOでログインする必要があります。
* 管理者は、<strong>［SSOを編集］</strong>から適用除外ユーザーを追加・更新できます。

</Accordion>

<div id="reset-passwords-for-sso-accounts" />

<Accordion title="SSOを使用するアカウントのパスワードのリセット">

すべてのユーザーが、パスワードを忘れた場合のリセット手続きを開始できます。ただし、新しいパスワードでログインできるのは、代替ログイン方法に<strong>［ユーザー名とパスワード］</strong>が割り当てられた適用除外ユーザーのみです。

適用除外ユーザー以外は、引き続きSSOでログインする必要があります。

</Accordion>

<div id="migrate-from-legacy-unforce-sso" />

<Accordion title="従来のUnforce SSO設定からの移行">

従来のアカウント全体のUnforce SSO（SSO必須設定の解除）から移行したアカウントでは、ユーザー名とパスワードでログインしていた既存ユーザーが適用除外ユーザーに追加され、代替ログイン方法に<strong>［ユーザー名とパスワード］</strong>が設定されます。

移行後に作成した新規ユーザーは、管理者が明示的に適用除外ユーザーに追加しない限り、SSOでログインする必要があります。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| **項目** | **説明** |
| --- | --- |
| SSOログインの必須設定 | アカウント全体では、引き続きSSOでのログインが必須です。適用除外ユーザーは、ユーザー単位で管理する例外設定です。 |
| 対応する代替ログイン方法 | 適用除外ユーザーは、**ユーザー名とパスワード**または**認証アプリ**を使用できます。 |
| SMS認証 | SMSは、代替ログイン方法として利用できません。 |
| 必要な権限 | 適用除外ユーザーを管理するには、管理者の<strong>［ログインセキュリティ］</strong>の権限が<strong>［管理］</strong>に設定されている必要があります。 |
| 閲覧のみの権限 | 閲覧のみの権限を持つ管理者は、既存の適用除外ユーザーを確認できますが、編集はできません。 |
| 移行後の新規ユーザー | 新規ユーザーは、管理者が適用除外ユーザーに追加しない限り、SSOでログインする必要があります。 |

</Accordion>

<div data-zendesk-anchors="about-exception-users=%E9%81%A9%E7%94%A8%E9%99%A4%E5%A4%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KSM9MR6FEJH62VN5BPG7C8C8=%E9%81%A9%E7%94%A8%E9%99%A4%E5%A4%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01KSM9MR6GG6K3JVYEDKKSARH5=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01KSM9RZPTBKSBH788FNP1PMDH=add-exception-users-during-sso-setup h_01KSM9RZPT9WGSMX5K10BA9WSY=add-login-methods-for-multiple-users h_01KSM9RZPTXDTM7Y0RV2PVRAX7=edit-exception-users-after-sso-activation h_01KSM9RZPT1G9MJ4BQYTSKPZ0F=delete-exception-users h_01KSM9RZPT3CZR4QGMWAH534H5=alternative-login-methods h_01KSM9RZPTJ988PFQA68DVE73G=handle-partial-activation-failures h_01KSM9RZPVS8AVWAD7EPGCG6F9=reset-passwords-for-sso-accounts h_01KSM9RZPV36BQWH360QSP98SY=migrate-from-legacy-unforce-sso h_01KSMA3KYT6F2FSB2QGDPV4CAM=traits-and-limitations" />
