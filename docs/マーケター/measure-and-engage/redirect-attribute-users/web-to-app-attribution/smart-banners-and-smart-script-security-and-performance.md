---
title: Smart BannersとSmart Scriptのセキュリティとパフォーマンス
metadata:
  keywords:
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-01-30T14:54:37Z'
  edited_at: '2026-10-28T09:20:07Z'
  id: 22082177372561
  locale: ja
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ja/articles/22082177372561
---
> **概要：** Smart BannersとSmart Scriptのセキュリティに関する懸念に対し、AppsFlyerがどのような対策を講じているかを説明します。

このQ&Aでは、Smart BannersとSmart Scriptの実装に関するよくある質問を、セキュリティとサイトの表示速度への影響を中心に紹介します。

## Smart BannersのAPIのセキュリティ

<div id="what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it" />

<Accordion title="Smart Bannerのクリック時や表示時には、どのようなデータを取得しますか？">

| データ | 説明 |
| --- | --- |
| クライアントIP | 位置情報（国、地域、州）の判定に使用します。 |
| イベント時刻 |  |
| ユーザーエージェント |  |
| Webサイトのページ | Web SDKの呼び出し元のURL。 |
| HTTPプロトコル | HTTP/HTTPS |
| ヘッダー | Host, Content-type, Origin, Content-length, Encoding |
| OneLinkのパラメータ |  |
| バナーのパラメータ | バナーの設定項目：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers#dismissal-behaviour">バナーを閉じた後の再表示設定</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers#param-table">受信パラメータ</Anchor></li><li>UTMパラメータ</li><li>AppsFlyerのパラメータ</li><li>デフォルトのパラメータ</li><li>その他のパラメータ</li></ul> |

</Accordion>

<div id="what-api-calls-are-needed-to-show-a-smart-banner" />

<Accordion title="Smart Bannerの表示には、どのようなAPI呼び出しが必要ですか？">

* `https://websdk.appsflyersdk.com`のCDNからSDKを取得するAPI。
* CTAのリンクを生成するAPI。エンドポイントは`banner.appsflyer.com`です。このAPIは、SDKの[showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner)メソッドで呼び出されます。
* `creatives-cdn-appsflyer.com`のCDNからバナーのクリエイティブを取得するAPI。

</Accordion>

<div id="do-these-api-calls-include-an-identifier" />

<Accordion title="これらのAPI呼び出しには識別子が含まれますか？">

はい。お客様固有のWebキーがAPI呼び出しの識別子として使用されます。このキーを基に、バナー表示に必要なデータの取得と、CTAに設定するOneLink URLの生成が行われます。

</Accordion>

<div id="is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key" />

<Accordion title="悪意のある第三者がURLやAPIのWebキーを変更できますか？">

いいえ。バナーのAPI呼び出しに使用するWebキーを決定するコードには、アクセスも変更もできません。そのため、悪意のある第三者がバナーの処理や、CTA用に生成されるOneLink URLを改ざんすることはできません。

</Accordion>

## Smart Bannersのスクリプト配信に関するセキュリティ

<div id="can-clients-host-a-copy-of-the-smart-banner-script-on-their-server" />

<Accordion title="Smart Bannersのスクリプトをコピーして、自社サーバーでホスティングできますか？">

Smart Bannersのスクリプトは、自社サーバーでホスティングできません。ただし、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor>でOneLink URLを生成し、独自のバナークリエイティブを実装することは可能です。

Smart Scriptと独自のバナーを組み合わせると、クリエイティブを自由にデザインでき、生成するリンクのマッピングやカスタマイズも行えます。WebサイトへのバナーSDKの実装や、外部APIの呼び出しは不要です。

</Accordion>

<div id="can-clients-host-their-own-code-and-still-use-banners" />

<Accordion title="独自のコードをホスティングしながら、バナーを利用できますか？">

バナーのデザイン、開発、サイトへの実装を自社で行い、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor>でバナーのCTA用リンクを生成できます。

</Accordion>

<div id="can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page" />

<Accordion title="ページにコードスニペットを埋め込まずに、Smart Bannersを利用できますか？">

* コードスニペットを直接実装する代わりに、タグマネージャーを使用してSmart BannersのAPIを呼び出せます。タグマネージャーの詳細は、<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-website-code-implementation-for-marketers#webサイトへのコード実装">こちら</Anchor>を参照してください。
* iFrame内でのスクリプトの実行には対応していません。

</Accordion>

<div id="how-does-appsflyer-protect-your-banners-from-postsave-tampering" />

<Accordion title="保存後のバナーの改ざんを、AppsFlyerはどのように防いでいますか？">

AppsFlyerのクリエイティブエディターでバナーを編集・保存する際に、攻撃者がリクエストを傍受して乗っ取り、有害なJavaScriptコードを挿入しようとする可能性があります。

AppsFlyerでは複数の対策を講じ、Smart Bannersへの攻撃や、ユーザーによる自分のアカウント以外への不正な編集を防いでいます。

* セキュリティチームがテストと確認を実施し、Smart Bannersを含むすべてのサービスが保護され、脆弱性がないことを確認しています。
* AppsFlyerの安全性とセキュリティを確認するため、独立した立場からの客観的なペネトレーションテストを定期的に実施しています。
* 内部ではHTMLタグとスクリプトタグを検証し、悪意のあるスクリプトを無害化しています。

</Accordion>

<div id="do-smart-banners-use-cookies" />

<Accordion title="Smart BannersはCookieを使用しますか？">

デフォルトでは、Smart BannersはCookieを使用しません。ただし、データをより安定して保持したいお客様向けに、ファーストパーティCookieを使用する任意の設定を提供しています。たとえば、iOS 26のSafariでストレージ内のデータが安定して保持されない問題への対応に利用できます。

Webサイトの所有者が、このオプションを明示的に<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#set-storage-mode-optional">有効にする</Anchor>必要があります。有効にした場合、Webサイトの所有者は、適用される法令に従ってCookie同意の管理方法とプライバシーに関する開示内容を更新する責任も負います。

</Accordion>

## Smart Bannersのパフォーマンス

<div id="does-the-smart-banner-web-sdk-impact-website-load-speed" />

<Accordion title="Smart BannersのWeb SDKは、Webサイトの読み込み速度に影響しますか？">

Webサイトへのコードの追加は読み込み時間に影響する可能性がありますが、Smart Bannersの処理の大半はサーバー側で非同期に行われ、ページの読み込みを妨げません。

また、ページやバナーをすばやく読み込めるよう、CDNを使用しています。

</Accordion>

<div id="can-you-share-some-metrics-regarding-banner-speed-performance" />

<Accordion title="バナーの表示速度について、具体的な数値を教えてもらえますか？">

バナーの読み込み速度は、以下を含むさまざまな要因によって変わります。

* インターネット回線の速度
* 接続状況と接続方式
* サイトのパフォーマンスなど。

これらの要因と、AppsFlyerのサーバーからブラウザーへの短い応答時間を合わせたものが、バナーの読み込み時間になります。

上記の変動要因はAppsFlyer側で管理するものではないため、処理全体にかかる正確な時間は提示できません。

</Accordion>

<div id="how-can-i-actively-improve-the-banner-loading-time" />

<Accordion title="バナーの読み込み時間を短縮するには、どうすればよいですか？">

バナーの読み込み時間は、主にバナー画像に関係するLargest Contentful Paint（LCP）の影響を受けます。 LCPの改善には、以下の方法があります。

* サイズの小さいバナーテンプレートを選択します。
* ロゴや背景画像のサイズを小さくします。
  * 背景画像を単色の背景に置き換えると、素材の読み込み時間を短縮できます。
  * バナー画像をCDNでホスティングし、読み込みを高速化します。

* バナー全体で同じフォントの太さを使用します。

</Accordion>

## Smart Scriptのセキュリティとパフォーマンス

<div id="does-smart-script-use-cookies" />

<Accordion title="Smart ScriptはCookieを使用しますか？">

いいえ。Smart ScriptではCookieを使用しません。

</Accordion>

<div id="does-smart-script-make-any-external-calls-to-generate-links" />

<Accordion title="Smart Scriptは、リンクの生成時に外部への呼び出しを行いますか？">

いいえ。スクリプトはお客様のWebサイト上でローカルに実行されるため、外部への呼び出しに依存せず、安全に使用できます。

</Accordion>

<div id="is-there-a-download-time-associated-with-smart-script" />

<Accordion title="Smart Scriptのダウンロードには時間がかかりますか？">

スクリプトをWebサイトに直接埋め込めるため、ダウンロード時間は発生しません。サーバーの呼び出しが不要なため、スクリプトをすばやく読み込めます。

</Accordion>

<div data-zendesk-anchors="smart-banners-api-security=smart-banners%E3%81%AEapi%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3 h_01HNDDT0XHK5Y5NYTQMSXYSCZ4=smart-banners%E3%81%AEapi%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3 h_01HNDDT0XHY7BZNXA2CRT1W46F=what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it h_01HNDDT0XJGFJE3XBAXTE0C2K5=what-api-calls-are-needed-to-show-a-smart-banner h_01HNDDT0XJVX8KXSZC10GTJMCS=do-these-api-calls-include-an-identifier h_01HNDDT0XJ7MGPFSZKJ7YRZ2HJ=is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key smart-banners-script-hosting-security=smart-banners%E3%81%AE%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E9%85%8D%E4%BF%A1%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3 h_01HNDDT0XJSS77BFVVT2QQV5HP=smart-banners%E3%81%AE%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%83%88%E9%85%8D%E4%BF%A1%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3 h_01HNDDT0XJYW3Y0MQZWW1C1ETJ=can-clients-host-a-copy-of-the-smart-banner-script-on-their-server h_01HNDDT0XJG1SKBMA14KBGKZGD=can-clients-host-their-own-code-and-still-use-banners h_01HNDDT0XJDEGBK5WTBJ52ZVST=can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page h_01HNDDT0XJC7FT514HEGN68T68=how-does-appsflyer-protect-your-banners-from-postsave-tampering h_01HNDDT0XJR4BQPN20FNGJPARY=do-smart-banners-use-cookies smart-banner-performance=smart-banners%E3%81%AE%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9 h_01HNDDT0XJNJXY52BZJS9T1G72=smart-banners%E3%81%AE%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9 h_01HNDDT0XJ456B4DG38BMMP98W=does-the-smart-banner-web-sdk-impact-website-load-speed h_01HNDDT0XJSEXVNRT8H27EMCNS=can-you-share-some-metrics-regarding-banner-speed-performance h_01HNDDT0XJK99RH6MAJFGQ7FPX=how-can-i-actively-improve-the-banner-loading-time smart-script-security-and-performance=smart-script%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%81%A8%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9 h_01HNDDT0XJSGVRA6SB2YYYAE0P=smart-script%E3%81%AE%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%81%A8%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9 h_01HNDDT0XJW9B4GJ3J4RMJDG6V=does-smart-script-use-cookies h_01HNDDT0XJNZXGPZN2NDHQ34KF=does-smart-script-make-any-external-calls-to-generate-links h_01HNDDT0XJXV12C5P1CD32FZW3=is-there-a-download-time-associated-with-smart-script" />
