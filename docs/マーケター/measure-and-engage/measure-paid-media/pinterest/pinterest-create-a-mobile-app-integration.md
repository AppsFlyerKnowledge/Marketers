---
title: Pinterestの連携設定
metadata:
  keywords:
    - Pinterest
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-11-09T12:51:03Z'
  edited_at: '2026-10-14T09:20:06Z'
  id: 216912786
  locale: ja
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/ja/articles/216912786
---
> **概要：** AppsFlyerの連携済みパートナーであるPinterestは、ブロガーやブランドのトラフィックの最大の貢献者の1つです。Pinterestは、クリックベースのモバイルアトリビューションとビュースルーモバイルアトリビューションの両方を提供しています。さらに、Pinterestは、AppsFlyerで計測できるクリックベースのリターゲティングも提供しています。

<div id="note" />

> 📘 **注**
>
> * 2021年6月より、PinterestはCPIキャンペーンを実施しなくなりました。その結果、AppsFlyerはインストールポストバックをPinterestに送信しません。
> * Pinterest広告利用規約に同意した後、 <Anchor target="_blank" href="https://ads.pinterest.com/terms/app_install/">こちら</Anchor>からPinterest Mobile Measurementの利用規約に同意してください。
> * Pinterestは、インストール後6か月でユーザーレベルのデータを削除するようアトリビューションプロバイダーに要請しています。つまり、これらのユーザーがアプリをインストールしてから6か月後に行われたイベントは、オーガニック経由としてカウントされます。過去の集計データは変わりません。
> * 2023年9月4日以降、Pinterestはユーザーのプライバシーを保護し、規制遵守を確保するために、<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">ローデータレポートの一部項目の利用可能性を制限</Anchor>することを要求します。

<div id="set-up-pinterest" />

## Pinterest連携の設定

**前提条件：** 連携を設定する前に、 <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>し、アカウントを開設してください。

**連携を有効化または編集する：**

1. **連携を有効に設定する：** AppsFlyer管理画面 左メニュー **連携** > パートナーマーケットプレイスへ移動します。  
   **連携を変更するには：** AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動します。
2. **Pinterest**を検索して選択します。
3. **連携の設定**をクリックします。連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注： パートナーとの作業中はトグルをオン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（アクティブ化）</Anchor>にしておいてください。**
5. 以下の手順に従い、各タブの設定を完了してください。

Pinterestの連携設定画面には、4つのタブが含まれています：連携、計測リンク、コスト、および権限。次の項目をクリックすると各タブの設定に関する説明が表示されます。

連携済みパートナーの設定画面のヘッダーについての詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>をクリックしてください。

<div id="integration-tab" />

<Accordion title="連携タブ">

<div id="activate-partner" />

### パートナーの有効化

このタブを**初めて開く**場合、連携タブのパラメーター設定を有効にするために**パートナーを有効にする**のトグルをオンにする必要があります。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。  
パートナーのライセンス認証の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>をクリックしてください。

<div id="general-settings" />

### 一般的な設定

以下は、Pinterestの連携タブの一般的な設定です。

**ビュースルー計測の有効化**

Pinterestからのビュースルーインストールを計測する場合は、これをオンにします。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

<div id="in-app-events-settings" />

### アプリ内イベントの設定

このセクションでは、PiterestへポストバックするAppsFlyerのイベントをマッピングできます。

**Tag ID**

アプリ内イベントのポストバックを Pinterestに送信できるようにするには、タグIDを入力する必要があります。タグIDをお持ちでない場合は、Pinterestから取得してください。

**タグIDを取得し、アプリ内イベントのポストバックを設定する：**

1. Pinterestビジネスアカウントで、**広告** > **コンバージョン**に移動し、**タグID**をコピーします。  
   まだタグがない場合は、**タグを作成する**をクリックして、作成プロセスを完了します。新しいタグをコピーします。  
   　**注：** タグIDは、イベントポストバックにのみ必要です。
2. AppsFlyerのPinterest連携設定で、**アプリ内イベント設定**までスクロールし、PinterestタグIDを入力します。
3. **アプリ内イベントポストバック**を有効にします。
4. アプリ内イベントのポストバック期間を設定します。
5. イベントのポストバック設定とマッピングを選択します。
6.
   | パラメータ名 | 説明 |
   | --- | --- |
   | **AppsFlyerイベント名** | アプリとSDKから、またはサーバー間（S2S）イベントから AppsFlyer が受信したイベント名  <br />**ヒント** - アプリ内イベント名がリストに表示されない場合、デバイス上で非オーガニックインストールによってアプリ内イベントが発生しているかを確認してください。 |
   | **パートナーイベント名** | Pinterest側で定義されている各イベントの固有の名前またはID。  <br />対応するイベントIDをPinterestから取得して、テキスト項目に設定してください。 |
   | **送信オプション** | このパートナーのみ：このパートナーにアトリビューションされたユーザーからのイベントのみを送信  <br />**オーガニックを含むすべてのメディアソース：** ユーザーベース全体をこのパートナーにレポートできるようにします。 |
   | **送信データ** | 選択すると、イベントの収益値がポストバックで媒体に送信されます。<br /><br />AppsFlyerは、アプリ内イベントに付随するすべてのパラメーターをパートナーに送信できます。ただし、収益パラメーターは **af\_revenue** パラメーターに含まれているため、このパラメーターは送信されません。または、AppsFlyerは、イベント内に存在する場合、収益値を含むすべてのパラメーターを送信できます。 |

7. **イベントを追加**をクリックして、SDKイベントをリストに追加します。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。単一プラットフォームリンクまたはOneLinkのいずれかを使用できます。  
<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">計測リンクの構造とパラメーターについての詳細はこちら</Anchor>

**計測リンクを作成**するには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">これらの手順</Anchor>に従ってください。

<div id="attribution-link-for-retargeting-campaign" />

#### リターゲティングキャンペーンの計測リンク

Pinterestでは、リターゲティングキャンペーンに OS固有の計測リンクを使用することをお勧めします。**単一プラットフォームのリンクを使用する** オプションを選択し、必要なパラメータをリターゲティング計測リンクに追加します。

<div id="deep-link-url" />

#### ディープリンクURL

<div id="note-1" />

> 📘 **注**
>
> ピン内からのディープリンクは、アプリがPinterestによって許可リストに登録されている場合にのみ正しく機能します。
> Pinterestの担当者または[apps@pinterest.com](mailto:apps@pinterest.com)へ連絡し、ディープリンクの許可リストに登録してください。

この項目は、ディープリンクを使用してユーザーをアプリの特定のアクティビティに遷移する場合に使用します。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

Pinterestのコストデータ連携を設定した後は、配信中のキャンペーン、広告セット、単一の広告の名前を変更したり、キャンペーン名パラメータで動的マクロを使用したりすると、重大な差異が生じたり、コストデータが欠落したりする可能性があるため、変更しないでください。

<div id="enabling-and-testing-pinterest-integration" />

### Pinterest連携の有効化とテスト

AppsFlyerはコストの詳細をAPIで取得します。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークのコスト連携に関する表</Anchor>を参照してください。　**注意**：コストデータの取得にはROI360のご契約が必要です。

**コストAPIを有効にする方法**：

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<div id="cost-data-sync-status" />

### コストデータ同期ステータス

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

<div id="stop-pinterest-cost-sync" />

### Pinterestのコスト同期を停止する

**接続されているアカウントを削除する方法：**

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">アクション列で、アカウントにカーソルを合わせて***接続を削除***をクリックします。</Anchor>削除すると、AppsFlyerはコストの取得を停止します。接続を削除しても過去のデータには影響しません。

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

広告収益データはこのパートナーではサポートしていません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

このタブでは、Pinterestに付与する権限を選択できます。Pinterestが連携設定が無効なっている場合でも権限タブは使用可能で、パートナーに対する権限付与ができます。

詳細：<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">Pinterestに付与できる権限</Anchor>

</Accordion>

</Accordion>

<div id="troubleshooting" />

## トラブルシューティング

コストタブエラーメッセージ：*一致するデータがない* ということは、AppsFlyerに接続したPinterestアカウントが正しい Pinterestアカウントではないことを意味します。アプリに一致するデータが見つかりませんでした。別の認証情報でPinterestにログインする必要があります。

<div data-zendesk-anchors="h_01H95QTA3ZZ9GJW9EN1VZ01TH2=%E6%B3%A8 set-up-pinterest=pinterest%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H95QTA3Z5HXW39AHAF8FMFWH=pinterest%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H95QTA3ZNQWBRA86E6TRQ46Y=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H95QTA3ZGEM34HY1A7NC8NX7=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01H95QTA3Z0NW9V51D8J7MHEX0=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H95QTA3ZWSF0JYZ9D4HEB4A4=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H95QTA3ZT7PVGAJW5AKPC186=attribution-link-tab attribution-link-for-retargeting-campaigns=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF h_01H95QTA3ZPQZ422AB2JBZAS07=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF deep-link-url=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AFurl h_01H95QTA3ZT23CYTCE2V3728MD=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AFurl h_01H95QTA3ZYHQED2T5B2FA5PV8=%E6%B3%A8-1 h_01H95QTA3Z3XJDM5YRXFK7DA0E=cost-tab enabling-and-testing-pinterest-integration=pinterest%E9%80%A3%E6%90%BA%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96%E3%81%A8%E3%83%86%E3%82%B9%E3%83%88 h_01H95QTA3ZZ56R8EZBJY1ESX5W=pinterest%E9%80%A3%E6%90%BA%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96%E3%81%A8%E3%83%86%E3%82%B9%E3%83%88 cost-data-sync-status=%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E5%90%8C%E6%9C%9F%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9 h_01H95QTA3ZST8WS3TAR79H06FM=%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E5%90%8C%E6%9C%9F%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9 stop-pinterest-cost-sync=pinterest%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E5%90%8C%E6%9C%9F%E3%82%92%E5%81%9C%E6%AD%A2%E3%81%99%E3%82%8B h_01H95QTA3ZFCJ82E3YDMP7S716=pinterest%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E5%90%8C%E6%9C%9F%E3%82%92%E5%81%9C%E6%AD%A2%E3%81%99%E3%82%8B h_01H95QTA3ZM2REWR2A5DHK1DSA=ad-revenue-tab h_01H95QTA3ZM4WPHV3MB00WZXSB=permissions-tab troubleshooting=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01H95QTA3ZP20DSJQGY4QQX0Z7=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0" />
