---
title: Google Ads（AdWords）｜広告主向けの連携設定
metadata:
  keywords:
    - Integration
    - Google AdWords
    - Configuration
    - google
    - migration
    - Advertisers
    - google ads configuration
    - ads
    - google ads
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-17T19:16:15Z'
  edited_at: '2026-10-28T09:15:28Z'
  id: 115002504686
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/115002504686
---
> **At a glance:** Google AdsアカウントをAppsFlyerと連携して、すべてのキャンペーンの計測データを表示します。

AppsFlyerでGoogle Ads連携を設定すると、Google Adsキャンペーンからのインストールおよびアプリ内イベントを計測・アトリビューションできるようになります。 AppsFlyer上では、この連携は`googleadwords_int`という名称で管理され、アトリビューション結果はメディアソース`googleadwords_int`としてレポートされます。

## 高度なデータ共有を使用したGoogle Adsの計測フロー

![Google ads attribution flow.png](https://files.readme.io/1c49e06e48658a8cb60ae6a9e9a83c0fad751766f3d4ce9c6afdd041fb5e8579-small-38644882427537.png)

1. AppsFlyerは、これまで通りインストールイベントをGoogleに送信します。［**高度なデータ共有**］がオンの場合、デバイスIDの有無にかかわらずインストールが送信されます。オフの場合は、**デバイスIDがある場合にのみ**インストールが送信されます。
2. Googleは、利用可能なデバイスIDによる決定論的な照合（IDマッチング）か、デバイスIDがない場合は確率論的モデリングを使った非決定論的な照合により、インストールの成果主張を試みます。
3. どちらの場合でも、GoogleはAppsFlyerに対し、決定論的または非決定論的な成果主張を返します。
4. AppsFlyerは、非決定論的な成果の主張を独自の確率論的モデリングで検証します。検証を通過した成果の主張のみを受け入れます。
5. 検証後、Googleの成果主張（受領したもの）はアトリビューション判断のステップに入り、AppsFlyerが他の成果候補（例：他のSRN、クリック計測のアドネットワーク、オーガニックなど）と比較します。インストールは、AppsFlyerのアトリビューションロジックと優先順位ルールに基づき、最も適切なソースに紐づけられます。
6. Googleによる成果の主張が受け入れられ、最終的な計測対象に選ばれた場合、インストールはGoogleの成果として計測されます。ローデータレポートでは、決定論的な成果の主張の<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#attribution::cecc12c5">match\_type</Anchor>は`srn`、非決定論的な成果の主張のmatch\_typeは`probabilistic`と表示されます。

## 広告主向けのGoogle Ads計測の設定

AppsFlyerでGoogle Adsキャンペーンの計測を開始するには、次の手順に従います：

<Accordion title="ステップ1：ICMの前提条件の確認">

AppsFlyerを通じてiOSでのGoogle PMODのインストール成果の主張に対応するには、以下の要件を満たしていることを確認してください。これは、GoogleのOn-Device Measurement（ODM）を有効にするために必要です。 Androidについては、SDKの更新は必要ありません。

1. [AppsFlyerのiOS SDKを更新](https://dev.appsflyer.com/hc/docs/install-ios-sdk)し、**v6.17.9以降**を使用してください（SDKの追加設定は不要です）。
2. Google SDKの更新については、次のいずれかが必要です：
   * **GoogleのFirebase iOS**SDK<strong>v11.14.0以降。</strong>詳細は、[Googleのドキュメント](https://github.com/firebase/firebase-ios-sdk/releases)を参照してください。**または**
   * **Google ODMのスタンドアロン**SDK。詳細は、[Firebaseのドキュメントを参照してください。](https://support.google.com/google-ads/answer/16384720)
3. <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#idfv">IDFV</Anchor>がアプリを開くたびやアプリ内イベントのたびにAppsFlyerに送信されることを確認してください。
4. アプリを開くイベントのたびにIPアドレスがAppsFlyerに送信されることを確認してください。アプリのIPマスキングが設定されている場合、ICMは機能しない可能性があります。

</Accordion>

<Accordion title="ステップ2：Google AdsのリンクID作成（必須）">

リンクIDを作成するにはアカウントに対する**Google管理者アクセス**が必要です。以下手順もしくは<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">Googleのドキュメント</Anchor>を参照してください。

1. Google Ads管理者アカウントにログインします。
2. 上部メニューから**ツールと設定**をクリックします。
3. **設定**メニューで**データマネージャー**を選択し、**+ 製品の接続**をクリックします。
4. **データソース**検索バーに「サードパーティアプリアナリティクス」と入力して選択し、**続行**をクリックします。
5. **リンクIDの作成**をクリックします。
6. アプリアナリティクスプロバイダーとして**AppsFlyer**を選択します。
7. プラットフォーム（AndroidまたはiOS）を選択します。
8. アプリを見つけて選択します。
9. **リンクIDの作成**をクリックします。

</Accordion>

<Accordion title="ステップ3：Google Adsとの連携設定（必須）">

**（AppsFlyerアカウントのすべてのメンバー）**

1. AppsFlyerのサイドメニューから、［**コラボレーション**］>［**パートナー連携>マーケットプレイス**］タブを選択します。
2. **Google Ads**を検索して選択します。
3. ［**連携**］をクリックします。連携の設定画面に移動します。
4. **連携**タブで、**パートナーを有効化**トグルをオンにします。  
   **注意：** このパートナーとの連携中は、トグルをオン（<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">有効</Anchor>）のままにしておく必要があります<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">。</Anchor>
5. 前の手順でコピーした**リンクID**を貼り付けます。
6. ［<Anchor target="_blank" href="/marketers/ja/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**EU域外のユーザー**</Anchor>］をオンにするかどうかを決めます。

   <Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="557px" />
7. ［**高度なデータ共有**］をオン**またはオフ**にします。オンの場合、広告識別子（IDFAまたはGoogle AdsID）を利用できないデバイスも含め、すべてのデバイスについて、デバイスレベルの識別子を含むポストバックとイベントがGoogle Adsに送信されます。

   さらに、［**高度なデータ共有**］がオンの場合、AppsFlyerはこれらのイベントの成果を計測します。オフの場合は、IDFAがあるデバイスのポストバックとイベントのみが送信され、成果として計測されます。
8. **インストール計測**の設定：
   1. **インストール：クリックスルールックバック期間**を設定します。  
      ルックバック期間の単位（時間または日）を選択し、スライダーを希望の値に設定します。 Google Adsに合わせて、ルックバック期間を30日に設定することをお勧めします。
   2. [オプション] Androidアプリで事前登録キャンペーンを行う場合は、**事前登録キャンペーンのルックバック期間**を設定します（デフォルトは90日です）。このスライダーは、インストールを事前登録キャンペーンに紐付ける際のルックバック期間を決定します。
   3. **インストール：ビュースルー計測**を有効にします。
   4. ルックバック期間の単位（時間または日）を選択し、スライダーを希望の値に設定します。ビュースルールックバック期間はGoogle Adsに合わせて1日に設定することをお勧めします。  
      **注意：** GoogleはiOSアプリのインプレッションに基づく成果の主張を送信しません。インストールのビュースルー計測のトグルとルックバック期間スライダーは、iOSアプリには無効です。

      ![](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)
9. 新規連携では、［**再インストールの計測**］トグルがデフォルトでオンになっています。再インストールの計測では、リアトリビューション期間中にアプリを再インストールしたユーザーを計測できます。

   再インストールの計測にはインストール計測の設定値が使用されるため、ルックバック期間を個別に設定する必要はありません。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls">再インストールの計測</Anchor>を参照してください。

   > 🚧 **重要！**
   >
   > 再インストールのコンバージョンデータは、Google Ads管理画面では**session\_startとして表示されます**。 AppsFlyerでは、リアトリビューションとして計測・表示されます。

10. ［**リエンゲージメントの計測**］の設定：
    1. <Anchor target="_blank" href="/marketers/ja/docs/app-settings#reengagement-attribution">アプリ設定画面でリターゲティングを有効に設定</Anchor>します。
    2. Google Adsの連携設定で、リエンゲージメントの計測を有効にします。
    3. ［**リエンゲージメント：クリックスルールックバック期間**］を設定します。これは広告クリックからの期間で、クリックをリエンゲージメントとして計測するには、この期間内にアプリが起動される必要があります。時間または日数でルックバック期間を選択し、スライダーを希望の値に設定します。
    4. **リエンゲージメント：ビュースルー計測**トグルを有効にします。  
       **注意：** GoogleはiOSアプリのインプレッションに基づく成果の主張を送信しません。リエンゲージメントのビュースルー計測トグルとルックバック期間スライダーは、iOSアプリには適用されません。
    5. ［**リエンゲージメント：ビュースルールックバック期間**］を設定します。これは広告表示からの期間で、インプレッションをリエンゲージメントとして計測するには、この期間内にアプリが起動される必要があります。時間または日数でルックバック期間を選択し、スライダーを希望の値に設定します。
    6. **リエンゲージメント期間**を設定します。これは、クリックまたはインプレッション後にユーザーのアプリ内イベントがリターゲティングメディアソースにアトリビューションされる期間です。値は日数（1-90）、時間（最大23）、またはライフタイムで設定できます。デフォルトは30日です。

       ![](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)
11. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2402582?hl=en">Google AdsのiOSアプリアセット</Anchor>（旧称：アプリ表示オプション）を使用している場合：  
    広告リンク経由の成果を計測するには、［<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">**計測リンク**</Anchor>］タブでAppsFlyerの単一プラットフォーム向け計測リンクを作成し、Google Adsのアプリアセットに挿入します。  
    **注意：** 静的なキャンペーン名を必ず追加してください（必須）。

    ![](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)
12. **コスト**タブに移動します。
13. ［**コスト、クリック、インプレッションデータを取得**］をオンにします。
14. **Google Adsを接続**ボタンをクリックして、Googleアカウントにログインし、AppsFlyerですべてのGoogle Adsのキャンペーンコストを取得します。 <Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-cost-and-ad-revenue">詳細はこちら</Anchor>
15. **保存**をクリックします。

> ❗️ **ストップ！**
>
> * Google AdsでのインストールとリエンゲージメントのAppsFlyer計測を表示するには、次のAppsFlyerイベントをインポートしてください。
>   * 「First open」（インストール用）
>   * 「Session start」（リエンゲージメント用）
> * AppsFlyerでGoogle Adsのインストールを確認するには、必ず[ステップ4](#h_01HACTC1H5GV04KFM29NCCK8J2)を実施してください。アプリ内イベントをGoogle Adsにマッピングする場合は、先に[ステップ5](#h_01HACTC1H50DDS3WCZ9DCHKN0P)を実施してください。

</Accordion>

<Accordion title="ステップ4：アプリコンバージョンのインポート（必須）">

> 🚧 **重要！**
>
> 新しいコンバージョンをGoogle Adsで登録するには、アプリを起動してマッピングされたアプリ内イベントを**少なくとも1回実行する必要があります**。 iOSアプリをテストするには、イベントを確認するためにIDFAを収集する必要があります。イベントコンバージョンがキューに追加されるまで、最大6時間かかる場合があります。一度追加されるとインポート可能になり、新しいコンバージョンのステータスは「最近のコンバージョンなし」から「コンバージョン記録中」に変わります。

このステップでは、リンクIDを作成するためにアカウントへの**Google管理者アクセス**が必要です。

<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7382633?sjid=11699141105296914680-EU">Google Adsヘルプドキュメント</Anchor>に記載されている手順に従ってください。以下の点に注意してください：

* すべてのアプリの**first\_open**イベントをコンバージョンイベントとして設定してください。 （インストール計測に必須です）
* Googleでリエンゲージメントを計測する場合は、**session\_start**のイベントをコンバージョンイベントとして設定してください。
* Googleで計測したい各アプリ内イベントについてこのプロセスを繰り返してください。

  > 📘 **注意**
  >
  > Google Adsのパートナーイベント識別子が変更されたり、CUSTOMとラベル付けされている場合に、対応するイベント名がAppsFlyerで変更された場合はデータを再インポートする必要があります。

* プロセスが完了した後、**コンバージョン** > **概要**ページでサードパーティのコンバージョンイベントを確認することができます。イベントがリストに表示されない場合や、Google Adsのコンバージョンリストから削除された場合
  1. **すべてのコンバージョンアクションを表示**をクリックしてください。［**ステータス**］フィルタが表示されます。
  2. **ステータス**をクリックし、**すべて**を選択することで、無効または削除されたイベントを含むすべてのイベントを表示することができます。
* 「コンバージョンに含む」設定が、Google Adsのキャンペーン目標と一致していることを確認してください。詳細については、Google担当者にお問い合わせになるか、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">こちら</Anchor>のGoogleドキュメントをご覧ください。

おめでとうございます！これで、AppsFlyerを使ってGoogle Adsのモバイルキャンペーンを計測できるようになりました！

</Accordion>

<Accordion title="ステップ5：アプリ内イベントのマッピング（推奨）">

**（AppsFlyerアカウントに所属するすべてのメンバー）**

![In-app_event_postbacks_en-us.png](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)

1. **連携**タブに移動し、**アプリ内イベントポストバック**セクションまでスクロールしてください。

   > 📘 **注意**
   >
   > アプリでGoogle Adsのアプリ内イベントマッピングを**初めて有効にする場合**：
   >
   > * **af\_app\_opened**イベントは自動的に**session\_start**にマッピング・設定されます（定義されていない場合は手動で追加します）。
   > * Google Adsがこれらのイベントを受信できるよう、イベントごとに［**送信対象ユーザー**］で［**オーガニックを含むすべてのメディアソース**］を選択する必要があります。連携が正常に設定された後は、どんなイベントでもこの選択を変更できるようになります。

2. **アプリ内イベントポストバック**をオンにします。
3. ［**イベントを追加**］をクリックして、SDKイベントまたはサーバー間イベントをリストに追加します。
4. 次のパラメータを入力してください：

| パラメータ名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>非オーガニックインストールのデバイスでイベントを発生させ、再度確認してください。</li><li>［**AppsFlyerイベント**］にイベント名を入力し、［**カスタムイベントを作成**］をクリックします。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor></li></ul> |
| **パートナー側のイベント名** | Google Adsで定義されている各イベントの一意の名前またはID。ドロップダウンから、事前定義済みのAppsFlyerイベントのうち最も適したものを選択します。 |
| **送信対象ユーザー** | イベントの送信オプションを選択してください：<ul><li>**このパートナーのみ：** このイベントがGoogle Adsに紐づく場合のみポストバックを送信します。</li><li>**オーガニックを含むすべてのメディアソース**：すべてのパートナーに紐づくイベントとオーガニックイベントのポストバックを送信します。</li></ul> |
| **送信するデータ** | <ul><li>**付随データなし（デフォルト）**：イベントの値を含まず、イベント自体のみを送信します。</li><li>**イベント値と収益**：**収益の額を含む**（存在する場合）、すべてのイベント値を送信します。</li><li>**イベント値のみ：収益値を除いた**すべてのパラメータを送信します。</li></ul> |

5. **連携を保存**をクリックします。
6. 連携を保存した後、設定ページにいる間に、さらに多くのアプリをパートナーと連携することができます。
   1. 左上のパートナー名の下にあるアプリ名をクリックし、アプリリストを開きます。
   2. ドロップダウンリストから別のアプリを選択してください。
   3. 選択したアプリで、連携ステップを再度実施してください。

</Accordion>

> 👍 **ヒント**
>
> Google AdsAPI連携には、Google Adsのリマーケティング機能が自動的に含まれています。この連携を完了し、イベントをGoogle Adsに送信することで、追加の連携なしでGoogle Adsでリマーケティングオーディエンスリストを作成することが可能です。

## Google Adsのチームメンバーへの権限付与

Google Adsに、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アカウントの特定のデータにアクセスするための権限</Anchor>を付与できます。これは、Google Adsの連携設定画面で、各アプリの [権限] タブから行うことができます。

これらの権限を取得しアプリにアクセスするためには、Google Ads担当者がAppsFlyerのGoogle Adsパートナーアカウントのチームメンバーである必要があります。

Googleのプライバシー要件により、Googleは広告主から明示的にリクエストされた場合にのみ、AppsFlyerパートナーアカウントに新しいチームメンバーを追加することができます。

Google Adsチームメンバーにアプリへのアクセスを許可するには、次の手順に従ってください：

1. アカウントマネージャーをAppsFlyerのGoogleパートナーアカウントに追加するようリクエストするには、<Anchor target="_blank" href="https://docs.google.com/forms/d/e/1FAIpQLSfJmwEPxy4bXw0mEsKfJ3D5dZmRZgHS3LCiyoEFsZRos0jWIQ/viewform">このフォーム</Anchor>に記入し提出してください。
2. GAアカウントマネージャーが追加されたことをGoogle Adsから確認されるまでお待ちください。
3. ［**設定**］>［**アクティブな連携**］>［**Google Ads**］>［**権限**］に移動し、担当アカウントマネージャーのメールアドレスをチームメンバーのリストに追加します。
4. Google Adsアカウントマネージャーに付与したい権限を有効にします。

詳細：<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークへの権限付与</Anchor>

## 代理店向けGoogle Ads計測の有効化

AppsFlyerは、Google Adsを使用した代理店連携をサポートしています。 AppsFlyerがデータを正しく計測するためには、広告主と代理店が別々のGoogle Adsアカウントを持っていることが重要です。詳細：<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-agencies">こちら</Anchor>

## 複数のGoogle Adsアカウントでの運用

AppsFlyerは、同一のアプリで複数のGoogle Adsアカウントを利用することを可能にしています。これを実現するには、Google AdsでリンクIDを共有し、各Google Adsアカウントにイベントをインポートします。

参照：<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001">Google AdsリンクIDの共有方法についての詳細</Anchor>

## iOSアプリキャンペーン

**注意**：このセクションはインストール向けアプリキャンペーンに適用され、エンゲージメント向けアプリキャンペーンには適用され**ません**。

2021年1月27日に、Googleは<Anchor target="_blank" href="https://blog.google/products/ads-commerce/preparing-developers-and-advertisers-for-policy-updates/">iOS 14のリリースに対応するためのポリシー更新</Anchor>を発表しました。

ATTの施行が開始されて以来、GoogleのiOSアプリはATTを要求しないため、ATTプロンプトをサポートするYouTubeアプリを除き、Google Ads製品はATTに該当するデバイス識別子（IDFA）の使用を<Anchor target="_blank" href="https://support.google.com/google-ads/answer/10417364">停止しました</Anchor>。

Googleは、レポートとキャンペーンの最適化を維持するために、iOS 14+のトラフィックにおいてモデル化されたコンバージョンを拡大しました。

モデル化されたコンバージョンはデバイスIDに依存しないため、iOS 14.5のリリース以降、Googleが採用しているiOSインストールアプリキャンペーンのインベントリロジックは次の通りです：

* iOSのACIの検索面の成果はデバイスIDによって計測されません。これはGoogleの2020年1月24日のポリシーに依るものです。
* iOSのACIのディスプレイ面は、デバイスIDがあり、広告主アプリとパブリッシャーアプリの両方でユーザーの同意が得られている場合に、成果を計測できます。
* なお、いずれのiOS ACIキャンペーンもICM連携を利用することで成果を計測可能です。これは、広告主アプリ、パブリッシャーアプリ、またはその両方でデバイスIDが利用できない場合に適用されます。
* Googleは現在、iOSではクリックスルーのみの成果を主張しています。インプレッションの場合には成果を主張しません。

## アプリキャンペーンでのディファードディープリンクの使用

**ディープリンクとは何ですか？どのように機能しますか？**

潜在的なユーザーがフィードをクリックすると、アプリのページにリダイレクトされます。ユーザーがアプリをインストールして起動すると、SDKはディファードディープリンクを使用して特定の製品の詳細（例：運動用シューズ）を提供します。アプリ開発者はこのデータを活用し、アプリ内で個々のユーザーに適切な体験を提供します。

**Googleでのディファードディープリンク**

<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9959794?hl=en&ref_topic=10011599">アプリキャンペーンのGoogleフィード</Anchor>または<Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">広告グループのディファードディープリンク</Anchor>を利用すると、新しいモバイルユーザー向けにスムーズでコンテンツ固有の体験を提供できます。 Googleでは、フィードと広告グループのいずれにもディープリンクを設定できます。AppsFlyerは、どちらの場合もディファードディープリンクに対応しています。

**Google Adsでディファードディープリンクを有効にするには：**

1. AppsFlyer SDKで`af_dp`パラメータを受信するには、必ず<Anchor target="_blank" href="/marketers/ja/docs/conversion-data-payloads-and-scenarios#ディファードディープリンクを使用したリアトリビューション">GCD</Anchor>を使用してください。
2. Googleで、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9958973?hl=en&ref_topic=10011599">フィードを設定</Anchor>するか、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">広告グループレベルのディファードディープリンクを設定</Anchor>してください。
3. AppsFlyerで、［**設定**］>［**アクティブな連携**］に移動します。 <strong>Google Ads（Adwords）</strong>を選択します。
4. **連携**タブで、**Google Adsのディファードディープリンク**を有効にします。
5. **連携を保存**をクリックします。

## Google Adsのパラメータマッピング

次の表は、Google AdsとAppsFlyer間のパラメータのマッピングを示しています。広告主はGoogle Adsキャンペーンにパーソナライズされたパラメータを追加できないことに注意してください。

| **ネットワークタイプ** | **検索** | **ディスプレイ** | **YouTube** |
| --- | --- | --- | --- |
| チャネル（`af_channel`） | 以下の表を参照し、[`Channel`パラメータの入力方法](/docs/google-ads-adwords-integration-setup-for-advertisers#google-adsのパラメータマッピング)をご確認ください。 |  |  |
| キャンペーン（`c`） | はい | はい | はい |
| キャンペーンID（`af_c_id`） | はい | はい | はい |
| 広告セット（`af_adset`）  <br />`ad_group_name`パラメータの値が設定されます。  <br />このパラメータがnullの場合、AppsFlyerは`af_adset`に`ad_group_id`の値を設定します。 | はい | はい | はい |
| 広告セットID（`af_adset_id`）：Googleの`ad_group_id`パラメータの値が設定されます。 | はい | はい | はい |
| 広告（`af_ad`）。 | N/A | N/A | N/A |
| 広告ID（`af_ad_id`）  <br />Googleの`creative_id`パラメータの値が設定されます。 | はい | はい | はい |
| 広告タイプ（`af_ad_type`） | はい* | はい* | はい* |
| サイトID（`af_siteid`） | GoogleSearch/  <br />SearchPartners | N/A | YouTubeVideos/  <br />VideoPartners |
| キーワード | N/A | N/A | N/A |

`Channel`パラメータを設定する方法

Google Adsは`Channel(af_channel)`パラメータを送信しません。 AppsFlyerは、以下のルールに基づいてGoogle Adsから受信したキャンペーンタイプに対してこのパラメータをどのように設定するかを決定します。

<table><thead><tr><th colspan="2">キャンペーン タイプ<strong>および</strong>ネットワークタイプのロジック：</th><th rowspan="2"> <kbd>Channel</kbd>パラメータ</th><th rowspan="2">例</th></tr><tr><th>campaign_type</th><th>network_type</th></tr></thead><tbody><tr><td> <kbd>ACI</kbd>、<kbd>ACE</kbd>、<kbd>ACPRE</kbd>、<kbd>Shopping</kbd>、または<kbd>Hotel</kbd> </td><td>すべてのネットワークタイプ</td><td><kbd>campaign_type_network_type</kbd></td><td>channel = <kbd>ACI_Search</kbd> </td></tr><tr><td><p><strong>次ではない：</strong></p><p><kbd>ACI</kbd>、<kbd>ACE</kbd>、<kbd>ACPRE</kbd>、<kbd>Shopping</kbd>、または<kbd>Hotel</kbd></p></td><td><kbd>Display</kbd></td><td><kbd>network_subtype</kbd></td><td>channel = <kbd>mGDN</kbd> </td></tr><tr><td><p><strong>次ではない：</strong></p><p><kbd>ACI</kbd>、<kbd>ACE</kbd>、<kbd>ACPRE</kbd>、<kbd>Shopping</kbd>、または<kbd>Hotel</kbd></p></td><td><p><strong>次ではない：</strong></p><p><kbd>Display</kbd></p></td><td><kbd>network_type</kbd></td><td>channel = <kbd>Search</kbd> </td></tr></tbody></table>

Googleのレスポンスで利用可能な広告タイプの詳細については、<Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">こちら</Anchor>をご覧ください。

> 📘 **注意**
>
> Googleが確率的アトリビューション（ICM）を通じてインストールに成果を紐づける際、Googleは`network_type`をAppsFlyerと共有しません。その結果、ネットワークタイプが欠落しており、チャネル値は`ACI_`（末尾の値なし）になります。

### キャンペーンタイプ： アプリキャンペーン

#### Google Adsによるキャンペーン名の変更

| 2021年2月15日以前 | 2021年2月23日以降 |
| --- | --- |
| UAC | ACI |
| UACE | ACE |
| UACPre | ACPRE |

**注意：** キャンペーン名のタイプは、インストール日ではなく、クリック日またはインプレッション日に基づいて設定されます。

### ローデータレポートのEngaged viewパラメータ

Engaged viewとは、ユーザーが動画広告を10秒より長く視聴したインプレッションです。クリックと同じアトリビューション優先度があります。  Androidでは、`engaged_view`はローデータレポートで、`Engagement Type` および `Sub Param 5`パラメータに反映されます。   
Engaged viewは、AppsFlyerで設定されたクリックのルックバック期間内に発生した場合にカウントされます。ただし、上限は3日です。

> 🚧 **重要！**
>
> * GoogleはSRN（Self-Reporting Network）です。これらのネットワークにおける計測フローの仕組みの詳細については、<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">こちら</Anchor>をクリックしてください。
> * AppsFlyerは、Googleが提供するすべてのキャンペーン情報を提示できます。キャンペーンタイプ（検索、動画、ディスプレイ）と関連情報はGoogleによって決定されます。詳細については、<Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">こちら</Anchor>をクリックしてください。

## 複数の商品を含むアプリ内イベントのGoogle Adsへの送信

複数の商品を含む複雑なアプリ内イベントをGoogle Adsに送信するには、新しい`af_order_info`イベントオブジェクトの使用を推奨します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/item-level-order-data-for-ad-networks-af-order-info">アドネットワーク向けの商品単位の注文データ（af\_order\_info）</Anchor>を参照してください。

## デバイスIDのないコンバージョンに向けたGoogle Adsキャンペーンの最適化

iOS 14.5以降およびAndroid 12以降、Google Adsに複数の識別子が導入されました。これらの識別子は、デバイスIDを使用しないコンバージョンの決定論的な成果計測に使用されます。

| 識別子 | 利用可能日 | ソース | オペレーティングシステム | 用途 | データの粒度 |
| --- | --- | --- | --- | --- | --- |
| gclid | 2021年12月 | Google Playリファラ | Android | インストール / 再インストール | ユーザーレベル |
| gclid | 2021年12月 | ディープリンクURL | Android + iOS | リエンゲージメント | ユーザーレベル |
| gbraid | 2021年3月 | ディープリンクURL | iOS | リエンゲージメント | 集計 |
| odm\_info | 2025年11月 | AppsFlyer SDK / S2S | iOS | インストール / 再インストール | 集計 |

Google AdsとAppsFlyerでは、デバイスIDのないトラフィックについても、リエンゲージメント、インストール、リアトリビューションのキャンペーンレベルのデータを取得できます。ただし、広告セットおよび広告レベルのデータはGoogleによって共有されません。  
**これらのパラメータを受信するための設定変更は、広告主側で特に必要ありません。**

### オペレーティングシステム別のデータの可視性

**Androidアプリ：**

AppsFlyerとGoogle Adsで、広告主はデバイスIDなしのトラフィックにおけるインストールおよびリエンゲージメントの完全なキャンペーンデータを受け取ることができます。

**iOSアプリ：**

Google AdsとAppsFlyerで、広告主はリエンゲージメントアクティビティのトラフィックにおいて、デバイスIDなしの完全なキャンペーンデータを受け取ることができます。

## Firebase SDKを実装せずに広告を配信する場合

Firebase SDKを実装せずにGoogle Adsで広告を配信する場合、以下の制限が適用されます。

| 制限事項 | 詳細 |
| --- | --- |
| tROASには非対応 | tROAS（目標広告費用対効果）による最適化は、Firebase SDKの収益イベントを使用する場合にのみ利用できます。 AppsFlyerやその他すべてのMMPの収益イベントは、この最適化の対象にはなりません。 |
| オーディエンスの除外には非対応 | アプリキャンペーンでユーザーを除外できるのは、MMPのイベントではなく、Firebase SDKのイベントに基づいてキャンペーンを最適化している場合に限られます。 |

## Googleの確率論的モデリングによる成果計測（ICM）の機能と制限事項

| 制限事項 | 詳細 |
| --- | --- |
| 計測範囲 | **インストールとリアトリビューションのみ**に対応しており、リエンゲージメントには対応して**いません**。 |
| 成果の主張に含まれるデータ | 通常、Googleによる成果の主張には、以下が含まれます。<ul><li>**キャンペーン名**</li><li>**キャンペーンID**</li><li>**広告グループ（広告セット）名**</li><li>**広告グループ（広告セット）ID**</li></ul>**広告の情報**は含まれません。 |
| チャネルフィールド | ネットワークタイプとサブタイプは提供されません; **チャネル**フィールドには部分的な値が含まれます： `ACI_`  <br />「チャネル」ロジックに関する詳細は、[`Channel`パラメータの表示ロジック](/docs/google-ads-adwords-integration-setup-for-advertisers#google-adsのパラメータマッピング)を参照してください。 |
| iOS ODMで計測をサポートしている地域 | EU、英国、スイスでは**サポートされていません**。 |
| 高プライバシー一括設定（AAP） | iOSのアプリ設定画面で<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor>（高プライバシー一括設定）トグルが**オン**に設定されている場合、Googleによってアトリビューションされたデータはローデータレポートでrestrictedとして表示されます。 Googleの非同意データを表示するには、AAPトグルが**オフ**であることを確認してください。 |
| 広告接触時間（Attributed touch time） | Googleの確率論的モデリングに基づく成果の主張のタイムスタンプは、15分間隔（00:00、00:15、00:30など）に丸められます。 |
| IPマスキング | IPマスキングを使用すると、ICMのパフォーマンスに影響する可能性があります。 Google Adsの計測とパフォーマンスに影響する可能性があるため、GoogleはIPマスキングの無効化を推奨しています。<Anchor target="_blank" href="/marketers/ja/docs/apply-ip-masking-to-user-data#ipマスキング">ユーザーデータへのIPマスキングの適用</Anchor>を参照してください。 |
| IDFV | ICMのパフォーマンスを最大限に高めるため、Googleは、取得可能な場合には、インストール、アプリ起動、アプリ内イベントとともに<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#idfv">IDFV</Anchor>を送信することを求めています。 |

<span id="h_01HDP0SBEE75MAT4A4S9E7Y7FF"></span>**関連記事：**

* iOS 14関連の考慮事項については、<Anchor target="_blank" href="/marketers/ja/docs/get-skan-postback-data-from-google-ads">Google AdsにおけるSKAdNetworkとAppsFlyerの相互運用性</Anchor>をご参照ください。

<div data-zendesk-anchors="google-icm-attribution-flow-with-advanced-data-sharing=%E9%AB%98%E5%BA%A6%E3%81%AA%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9Fgoogle-ads%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%95%E3%83%AD%E3%83%BC h_01K0VKGRK7XXC4GNF6B9X76M4T=%E9%AB%98%E5%BA%A6%E3%81%AA%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9Fgoogle-ads%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%95%E3%83%AD%E3%83%BC configuring-google-ads-attribution-for-advertisers=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%90%91%E3%81%91%E3%81%AEgoogle-ads%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HACTC1H5MANBCRWYQPNW5CC2=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%90%91%E3%81%91%E3%81%AEgoogle-ads%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HACTC1H5R995RXYRFQBFHRF1=%E9%87%8D%E8%A6%81 h_01HACTC1H5EFJKV6AXNSTNFZA4=%E3%82%B9%E3%83%88%E3%83%83%E3%83%97 h_01HSX7TJC7PQ0ATM1J86Z4HMYJ=%E9%87%8D%E8%A6%81-1 h_01KA6S8V6CKRATXHZQZ4YN7V9R=%E6%B3%A8%E6%84%8F h_01HACTC1H58WHJDBN2DRQAZKGB=%E6%B3%A8%E6%84%8F-1 h_01HACTC1H5Z3XXS1MGBS4WYJBV=%E3%83%92%E3%83%B3%E3%83%88 granting-permissions-to-google-ads-team-members=google-ads%E3%81%AE%E3%83%81%E3%83%BC%E3%83%A0%E3%83%A1%E3%83%B3%E3%83%90%E3%83%BC%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E h_01HACTC1H5PAY95M4H1A6WTSEF=google-ads%E3%81%AE%E3%83%81%E3%83%BC%E3%83%A0%E3%83%A1%E3%83%B3%E3%83%90%E3%83%BC%E3%81%B8%E3%81%AE%E6%A8%A9%E9%99%90%E4%BB%98%E4%B8%8E enabling-google-ads-attribution-for-agencies=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91google-ads%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HACTC1H5QE93EAYYVVDQV2WC=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91google-ads%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 running-with-multiple-google-ads-accounts=%E8%A4%87%E6%95%B0%E3%81%AEgoogle-ads%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%A7%E3%81%AE%E9%81%8B%E7%94%A8 h_01HACTC1H5Z8B15RHQ75HVV2RP=%E8%A4%87%E6%95%B0%E3%81%AEgoogle-ads%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%A7%E3%81%AE%E9%81%8B%E7%94%A8 ios-app-campaigns=ios%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_01HACTC1H5X567H6A8M3FWCTAN=ios%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 using-deferred-deep-linking-in-app-campaigns=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%A7%E3%81%AE%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E4%BD%BF%E7%94%A8 h_01HACTC1H57HJZNAGDKSQD6MVC=%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%A7%E3%81%AE%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E4%BD%BF%E7%94%A8 google-ads-parameter-mapping=google-ads%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01HACTC1H6P1A2E160Z6GAGZZS=google-ads%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 how-to-populate-the-channel-parameter=google-ads%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01HACTC1H6TPTDDFSMPQ9YVMDY=google-ads%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01KEYE1W4VJYXYHY4FP1KN3SP9=%E6%B3%A8%E6%84%8F-2 campaign-type-app-campaigns=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%82%BF%E3%82%A4%E3%83%97-%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_01HACTC1H6CEGD2E3HXHWFWBRB=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%82%BF%E3%82%A4%E3%83%97-%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 changes-to-campaign-names-by-google-ads=google-ads%E3%81%AB%E3%82%88%E3%82%8B%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E5%90%8D%E3%81%AE%E5%A4%89%E6%9B%B4 h_01HACTC1H6A028HKVXJ66MCF6M=google-ads%E3%81%AB%E3%82%88%E3%82%8B%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E5%90%8D%E3%81%AE%E5%A4%89%E6%9B%B4 engaged-view-parameter-in-raw-data-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AEengaged-view%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HACTC1H6Q6WCTK4Z9RGV6PA4=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AEengaged-view%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HACTC1H62HC36C08ZBFZ05XS=%E9%87%8D%E8%A6%81-2 h_01M20SN9DCHRQP8TD5Q2Z00CWQ=%E8%A4%87%E6%95%B0%E3%81%AE%E5%95%86%E5%93%81%E3%82%92%E5%90%AB%E3%82%80%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AEgoogle-ads%E3%81%B8%E3%81%AE%E9%80%81%E4%BF%A1 optimize-google-ads-campaigns-for-conversions-without-device-id=%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9id%E3%81%AE%E3%81%AA%E3%81%84%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%AB%E5%90%91%E3%81%91%E3%81%9Fgoogle-ads%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E6%9C%80%E9%81%A9%E5%8C%96 h_01HACTC1H6EFDVN9N89Y17HDFR=%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9id%E3%81%AE%E3%81%AA%E3%81%84%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%AB%E5%90%91%E3%81%91%E3%81%9Fgoogle-ads%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E6%9C%80%E9%81%A9%E5%8C%96 data-visibility-by-operating-system=%E3%82%AA%E3%83%9A%E3%83%AC%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%B7%E3%82%B9%E3%83%86%E3%83%A0%E5%88%A5%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E8%A6%96%E6%80%A7 h_01HACTC1H6WZNMVJK479M5KJYF=%E3%82%AA%E3%83%9A%E3%83%AC%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%B7%E3%82%B9%E3%83%86%E3%83%A0%E5%88%A5%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E8%A6%96%E6%80%A7 h_01_advertising-without-firebase-sdk=firebase-sdk%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%9B%E3%81%9A%E3%81%AB%E5%BA%83%E5%91%8A%E3%82%92%E9%85%8D%E4%BF%A1%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 advertising-without-the-firebase-sdk=firebase-sdk%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%9B%E3%81%9A%E3%81%AB%E5%BA%83%E5%91%8A%E3%82%92%E9%85%8D%E4%BF%A1%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 google-icm-traits-and-limitations=google%E3%81%AE%E7%A2%BA%E7%8E%87%E8%AB%96%E7%9A%84%E3%83%A2%E3%83%87%E3%83%AA%E3%83%B3%E3%82%B0%E3%81%AB%E3%82%88%E3%82%8B%E6%88%90%E6%9E%9C%E8%A8%88%E6%B8%ACicm%E3%81%AE%E6%A9%9F%E8%83%BD%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01K0XMCXSS5MKY90DZWJTNVBBS=google%E3%81%AE%E7%A2%BA%E7%8E%87%E8%AB%96%E7%9A%84%E3%83%A2%E3%83%87%E3%83%AA%E3%83%B3%E3%82%B0%E3%81%AB%E3%82%88%E3%82%8B%E6%88%90%E6%9E%9C%E8%A8%88%E6%B8%ACicm%E3%81%AE%E6%A9%9F%E8%83%BD%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
