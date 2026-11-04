---
title: アカウント間でのアプリの移管
metadata:
  keywords:
    - Account
    - Advertisers
    - Agencies
    - moving apps
    - move app
    - app transfer
    - transferring apps
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
  created_at: '2018-07-24T07:56:37Z'
  edited_at: '2026-10-14T09:37:22Z'
  id: 360001336005
  locale: ja
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ja/articles/360001336005
---
> **概要：** この記事で説明する手順に沿って、AppsFlyerアカウント間でアプリを移管します（移管先と移管元のアカウントアドミンが実行する必要があります）。

![5638-Transfering-an-app-NEW1.gif](https://files.readme.io/f4288a79bbd96e8cf828cf0ca9ae9ef994400f702cd66108d2861e3a405c4d79-360010967257.gif)

<div id="app-transfer-between-accounts" />

## アカウント間でのアプリの移管

AppsFlyerアカウント間でアプリを移管するには、送信側および受信側のアプリ所有者（AppsFlyerアカウントでいうアドミンユーザー）が必要な前提条件を完了し、移管に同意する必要があります。

<div id="prerequisites" />

### 前提条件

* 送信者と受信者の両方のアカウント（管理者）のメールがあることを確認してください。
* 両方のアカウントが有効であること。停止中のアカウントはアプリを送受信できません。
* いずれのアカウントにも未処理の請求書がないこと。
* アカウント間のアプリの移行は、<Anchor target="_blank" href="/marketers/ja/docs/user-management#アカウント所有者">アカウント所有者</Anchor>のみが行うことができます。管理者ロールでは実行できません。
* 管理画面上でのアプリ移管は、グロースプランまたはエンタープライズプランのアカウントに限ります。<Anchor target="_blank" href="/marketers/ja/docs/account-management-plans-payments-and-billing#appsflyer-plans">詳細はこちら</Anchor>

<div id="app-transfer-process" />

### アプリの移管プロセス

アプリの移管プロセスの概要は以下の通りです：

1. 送信者は、受信者のメールアドレスを入力して、選択したアプリの移管をAppsFlyerにリクエストします。
2. 受信者は通知を受け取り、アプリの移管に同意します。
3. 送信側と受信側の管理人が転送保留中という通知を、メールおよび**My Apps**画面で受け取ります。    
   **注記：** 移管が保留中の間は、どちらかのアドミンがアプリの移管リクエストを取り消す（キャンセルする）ことができます。
4. AppsFlyerがアプリを転送します。前提条件が満たされていない場合、AppsFlyerはアカウント管理者に連絡し、必要な作業を依頼します。

<div id="app-transfer-scope" />

<Accordion title="アプリ移管の範囲">

どのアプリの機能や設定が引き継がれるかに関しては、次の表のとおりです。なお、送信側の判断で、移管前に特定の設定や構成情報を削除することができます。

<table><thead><tr><th>アイテム</th><th>移管対象 /<br/>移管対象外</th><th>詳細 / 考慮事項</th></tr></thead><tbody><tr><td>アプリ設定 </td><td>移管対象</td><td> <strong>任意：</strong>送信者は、転送前にFirebase/GCMサーバーキーを削除できます。 </td></tr><tr><td rowspan="2">連携済みパートナー</td><td>移管対象</td><td><p>連携、コスト、収益の設定（コストと収益データを含む）</p><p><strong>任意：</strong>受信側が連携パートナーの移管が不要な場合は、送信側はパートナーを無効にし、関連する設定と認証情報を削除してください（コスト、広告収益の設定を含む）。</p></td></tr><tr><td>移管対象外</td><td><p>アドネットワークと代理店の権限</p><p>Twitter連携設定と認証情報</p></td></tr><tr><td>OneLink管理</td><td>移管対象外</td><td>OneLinkのテンプレートとリンクは自動的には転送されませんが、CSMによって転送できます。<strong>任意：</strong> <ul><li>テンプレートとリンクを転送するには、CSM に連絡するか <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a> にご連絡ください。</li><li>送信者は、転送前に古いリンクを削除できます。</li></ul></td></tr><tr><td>Push API</td><td>移管対象</td><td> <strong>任意：</strong><ul><li>受信側がPush APIの設定（エンドポイント）を引き継ぐ必要がない場合、送信側は設定を削除してください。そうしないと、データは引き続き送信側が定義したエンドポイントに送信されます。</li><li>または、移管後に受信側が設定を変更し、送信側がユーザーレベルデータを受信しないようにすることも可能です。 </li></ul></td></tr><tr><td>スマートバナー</td><td>移管対象外</td><td><p>バナー、バナーグループ、クリエイティブ、ウェブサイトは転送されません。  </p></td></tr><tr><td>スマートスクリプト</td><td>移管対象外</td><td>AppsFlyerのUI内で作成されたスマートスクリプトは、新しいアカウントでは利用できません。  </td></tr><tr><td>代理店権限</td><td>移管対象外</td><td>代理店はアクセスを失うため、移管先のアカウントから再度権限付与の作業が必要です。</td></tr><tr><td>Audiences</td><td>移管対象外</td><td>オーディエンスは削除されます。</td></tr><tr><td>コストインポート</td><td>N/A</td><td>過去のコストインポートファイルは、受信者はアクセスできません。これはコスト履歴には影響しません。  </td></tr><tr><td>Data Locker</td><td>移管対象外</td><td>アプリはData Lockerの設定から削除され、送信者アカウントではアプリデータの受信が停止されます。  </td></tr><tr><td>過去データ</td><td>移管対象</td><td> </td></tr><tr><td>PBAブランドバンドル</td><td>移管対象外</td><td><p>関連するアプリが移管された場合、送信者はバンドルが利用できなくなります。受信者はPBAデータにはアクセスできません。</p><p>つまり、クライアントが新しいアカウントでPBAを使い続ける必要がある場合は、アプリの転送が完了する前にWebバンドルを削除する必要があり、そうしないと、新しいアカウントで同じWebバンドルを作成できません。</p></td></tr><tr><td>Protect360データ</td><td>移管対象</td><td> </td></tr><tr><td>ローデータ＆集計データ</td><td>移管対象</td><td> </td></tr><tr><td>SDK Dev Key</td><td>移管対象</td><td> </td></tr><tr><td>検証ルール</td><td>移管対象</td><td> </td></tr></tbody></table>

</Accordion>

<div id="transfer-procedures" />

## 移管の手順

1つ以上のアプリを別のAppsFlyerアカウントに移管するようリクエストするには、プロセスを開始すると、画面に手順についてのウィザードが表示されます。

<div id="sender" />

<Accordion title="送信者">

**移管リクエストを送信する方法：**

1. 受信側のアドミンに連絡してください。
   1. [アプリ移管の範囲](/docs/transferring-apps-between-accounts#app-transfer-scope)を確認し同意してください。双方が、どの設定が転送され、そのための準備が正しくできているかを確認してください。
   2. 受信者がAppsFlyerで使用している管理者のメールアドレスを提供するようリクエストしてください。
2. 次のいずれかを実行してください：  
   * 1つのアプリを移行するには：**上部のメニューバー マイアプリ > アプリのアクションメニュー (...) > アプリの転送を選択します。**
   * 2つ以上のアプリを転送するには：**上部のメニューバー** /strong>**マイアプリ** > アプリのアクションメニュー (...) > **アプリの転送**を選択します。
3. 移管する1つまたは複数のアプリを選択します。
4. **次へ**をクリックしてください。
5. 受信側アカウント管理者のメールアドレスを入力してください
6. **次へ**をクリックしてください。
7. 利用規約を読み、署名します。
   * リクエストが正常に送信されると、送信者と受信者に通知（メール）されます。
   * リクエストがAppsFlyerによる作業を必要とする場合、送信者に通知（ポップアップが表示）されます。
   * アプリは**My apps**ページに、Pending transfer to `<receiver email>`（`<受信者メールアドレス>`へ移管保留中）と表示されます。この段階でも、リクエストを削除することは可能です。[![App_transfer_sender_side.JPG](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)

</Accordion>

<div id="receiver" />

<Accordion title="受信者">

1. 送信側のアドミンに連絡し、[アプリ移管の範囲](/docs/transferring-apps-between-accounts#app-transfer-scope)を確認し同意するよう依頼してください。双方が、どの設定が転送され、そのための準備が正しくできているかを確認してください。
2. 送信者が移管リクエストを開始したことを通知するメールが届きます。
3. **My Apps**ページにて、**リクエストを確認**をクリックしてください。リクエストには1つまたは複数のアプリが含まれます。  
   [![App_transfer_receiver_side.JPG](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)
4. 各リクエストを確認し、承認または拒否してください。
5. 利用規約を読み、同意できる場合は署名してください。
6. リクエストが受け入れられたことを通知するメールが、受信側と送信側に送信されます。
7. 移管されたアプリが**My Apps**ページに表示されます。

<div id="delete-transfer-request" />

<Accordion title="移管リクエストの削除">

移管が完了する前に、送信側または受信側の管理者によってアプリの移管プロセスを削除（キャンセル）できます。

**アプリ移管リクエストを削除する方法：**

* **送信側の管理者**：送信側の管理者：**My apps** > **Pending transfer to [email]** セクション > **リクエストを削除**をクリックします。  
  送信者と受信者のアドミンアカウントへメールで通知されます。
* **受信者の管理者**：
* 上部のメニューバー **マイアプリ** > **転送保留中のアプリ**セクション > 拒否をクリックします。  
  送信者と受信者のアドミンアカウントへメールで通知されます。

</Accordion>

</Accordion>

<div data-zendesk-anchors="app-transfer-between-accounts=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E9%96%93%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E7%A7%BB%E7%AE%A1 h_01HJR1G7Q71H5DAH1G9QFSYK35=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E9%96%93%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E7%A7%BB%E7%AE%A1 prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HJR1G7Q7T1Q768MTTR3Y542X=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 app-transfer-process=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E7%A7%BB%E7%AE%A1%E3%83%97%E3%83%AD%E3%82%BB%E3%82%B9 h_01HJR1G7Q7EDJZ4E1T17GWYGTP=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E7%A7%BB%E7%AE%A1%E3%83%97%E3%83%AD%E3%82%BB%E3%82%B9 h_01HJR1G7Q7AWF07RG2J4Q3V2KN=app-transfer-scope transfer-procedures=%E7%A7%BB%E7%AE%A1%E3%81%AE%E6%89%8B%E9%A0%86 h_01HJR1G7Q7JB0XD3NGT0MWYJZ5=%E7%A7%BB%E7%AE%A1%E3%81%AE%E6%89%8B%E9%A0%86 h_01HJR1G7Q7ERYXGB83D475AEPN=sender h_01EDBXVWAB5VBWT3XFK21KPV6W=receiver h_01HJR1G7Q8NEF5P5N95C6CGSF9=delete-transfer-request" />
