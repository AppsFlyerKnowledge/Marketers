---
title: OneLink APIを使用した大規模キャンペーン向けリンクの作成
metadata:
  keywords:
    - api
    - Premium
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Premium
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2018-06-27T12:00:29Z'
  edited_at: '2026-10-21T19:18:06Z'
  id: 360001250345
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/360001250345
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** OneLink APIでは、SMS、メール、Web、QRコードなどのオウンドメディアからユーザーをモバイルアプリへ直接誘導する、パーソナライズされた短縮リンクを大規模に自動生成できます。チャネルをまたいだスムーズなユーザージャーニーを構築し、エンゲージメントの強化とコンバージョンの向上につなげられます。

## OneLink APIについて

OneLink APIは、あらゆるオウンドチャネルをモバイルアプリへの直接的な導線として活用できるプレミアム機能です。パーソナライズされた短縮リンクをプログラムから自動生成することで、SMS、メール、Webサイト、ソーシャル投稿など、さまざまなチャネルでユーザーごとに最適化されたジャーニーを大規模に提供し、エンゲージメントの強化とコンバージョンの向上を実現できます。 OneLink APIでは、以下のことができます。

* 短縮リンクをプログラムから<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelink-v2-create-link">作成</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link">取得</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-v2-link">更新</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-v2-link">削除</Anchor>する。
* より詳細な計測を行うために、アトリビューションパラメーター（例：メディアソース、キャンペーン、アセット）を動的に追加する。  
  **注意：** メディアソース（pid）パラメーターは必須です。
* パーソナライズされたリダイレクトパラメーターやディープリンクパラメーターを追加し、商品ページ、クーポン、プロモーションなど、ユーザーごとに最適化されたアプリ内またはWeb上のコンテンツへ誘導する。
* 大量の短縮リンクや<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-qr">QRコード</Anchor>を自動生成する。
* ユースケースに応じて、TTL（Time To Live：有効期間）や更新時の動作をカスタマイズする。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-onelink-short-url-ttls-automatically-extend">詳細はこちら</Anchor>
* 厳格なパラメーターバリデーションにより、想定どおりのリダイレクト動作と安定した計測を実現する。
* 利用量を管理するため、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota">クオータ使用状況を取得</Anchor>する。

> 📄 **例**
>
> あるグローバル旅行アプリでは、CRM、メール、QRコードなどのユーザー体験を通じて、コンテキストに応じた数百万件の短縮リンクを毎日生成しています。 OneLink API v2.0を活用し、地域、ロイヤルティランク、特定のアプリ内遷移先に応じて、ユーザーごとのディープリンクを自動生成しています。同時に、すべての市場でガバナンスを維持し、一貫した計測を実現しています。

## 利用開始手順

**OneLink APIの利用を開始するには、以下の手順を行います。**

**前提条件：** AppsFlyerアカウント。 OneLink APIを利用するには、CSMまたはhello@appsflyer.comまでお問い合わせください。

**OneLink APIの設定手順：**

1. <Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#トークンの種類">OneLink APIトークン</Anchor>を生成します（管理者権限が必要です）。
2. <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレートを作成</Anchor>します。
3. テンプレートIDをコピーします。   
   [![](https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg)](https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg)
4. テンプレートIDとAPIトークンを開発者に共有し、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelinkapi_v2_overview">こちらの手順</Anchor>に従って実装するよう依頼します。

## **ダッシュボード**

OneLink APIダッシュボードでは、日次、月次、および直近3か月のAPI利用状況を確認できます。月間クオータ上限に対する利用状況を把握するのに役立ちます。 

**OneLink APIダッシュボードの確認方法：** 

AppsFlyerのサイドメニューから、**［エンゲージメント］** > <strong>［OneLink API］</strong>の順に選択します。

## ユースケース

以下では、OneLink APIを使って、コンテキストに応じたスムーズなアプリへの導線を構築する代表的なユースケースを紹介します。

<div id="crossplatform-journeys-ctv-desktop-webtoapp" />

<Accordion title="クロスプラットフォームジャーニー（CTV、デスクトップ、Web-to-app）">

有効期間の短いリンクやセッション単位のリンクを生成し、ユーザーがデバイス間をスムーズに移動できるようにします。代表的な例として、テレビ広告に表示するQRコードや、デスクトップ上の「スキャンして続行」フローがあります。ユーザーをアプリ内の適切なステップへ直接誘導できます。

**メリット：** デバイスをまたいだスムーズな体験の継続とコンバージョンの向上。

</Accordion>

<div id="crmpowered-channels-sms-email-whatsapp" />

<Accordion title="CRMを活用したチャネル（SMS、メール、WhatsApp）">

値下げ通知、ウェイトリスト、休眠ユーザーの呼び戻し、請求リマインダー、マジックリンクによるサインインなど、ユーザーの意向が高いメッセージを送信する際に、ユーザーごとにパーソナライズされた短縮リンクを生成します。

**メリット：** 一貫したアトリビューションを維持しながら、大規模なパーソナライゼーションを実現。

</Accordion>

<div id="offline-and-qrbased-engagement" />

<Accordion title="オフライン／QRコードを活用したエンゲージメント">

店頭ツール、レシート、商品パッケージ、イベント会場の掲示物などに掲載できる、スキャン可能なリンクを生成します。印刷物などの物理アセットを作り直すことなく、リンクの遷移先設定を後から更新できます。

**メリット：** 物理アセットを再印刷することなく、動的なルーティングとオフラインアトリビューションを実現。

</Accordion>

<div id="referral-and-advocate-sharing" />

<Accordion title="紹介／アドボケイトによるシェア">

インフルエンサー、クリエイター、顧客による紹介プログラム向けに、パラメーターをカスタマイズでき、アトリビューションに対応した共有用短縮リンクを作成できます。

**メリット：** 紹介施策を大規模に計測し、正確にアトリビューション。

</Accordion>

## **特性と制限事項**

このセクションでは、OneLink APIの主な特性と制限事項を紹介します。詳細は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelinkapi_v2_overview">完全な一覧</Anchor>を参照してください。

| 特性 | 備考 |
| --- | --- |
| APIクオータ上限 | <ul><li>OneLink APIを使用したOneLinkリンクの作成、編集、削除は、アカウントごとに月間750万リクエスト（UTC基準）が上限です。</li><li>POST、PUT、DELETEリクエストは、この上限の対象としてカウントされます。 GETリクエストおよびGET QRリクエストは、クオータにはカウントされません。</li><li>クオータを超過した後のリクエストは処理されません。APIコールにはステータスコード429と「Monthly quota exceeded」というメッセージが返されます。</li><li>クオータの使用量と残量は、以下のいずれかの方法で確認できます。<br />• AppsFlyerプラットフォームのOneLink APIページで、過去4か月の利用履歴を確認する<br />• GET quota APIを使用して、現在のクオータ状況を取得する<br />また、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota">GET quota API</Anchor>を使用し、利用量が設定したしきい値に近づいた際に社内アラートを発報することもできます。</li></ul> |
| リンクの表示 | <ul><li>API経由で作成したリンクは、AppsFlyerダッシュボードのOneLinkカスタムリンク一覧には表示されません。</li></ul>**ベストプラクティス：** APIで作成したリンクは、後から参照できるようローカルテーブルに保存しておくことを推奨します。 |

> 📘 **注意**
>
> OneLink APIの新バージョン（v2.0）は、2025年12月にリリースされました。旧バージョン（v1.0）は非推奨となっており、2026年6月までは引き続き動作しますが、それ以降はメンテナンスされません。新規連携では、OneLink API v2.0を使用してください。移行方法については、Dev Hubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/migrate_to_onelink_api_v2">移行ガイド</Anchor>を参照してください。

<div data-zendesk-anchors="onelink-api=onelink-api%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HJR5MAKKNH236MVDZ03X1B1P=onelink-api%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HJR5MAKKTDRPS0WQ44VN594X=%E4%BE%8B get-started=%E5%88%A9%E7%94%A8%E9%96%8B%E5%A7%8B%E6%89%8B%E9%A0%86 h_01KATK4KWTGSHTW5BEY8TEE5JD=%E5%88%A9%E7%94%A8%E9%96%8B%E5%A7%8B%E6%89%8B%E9%A0%86 dashboard=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89 h_01KATKWCPHZB1MKCJ8DVDYZ1B3=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89 use-cases=%E3%83%A6%E3%83%BC%E3%82%B9%E3%82%B1%E3%83%BC%E3%82%B9 h_01KAGQNZZA0NM19KV29QZ9ZDKP=%E3%83%A6%E3%83%BC%E3%82%B9%E3%82%B1%E3%83%BC%E3%82%B9 h_01KBJ92FSTKCH9KXGWKJAF1DFH=crossplatform-journeys-ctv-desktop-webtoapp h_01KBJ92FST51NKDB465N76EX3M=crmpowered-channels-sms-email-whatsapp h_01KBJ92FST5H7V5S13TZ502VJV=offline-and-qrbased-engagement h_01KBJ92FST4FP4ZES5T643DD3R=referral-and-advocate-sharing traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KAGQP00QZ2VBE9EY3SNPHGBP=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KAGM8HN6FHRK73FSF0TGXSX7=%E6%B3%A8%E6%84%8F" />
