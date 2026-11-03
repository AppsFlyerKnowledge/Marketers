---
title: ATTの影響（iOS14以降）とLATの廃止
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-10-07T17:33:35Z'
  edited_at: '2026-10-28T09:17:19Z'
  id: 360014090597
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/360014090597
---
> **概要**：iOS14以降では、プライバシーに関するユーザーの設定をATTで確認します。広告トラッキング制限（LAT）は廃止されました。

### ATTの値

* iOS14以降では、Appleの<Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor>（ATT）を通じて、アプリによるトラッキングの許可状況を示すステータス値を取得できます。
* AppsFlyerは、以下のいずれかからATTの値を取得します。
  * アプリに実装されたAppsFlyer SDK V6以降。
  * 広告主からAPI経由で送信されたデータ。たとえば、S2S APIが該当します。
* ローデータレポートにはATTを含めることができます。 ATTを含めるには、以下の設定を明示的に行う必要があります。
  * Pull API：リクエストのadditional\_ fieldsパラメータ*に*ATTを追加します。
  * データエクスポート画面：レポートのフィールドタブでATTを選択します。
  * Data Locker：設定画面でフィールド一覧にATTを追加します。
  * Push API：APIアクセス画面でフィールド一覧にATTを追加します。
* 場合によっては、AppsFlyerが定義した値がATTに設定されます。以下の表では、先頭に*af*が付いている値が該当します。
* IDFAを取得できない場合、その値はすべてゼロになります。

#### Appleが定義するATTの値

| ATTステータス | IDFAの取得可否 | 動作 |
| --- | --- | --- |
| not\_determined | iOS14〜14.4：取得可能<br /><br />iOS14.5以降：取得不可 | ATTのデフォルト値 |
| restricted | 取得不可 | iTunesアカウントの情報に基づいてAppleが決定します。ユーザーの操作によるものではありません。たとえば、ユーザーの年齢や、組織が管理するデバイスかどうかなどに基づいて決定されます。 |
| denied | 取得不可 | 以下のいずれかに該当する場合に設定されます。<ul><li>許可を求めるダイアログの表示後に設定された場合</li><li>ユーザーが*［アプリからのトラッキング要求を許可］*（デバイス全体の設定）をオフにしている場合</li><li>デバイスにiOS14をインストールする前にLATがオンになっていた場合</li></ul> |
| authorized | 取得可能 | ユーザーが明示的に同意しています。 |

#### AppsFlyerが独自に定義するATTの値

| ATTステータス | 補足 | IDFAの取得可否 |
| --- | --- | --- |
| af\_unknown | 広告主からATTの値が報告されましたが、<Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor>の仕様に定義されていない値です。 | iOSのバージョンによって異なります |
| af\_authorized | 以下のいずれかの理由により、IDFAの使用が許可されています。<ul><li>デバイスのiOSバージョンが14未満。</li><li>報告されたイベントにIDFAが含まれているものの、ATTが含まれていない。たとえば、iOS14未満のデバイスで、SDK V5.Xを実装したアプリを使用している場合が該当します。</li></ul> | 取得可能 |
| af\_unavailable | <ul><li>広告主から送信されたイベントにATTが含まれておらず、IDFAも取得できません。</li><li>AppsFlyer SDK V5.XではATTを取得できず、IDFAも取得できていません。</li></ul> | 取得不可 |

### iOSのIs LAT｜注意点とiOS14におけるATTとの対応

| iOSのバージョン | Is LATの扱い |
| --- | --- |
| iOS13以前 | <Image alt="IsLatTrue_us-en.png" src="https://files.readme.io/28440075d9c3913a148228a85ede15048d76f24913b48799ec4de3952d8f33e7-360011938457.png" width="221px" /><br /><br />trueの場合、ユーザーが広告トラッキング制限を有効にしているため、IDFAは取得できません。 |
| iOS14以降 | <Anchor target="_blank" href="https://developer.apple.com/documentation/adsupport/asidentifiermanager/1614148-isadvertisingtrackingenabled">AppleはI*s LAT*</Anchor>を廃止しました。 *Is LAT*の値は使用せず、代わりにATTを使用してください。 |

**iOS14におけるLATとATTの対応関係**

[<Image alt="LATtoiOS14.5.png" src="https://files.readme.io/872b3acdcd975337ff4de791a9fc98cd45eb50a487e80b3dfad6a1c7d9495739-360017977837.png" width="522px" />](https://files.readme.io/872b3acdcd975337ff4de791a9fc98cd45eb50a487e80b3dfad6a1c7d9495739-360017977837.png)

<div data-zendesk-anchors="att-values=att%E3%81%AE%E5%80%A4 h_01HGX9468F5YF0KSHB3S49CW2Y=att%E3%81%AE%E5%80%A4 att-values-defined-by-apple=apple%E3%81%8C%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8Batt%E3%81%AE%E5%80%A4 h_01HGX9468F0TFTMKP1W2J6GEBV=apple%E3%81%8C%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8Batt%E3%81%AE%E5%80%A4 additional-att-values-defined-by-appsflyer=appsflyer%E3%81%8C%E7%8B%AC%E8%87%AA%E3%81%AB%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8Batt%E3%81%AE%E5%80%A4 h_01HGX96RG9NX9QM2WTX8789DDR=appsflyer%E3%81%8C%E7%8B%AC%E8%87%AA%E3%81%AB%E5%AE%9A%E7%BE%A9%E3%81%99%E3%82%8Batt%E3%81%AE%E5%80%A4 is-lat-in-ios%E2%80%94considerations-and-how-lat-translates-to-att-in-ios-14=ios%E3%81%AEis-lat%E6%B3%A8%E6%84%8F%E7%82%B9%E3%81%A8ios14%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Batt%E3%81%A8%E3%81%AE%E5%AF%BE%E5%BF%9C h_01HGX9468F0VTYNXBJRSTNBCMB=ios%E3%81%AEis-lat%E6%B3%A8%E6%84%8F%E7%82%B9%E3%81%A8ios14%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Batt%E3%81%A8%E3%81%AE%E5%AF%BE%E5%BF%9C" />
