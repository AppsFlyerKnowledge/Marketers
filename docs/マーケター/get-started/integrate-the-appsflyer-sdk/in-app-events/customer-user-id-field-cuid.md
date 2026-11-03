---
title: カスタマーユーザーID（CUID）フィールド
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2026-10-29T07:44:15Z'
  id: 207032016
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/207032016
---
> **At a glance:** CUIDを使うと、異なるデバイス、メディアソース、チャネルで発生した同一ユーザーのイベントをまとめられます。

## CUIDとは

カスタマーユーザーID（CUID）は、アプリ側で設定する一意のユーザー識別子です。通常、アプリの運営者がユーザー登録時に生成・設定します。 CUIDを使うと、アプリの運営者は複数のデバイスにまたがるユーザーの一連の行動を追跡できます。

> 📘 **例**
>
> たとえば、2台以上のデバイスを使うユーザーに、各アプリで共通のCUIDを設定します。ユーザーがモバイル端末やデスクトップ端末でイベントを実行するたびに、SDKがイベントとCUIDを取得します。広告主は各デバイスのデータを統合し、ユーザーの行動を全体として把握できます。
>
> 主な活用例：
>
> * 同一ユーザーが複数のデバイス（スマートフォン、タブレット、テレビ、デスクトップ）で同じアプリ内の購入を行った場合、それらを1人のユーザーの購入データとしてまとめて確認できます。
> * 複数のプラットフォーム（デスクトップ、モバイル、テレビ）でユーザーの利用状況データを共有し、一貫したユーザー体験を提供できます。

## CUIDの設定

できるだけ多くのイベントをCUIDに紐づけられるよう、SDKの初期化処理のできるだけ早い段階でCUIDを設定することを推奨します。

<Tabs>
<Tab title="Androidネイティブ">

CUIDを取得できたら、`setCustomerUserID`を呼び出して設定できます。 CUIDを紐づけられるのは、設定後に発生したアプリ内イベントのみです。そのため、`start`を`setCustomerUserID`より先に呼び出すと、インストールイベントにCUIDは含まれません。

### インストールイベントとCUIDの紐付け

インストールイベントにCUIDを紐づける必要がある場合は、`start`を呼び出す前に設定することを推奨します。

**重要：**`start`より先にCUIDを設定する実装では、CUIDの設定を待つ間、SDKからインストールイベントが送信されず、アトリビューションが行われなくなる場合があります。たとえば、ユーザーがアプリを初めて起動した後、SDKがCUIDを設定する前にアプリを終了すると、この状況が発生する可能性があります。

Androidでは、アプリの実装に応じて、グローバルな`Application`クラスまたは`Activity`クラスから`start`メソッドの実行とCUIDの設定を行えます。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#sdkを起動するクラスの選択">SDKを開始するクラスの選択</Anchor>を参照してください。

#### ApplicationクラスでSDKを開始する場合

グローバルな`Application`クラスからSDKを開始し、インストールイベントにCUIDを紐づける場合は、`waitForCustomerUserId`メソッドを使ってインストールイベントの送信を遅らせてください。このメソッドは、CUIDが設定されるまでSDKを待機状態にします。

注意：何らかの理由でCUIDの設定に失敗すると、SDKは待機状態のままとなり、イベントを一切送信しません。

#### ActivityクラスでSDKを開始する場合

`Activity`クラスからSDKを開始し、インストールイベントにCUIDを紐づける場合は、インストールイベントの送信を遅らせる必要はありません。 `start`を呼び出す前に`setCustomerUserId`を呼び出してください。

#### 開発者向けの手順

開発者に、以下を伝えてください。

* グローバルな`Application`クラスからSDKを開始する場合は、`waitForCustomerUserId`を使用します。
* 開発者向けのリンク：
  * インストールイベントにCUIDを紐づける方法は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event">こちら</Anchor>を参照してください。

</Tab>

<Tab title="iOSネイティブ">

`customerUserId`メソッドを使ってCUIDを設定します。 `start`メソッドを呼び出す前と後のどちらで`customerUserId`を設定するかによって、CUIDを紐づけられるイベントが異なります。

* `start`より先に`customerUserId`を呼び出すと、SDKはインストールイベントと、それ以降のアプリ内イベントにCUIDを紐づけます。
* `start`の後に呼び出すと、SDKはCUIDの設定後に記録されたイベントにのみCUIDを紐づけます。

#### 開発者向けの手順

Dev Hubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id">カスタマーユーザーIDの設定</Anchor>を開発者に案内してください。

</Tab>

<Tab title="Unity">

#### 開発者向けの手順

Dev Hubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">カスタマーユーザーIDの設定</Anchor>を開発者に案内してください。

</Tab>

<Tab title="React Native">

#### 開発者向けの手順

Dev HubのAPIリファレンスにある<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid">setCustomerUserId</Anchor>の説明を開発者に案内してください。

</Tab>

<Tab title="Web">

実装手順の詳細は、「AppsFlyer Web SDKの実装」の<Anchor target="_blank" href="/marketers/ja/docs/integrate-appsflyer-web-sdk#4-カスタマーユーザーidの設定">カスタマーユーザーIDの設定</Anchor>を参照してください。

</Tab>
</Tabs>

## CUIDとプライバシー

AppsFlyerはユーザーのプライバシーを尊重し、<Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">機微な個人情報の収集やAppsFlyerプラットフォームへの送信を認めていません。</Anchor>

ユーザーのプライバシーを保護するため、ユーザーを直接識別できる情報をCUIDに含めないでください。これには、社会保障番号や国民識別番号が含まれます。

CUIDにユーザーのメールアドレスや電話番号が含まれる場合は、AppsFlyerに送信する前にハッシュ化する必要があります。個人情報を含むCUIDを、ハッシュ化せずにAppsFlyerに送信しないでください。

> 📘 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview#ユーザージャーニーレポート">ユーザージャーニーレポート</Anchor>（ローデータレポート内のCUIDに関する詳細）
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">個人を特定できる情報（PII）を送信しないためのGoogleのベストプラクティス</Anchor>

<div data-zendesk-anchors="what-is-cuid=cuid%E3%81%A8%E3%81%AF h_01HAJ00DVHRSDBS4FFKM16JFER=cuid%E3%81%A8%E3%81%AF h_01HAJ00DVHZ8V8MRAXN2W3T8DS=%E4%BE%8B setting-the-cuid=cuid%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HAJ00DVHDGM133A72HD5JXER=cuid%E3%81%AE%E8%A8%AD%E5%AE%9A associate-the-cuid-with-the-install-event=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A8cuid%E3%81%AE%E7%B4%90%E4%BB%98%E3%81%91 h_01HAJ00DVHDE9V2MT6JQF8SAH3=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A8cuid%E3%81%AE%E7%B4%90%E4%BB%98%E3%81%91 if-the-sdk-starts-in-the-application-class=application%E3%82%AF%E3%83%A9%E3%82%B9%E3%81%A7sdk%E3%82%92%E9%96%8B%E5%A7%8B%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 h_01HAJ00DVH746B6YJVF70PMZJ8=application%E3%82%AF%E3%83%A9%E3%82%B9%E3%81%A7sdk%E3%82%92%E9%96%8B%E5%A7%8B%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 if-the-sdk-starts-in-an-activity-class=activity%E3%82%AF%E3%83%A9%E3%82%B9%E3%81%A7sdk%E3%82%92%E9%96%8B%E5%A7%8B%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 h_01HAJ00DVHYZBER40RJH0GM8KF=activity%E3%82%AF%E3%83%A9%E3%82%B9%E3%81%A7sdk%E3%82%92%E9%96%8B%E5%A7%8B%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 developer-instructions-android=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E6%89%8B%E9%A0%86 h_01HAJ00DVHZBZCRA1VGYJY44VY=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E6%89%8B%E9%A0%86 developer-instructions::31dbab4b=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E6%89%8B%E9%A0%86 h_01HAJ00DVH2RV902D6G224A4QY=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E6%89%8B%E9%A0%86 developer-instructions-unity=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E6%89%8B%E9%A0%86 h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E6%89%8B%E9%A0%86 developer-instructions-react=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E6%89%8B%E9%A0%86 h_01M25Y3EFC7BJAYE9YEJYA4S5A=%E9%96%8B%E7%99%BA%E8%80%85%E5%90%91%E3%81%91%E3%81%AE%E6%89%8B%E9%A0%86 cuid-and-privacy=cuid%E3%81%A8%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC h_01HAJ00DVH4987JGZZVDA1NB29=cuid%E3%81%A8%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC h_01HE7RXTEPQAWV03276TDEPG0V=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
