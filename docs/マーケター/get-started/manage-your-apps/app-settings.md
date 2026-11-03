---
title: アプリ設定
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2016-08-16T07:50:37Z'
  edited_at: '2026-10-14T09:33:33Z'
  id: 211719806
  locale: ja
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ja/articles/211719806
---
> **概要：** すべてのメディアソースにわたってアプリのアトリビューションと分析に影響を与える設定について説明します。

## アプリ設定

**アクセス：**

* 管理者（または適切な権限を持つ他のユーザー）は、アプリの設定を**変更**できます。
* 特定のアプリにアクセスできるすべてのアカウントユーザーは、そのアプリの設定を**表示**できます。

**アプリ設定を変更または表示するには：**

1. **AppsFlyer管理画面左メニュー** **設定** > アプリ設定へ移動します。
2. アプリ設定ページで設定を確認し、必要に応じて変更を加えてください。
3. **設定を保存**をクリックします。

### 一般設定

<Table>
  <thead>
    <tr>
      <th>
        設定
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="sdk-authentication-dev-key"></span>
        SDK認証：開発キー
      </td>
      <td>
        * この開発キーは、アプリまたはS2SからAppsFlyerに送信されるイベントの認証に使用されます。
        * このキーはアカウントごとに一意で、アカウント内のすべてのアプリで使用されます。
        * そのアプリにアクセスできるアカウントユーザーは、アプリ設定ページでこのキーを利用できます。
        * [オプション] 特定のシナリオでは、個別のアプリキーを割り当てることが可能です。詳細については、CSMに相談してください。
      </td>
    </tr>
    <tr>
      <td><span id="aggregated-advanced-privacy-ios-apps"></span>
        高プライバシー一括設定（iOSアプリのみ）
      </td>
      <td>
        この設定をオンにすると、ユーザーレベルのアトリビューションデータが利用できなくなります。ポストバックおよびパートナーと共有されるイベントデータは集計データとなり、匿名化されます（詳細：<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高プライバシー一括設定</Anchor>）。

        オフにすると、ユーザーレベルのアトリビューションデータは全パートナーに対して集計データとして利用可能で、パートナーごとに個別設定が可能です。
      </td>
    </tr>
    <tr>
      <td><span id="analytics-define-loyal-user-trigger"></span>
        分析：ロイヤルユーザーの定義を設定
      </td>
      <td>
        * ユーザーをロイヤルユーザーとして識別するための発火地点。アプリ追加の際のデフォルトのオプションは、最低3回のアプリ起動です。
        * アプリ内イベントをアトリビューションした後、そのイベントをトリガーとして利用できます。
          * [デフォルト] 3回のアプリ起動。
          * ロイヤルユーザー設定は、ユーザーの質を示す指標です。不正対策として、<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide#faq">Protect360</Anchor>の利用を検討してください。
          * この設定を変更すると、過去のロイヤルユーザーデータが遡及的に再計算されます。
      </td>
    </tr>
    <tr>
      <td><span id="app-store-country"></span>
        アプリストアの国
      </td>
      <td>
        アプリが利用可能なアプリストアの国を設定します。この設定は、ここで詳しく説明されているようにアプリに影響します。

        * **アプリのステータスを保留から公開に変更する：**
          * <Anchor target="_blank" href="/marketers/ja/docs/why-is-my-app-still-pending">アプリが公開</Anchor>されると、AppsFlyerは国設定を使用してストアをチェックし、アイコンなどのアプリの詳細を取得します。
          * アプリがストアの国設定で見つからない場合、AppsFlyerはアプリのステータスを保留から公開に変更できません。
        * リダイレクト動作は、次の表に示すように、シナリオに応じて設定の影響を受けます。

        | ユーザータイプ | リダイレクトシナリオ |
        | --- | --- |
        | <span id="mobile"></span>モバイル | ユーザーは通常、他のモバイルアプリ内のアトリビューションリンクをクリックします。クリックすると、オペレーティングシステムがユーザーをリダイレクトするアプリストアの国を決定します。  <br /><br />* **Android**はユーザーのIPまたは位置情報に基づいてリダイレクトします。<br />* **iOS**は、デバイス上でアクティブなiTunesアカウントに関連付けられたアプリストアにリダイレクトします。 |
        | <span id="mobile-and-web"></span>モバイルとウェブ | ウェブユーザーが**ウェブサイト**（モバイルとデスクトップ）内のアトリビューションリンクをクリックすると、最初のリダイレクトはアプリストアの国で設定されたストアに行われます。<br /><br />インストールを試みると、オペレーティングシステムは、前の行のモバイルで説明したように、国別ストアにリダイレクトします。 |
        | <span id="ipad-ios-13"></span>iPad iOS 13 | iOS 13以降では、<Anchor target="_blank" href="https://www.apple.com/ipados/features/">iPadはウェブサイトのデスクトップバージョンが提供されます</Anchor>。これは、ユーザーの種類（モバイルまたはウェブ）が関係ないことを意味します。アトリビューションリンクをクリックするとデスクトップサイトに移動し、その後のリダイレクトルールはウェブユーザーのルールになります。 |
      </td>
    </tr>
    <tr>
      <td><span id="localization-time-zone"></span>
        ローカリゼーション：タイムゾーン
      </td>
      <td>
        デフォルトのアプリ設定：UTC時間 <Anchor target="_blank" href="/marketers/ja/docs/changing-app-time-zone-settings">/ アプリのタイムゾーンについて</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="localization-currency"></span>
        ローカリゼーション：通貨設定
      </td>
      <td>
        * これは、以下の指標に使用されるアプリ固有の通貨を定義します：
          * コスト
          * アプリ内イベント / 収益の計測
          * 広告収益
        * デフォルトのアプリ設定はUSDです。
          * 通貨の変更は、収益やコストのないアプリで利用できます。
          * 新しいアプリの場合、通貨はアプリが追加されたときに設定します。

        #### アプリの通貨によって影響を受けるレポートツール

        | レポートツール | 利用可能な通貨オプション |
        | --- | --- |
        | <span id="dashboards"></span>ダッシュボード | アプリ固有の通貨 |
        | <span id="export-data-page"></span>データ出力画面 | アプリ固有の通貨 |
        | <span id="push-api"></span>Push API | アプリ固有の通貨とUSDを同時に利用可能 |
        | <span id="pull-api"></span>Pull API | 集計データ：アプリ固有の通貨<br /><br />ローデータ：選択可能なUSDまたはアプリ固有の通貨 |
        | <span id="master-api"></span>Master API | 選択可能なUSDまたはアプリ固有の通貨 |
        | <span id="data-locker"></span>Data Locker | USDのみ |
      </td>
    </tr>
  </tbody>
</Table>

### アトリビューション設定

| 設定 | 説明 |
| --- | --- |
| <span id="reattribution-window"></span>リアトリビューション期間 | <Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>は、最初のインストール日から始まる期間であり、この期間中は再インストールは新規インストールとしてアトリビューションされません。<ul><li>[デフォルト] 3か月</li><li>値の範囲：1～24か月</li></ul> |
| <span id="viewthrough-attribution-via-probabilistic-modeling"></span>確率論的モデリングによるビュースルーアトリビューション | <ul><li>[ベストプラクティス] 常に有効なクリックスルーアトリビューションに加え、ビュースルー確率論的モデリングを有効にします。</li><li>ビュースルー確率論的モデリングを有効にした後、アドネットワーク連携タブでもビュースルーアトリビューションを有効にする必要があります。</li></ul> |
| <span id="reengagement-attribution"></span>リエンゲージメント計測 | 関連記事：<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティングガイド</Anchor><br /><br />**リエンゲージメント計測を有効にする：**<ul><li>**AppsFlyer管理画面左メニュー** **設定** > **アプリ設定** へ移動し、リエンゲージメントCV計測のトグルをオンにします。</li></ul>このアプリ設定に加えて、連携済みパートナーが目にて<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#retargeting-settings">パートナーごとの設定</Anchor>も行う必要があります。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#計測除外設定">**リエンゲージメントCV再計測までの最短時間**</Anchor>設定は、既存のリエンゲージメント期間を設定時間より前に終了しないようにするために使用します。 |
| <span id="organic-search-seo-mobile-app-attribution"></span>オーガニック検索（SEO）計測 | 関連記事：<Anchor target="_blank" href="/marketers/ja/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">オーガニック検索の計測</Anchor><br /><br />**オーガニック検索アトリビューションを有効にするには：**<ul><li>AppsFlyer管理画面左メニュー **設定** > **アプリ設定** へ移動し、**オーガニック検索（SEO）計測**のトグルをオンにします。</li></ul> |
| <span id="uninstall-measurement"></span>アンインストール計測 | <Anchor target="_blank" href="/marketers/ja/docs/measure-uninstalls">アンインストールの計測</Anchor>は、アンインストール計測が有効のときに発生するインストールに関連しています。<br /><br />**アンインストール計測を有効にするには：**<ol><li>各OSに対して以下を完了します：<ul><li>**iOS：** iOSアンインストール計測機能を実装するアプリは、ここにP12証明書をアップロードする必要があります。</li><li>**Android：** アプリはAndroidアンインストール計測用に、ここでFirebase/GCMサーバーキーを定義する必要があります。</li></ul></li><li>**アンインストール計測**トグルをオンにします。</li><li>**設定を保存**をクリックします。</li></ol>**アンインストール計測を停止するには：**<ol><li>**アンインストール計測**トグルをオフにします。</li><li>**設定を保存**をクリックします。</li></ol> |

### 詳細設定

| 設定 | 説明 |
| --- | --- |
| <span id="mask-ip-address-in-raw-data-reports"></span>IPアドレスをマスクする | オンにすると、エンドユーザーデバイスの<Anchor target="_blank" href="/marketers/ja/docs/apply-ip-masking-to-user-data">IPアドレスが、ローデータレポートおよび現在選択されたアプリからパートナーに送信されるポストバックでマスク</Anchor>されます。 |
| <span id="reinstall-detection-using-ondevice-storage-ios-only"></span>端末上のストレージを使用した再インストールの検出（iOSのみ） | 広告IDに依存せずに再インストールを検出します。これは、デバイスの安全なローカルストレージ（iOSの場合はKeychain）で最終アプリインストール日を保存することで実現されます。インストールが再インストールか新規インストールかを判断することで、NOIからの再インストールを重複排除し、アトリビューション分析の精度を向上させることができます。 |
| <span id="ios-103-redirect-fallback"></span>iOS 10.3 リダイレクトフォールバック | [廃止] iOS 10.3以降向けiOSユーザー向けフローが簡素化されたため、このパラメータは使用されなくなりました。 詳細：<Anchor target="_blank" href="/marketers/ja/docs/uri-scheme-fallback-for-ios">iOSリダイレクト</Anchor><br /><br />このオプションはiOSアプリでのみ利用可能です。 |
| <span id="change-app-name"></span>アプリ名の変更 | <ul><li>アプリ名は、管理画面やデータレポート全体に表示されます。異なるバージョンのアプリがある場合、例えば地域別配信のために、便利です。</li><li>この変更はアプリの表示に影響します。アプリIDは、さまざまなAppsFlyer APIでアプリを識別するため**変わりません**。</li><li>名前は50文字以内に制限されています。</li></ul> |
| <span id="outofstore-app-url"></span>ストア外アプリURL | <ul><li>アプリに関連する計測リンクのデフォルトリダイレクト先として使用するアプリダウンロードURLを設定します。</li><li>Androidアプリがストア外アプリとして指定された場合、このフィールドは必須です。</li><li>設定すると、約1時間以内にデフォルトリダイレクト先としてURLが適用されます。</li></ul> |

> 📄 **参照**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティング計測ガイド</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">オーガニック検索の計測</Anchor>

<div data-zendesk-anchors="app-settings=%E3%82%A2%E3%83%97%E3%83%AA%E8%A8%AD%E5%AE%9A 01ECHQME56X51MDW9TMA6DBNCK=%E3%82%A2%E3%83%97%E3%83%AA%E8%A8%AD%E5%AE%9A general-app-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01HAVS8CVPQKSDKCEM3YHHJ99Y=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A reporting-tools-impacted-by-app-currency=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E9%80%9A%E8%B2%A8%E3%81%AB%E3%82%88%E3%81%A3%E3%81%A6%E5%BD%B1%E9%9F%BF%E3%82%92%E5%8F%97%E3%81%91%E3%82%8B%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB h_01HAVS8CVQESWAQXKDW5SNVHCJ=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E9%80%9A%E8%B2%A8%E3%81%AB%E3%82%88%E3%81%A3%E3%81%A6%E5%BD%B1%E9%9F%BF%E3%82%92%E5%8F%97%E3%81%91%E3%82%8B%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB attribution-settings=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%AD%E5%AE%9A h_01HAVS8CVQN1YYTT7S49VGB3J0=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%AD%E5%AE%9A advanced-settings=%E8%A9%B3%E7%B4%B0%E8%A8%AD%E5%AE%9A h_01HAVS8CVQTKXVXSMT5KNYZ3T4=%E8%A9%B3%E7%B4%B0%E8%A8%AD%E5%AE%9A h_01HDPCC9465DR4A3CCXYQC2M56=%E5%8F%82%E7%85%A7" />
