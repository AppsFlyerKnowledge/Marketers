---
title: Web Performance Measurement - 概要
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T15:07:53Z'
  edited_at: '2026-10-14T09:23:19Z'
  id: 43521734577809
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/43521734577809
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** AppsFlyerのWeb Performance Measurement（Web計測機能）を利用すると、どのメディアソースやキャンペーンがユーザーをWebサイトへ誘導しているかを特定し、その訪問がその後のユーザー行動にどのような影響を与えているかを長期的に計測できます。初回訪問からLTV計測まで、ユーザーのインタラクションをエンドツーエンドで取得・アトリビューションできるため、ユーザー獲得（初回訪問者）とリエンゲージメントの両方に対応できます。

## Web Performance Measurementについて

Web計測は、どのメディアソースやキャンペーンがユーザーのWebサイト訪問を促し、その後の行動に影響を与えたかを特定するプロセスです。

Web訪問は、閲覧行動であると同時に、その訪問の直前に発生した広告エンゲージメントでもあります。モバイルアトリビューションではクリックとインストールを照合する必要がありますが、Web訪問では、遷移先URLやヘッダーにマーケティングソース情報が含まれるため、初回の照合を即時に行うことができます。

この記事では、AppsFlyerのWeb Performance Measurementのエンドツーエンドのプロセスを説明します。初回のWebサイト訪問からLTV計測まで、ユーザーのインタラクションがどのように取得、識別、計測されるかを解説します。このプロセスにより、初回訪問者を特定・アトリビューションするユーザー獲得と、再訪問ユーザーを対象としたキャンペーン効果を計測するリターゲティングまたはリエンゲージメントの両方に対応できます。

#### People-Based Attribution（PBA）をご利用の場合

現在<Anchor target="_blank" href="/marketers/ja/docs/people-based-attribution-pba">People-Based アトリビューション (PBA)</Anchor>を使用している場合は、より粒度の細かい アトリビューションで追加のシグナルを得るために、Web Performance Measurementに切り替えることを検討してください。

### Web Performance Measurementのフロー

AppsFlyerのWeb Performance Measurementのフローは、Webサイトへの生の訪問データを、実用的なマーケティングインサイトへ変換する一連のステップで構成されています。

1. [データ収集](#1-data-collection)：Web SDK（Pixel）または Server-to-Server（S2S）API のいずれかを通じて、ユーザーのインタラクションデータを取得します。
2. [サイト訪問の記録](#2-visit-recording)[：](/docs/web-performance-measurement-overview#2-visit-recording)トラフィックソースがまだ不明な場合でも、ユーザーのWebサイト到達を取得し、訪問イベントとして記録します。
3. [メディアソースの特定](#3-media-source-resolution)：定義された優先順位に従ってURLパラメータを解析し、メディアソースを特定します。
4. [30分間のID判定遅延](#4-the-30minute-identity-delay)：ユーザーログインによるID判別を可能にするため、アトリビューション判定を30分間遅らせます。
5. [ユーザー識別とデータ統合](#5-stitching-and-identity-resolution)：：現在のセッションを Customer User ID（CUID）やブラウザCookieと紐づけ、同一ユーザーとして継続的に計測できるようにします。
6. [ユーザー獲得イベント](#6-user-acquisition-ua-event)：UAルックバック期間内に発生した、獲得を定義するイベント（例：`first_visit` またはカスタム獲得イベント）を記録します。
7. [プレ獲得期間](#7-preacquisition-period)：初回訪問からUAイベントまでの間に発生した中間イベントをアトリビューションします。
8. [リエンゲージメントと再獲得](#8-reengagement-and-reacquisition)：休眠期間の設定に基づいて再訪問ユーザーをアトリビューションし、その再訪問がリエンゲージメントか再獲得かを判定します。
9. [LTV計測](#9-ltv-measurement)：継続的なイベントや収益をアトリビューションし、アトリビューション期間の設定に基づいてユーザーのLTVを計測します。

## Web Performance Measurementのフロー

以降のセクションでは、各ステップについて詳しく説明します。

<div id="1-data-collection" />

<Accordion title="1. データ収集">

ユーザーがランディングページに到達すると、AppsFlyer は連携済みのリスナーを通じて、そのユーザー行動を取得する必要があります。

* **Web SDK（ピクセル）**：<Anchor target="_blank" href="/marketers/ja/docs/integrate-appsflyer-web-sdk">Webサイトに直接実装する、または Google Tag Manager（GTM）経由で設定する</Anchor>クライアント側のスニペットです。
* **サーバー間（S2S）API**：サーバー側で連携する、より堅牢な実装方法です。ブラウザによる計測制限や広告ブロッカーの影響を受けにくくできるほか、AppsFlyer にデータを送信する前に、必要な情報を追加できます。S2S連携は、顧客側のサーバーから直接行うことも、Google Tag Manager Server Side 経由で行うこともできます。

</Accordion>

<div id="2-visit-recording" />

<Accordion title="2. サイト訪問の計測">

セッションデータが収集されると、システムは初回訪問レコードを作成するかどうかを判定します。このレコードは、実際にメディアソースを判定してアトリビューションを行う前に、ユーザーの生の行動データを取得するための前処理レイヤーとして機能します。すべてのセッションがサイト訪問として記録されるわけではありません。

AppsFlyer は、新しいセッションとしてユーザーがサイトにアクセスした場合、または判別可能な流入元パラメータが含まれている場合に、訪問を記録します。一方で、除外対象ドメインからの訪問は記録しません。こうした訪問記録のルールにより、セッションの重複カウントを防ぎます。

詳細は、「<Anchor target="_blank" href="/marketers/ja/docs/about-traffic-source-resolution#ステップ１サイト訪問の計測">サイト訪問の記録</Anchor>」をご覧ください。

</Accordion>

<div id="3-media-source-resolution" />

<Accordion title="3. メディアソースの判定">

データが収集され、サイト訪問が記録されると、AppsFlyer のエンジンは定義された優先順位に沿ってその情報を評価します。このウォーターフォール方式では、AppsFlyer固有のパラメータと市場で一般的に使われている標準パラメータの両方に対応しているため、<strong>移行時に既存のアトリビューションリンクを変更する必要はありません。</strong>ウォーターフォール内で最初に一致したシグナルが、訪問元の判定に使用されます。

* **PID**：まず、AppsFlyer独自のパラメータがあるかを確認します。
* **UTMパラメーター**：PID が存在しない場合は、`utm_source` などの標準タグを確認します。
* **クリックID**：次に、Google Click ID（`gclid`）や TikTok Click ID（`ttclid`）など、媒体固有のIDを確認します。
* **リファラー**：最後のフォールバックとして、ユーザーがサイトに到達する直前に閲覧していたURLを特定します。

詳細については、「<Anchor target="_blank" href="/marketers/ja/docs/about-traffic-source-resolution#ステップ２メディアソースの判定">メディアソースの判定</Anchor>」をご覧ください

</Accordion>

<div id="4-the-30minute-identity-delay" />

<Accordion title="4. 30分間のID判定遅延">

多くのユーザーはサイト訪問から30分以内にログインするため、AppsFlyer はアトリビューション判定を意図的に30分間遅らせます。この遅延により、CUID（Customer User ID）を取得し、Cookieの有効期限が切れている既存ユーザーでも元の流入元と正しく紐づけられるため、「オーガニック」と誤判定されることを防ぎます。

</Accordion>

<div id="5-stitching-and-identity-resolution" />

<Accordion title="5. ユーザー識別とデータ統合">

流入元が特定され、30分間の遅延が完了すると、システムは分断されたユーザーセッションを1つのユーザージャーニーとして統合します。

* **CUIDによる統合**：Customer User ID（例：ハッシュ化されたメールアドレス）が取得できた場合、エンジンはそのセッションを、ユーザーのクロスデバイス履歴と紐づけます。
* **Cookieによるフォールバック**：CUID が利用できない場合は、ブラウザCookieを利用して識別を行います。ただし、Cookie はデバイス依存であり、安定性はCUIDより低くなります。

</Accordion>

<div id="6-user-acquisition-ua-event" />

<Accordion title="6. ユーザー獲得イベント">

ユーザー識別が完了すると、エンジンはそのユーザーを「獲得済み」と判定するための特定アクションを確認します。業界標準では `first_visit` が使用されますが、これは必ずしも質の高いシグナルとは限りません。例えば、ユーザーが誤って広告をクリックしたり、すぐ離脱したりするケースもあります。登録完了や購入完了などのカスタム獲得イベントを設定することで、LTV（顧客生涯価値）を、単なる興味本位のクリックではなく、実際に価値ある行動を生み出したマーケティングソースへ正しく紐づけることができます。

ユーザー獲得イベントが発生すると、アトリビューションエンジンは、<strong>ルックバック期間（ユーザー獲得）</strong>の期間分だけ遡り、アトリビューション対象となる非オーガニック訪問を探します。この設定は、ユーザー訪問からUAイベント完了まで許容される最大期間を定義します（デフォルト設定：30日）このルックバック期間内に非オーガニックタッチポイントが見つからない場合、そのUAイベントはオーガニックとして扱われ、アトリビューションされません。カスタムイベントのルックバック期間は、Webアプリを AppsFlyer に追加する際に設定できます。詳細は「<Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings#lookback-window-user-acquisition">ルックバック期間（ユーザー獲得）</Anchor>」をご覧ください。

ビジネスモデルによって、ユーザー獲得トリガーとして定義するイベントは異なります。例えば：

* **登録完了イベント（例：銀行アプリ）**：サインアップフローが正常完了した時点で、獲得イベントが発火します。
* **初回注文イベント（例：フードデリバリーアプリ）**：商品閲覧やカート追加は対象とならず、購入完了時のみイベントが発火します。
* **サブスクリプション開始イベント（例：動画配信サービスやSaaSアプリ）**：トライアル開始やアプリインストールではなく、サブスクリプション契約確定時に獲得イベントとして記録されます。

ユーザー獲得イベント設定の詳細は、「<Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings#ユーザー獲得uaの設定">ユーザー獲得設定</Anchor>」をご覧ください。

</Accordion>

<div id="7-preacquisition-period" />

<Accordion title="7. プレ獲得期間">

ユーザー識別が完了してから正式な獲得イベントが発生するまでの間には、「プレ獲得期間（Pre-acquisition period）」と呼ばれる期間が存在する場合があります。これは、デフォルトの `first_visit` ではなく、カスタムユーザー獲得（UA）イベントを設定している場合にのみ関連します。この期間中、ユーザーは正式な獲得イベント（例：登録完了や初回購入）に至る前に、カート追加、商品閲覧、コンテンツ閲覧など、重要な行動を行うことがあります。

AppsFlyer は、これらのプレ獲得イベントを取得し、該当するマーケティングソースへアトリビューションしたうえで、レポート上では プレ獲得 として区別して表示します。プレ獲得アトリビューションと獲得後アトリビューションの主な違いは、アトリビューション期間にあります。プレ獲得期間では、これらのイベントが正式なUAイベント発生前に起きているため、アトリビューション期間は短く設定され、UAイベントのルックバック期間と同じになります。一方で、カスタムUAイベントが発生してユーザーが正式に獲得されると、アトリビューション期間はLTV計測向けに拡張され、そのユーザーを獲得したマーケティングソースへ長期的な成果が紐づけられます。

</Accordion>

<div id="8-reengagement-and-reacquisition" />

<Accordion title="8. リエンゲージメントと再獲得">

ユーザーが獲得された後、時間をおいてWebサイトを再訪する場合があります。既存ユーザーが広告をクリックしてWebサイトを訪問すると、リエンゲージメント（再訪）のアトリビューションが発生します。

*リエンゲージメント*が既存ユーザーを対象とする一方で、ユーザーが長期間アクティブでなかった場合、その再訪は*再獲得*として分類されることもあります。再獲得の対象となるには、まずユーザーが**非アクティブ期間**（デフォルト：90日）を超えている必要があります。90 日間) - この期間は、ユーザーを「離脱した」とみなすために必要な非アクティブ期間を定義します。この期間を経過した後にユーザーが再訪すると、エンジンは通常の再訪ではなく、新しいユーザー獲得イベントとして記録します。

詳細は、「<Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings#リエンゲージメント設定">リエンゲージメント設定</Anchor>」および「<Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings#再獲得の設定">再獲得設定</Anchor>」をご覧ください。

</Accordion>

<div id="9-ltv-measurement" />

<Accordion title="9. LTV計測">

ユーザーが最初の獲得キャンペーンによって流入した場合でも、その後のリターゲティング施策によって再訪した場合でも、最終的な目的は、そのユーザーが長期的にもたらす価値を計測することです。ユーザーが特定の流入元へ正常にアトリビューションされると、システムは継続的なユーザー行動を計測し、LTV（顧客生涯価値）を算出します。

この計測は**アトリビューション期間**の設定に基づいて行われ、デフォルトでは「Forever（半永久）」に設定されています。これにより、リピート購入やサブスクリプション更新など、その後のすべての行動が、最初にユーザーをサイトへ誘導したマーケティングソースへ継続的に紐づけられます。この長期的なデータを取得することで、単純なコンバージョン数だけではなく、キャンペーンごとの真のROAS（広告費用対効果）を把握できるようになります。

**アトリビューション期間**の設定の詳細は、「<Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings#アトリビューション期間">アトリビューション期間</Anchor>」をご覧ください。

</Accordion>

<div data-zendesk-anchors="about-web-attribution=web-performance-measurement%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KGMK4P46QE2HQHADD25TPCQF=web-performance-measurement%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 if-you-use-peoplebased-attribution-pba=people-based-attributionpba%E3%82%92%E3%81%94%E5%88%A9%E7%94%A8%E3%81%AE%E5%A0%B4%E5%90%88 h_01KH0P7BB9KF19S8XRH49DKMZA=people-based-attributionpba%E3%82%92%E3%81%94%E5%88%A9%E7%94%A8%E3%81%AE%E5%A0%B4%E5%90%88 the-appsflyer-web-attribution-flow=web-performance-measurement%E3%81%AE%E3%83%95%E3%83%AD%E3%83%BC h_01KGMK4P4614EEQ28V5FV32CY5=web-performance-measurement%E3%81%AE%E3%83%95%E3%83%AD%E3%83%BC the-appsflyer-web-attribution-process-step-by-step=web-performance-measurement%E3%81%AE%E3%83%95%E3%83%AD%E3%83%BC-1 h_01KGMK4P46HTB82K2PH9V0E33B=web-performance-measurement%E3%81%AE%E3%83%95%E3%83%AD%E3%83%BC-1 h_01KGMK4P46VJ0NF1FKFRS8V6J2=1-data-collection h_01KGMK4P46GWBP56NJM2ENARTR=2-visit-recording h_01KGMK4P46ZKS856R5C5KEQDBK=3-media-source-resolution h_01KGMK4P465777YN9MQ1JYZ7HT=4-the-30minute-identity-delay h_01KGMK4P46GFBZTMHDVW2MD3K1=5-stitching-and-identity-resolution h_01KGMK4P46MBT49ECD7RFHDY3X=6-user-acquisition-ua-event h_01KGMK4P46XYPVFV67F000EM6C=7-preacquisition-period h_01KGMK4P472B4TFGVR4VBH4REH=8-reengagement-and-reacquisition h_01KGMK4P47E9TPX0S26TTPW4CB=9-ltv-measurement" />
