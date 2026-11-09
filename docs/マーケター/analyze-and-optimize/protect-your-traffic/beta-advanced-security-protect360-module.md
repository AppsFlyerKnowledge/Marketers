---
title: ［Beta機能］Protect360｜Advanced Security Module
metadata:
  keywords:
    - Beta feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-09-17T15:23:22Z'
  edited_at: '2026-10-28T08:58:12Z'
  id: 39145848948625
  locale: ja
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ja/articles/39145848948625
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **概要：** Advanced Security Module（高度なセキュリティ機能）で、Androidアプリの不正対策を強化できます。この機能は、インストールのアトリビューションが行われる前に、アトリビューション偽装や改ざんされたトラフィックをリアルタイムで検知・ブロックします。トラフィック量の多いアプリやProtect360の利用者、特にアフィリエイトと連携している利用者向けに設計されています。モジュールの設定は、すべてお客様自身で行えます。初期設定や継続的な保守を通じて、変化する不正の傾向に対応し、データの正確性を保てます。

<div id="important" />

> 🚧 **重要！**
>
> Advanced Security Moduleのベータ版は、Protect360をご利用のすべてのお客様が利用できます。利用を希望する場合は、担当のカスタマーサクセスマネージャー（CSM）にお問い合わせください。

<div id="what-is-sdk-spoofing" />

## SDKスプーフィングとは

SDKスプーフィング（SDKからの通信を装う不正）は、実際のデバイスにアプリをインストールしたり起動したりせずに、偽のインストールやアプリ内イベントのリクエストをAppsFlyerサーバーに直接送信する、高度な不正手法です。アプリのSDK自体に不正侵入や改ざんが行われるわけではありません。実際のアプリが送信するネットワークリクエストを不正行為者が模倣し、正当なアクティビティに見せかけます。

広告主にとってSDKスプーフィングは、実際には発生していないインストールやエンゲージメントの計上、インストール数の水増し、AppsFlyerとアプリストアの数値の不一致、広告費の無駄につながるおそれがあります。

<div id="about-the-advanced-security-module" />

## Advanced Security Moduleの概要

**Advanced Security Module**は、AppsFlyerのProtect360に追加できる機能です。Androidにおける高度なアトリビューション偽装を検知し、防止するために設計されています。アプリの初回起動後、アトリビューションが行われる前にインストールに関するアクティビティを評価し、不審なトラフィックを特定します。これにより、不正インストールが成果指標に影響するのを防ぎます。

この機能は、アプリストアのデータとAppsFlyerのアトリビューションデータに不一致があるアプリや、アフィリエイト経由のトラフィックを扱うアプリに特に有効です。これらは、インストール不正を示す代表的な2つの兆候です。

**仕組み**

モジュールは、SDKが記録するアプリの初回起動後、インストールのアトリビューションが行われる前に動作します。 Advanced Security Moduleの利用には、Android SDK v6.15.2以降が必要です。

<div id="prerequisites" />

## 事前準備

設定を始める前に、次のものが揃っていることを確認してください。

* アプリに実装された**Android SDK v6.15.2以降**。
* **API V2トークン**：開発者がSecurity Moduleの依存ライブラリを組み込む際に、Mavenリポジトリでの認証に必要です。取得・生成方法については、<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#api-v2トークンの用途">AppsFlyerトークンの管理</Anchor>を参照してください。
* アプリの署名に使用するすべての証明書（デバッグ用・リリース用）の**証明書ハッシュ値（SHA-256）**。 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint">SHA256フィンガープリントの生成</Anchor>を参照してください。

<div id="important-1" />

> 🚧 **重要！**
>
> アカウントですでにAPI V2トークンの上限である2個に達している場合、新しいトークンをリクエストする必要はありません。この実装には、既存のAPI V2トークンを再利用できます。トークンの割り当てについて不明な点がある場合は、担当CSMにお問い合わせください。
>
> 技術的な実装手順の詳細は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-security-plugin">Androidセキュリティプラグインの開発者向けガイド</Anchor>を参照してください。

<div id="set-the-advanced-security-module" />

## Advanced Security Moduleの設定

Advanced Security Moduleを設定すると、アプリ内のトラフィックが署名済みのアプリビルドから送信されていることを検証し、偽装されたトラフィックを検知できます。必要に応じて、ブロックすることも可能です。

<Accordion title="Advanced Security Moduleの設定手順">

<div id="step-1-open-and-select-an-app" />

#### **ステップ1：設定画面を開き、アプリを選択**

1. AppsFlyerで<strong>［設定］＞［Protect360］＞［Advanced Security Module］</strong>に移動します。
2. <strong>［設定を開始（Get Started）］</strong>または<strong>［ビルドを追加（Add build）］</strong>をクリックします。
3. Advanced Security Moduleを実装するアプリを選択します。
4. <strong>［次へ］</strong>をクリックします。

<div id="step-2-add-certificate" />

#### **ステップ2：証明書の追加**

1. 次の項目を入力します。
   1. <span class="af-ol-a"></span>証明書名（Certificate name）
   2. 証明書の値（Certificate Value）
2. <strong>［次へ］</strong>をクリックします。

注意：アプリの署名に使用するすべての[証明書ハッシュ値](https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint)を、開発者に確認してください。 Security Moduleは、これらの証明書を使ってトラフィックが対象アプリから送信されたことを検証するため、該当するハッシュ値をすべて含める必要があります。

<div id="step-3-excluded-app-versions-from-detection" />

#### **ステップ3：検知対象から除外するアプリバージョンの指定**

* Advanced Securityの検知対象から除外するアプリバージョンを追加します。通常は、次のようなバージョンが該当します。
  * Advanced Security Moduleを実装する前にリリースされたバージョン。
  * モジュールを含まないテスト用ビルドや旧ビルド。

<div id="step-4-build-activation" />

#### **ステップ4：ビルドの有効化**

1. <strong>［ビルドを有効化（Activate build）］</strong>をクリックします。
2. ビルドが完了するまでは、<strong>［処理中（In progress）］</strong>の状態になります。完了までに10～15分かかる場合があります。
3. 完了後、ビルドの<strong>［コードをコピー（Copy code）］</strong>ボタンをクリックしてコードをコピーし、アプリのSDKに組み込めるよう開発者に共有します。 0>

<div id="note" />

> 📘 **注意**
>
> ビルド後、検知モードはデフォルトで<strong>［検知のみ（Tagged）］</strong>に設定されます。このモードでは、AppsFlyerは不審なトラフィックにフラグを付けますが、ブロックはしません。セキュリティ機能を組み込んだバージョンが公開されたら、<strong>［ブロック有効（Implemented）］</strong>モードに切り替え、偽装されたトラフィックをブロックします。「検知のみ」と「ブロック有効」の各モードについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/beta-fraud-protection-studio#fpsのモード">FPSのモード</Anchor>を参照してください。

</Accordion>

<Accordion title="設定の保守と更新">

不正の手法は時間とともに変化し、不正行為者が検知の仕組みを解析しようとする場合もあります。定期的に設定を見直すことで、継続して効果を維持できます。

<div id="when-to-update-the-configuration" />

#### **設定を更新するタイミング**

次のような状況が見られた場合は、設定を更新してください。

* 不審なインストールやイベントが検知をすり抜けている
* トラフィックの傾向が変化している
* 新しいアプリバージョンがある、または証明書が変更されている
* 既存の保護機能の効果が低下している

<div id="what-you-can-update" />

#### **更新できる項目**

次の変更が可能です。

* アプリの証明書の追加・更新
* 検知対象から除外するアプリバージョンの変更
* Security Moduleの再ビルド・再配布
* 公開状況に応じた検知モードの調整

<div id="best-practices" />

#### **推奨される運用方法**

* Advanced Securityの分析結果を定期的に確認する
* アプリのリリース前に開発者と連携する
* 署名を変更したら、速やかに証明書を更新する
* 新たな不正手法に対応できるよう、設定を定期的に見直す

</Accordion>

<div id="data-visibility" />

## **データの確認**

Advanced Security Moduleによる検知結果は、次の2か所に表示されます。

* Protect360ダッシュボード
* Fraud Protection Studio

<Accordion title="Protect360ダッシュボード">

Advanced Security Moduleによる検知結果は、<strong>［アトリビューション偽装（Attribution Spoofing）］</strong>セクションで確認できます。

データは、2つのKPIとグラフに分けて表示されます。

**KPI**

* **検知のみモードで検知されたアトリビューション偽装（Tagged attribution spoofing）**：Advanced Security Moduleが「検知のみ」モードで検知したインストール候補の件数です。
* **ブロック有効モードで検知されたアトリビューション偽装（Implemented attribution spoofing）**：Advanced Security Moduleが「ブロック有効」モードで検知し、ブロックしたインストール候補の件数です。

**グラフ**

* **アトリビューション偽装の推移（Attribution spoofing trend）**：Advanced Security Moduleによる検知結果の時系列の変化を示します。このグラフでは、アプリ単位で偽装の検知状況の概要を確認できます。

<Image align="center" alt="" src="https://files.readme.io/2f9e63d283850d3b1150dfcefff3c3cd47383cb58c4194dbbec3296da807fcb9-39145854862353.png" width="624px" />

</Accordion>

<Accordion title="Fraud Protection Studio（FPS）">

Advanced Security Moduleは、Fraud Protection Studioのページで確認できます。

<div id="how-to-access" />

#### アクセス方法

Advanced Security Moduleにアクセスするには、次の手順を実行します。

1. AppsFlyerにログインします。
2. 左側のメニューから、［設定］＞［Protect360］＞［Fraud Protection Studio］に移動します。
3. ページ上部のアプリ選択ドロップダウンで、設定するアプリを選択します。
4. 左側のメニューから、Advanced Security Moduleのカードを選択します。

<div id="the-advanced-security-module-page" />

#### 設定画面：Advanced Security Module

<Image align="center" alt="" src="https://files.readme.io/a94b0c810f719846ae2882cac2ff1dbe4e32f815ee4e023e65e563199f4e3345-39145848945681.png" width="624px" />

Advanced Security Moduleのページは、3つのセクションで構成されています。

<div id="detection-status" />

##### 検知モード（Detection status）

* 検知モードを表示します。「ブロック有効」と「検知のみ」の2つの選択肢があります。デフォルトでは<strong>［検知のみ］</strong>に設定されています。

注意：検知モードを変更するには、担当CSMにお問い合わせください。

<div id="top-app-versions-by-detection-status" />

##### 検知状況別の上位アプリバージョン（Top app versions by detection status）

* グラフには、インストール数が多い上位5つのアプリバージョンが表示されます。
  * 各アプリバージョンは、次の内訳で表示されます。
    * **未検知（Untagged）**：Advanced Security Moduleで検知されなかったインストール候補です。
    * **検知のみ（Tagged）**：Advanced Security Moduleが「検知のみ」モードで検知したインストール候補です。
    * **ブロック済み（Blocked）**：Advanced Security Moduleが「ブロック有効」モードで検知したインストール候補です。ブロックされたインストール候補は、その後の処理に進みません。

<div id="insights" />

##### 分析結果（Insights）

分析結果では、グラフの内訳を理解するための情報を確認できます。分析結果は、次の3種類です。

* **すべてのトラフィックがブロック済み（All traffic is blocked）** ： 100%ブロックされているアプリバージョンは、除外リストに追加されていない可能性があります。担当CSMとアプリバージョンの除外リストを確認し、該当するバージョンの追加を検討してください。
* **すべてのトラフィックを検知（All traffic is tagged）**：100%検知されているアプリバージョンは、除外リストに追加されていない可能性があります。担当CSMとアプリバージョンの除外リストを確認し、該当するバージョンの追加を検討してください。
* **検知のみモードでの検知率が高い（High rate of tagged detections）**：1つ以上のアプリバージョンで、Advanced Security Moduleが「検知のみ」モードで検知した割合が20%を超えています。より高い効果を得るため、担当CSMに連絡し、「ブロック有効」モードに切り替えることを強く推奨します。

</Accordion>

<Accordion title="よくある質問">

<div id="what-is-advanced-security" />

#### Advanced Securityとは何ですか？

Advanced Securityは、AppsFlyerのAndroid SDKに追加できる保護機能です。実際のユーザーがアプリをインストールしたり利用したりしていないにもかかわらず、偽のインストールやイベントが報告される「アトリビューション偽装」を防ぐのに役立ちます。

<div id="what-problem-does-advanced-security-solve" />

#### Advanced Securityは、どのような問題を解決しますか？

Advanced Securityは、偽装によってAppsFlyerに記録される一方、アプリストアやバックエンドシステムには存在しない、架空のインストールやアプリ内のアクティビティを防ぐのに役立ちます。これにより、インストール数の水増し、データの不一致、広告費の無駄を減らせます。

<div id="what-is-attribution-spoofing" />

#### アトリビューション偽装とは何ですか？

アトリビューション偽装は、不正行為者が偽のインストールデータやアプリ内イベントデータを生成し、対象アプリから送信されたように装ってAppsFlyerに送信する不正手法です。実際のアプリのインストールやユーザーの行動は、発生していません。

<div id="how-does-advanced-security-prevent-attribution-spoofing" />

#### Advanced Securityは、アトリビューション偽装をどのように防ぎますか？

Advanced Securityは、各リクエストに固有の検証用署名を追加することで、インストールやアプリ内イベントのデータが対象アプリのSDKから送信されたものであることを検証します。 AppsFlyerはこの署名を確認し、データが正当なものであり、偽装や改ざんが行われていないことを確かめます。

<div id="does-advanced-security-affect-the-app-or-user-experience" />

#### Advanced Securityは、アプリやユーザー体験に影響しますか？

いいえ。 Advanced Securityはバックグラウンドで動作し、ユーザーによるアプリのインストール方法や利用方法を変えることはありません。追加の処理はバックグラウンドで行われるため、ユーザーが意識することはありません。

<div id="who-should-use-advanced-security" />

#### Advanced Securityは、どのようなアプリに適していますか？

非SRNやアフィリエイトネットワークを多く利用するアプリ、アプリストアのインストール数とAppsFlyerのデータに原因不明の差があるアプリ、通常の方法では検知が難しい高度な不正が疑われるアプリに、特に適しています。

<div id="is-advanced-security-available-for-all-platforms" />

#### Advanced Securityは、すべてのプラットフォームで利用できますか？

いいえ。 Advanced Securityは、現在Androidアプリのみを対象としており、Protect360のプレミアム顧客向けに提供されています。また、すべてのAppsFlyerプラグインに対応しています。

<div id="how-do-i-know-advanced-security-is-working" />

#### Advanced Securityが動作しているか、どのように確認できますか？

検知結果は、Protect360ダッシュボードとFraud Protection Studioに表示されます。偽装されたトラフィックの検知・ブロック状況を確認し、その推移を分析できます。

</Accordion>

<div data-zendesk-anchors="h_01K5EBZV8BY54H332WTWEMYVSA=%E9%87%8D%E8%A6%81 what-is-sdk-spoofing=sdk%E3%82%B9%E3%83%97%E3%83%BC%E3%83%95%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A8%E3%81%AF h_01KH8MPFJBSN67PSQXX25NG6ZZ=sdk%E3%82%B9%E3%83%97%E3%83%BC%E3%83%95%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A8%E3%81%AF about-the-advanced-security-module=advanced-security-module%E3%81%AE%E6%A6%82%E8%A6%81 h_01K5C4BCNRE8JWQ9DA20DJ3A07=advanced-security-module%E3%81%AE%E6%A6%82%E8%A6%81 h_01K9PRQNEWSECTION0001AB=%E4%BA%8B%E5%89%8D%E6%BA%96%E5%82%99 prerequisites=%E4%BA%8B%E5%89%8D%E6%BA%96%E5%82%99 h_01K9PRQNEWSECTION0002AB=%E9%87%8D%E8%A6%81-1 set-the-advanced-security-module=advanced-security-module%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KHK6M3CTY4YSCRTSMS707S5Z=advanced-security-module%E3%81%AE%E8%A8%AD%E5%AE%9A step-1-open-and-select-an-app=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E8%A8%AD%E5%AE%9A%E7%94%BB%E9%9D%A2%E3%82%92%E9%96%8B%E3%81%8D%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E9%81%B8%E6%8A%9E h_01KH8XDACWA2C46MEEGFMM6J8M=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E8%A8%AD%E5%AE%9A%E7%94%BB%E9%9D%A2%E3%82%92%E9%96%8B%E3%81%8D%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E9%81%B8%E6%8A%9E step-2-add-certificate=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E8%A8%BC%E6%98%8E%E6%9B%B8%E3%81%AE%E8%BF%BD%E5%8A%A0 h_01KH8XDACYBFZJWHZZCD0JSNGJ=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E8%A8%BC%E6%98%8E%E6%9B%B8%E3%81%AE%E8%BF%BD%E5%8A%A0 step-3-excluded-app-versions-from-detection=%E3%82%B9%E3%83%86%E3%83%83%E3%83%973%E6%A4%9C%E7%9F%A5%E5%AF%BE%E8%B1%A1%E3%81%8B%E3%82%89%E9%99%A4%E5%A4%96%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%AE%E6%8C%87%E5%AE%9A h_01KH8XDAD08E1JJVVSV9GY4RAB=%E3%82%B9%E3%83%86%E3%83%83%E3%83%973%E6%A4%9C%E7%9F%A5%E5%AF%BE%E8%B1%A1%E3%81%8B%E3%82%89%E9%99%A4%E5%A4%96%E3%81%99%E3%82%8B%E3%82%A2%E3%83%97%E3%83%AA%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%AE%E6%8C%87%E5%AE%9A step-4-build-activation=%E3%82%B9%E3%83%86%E3%83%83%E3%83%974%E3%83%93%E3%83%AB%E3%83%89%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01KH8XDAD122D7PWP2367YVNP2=%E3%82%B9%E3%83%86%E3%83%83%E3%83%974%E3%83%93%E3%83%AB%E3%83%89%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01KH8XJXN717M3GDJNPPMWDBHY=%E6%B3%A8%E6%84%8F when-to-update-the-configuration=%E8%A8%AD%E5%AE%9A%E3%82%92%E6%9B%B4%E6%96%B0%E3%81%99%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0 h_01KH8XDAD3M4RARMK7DS7RA08X=%E8%A8%AD%E5%AE%9A%E3%82%92%E6%9B%B4%E6%96%B0%E3%81%99%E3%82%8B%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0 what-you-can-update=%E6%9B%B4%E6%96%B0%E3%81%A7%E3%81%8D%E3%82%8B%E9%A0%85%E7%9B%AE h_01KH8XDAD46P524Z2H8BBZRAR1=%E6%9B%B4%E6%96%B0%E3%81%A7%E3%81%8D%E3%82%8B%E9%A0%85%E7%9B%AE best-practices=%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E9%81%8B%E7%94%A8%E6%96%B9%E6%B3%95 h_01KH8XDAD5PVKNPW37PMG3NKHH=%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E9%81%8B%E7%94%A8%E6%96%B9%E6%B3%95 data-visibility=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01K5C4BCNTBVDQX8DGTGEAN01T=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D how-to-access=%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95 h_01K5C4BCNZBS424A4PMS7AR8XG=%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%96%B9%E6%B3%95 the-advanced-security-module-page=%E8%A8%AD%E5%AE%9A%E7%94%BB%E9%9D%A2advanced-security-module h_01K5C4BCP14ARR3JMDPMRWZPTT=%E8%A8%AD%E5%AE%9A%E7%94%BB%E9%9D%A2advanced-security-module h_01K5C4BVN5CQVP8HJG1MBV72AW=%E6%A4%9C%E7%9F%A5%E3%83%A2%E3%83%BC%E3%83%89detection-status h_01K5C4BVN69SK4TBNWPFPWYXPN=%E6%A4%9C%E7%9F%A5%E7%8A%B6%E6%B3%81%E5%88%A5%E3%81%AE%E4%B8%8A%E4%BD%8D%E3%82%A2%E3%83%97%E3%83%AA%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3top-app-versions-by-detection-status h_01K5C4BVN6XA4SNP4TK9SSRHS9=%E5%88%86%E6%9E%90%E7%B5%90%E6%9E%9Cinsights what-is-advanced-security=advanced-security%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B h_01KH9HERVW7QE2JXCGBBC206VW=advanced-security%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B what-problem-does-advanced-security-solve=advanced-security%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E5%95%8F%E9%A1%8C%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B h_01KH9HERVX8V537KQBSMAR31T8=advanced-security%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E5%95%8F%E9%A1%8C%E3%82%92%E8%A7%A3%E6%B1%BA%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B what-is-attribution-spoofing=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E5%81%BD%E8%A3%85%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B h_01KH9HERVY5G1J5KQV9ZKTHGXX=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E5%81%BD%E8%A3%85%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B how-does-advanced-security-prevent-attribution-spoofing=advanced-security%E3%81%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E5%81%BD%E8%A3%85%E3%82%92%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E9%98%B2%E3%81%8E%E3%81%BE%E3%81%99%E3%81%8B h_01KH9HERVZAT11WNX99R2EQCPB=advanced-security%E3%81%AF%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E5%81%BD%E8%A3%85%E3%82%92%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E9%98%B2%E3%81%8E%E3%81%BE%E3%81%99%E3%81%8B does-advanced-security-affect-the-app-or-user-experience=advanced-security%E3%81%AF%E3%82%A2%E3%83%97%E3%83%AA%E3%82%84%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E4%BD%93%E9%A8%93%E3%81%AB%E5%BD%B1%E9%9F%BF%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B h_01KH9HERW0XFEGCKGJZA6C44HY=advanced-security%E3%81%AF%E3%82%A2%E3%83%97%E3%83%AA%E3%82%84%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E4%BD%93%E9%A8%93%E3%81%AB%E5%BD%B1%E9%9F%BF%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B who-should-use-advanced-security=advanced-security%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E9%81%A9%E3%81%97%E3%81%A6%E3%81%84%E3%81%BE%E3%81%99%E3%81%8B h_01KH9HERW00N9M05DSF8998JE0=advanced-security%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AB%E9%81%A9%E3%81%97%E3%81%A6%E3%81%84%E3%81%BE%E3%81%99%E3%81%8B is-advanced-security-available-for-all-platforms=advanced-security%E3%81%AF%E3%81%99%E3%81%B9%E3%81%A6%E3%81%AE%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%A7%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01KH9HERW13WYZYBAGA9XXKW1B=advanced-security%E3%81%AF%E3%81%99%E3%81%B9%E3%81%A6%E3%81%AE%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%A7%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B how-do-i-know-advanced-security-is-working=advanced-security%E3%81%8C%E5%8B%95%E4%BD%9C%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E3%81%8B%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E7%A2%BA%E8%AA%8D%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01KH9HERW2CQ76W33ERFTP0FS9=advanced-security%E3%81%8C%E5%8B%95%E4%BD%9C%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E3%81%8B%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AB%E7%A2%BA%E8%AA%8D%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B" />
