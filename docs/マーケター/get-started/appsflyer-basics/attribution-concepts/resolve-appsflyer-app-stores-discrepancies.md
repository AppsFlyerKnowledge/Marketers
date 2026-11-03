---
title: AppsFlyerとアプリストアの計測値の差異への対処
metadata:
  keywords:
    - Google Play
    - AppsFlyer
    - iTunes
    - installs
    - Discrepancies
    - App Stre
    - Compare
    - Account
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T12:52:53Z'
  edited_at: '2026-10-28T09:08:04Z'
  id: 207040726
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/207040726
---
> **概要：** AppsFlyerとアプリストアのアトリビューションの差異の主な原因と、差異を最小限に抑えるヒントを説明します。

## アトリビューションの差異

モバイルアトリビューションに関わる各事業者が採用するモデルには、それぞれ違いがあります。 AppsFlyerと主要なアプリストアであるApp Store（iOS）、Google Play（Android）も同様です。 **注意**：本記事では、この2つのストアを「アプリストア」と表記します。

モデルの違いにより、アプリストアのインストール数がAppsFlyerより多く記録される場合があります。反対に、AppsFlyerのインストール数がアプリストアより多く記録される場合もあります。

<Image alt="AF_vs_app_stores.png" src="https://files.readme.io/6f81aac30cdf1ab2331cd08e7a221c154e1f7104c15d47c47690baabaace856a-34114275895825.png" width="605px" />

> 📘 **注意**
>
> AppsFlyerのアトリビューションモデルでは、広告クリックごとに1件のインストールを紐付けるため、差異が**ノンオーガニック**のインストール数の正確性に影響することはありません。アプリストアに複数のデバイスを登録しているユーザーについても同様です。

### AppsFlyerの計測数が少なくなる理由

AppsFlyerの計測数が少なくなる主な原因は、以下のとおりです。

| 原因 | アプリストア | AppsFlyer | AppsFlyerでの対処のヒント |
| --- | --- | --- | --- |
| **インストールの定義** | アプリストアは、ユーザーがアプリをダウンロード・インストールした時点で、後にアプリを起動するかどうかに関係なく、インストールを記録します。 | AppsFlyerは、アプリの初回起動後にのみ新規インストールを記録します。<br /><br />アプリストアの定義でダウンロード・インストールが完了していても、**一度も起動していないユーザーはAppsFlyerでは計上されません**。 | モバイルアプリのダウンロードの約90％は、少なくとも1回の起動につながります。ただし、国・地域や業種によって大きく異なります。 |
| **インストールの記録日** | アプリストアは、ダウンロード日をインストール日として記録します。 | AppsFlyerは、初回起動日をインストール日として記録します。 | この差異を小さくするには、AppsFlyerでデータを確認する日付範囲を長く設定してください。 |
| **タイムゾーン** | 広告主の現地のタイムゾーンでデータを表示します。 | デフォルトでは、UTC±00:00でデータを表示します。 | アプリのタイムゾーンを設定して、この差異を小さくできます（<Anchor target="_blank" href="/marketers/ja/docs/changing-app-time-zone-settings">詳しくはこちら</Anchor>）。 |
| **Androidユーザーが、設定したリアトリビューション期間内にアンインストールと再インストールを行う** | Google Playの一部の表示では、初回インストールからの経過時間に関係なく、同じユーザーについて**2件**の**ユニークインストール**を表示します。一方、別の表示では**ユニークユーザー数**を表示するため、AppsFlyerに近い値になります。 | 元のインストールからリアトリビューション期間内（デフォルトは3か月）に再インストールした場合、AppsFlyerは新規ユーザーとして扱いません。 | <Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間は、1～24か月の範囲で設定</Anchor>できます。 |
| **iOSユーザーが、設定したリアトリビューション期間内にアンインストールと再インストールを行う** | iTunesは、ユーザーがアンインストールして再インストールするたびに、新規インストールとして計上します。 | 元のインストールからリアトリビューション期間内（デフォルトは3か月）に再インストールした場合、AppsFlyerは新規ユーザーとして扱いません。 | <Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間は、1～24か月の範囲で設定</Anchor>できます。 |

### AppsFlyerの計測数が多くなる理由

AppsFlyerの計測数が多くなる主な原因は、以下のとおりです。

| 原因 | アプリストア | AppsFlyer | AppsFlyerでの対処のヒント |
| --- | --- | --- | --- |
| **AppsFlyer SDKを含まないバージョンから、SDKを含むバージョンに既存アプリをアップデートする** | アプリストアは、同じユーザーとして扱い、新規インストールには数えません。 | AppsFlyerは、このアップデートをオーガニックインストールとして表示します。 | <ul><li>通常、数日で大半のユーザーのアップデートが完了するため、この一時的な増加は収まります。</li><li>新規アカウントでは、こうした増加を防ぐため、<Anchor target="_blank" href="/marketers/ja/docs/migration-to-appsflyer-from-other-vendors#デバイスidの移行任意">既存ユーザーのAppsFlyerへの移行</Anchor>を検討してください。</li></ul> |
| **デバイスIDのリセットや、広告トラッキングの制限（LAT）を悪用した不正** | アプリストアでは同じユーザーとして扱われ、新規インストールにはカウントされません。 | AppsFlyerは、新しいデバイスでの新規インストールとして扱います。 | AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide">不正対策ソリューションProtect360</Anchor>で、アプリがこの種の不正の影響を受けていないかを検知できます。 |
| **<Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">Google Play以外のマーケット</Anchor>経由のインストールや、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-factory-preinstall-using-manifest-android">プリインストール</Anchor>** | Google Playは、これらのインストールを記録しません。 | AppsFlyerは、これらのインストールを計上します。 | <Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">Google Play以外のAndroidマーケット</Anchor>で広告を配信する場合は、ドキュメントを参照して正しく設定してください。 |
| **Androidユーザーが、設定したリアトリビューション期間の終了後にアンインストールと再インストールを行う** | Google Playでは、初回インストールからの経過時間に関係なくユニークユーザー数を表示する場合と、同じユーザーについて2件のユニークインストールを表示する場合があります。後者はAppsFlyerに近い値になります。 | リアトリビューション期間（デフォルトは3か月）の終了後は、AppsFlyerは再インストールを通常の新規インストールとして扱います。つまり、同じユーザーが2回計上されます。 | <Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間は、1～24か月の範囲で設定</Anchor>できます。 |

<div data-zendesk-anchors="attribution-discrepancies=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%B7%AE%E7%95%B0 h_01HNWP7A6GQC5ZX6WKBW411DVG=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%B7%AE%E7%95%B0 h_01HNWP7A6GZJS246548Q5AFPZR=%E6%B3%A8%E6%84%8F why-appsflyer-attributes-less=appsflyer%E3%81%AE%E8%A8%88%E6%B8%AC%E6%95%B0%E3%81%8C%E5%B0%91%E3%81%AA%E3%81%8F%E3%81%AA%E3%82%8B%E7%90%86%E7%94%B1 h_01HNWP7A6G85PR1R66Q3KCRPNW=appsflyer%E3%81%AE%E8%A8%88%E6%B8%AC%E6%95%B0%E3%81%8C%E5%B0%91%E3%81%AA%E3%81%8F%E3%81%AA%E3%82%8B%E7%90%86%E7%94%B1 why-appsflyer-attributes-more=appsflyer%E3%81%AE%E8%A8%88%E6%B8%AC%E6%95%B0%E3%81%8C%E5%A4%9A%E3%81%8F%E3%81%AA%E3%82%8B%E7%90%86%E7%94%B1 h_01HNWP7A6GVVWMV6HECXQFTJT6=appsflyer%E3%81%AE%E8%A8%88%E6%B8%AC%E6%95%B0%E3%81%8C%E5%A4%9A%E3%81%8F%E3%81%AA%E3%82%8B%E7%90%86%E7%94%B1" />
