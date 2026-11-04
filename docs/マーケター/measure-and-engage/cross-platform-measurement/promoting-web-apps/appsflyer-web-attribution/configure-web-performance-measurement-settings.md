---
title: Web Performance Measurementの設定
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-02-05T08:47:53Z'
  edited_at: '2026-10-14T09:22:10Z'
  id: 43541863890961
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/43541863890961
---
> **概要：** Web Performance Measurementの設定では、AppsFlyer がウェブサイトへの訪問、コンバージョン、およびユーザーアクティビティをマーケティングキャンペーンへどのようにアトリビューションするかを管理できます。設定項目には、アトリビューション期間、ユーザー獲得イベント、リエンゲージメントルール、および除外ドメインが含まれます。

<div id="overview" />

## 概要

Webアトリビューション設定では、AppsFlyer がウェブサイト上のユーザーアクティビティをどのように計測し、アトリビューションするかを定義します。これらの設定により、以下を決定できます。

* どのイベントをユーザー獲得とみなすか
* その後に発生するイベントを、どの期間マーケティングソースに紐づけるか
* ユーザーをリエンゲージメントまたは再獲得と判断するタイミング
* アトリビューション対象から除外するドメイン

<div id="who-should-configure-these-settings" />

### 設定対象者

通常、これらの設定はビジネス目標に基づいてマーケティングチームやグロース担当者が設定します。SDK連携やドメイン設定については、技術チームが関与する場合があります。

<div id="accessing-web-attribution-settings" />

### Webアトリビューション設定へのアクセス

Webアプリのアトリビューション設定にアクセスするには、以下の手順を実行します：

1. AppsFlyerで **マイアプリ** に移動します。
2. アプリ一覧から対象のWebアプリを選択します。
3. **アプリ設定** > **アトリビューション** に移動します。

<div id="quick-reference" />

## クイックリファレンス

| 設定 | デフォルト値 | 設定可能範囲 | 編集可否 | 管理内容 |
| --- | --- | --- | --- | --- |
| アプリ名 | ユーザー入力 | 1 - 100文字 | 可 | AppsFlyer上での表示名 |
| Full URL（プライマリドメイン） | ユーザー入力 | 1 - 500 文字 | 不可 | アプリ識別子および主な除外ドメイン |
| Web SDK ID | 自動生成 | 1 - 550文字 | 不可 | イベント収集用のSDK識別子 |
| 通貨 | ユーザー選択 | ISO通貨コード | 可 | 売上・ROIのレポート |
| タイムゾーン | ユーザー選択 | IANAタイムゾーン | 一部制限あり | レポート上のタイムスタンプ |
| ユーザー獲得イベント | First visit | イベント名 | 可 | ユーザー獲得とみなす条件 |
| ルックバック期間 | 30日間 | 1時間 - 90日 | 可 | ユーザー獲得タッチポイントを遡る期間 |
| リエンゲージメント期間 | 30日間 | 1時間 - 90日 | 可 | リターゲティング施策へ成果を紐付ける期間 |
| 休眠期間（リエンゲージメント） | 無効 | 0 - 30日 | 可 | リターゲティング対象となるための最低休眠期間 |
| アトリビューション期間 | ライフタイム | プリセット選択 | 可 | イベントをユーザー獲得へ紐づける期間 |
| 休眠期間（再獲得） | 90日 | 1 - 180日 | 可 | ユーザーを離脱済みと判断する期間 |
| 再獲得イベント | Visit | イベント名 | 可 | 離脱ユーザーが復帰したと判断するイベント |
| 除外ドメイン | プライマリドメインのみ | 最大100件 | 可 | アトリビューション対象外とするドメイン |

**制約事項：**  
リエンゲージメントの休眠期間は、再獲得の休眠期間よりも短いくなければなりません。そうでない場合、ユーザーがリターゲティング対象となる前に再獲得ユーザーとして扱われる可能性があります。

<div id="basic-settings" />

## **基本設定**

Webアプリの基本設定は以下のとおりです：

* アプリ名
* Full URL
* Web SDK ID
* 通貨
* タイムゾーン

詳細については、「<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#web">AppsFlyerへのアプリ追加</Anchor>」をご参照ください。

<div id="user-acquisition-settings" />

## ユーザー獲得（UA）の設定

ユーザー獲得（UA）設定では、AppsFlyer がユーザーを初めて獲得したタイミングをどのように判定し、その獲得をどのマーケティングソースにアトリビューションするかを定義します。

<div id="user-acquisition-event" />

<Accordion title="ユーザー獲得イベント">

ユーザー獲得を発生させるイベントです。このイベントは、ユーザーを「獲得した」とみなす基準となる重要なビジネスアクションです。

<div id="why-customize" />

#### カスタマイズする理由

デフォルト設定の「**first visit（初回訪問）**」は、ユーザー価値を示すシグナルとしては弱い場合があります。ユーザーが誤って広告をクリックしたり、すぐに離脱したりするケースもあるためです。この設定をカスタマイズすることで、長期的な価値（LTV）を単なる興味本位のクリックではなく、実際に価値あるアクションを促したマーケティングソースにアトリビューションできるようになります。

**デフォルト設定：** First visit（初回サイト訪問時にユーザー獲得とみなす）

<div id="common-alternatives-by-industry" />

#### 業界別の一般的な設定例

| **業界** | **推奨UAイベント** |
| --- | --- |
| 銀行 / 金融 | registration または first\_time\_deposit |
| EC | sign\_up または first\_purchase |
| フードデリバリー | first\_order |
| SaaS・サブスクリプション | subscription\_start |
| ゲーム | sign\_up、tutorial\_complete、またはfirst\_purchase |

<div id="how-it-works" />

#### 動作の仕組み

**First visit** に設定した場合：

* ユーザーは初回サイト訪問時に獲得済みとみなされます。
* アトリビューションは初回訪問時点から開始されます。

**カスタムイベント**（例：sign\_up）に設定した場合：

* ユーザーは初回訪問から対象イベントを実行するまで「**プレ獲得期間**」に入ります。
* プレ獲得期間中のイベントは、ルックバック期間内の直近のオーガニック以外のタッチポイントにアトリビューションされます（ラストタッチアトリビューション）。
* カスタムUAイベントが発生すると、**ユーザー獲得コンバージョン**が作成され、長期的なアトリビューションが開始されます。

<div id="example-scenario-ua-event--sign_up" />

#### 利用例（UAイベント = sign\_up）：

* **0日目：** ユーザーがFacebook広告経由で訪問 → プレ獲得期間が開始
* **2日目：** Google広告経由で再訪問 → アトリビューション先がGoogleへ変更（ラストタッチ）
* **3日目：** ユーザーが会員登録（sign\_up）→ Google広告にユーザー獲得をアトリビューション

**10日目：** ユーザーが購入 → LTV計測のためGoogle広告に購入成果を紐づけ

</Accordion>

<div id="lookback-window-user-acquisition" />

<Accordion title="ルックバック期間（ユーザー獲得）">

ユーザー獲得につながったマーケティングタッチポイントを検索するために、AppsFlyer がどこまで過去に遡るかを定義します。

この設定は、AppsFlyer がマーケティングタッチポイントをどの程度の期間「記憶」するかを決定します。ユーザーが広告経由で訪問した後、しばらく経ってからUAイベントを完了した場合でも、その広告に成果を紐付けるかどうかを制御します。

**デフォルト設定：** 30日間

**設定範囲：** 1時間～90日

<div id="how-it-works-1" />

#### 動作の仕組み

ユーザーがUAイベント（例：sign\_up）を実行すると、AppsFlyer は指定されたルックバック期間内を遡り、最も新しいオーガニック以外のタッチポイントを探し、そのマーケティングソースへユーザー獲得をアトリビューションします。

<div id="example-1-30-day-lookback" />

#### 例1（30日間のルックバック）：

* **0日目：** ユーザーがFacebook広告をクリックしてサイト訪問
* **25日目：** ユーザーがダイレクト流入で再訪し、sign\_upイベントを実行
* **結果：** Facebookにユーザー獲得をアトリビューション（30日ルックバック期間内のため）

<div id="example-2-window-expired" />

#### 例2（ルックバック期間切れ）：

* **0日目：** ユーザーがFacebook広告をクリックしてサイト訪問
* **40日目：** ユーザーがダイレクト流入で再訪し、sign\_upイベントを実行

**結果：** 30日ルックバック期間外のため、ユーザー獲得はオーガニックとして記録

</Accordion>

<div id="re-engagement-settings" />

## リエンゲージメント設定

リエンゲージメント設定では、既に獲得済みのユーザーがリターゲティングキャンペーンを通じてウェブサイトへ再訪した際に、AppsFlyer がそのアクティビティをどのようにアトリビューションするかを管理します。

<div id="reengagement-window-item" />

<Accordion title="リエンゲージメント期間">

リエンゲージメントコンバージョン発生後、AppsFlyer がそのマーケティングタッチポイントに対してイベントをアトリビューションし続ける期間です。

この設定では、リターゲティングキャンペーンに対してどの程度の期間成果を紐付けるかを決定します。リターゲティング施策への適切な評価を行いながら、長期的なLTVについては元のユーザー獲得ソースへアトリビューションできるよう設計されています。

**デフォルト設定：** 30日間

**設定範囲：** 1時間～90日

<div id="how-it-works-2" />

#### 動作の仕組み

獲得済みユーザーがオーガニック以外の流入元（例：リターゲティング広告）を経由して再訪し、リエンゲージメント条件を満たした場合、**リターゲティングコンバージョン**が作成されます。この期間内に発生したイベントには、**二重アトリビューション**が適用されます：

1. **プライマリアトリビューション（メインの紐づけ先）** → リターゲティングキャンペーン
   * 目的：リターゲティングキャンペーンの成果を評価するため
2. **セカンダリアトリビューション（サブの紐づけ先）** → 元のユーザー獲得（UA）ソース
   * 目的：ユーザー獲得ビューにおいて、ユーザーの生涯価値（LTV）を元の獲得元へ紐付けて計測するため

<div id="example-within-window" />

#### 例（リエンゲージメント期間内）：

* **0日目：** ユーザーをFacebook広告経由で獲得
* **50日目：** ユーザーがメールによるリターゲティングキャンペーンをクリックして再訪問（リターゲティングコンバージョン作成）
* **60日目：** ユーザーが100ドルの商品を購入（リターゲティングから10日後）
* **結果 ー 二重アトリビューション：**
  * **プライマリ（リターゲティングビュー）:** メールキャンペーンに100ドルの購入実績をアトリビューション
  * **セカンダリ（ユーザー獲得ビュー）：** Facebook広告にもユーザーLTVの一部として100ドルを計測
* **レポート上の表示：**
  * 統合ビュー：メールキャンペーンに購入を紐づけ
  * リターゲティングビュー：メールキャンペーンに購入を紐づけ
  * ユーザー獲得ビュー：Facebook広告に購入を紐づけ

</Accordion>

<div id="inactivity-window-for-reengagement" />

<Accordion title="リエンゲージメント用の休眠期間">

オーガニック以外のタッチポイントによってリエンゲージメント（リターゲティング）コンバージョンを発生させるために必要な、最小の休眠期間です。

既にウェブサイトでアクティブなユーザーに対してリターゲティング施策の成果を付与しないようにするための設定です。これにより、本当に離脱しているユーザーのみをリターゲティング対象とし、広告予算の最適化につながります。

**デフォルト設定：** 無効

**設定範囲：** 0（無効） - 30日

<div id="how-it-works-3" />

#### 動作の仕組み

**無効**の場合：

* 獲得済みユーザーによるすべてのオーガニック以外のタッチポイントでリターゲティングコンバージョンが作成されます。

**有効な場合（例：7日間）：**

* ユーザーが少なくとも7日間非アクティブだった場合のみ、リターゲティングコンバージョンを作成します。
* 最近までアクティブだった場合、その訪問は元のUAソースへアトリビューションされます。

**制約事項：**

* リエンゲージメント用の休眠期間は、再獲得用の休眠期間を超えることはできません。

<div id="example-7-day-inactivity-window" />

#### 例（休眠期間 = 7日）：

* **0日目：** ユーザーをFacebook広告経由で獲得
* **3日目：** ユーザーがオーガニックで訪問
* **5日目：** ユーザーがリターゲティング広告をクリック → **リターゲティングコンバージョンは作成されない**（休眠したのは2日間のみ）
* **15日目：** ユーザーがリターゲティング広告をクリック → **リターゲティングコンバージョン作成**（12日間休眠だったため）

</Accordion>

<div id="re-acquisition-settings" />

## 再獲得の設定

再獲得の設定では、休眠ユーザーをいつ「離脱済み（Churned）」と判断するか、およびそのユーザーをどのように再獲得ユーザーとして扱うかを定義します。

<div id="inactivity-window-reacquisition" />

<Accordion title="休眠期間（再獲得）">

ユーザーを「離脱済み」と判断するために必要な完全な休眠期間です。離脱済みユーザーは再獲得対象となり、新たなユーザー獲得コンバージョンを生成できます。

この設定は、ビジネスにおける離脱判定基準を定義します。ユーザーを「失われたユーザー」とみなすタイミングを決定し、再獲得キャンペーンが離脱ユーザーの復帰に対して成果を獲得できるようにします。

**デフォルト設定：** 90日

**設定範囲：** 1 - 180日

<div id="how-it-works-4" />

#### 動作の仕組み

**ユーザーが離脱済みと判定された場合：**

* その後の新しいイベントは元のUAソースにアトリビューションされません。
* ユーザーは「プレ獲得状態（Pre-acquisition）」へ移行し、再獲得待ちとなります。
* 元の獲得に基づくアトリビューション期間は適用されなくなります。

**離脱済みユーザーが再訪した場合：**

* ユーザーが再獲得イベントを実行すると、新しいUAコンバージョンが作成されます。
* 再訪させたキャンペーンが新しい獲得元として成果を獲得します。
* レポート上では、ユーザーは新規獲得ユーザーとして扱われます。

<div id="example-90-day-window" />

#### 例（休眠期間 = 90日）

* **0日目：** Google広告経由でユーザー獲得
* **50日目：** 最後のアクティビティ
* **140日目：** ユーザーが離脱済みと判定される（90日間休眠）
* **145日目：** ユーザーがメールのユーザー復帰キャンペーンをクリック

**146日目：** ユーザーが再獲得イベントを実行 → **新しいUAコンバージョン**が作成され、メールキャンペーンにアトリビューションされる

</Accordion>

<div id="reacquisition-event" />

<Accordion title="再獲得イベント">

離脱済みユーザーの再獲得を発生させるイベントです。再獲得できるのは離脱済みユーザーのみです。

多くのユーザー獲得イベント（例: sign\_up、first\_purchase）は一度しか発生しないイベントであり、再度実行できません。この設定では、離脱ユーザーの復帰を示す繰り返し可能なイベントを定義できます。

**デフォルト設定**： visit（離脱済みユーザーは最初の再訪問時に**即座に再獲得**と定義される）

**一般的な代替イベント：** sign\_in や purchase

<div id="how-it-works-5" />

#### 動作の仕組み

**カスタムイベント**（例: **sign\_in**）を設定した場合：

* 離脱済みユーザーは、指定されたイベントを実行した時点で再獲得されます。
* 再獲得が発生する前に複数回訪問することも可能です。
* 「本当に復帰したユーザー」の定義をより厳格にできます。

<div id="example-re-acquisition-event--sign_in" />

#### 例（再獲得イベント = sign\_in）：

* ユーザーが90日間休眠し離脱判定
* ユーザーがメールの休眠復帰キャンペーンをクリックして訪問 → まだ再獲得とはみなされない
* 翌日、ユーザーがサインイン（sign\_in）→ 再獲得コンバージョンが作成され、メールキャンペーンにアトリビューションされる

</Accordion>

<div id="attribution-window" />

## アトリビューション期間

<div id="time-period" />

<Accordion title="期間">

ユーザー獲得後、AppsFlyer がそのコンバージョンに対してイベントをアトリビューションし続ける最大期間です。

**デフォルト設定：** 半永久

**利用可能な設定値：** None、1日、7日、30日、60日、90日、180日、365日、半永久（データ保持期間の範囲内）

</Accordion>

<div id="excluded-domains" />

## 除外ドメイン

アトリビューション対象から除外するドメインを設定します。これにより、ユーザーが指定したドメインと自社サイト間を移動した場合でも、AppsFlyer が訪問やイベントをアトリビューションしないようにできます。

**目的：**

1. **セルフアトリビューションの防止：** 自社ドメインを除外
2. **サードパーティフローの除外：** 決済ゲートウェイや認証プロバイダーを除外

<div id="domain-types" />

<Accordion title="ドメインの種類">

<div id="primary-required-automatic" />

#### PRIMARY（必須・自動設定）

* アプリ作成時に設定したメインのウェブサイトドメインです。
* 自動的に追加され、削除できません
* WebアプリごとにPRIMARYドメインは1つのみ設定可能です
* **サブドメインの自動除外：** プライマリドメインを設定すると、そのすべてのサブドメインも自動的に除外されます。
  * 例：example.com を設定した場合、以下のサブドメインも自動的に除外されます shop.example.com、blog.example.comなど
* **ドメイン除外時の影響：** セルフアトリビューションが発生しなくなります。

<div id="internal-optional" />

#### INTERNAL（任意）

* PRIMARYドメインに含まれない、自社ブランドが保有するその他のドメインです。
* 最大99件まで追加できます
* 例：以下のような異なるトップレベルドメインの場合： example.co.uk、example.inなど
* **ドメイン除外時の影響：** セルフアトリビューションが発生しなくなります。

<div id="external-optional" />

#### EXTERNAL（任意）

外部ドメインの除外には、2つの種類があります：

<div id="external-listed-by-you" />

#### External（ユーザーが追加するドメイン）

* 自社ウェブサイトで利用しているものの、自社ブランドには属さないドメインです。
* 対象例：決済ゲートウェイ / 決済処理サイト / 認証プロバイダーなど
* 最大99件まで追加できます
* 例：auth0.com、okta.com、facebook.com、google.com
* **ドメイン除外時の影響：** これらのドメイン経由の訪問はアトリビューション対象外となります。

<div id="external-listed-by-appsflyer" />

#### External（AppsFlyer が自動登録するドメイン）

* AppsFlyer により自動的に除外されるドメインです。

  **決済プロバイダー**

  * PayPal（決済）
  * Stripe（決済）
  * Adyen（決済）
  * Klarna（決済）
  * Braintree（決済ゲートウェイ）
  * Square（決済）
  * Paddle（決済）
  * Mollie（決済）
  * Alipay（決済）
  * Razorpay（決済）
  * Paytm（決済）
  * PayU（決済）
  * Mercado Pago（決済）
  * Yandex Pay（決済）
  * Naver Pay（決済）

  **OAuthおよびSSOサインイン**

  * Google Sign-In（Googleアカウントへのログイン）
  * Apple ID（Appleアカウントへのログイン）
  * Microsoft（Microsoft 365 / Entraアカウントへのログイン）
  * Microsoft Live（Outlook / Liveアカウントへのログイン）
  * Facebook Login（Facebookのサインイン用ドメインのみ）
  * Yandex Login（Yandexアカウントへのログイン）
  * Kakao Login（Kakaoアカウントへのログイン）
  * Naver Login（Naverアカウントへのログイン）
  * LINE Login（LINEアカウントへのログイン）
  * Weixin Login（WeChatのOAuthサインイン）
  * VK Login（VKアカウントへのログイン）
  * Daum Login（Daumアカウントへのログイン）
* 自動除外ドメインのリストは編集できません。
* **ドメイン除外時の影響：** これらのドメイン経由の訪問はアトリビューション対象外となります。

</Accordion>

<div id="adding-excluded-domains" />

<Accordion title="除外ドメインの追加方法">

**ドメインを追加するには：**

1. Webアプリ設定の アトリビューション に移動します
2. 除外ドメインのセクションに移動します
3. **ドメインを追加**をクリックしてください。
4. ドメイン名を入力してください（例：custom-gateway.com）
5. ドメインタイプとして、 Internal または External を選択します
6. **保存**をクリックしてください。

**重要事項：**

* 除外設定は**1時間以内**に反映されます
* 変更は**適用後のデータにのみ反映**され、過去データには影響しません
* 一般的な決済プロバイダーやOAuth / SSOサインイン用ドメインは自動的に除外されます。詳細は、[外部（AppsFlyerが登録）の一覧](#externalappsflyer-が自動登録するドメイン)を確認してください（手動で追加する必要はありません）。

</Accordion>

<div id="requirements-and-validation" />

<Accordion title="要件と検証">

<div id="domain-format" />

#### ドメイン形式

* ドメイン名のみ指定できます（プロトコル、パス、ポート番号は指定不可）。
* ドメインごとの最大文字数：500文字
* プロトコル（https:// など）は自動的に削除され、ドメイン名は自動的に小文字へ変換されます

<div id="examples" />

#### 例：

* example.com ✅
* shop.example.com ✅（ただし example.com がPRIMARYドメインの場合は不要）
* https://example.com → example.com として保存される ✅
* example.com/path ❌（パスは指定不可）
* example.com:8080 ❌（ポート番号は指定不可）

<div id="limits" />

#### 制限：

* 登録可能なドメイン数は最大100件です（PRIMARYドメイン1件を含む）。

</Accordion>

<div id="migrating-from-people-based-attribution-pba" />

## People-Based Attribution（PBA）からの移行

<div id="key-differences" />

<Accordion title="主な違い：">

| **項目** | **PBA（従来版）** | **新しいWeb Performance Measurement** |
| --- | --- | --- |
| **設定単位** | Brand Bundle単位 | Webアプリ単位 |
| **カスタムUAイベント** | 非対応 | 完全にカスタマイズ可能 |
| **期間設定** | 限定的 | 1時間〜半永久まで柔軟に設定可能 |

</Accordion>

<div id="migration-steps" />

<Accordion title="移行手順">

1. 新しいWebアプリを作成する
   1. マイアプリ → アプリ追加 → Webサイト を選択します。
2. Web SDK ID を選択する   
   既存のPBA用Dev Keyを再利用することを推奨します。これにより、ウェブサイト側のコード変更を回避できます。
3. 設定を構成する   
   PBAの設定内容を、新しいWebアトリビューション設定へマッピングします。
4. 除外ドメインを追加する   
   PBA（Brand Bundle）の除外ドメイン設定を、新しいWeb Attribution設定へ移行します。

**注意：** 各PBA Dev Keyは、1つの新しいWebアプリにのみ割り当てることができます。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01KGPFHN8MKTPX5VYDEV30M9A7=%E6%A6%82%E8%A6%81 who-should-configure-these-settings=%E8%A8%AD%E5%AE%9A%E5%AF%BE%E8%B1%A1%E8%80%85 h_01KGPFK1RNA7ZTJRACJ6M97EAB=%E8%A8%AD%E5%AE%9A%E5%AF%BE%E8%B1%A1%E8%80%85 accessing-web-attribution-settings=web%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%AD%E5%AE%9A%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01KGPFM0DJDMVDXZC2B6G6DVX5=web%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%AD%E5%AE%9A%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 quick-reference=%E3%82%AF%E3%82%A4%E3%83%83%E3%82%AF%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9 h_01KGPFT1W65R724WCNDPBHY3F6=%E3%82%AF%E3%82%A4%E3%83%83%E3%82%AF%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9 basic-settings=%E5%9F%BA%E6%9C%AC%E8%A8%AD%E5%AE%9A h_01KGPGJG092S1TEDB1T9JNBASE=%E5%9F%BA%E6%9C%AC%E8%A8%AD%E5%AE%9A user-acquisition-settings=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97ua%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGPGE592EK59XXVKTTFDGX16=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97ua%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGPGRTEFA0PJ3DB7MR4W85EB=user-acquisition-event why-customize=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%82%A4%E3%82%BA%E3%81%99%E3%82%8B%E7%90%86%E7%94%B1 h_01KGPHMJWF6Z1VV0KH301TYAS5=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%82%A4%E3%82%BA%E3%81%99%E3%82%8B%E7%90%86%E7%94%B1 common-alternatives-by-industry=%E6%A5%AD%E7%95%8C%E5%88%A5%E3%81%AE%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A%E4%BE%8B h_01KGPHMSEDGJ2E6NSB1ZCR5CCW=%E6%A5%AD%E7%95%8C%E5%88%A5%E3%81%AE%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A%E4%BE%8B how-it-works=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF h_01KGPHN5M5GBBMPBYRMYHB9F0E=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF example-scenario-ua-event-sign_up=%E5%88%A9%E7%94%A8%E4%BE%8Bua%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88--sign_up h_01KGPHQES3SF5AKBNYD8CY3RG8=%E5%88%A9%E7%94%A8%E4%BE%8Bua%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88--sign_up h_01KGPGRTEFYRAZD7Z9NYDKV907=lookback-window-user-acquisition how-it-works::69b3417c=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-1 h_01KGPHX2JNAWZ8VJZ25CRWP1ER=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-1 example-1-30day-lookback=%E4%BE%8B130%E6%97%A5%E9%96%93%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF h_01KGPHX8JMG7FMRS1MYFYS6JRV=%E4%BE%8B130%E6%97%A5%E9%96%93%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF example-2-window-expired=%E4%BE%8B2%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93%E5%88%87%E3%82%8C h_01KGPHXT83JHJ6J0APVN7NRJ3E=%E4%BE%8B2%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93%E5%88%87%E3%82%8C reengagement-settings=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E8%A8%AD%E5%AE%9A h_01KGPJ1ZMXXJJNCBB52CHY95Z2=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E8%A8%AD%E5%AE%9A reengagement-window%C2%A0item=reengagement-window-item h_01KGPJ58N3712E1NZ4E6JVGAY2=reengagement-window-item how-it-works::dafb60ec=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-2 h_01KGPJFG3X578XCP5X353RRVR1=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-2 example-within-window=%E4%BE%8B%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E6%9C%9F%E9%96%93%E5%86%85 h_01KGPJG6WSYX2R0VVQYXXWZSMA=%E4%BE%8B%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E6%9C%9F%E9%96%93%E5%86%85 h_01KGPJ58N3QH9RKXTVZXCZ1WGW=inactivity-window-for-reengagement how-it-works::4a4cf0f=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-3 h_01KGPJK3H2JF7PV1ATQB3TE9AX=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-3 example-7day-inactivity-window=%E4%BE%8B%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93--7%E6%97%A5 h_01KGPJKDMY4FRAJSMHE19GGJCA=%E4%BE%8B%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93--7%E6%97%A5 reacquisition-settings=%E5%86%8D%E7%8D%B2%E5%BE%97%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGPJMJDX83SBA77A7BSRZ87V=%E5%86%8D%E7%8D%B2%E5%BE%97%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGPJPC0QXYFD6Q09XF7T3XA9=inactivity-window-reacquisition how-it-works::9c91010b=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-4 h_01KGPJV8EJR94H1P7GZXMP8HSR=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-4 example-90day-window=%E4%BE%8B%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93--90%E6%97%A5 h_01KGPJVHCNBZHD9ZXW288CGG9H=%E4%BE%8B%E4%BC%91%E7%9C%A0%E6%9C%9F%E9%96%93--90%E6%97%A5 h_01KGPJPC0QY2726Z583AQ7G5W2=reacquisition-event how-it-works::587eebec=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-5 h_01KGPJY5PA9907PXBRC2QHNJ6T=%E5%8B%95%E4%BD%9C%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF-5 example-reacquisition-event-sign_in=%E4%BE%8B%E5%86%8D%E7%8D%B2%E5%BE%97%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88--sign_in h_01KGPJYWG31QJ1G5A09QC00AMY=%E4%BE%8B%E5%86%8D%E7%8D%B2%E5%BE%97%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88--sign_in attribution-window=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93 h_01KGPK8H7P5AT59S0GQ9ZK0F01=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93 h_01KGPK1CSV5XGKHX3XVS37QFKS=time-period excluded-domains=%E9%99%A4%E5%A4%96%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01KGPKA56KQRJKRS54HBR50NJN=%E9%99%A4%E5%A4%96%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01KGPKCY1EBCMYDDYS6SZEK1ZR=domain-types primary-required-automatic=primary%E5%BF%85%E9%A0%88%E8%87%AA%E5%8B%95%E8%A8%AD%E5%AE%9A h_01KGPKJQ7M82KW5VE9ESYNNFEQ=primary%E5%BF%85%E9%A0%88%E8%87%AA%E5%8B%95%E8%A8%AD%E5%AE%9A internal-optional=internal%E4%BB%BB%E6%84%8F h_01KGPKJV9B2BHDR64JD24VHH1X=internal%E4%BB%BB%E6%84%8F external-optional=external%E4%BB%BB%E6%84%8F h_01KGPKJZQYZESHHH3D0NA2WC9F=external%E4%BB%BB%E6%84%8F external-listed-by-you=external%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%8C%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01KGPKK4THXQ88AXT58GZ2MHHE=external%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%8C%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 external-listed-by-appsflyer=externalappsflyer-%E3%81%8C%E8%87%AA%E5%8B%95%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01KGPKK96ZAZSKVPBX60FC888X=externalappsflyer-%E3%81%8C%E8%87%AA%E5%8B%95%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01KGPKCY1ETKF1NQ2BP6Z3JH4T=adding-excluded-domains h_01KGPKCY1EE01631ZEYGC6FEJH=requirements-and-validation domain-format=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E5%BD%A2%E5%BC%8F h_01KGPKKXRA59A4RDY4QE1M0Q66=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E5%BD%A2%E5%BC%8F examples=%E4%BE%8B h_01KGPKM213203KA8CEBHZ9KJP3=%E4%BE%8B limits=%E5%88%B6%E9%99%90 h_01KGPKM8AMQ5BA88ZCSTRJ2JV7=%E5%88%B6%E9%99%90 migrating-from-peoplebased-attribution-pba=people-based-attributionpba%E3%81%8B%E3%82%89%E3%81%AE%E7%A7%BB%E8%A1%8C h_01KGPKPGSF3VSBTQJR6JN80BF4=people-based-attributionpba%E3%81%8B%E3%82%89%E3%81%AE%E7%A7%BB%E8%A1%8C h_01KGPKQPWC1GYYGYYD6PCDWX29=key-differences h_01KGPKQPWD00B08Z76ZYGRP4AT=migration-steps" />
