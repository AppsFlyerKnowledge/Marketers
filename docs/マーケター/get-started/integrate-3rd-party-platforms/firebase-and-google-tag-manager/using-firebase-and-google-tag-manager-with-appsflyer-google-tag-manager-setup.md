---
title: AppsFlyerでのFirebaseとGoogleタグマネージャーの活用｜Googleタグマネージャーの設定
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:28:45Z'
  edited_at: '2026-10-28T09:04:08Z'
  id: 4410481509393
  locale: ja
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/ja/articles/4410481509393
---
> **At a glance:** Firebase SDKで記録したイベントをAppsFlyerに送信するための、Googleタグマネージャーの設定手順を説明します。

<div id="google-tag-manager-setup" />

## Googleタグマネージャーの設定

このセクションでは、Googleタグマネージャー（GTM）の画面で必要な設定を説明します。 GTMからAppsFlyerにイベントを送信するには、このセクションのすべての手順を実施する必要があります。記載された順に手順を進めてください。

以下の手順は、モバイルアプリ向けのGoogleタグマネージャーを対象としています。 Googleタグマネージャーの画面が各手順のスクリーンショットと異なる場合は、次の点を確認してください。

1. Googleタグマネージャーのコンテナがモバイルアプリ用に設定されていること。
2. コンテナのバージョンがv5であること。詳細は、<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7003315">こちら</Anchor>をご覧ください。

> 📘 **Note**
>
> **注意**
>
> このセクションでは購入イベントを例に説明しますが、送信したいほかのイベントにも同じ手順を適用できます。

<div id="1-creating-event-parameter-variables" />

<Accordion title="1. イベントパラメータ変数の作成">

イベントパラメータ変数を使うと、Googleタグマネージャーはイベントからデータを取得できます。イベントの送信時に、AppsFlyer IDとDevキーの変数も渡されます。 Googleタグマネージャーは、これらの変数を評価して値を取得します。イベントのデータには、次の2つの役割があります。

1. AppsFlyer IDとDevキーをGoogleタグマネージャーに渡す
2. イベント名とイベントパラメータをGoogleタグマネージャーに渡す

<Tabs>
<Tab title="AppsFlyerデバイスIDとDevキー">

GoogleタグマネージャーからAppsFlyerにイベントを送信する際は、必ずAppsFlyer IDとDevキーを含める必要があります。 Devキーにより、GoogleタグマネージャーとAppsFlyerのサーバーが通信できます。 AppsFlyer IDにより、イベントをどのユーザーに紐付けるかをAppsFlyerが判別できます。

1. Googleタグマネージャーで<strong><em>［変数］</em></strong>、<strong><em>［新規］</em></strong>の順にクリックします。
2. 変数名を「AppsFlyer Dev Key」にし、<strong><em>［変数の設定］</em></strong>をクリックします。
3. <strong><em>［イベントパラメータ］</em></strong>を選択します。
4. <strong><em>［カスタムパラメータ］</em></strong>を選択します。
5. <strong><em>［イベントパラメータ］</em></strong>フィールドに「dev\_key」と入力して保存します。
6. AppsFlyer IDについても同様に、変数名を「AppsFlyer Device ID」にし、<strong><em>［イベントパラメータ］</em></strong>フィールドに「af\_id」と入力します。

> 📘 **Note**
>
> **例**
>
> 以下はGTM画面のスクリーンショットです。イベントパラメータの設定完了後の状態を示しています。
>
> <Image align="center" alt="event_parameter_variable_dev_key.png" src="https://files.readme.io/f5030ce110ec4459f673a4088c2c09a4e3f90a35976f4fbfccb8750cb112e69e-49839295695889.png" />

> 🚧 **Important**
>
> **重要**
>
> iOSでは、追加のイベントパラメータを設定する必要があります。上記と同じ手順を進めます。変数を作成し、名前を「Apple App ID」にします。［イベントパラメータ］フィールドに「apple\_app\_id」と入力して保存します。

次に、アプリ内でAppsFlyer IDとDevキーの変数を作成・設定します。この手順は、<Anchor target="_blank" href="/marketers/ja/docs/using-firebase-and-google-tag-manager-with-appsflyer-sending-installs-and-events#アプリでのイベントの設定">イベントの送信</Anchor>セクションで説明します。

</Tab>

<Tab title="収益と価格">

ほとんどのアプリ内イベントには、イベント値のパラメータが必要です。この例ではaf\_revenueとaf\_priceを使用しますが、任意のイベントパラメータを送信できます。アプリでイベントを設定したら、Googleタグマネージャーで収益と価格の変数を作成します。これらの変数は、後でPurchaseイベントのタグに使用します。

1. Googleタグマネージャーで、af\_revenueとaf\_priceの2つのイベントパラメータ変数を作成します。
2. 「af\_revenue」の変数名を「Revenue」にし、<strong><em>［イベントパラメータキー］</em></strong>を「af\_revenue」に設定します。
3. 「af\_price」の変数名を「Price」にし、<strong><em>［イベントパラメータキー］</em></strong>を「af\_price」に設定します。

> 📘 **Note**
>
> **例**
>
> 以下はGTM画面のスクリーンショットです。イベントパラメータの設定完了後の状態を示しています。
>
> <Image align="center" alt="event_parameter_variable_revenue.png" src="https://files.readme.io/40e6ccd8d2df9370210847d6ff54a5a44c04f295dac9ece18dac715e5fc335a1-49839295696657.png" />

> 📘 **Note**
>
> **注意**
>
> この例では、RevenueとPriceのイベントパラメータ変数の作成方法を示しています。送信するイベントに応じて、任意のイベントパラメータの変数を作成できます。

</Tab>
</Tabs>

</Accordion>

<div id="2-creating-a-trigger-for-the-purchase-event" />

<Accordion title="2. 購入イベントのトリガーの作成">

GoogleタグマネージャーがAppsFlyerへの送信対象イベントを判断できるように、イベントのトリガーを設定します。

1. Googleタグマネージャーで<strong><em>［トリガー］</em></strong>、<strong><em>［新規］</em></strong>の順にクリックします。
2. トリガー名を「Purchase」にし、<strong><em>［トリガーの設定］</em></strong>をクリックします。
3. <strong><em>［カスタム］</em></strong>を選択します。
4. <strong><em>［一部のイベント］</em></strong>を選択します。
5. 条件として、<strong><em>［イベント名］</em></strong>が「af\_purchase」と等しい場合にトリガーが発火するよう設定します。
6. ［***保存***］をクリックします。

> 📘 **Note**
>
> **例**
>
> 以下はGTM画面のスクリーンショットです。トリガーの最終的な設定は、次のようになります。
>
> <Image align="center" alt="trigger_purchase_event.png" src="https://files.readme.io/ef2e70fb2aa0b25f1243d6fa565e3cdb1df407fd2d4b3105dee412ccad7f2704-49839256428689.png" />

</Accordion>

<div id="3-creating-a-tag-for-the-purchase-event" />

<Accordion title="3. 購入イベントのタグの作成">

必要な変数とイベントトリガーを設定したら、Purchaseイベントのタグを作成できます。

1. Googleタグマネージャーで<strong><em>［タグ］</em></strong>、<strong><em>［新規］</em></strong>の順にクリックします。
2. タグ名を「Purchase」にし、<strong><em>［タグの設定］</em></strong>をクリックします。
3. ***AppsFlyer***を選択します。
4. <strong><em>［アプリケーションID］</em></strong>フィールドに、組み込み変数のApp IDを設定します。

   > 🚧 **Important**
   >
   > **重要**
   >
   > iOSでは、<strong><em>［アプリケーションID］</em></strong>フィールドにカスタム変数「apple\_app\_id」を設定します。

5. <strong><em>［Devキー］</em></strong>フィールドで、「AppsFlyer Dev Key」変数を選択します。
6. <strong><em>［AppsFlyerデバイスID］</em></strong>フィールドで、「AppsFlyer Device ID」変数を選択します。
7. ［イベント名］フィールドに、組み込み変数の***Event Name***を設定します。
8. <strong><em>［イベント通貨］</em></strong>フィールドに、USDなどの通貨コードを設定します。
9. <strong><em>［イベント値を追加］</em></strong>を2回クリックします。
10. 次のように設定します。  
    ***キー***：af\_revenue、***値***：イベントパラメータ変数「Revenue」を選択  
    ***キー***：af\_price、***値***：イベントパラメータ変数「Price」を選択
11. ***［トリガー］***セクションの***［配信トリガー］*** に、「Purchase」イベントのトリガーを設定します。
12. ［***保存***］をクリックします。

> 📘 **Note**
>
> **例**
>
> 以下はGTM画面のスクリーンショットです。タグの最終的な設定は、次のようになります。
>
> <Image align="center" alt="purchase_tag.png" src="https://files.readme.io/893bdf6ce65bf6bd0435f4e7c02ff044b35e5e14ebea131f547040f763d7512d-49839295697169.png" />

</Accordion>

<div id="4-publishing-the-tag-manager-container" />

<Accordion title="4. タグマネージャーのコンテナの公開">

Googleタグマネージャーでタグの追加などの変更を行うたびに、コンテナをダウンロードし、アプリのルートフォルダに追加する必要があります。

* Android：app/src/main/assets/containers
* iOS：ルートフォルダ／container

アプリをビルドしてテストデバイスにインストールし、デバッグログでイベントが発火・送信されていることを確認します。

</Accordion>

<div data-zendesk-anchors="google-tag-manager-setup=google%E3%82%BF%E3%82%B0%E3%83%9E%E3%83%8D%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HE7SFG97FKSVAY5QHVHGF3GV=google%E3%82%BF%E3%82%B0%E3%83%9E%E3%83%8D%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HE7SFG97YVYNT385MNFA9ECN=1-creating-event-parameter-variables h_01HE7SFG98XGBMTA7ZF8XSNF29=2-creating-a-trigger-for-the-purchase-event h_01HE7SFG98R4DGTRWXE247MRPK=3-creating-a-tag-for-the-purchase-event h_01HE7SFG98R2KGRRDA9TQTYD3B=4-publishing-the-tag-manager-container" />
