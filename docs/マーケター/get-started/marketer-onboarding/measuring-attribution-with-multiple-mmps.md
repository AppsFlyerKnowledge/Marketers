---
title: 複数のMMPによるアトリビューション測定
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-07-27T08:29:19Z'
  edited_at: '2026-10-14T09:30:09Z'
  id: 17316973509393
  locale: ja
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ja/articles/17316973509393
---
> **概要：** 概要： 複数のMMPを同時に操作した場合、アトリビューションを測定できるメディアソースを確認し、AppsFlyerと他のMMPの計測結果を比較できます。

<div id="overview" />

## 概要

別のMMPからAppsFlyerへの移行を検討する際、広告主は、同じメディアソースとキャンペーンで両方のMMP測定値を同時に比較する場合があります。これを行うには、次の要件を満たす必要があります。

* テスト対象のアプリには **両方のMMP SDKが統合されている**必要があります
* メディアソースは、**2つの MMP によるアトリビューションをサポートするように構成する**必要があります

ただし、すべてのメディアソースが複数の MMP での測定をサポートしているわけではありません。

<div id="details-and-limitations-of-media-source-measurement" />

## メディアソース測定の詳細と制限

複数のMMPを同時に操作する場合のメディアソース測定の詳細と制限を示します。

<div id="self-reporting-networks" />

### セルフレポーティングネットワーク

| SRN | 詳細と制限事項 | 測定の対応 |
| --- | --- | --- |
| Apple検索広告 | ASA は、制限なく複数の MMP 測定をサポートします。複数のMMPからAPI呼び出しリクエストがある場合、データは対応するMMPに送信されます。 | ✓ |
| DV360 (GMP) | MMPは複数可能ですが、キャンペーン設定では、フラッドライトのトラッキング（リンク ID）ごとに個別のライン項目を設定する必要があります。 | ✓ |
| Google Ads | Google広告では、複数のMMP測定がサポートされています。<ul><li>広告主は、複数の MMP リンク ID を 1 つの Google 広告アカウントにリンクし、各 MMP からポストバックを受け取ることができます</li><li>Google 広告は複数の MMP からポストバックを受け取ることができます</li><li>複数のMMP性能が測定可能です</li></ul>**注意：** 注： 新しい MMP にデータが流れるようになると、既存の連携の停止をおすすめします。 | ✓ |
| Meta ads | Meta広告は、複数のMMPからデータリクエストを受信します。しかしながら、以下の理由から、複数のMMPを**持たない**ことを強く推奨しています。<ul><li>Meta広告はインストール時の重複除去のみ処理でき、イベントに対しては処理できません。したがって、イベントは 1 つの MMP からのみ送信する必要があります</li><li>MMP から複数の SDK を挿入する場合、重複排除プロセス中に問題や二次エラーが発生する可能性が非常に高くなります</li><li>Meta広告に大量のデータが送信されると、2倍のデータが最適化システムや測定システムに送り込まれる可能性があります。</li></ul>したがって、複数のMMPアトリビューションは短期的にのみサポートされます。 | 制限あり |
| Snapchat | Snapchatと複数のMMP間でデータを転送することが可能です。ただし、重複する移行期間を最小限に抑えることをお勧めします。複数のMMPデータを受信する場合、特定のMMPを選択して最適化するオプションはありません。これは両方のMMPに対して最適化が実行され、データが重複する可能性が高いことを意味します。 | 制限あり |
| TikTok for Business | TikTok for Businessへのポストバック送信は、1つのMMPでのみサポートされています。別のMMPから移行する場合、AppsFlyerがコンバージョンをTikTok for Businessにアトリビュートできるようにするには、まず他のMMPからのポストバックをオフにしてからAppsFlyerを設定する必要があります。 | x |
| X Ads | X Adsは複数のMMP連携をサポートしていません。 | x |

### SKAN

<div id="non-srn-ad-networks" />

### SRN以外のアドネットワーク

MMPアトリビューションリンクは、SRN以外の広告ネットワークでのユーザーのエンゲージメントを記録し、その後、実際のインストールになるエンゲージメントをアトリビューション（計測）するために使用されます。複数のMMPのアトリビューションを同時に有効にするには、広告ネットワークで以下の要件を満たしていることを確認する必要があります：

| アドネットワーク要件 | 詳細 |
| --- | --- |
| エンゲージメントのデータ１つを両方の MMP に送信する必要があります | <ul><li>**クリック数:** クリック： 計測リンクはユーザーをアプリストアにリダイレクトします。したがって、使用できる計測リンクは1つだけです。既存のMMPの計測リンクを引き続き使用しながら、 <Anchor target="_blank" href="/partners/ja/docs/redirecting-users-to-the-app-store#概要">S2SクリックアトリビューションデータをAppsFlyerに送信する</Anchor>ことをお勧めします。</li><li>インプレッションインプレッション： インプレッションはユーザーをアプリストアにリダイレクトしないため、広告ネットワークは両方のMMPにインプレッションデータを送信する必要があります。</li></ul> |
| 受信したインストールポストバックは重複排除する必要があります | アドネットワークは、両方の MMP からインストールポストバックを受け取ります。二重請求を避けるために、アドネットワークはこれらのポストバックの 1 つを重複排除する必要があります。 |
| 受信したアプリ内イベントのポストバックは重複排除する必要があります | 各MMPがアプリ内イベントポストバックを送信するように設定されている場合、アドネットワークは両方のMMPからアプリ内イベントポストバックを受信します。二重計測による二重請求を避けるために、アドネットワークはこれらのポストバックの 1 つを重複排除する必要があります。アドネットワークが二重のアプリ内イベントポストバックを重複排除できない場合は、アプリ内イベントポストバックがMMP１つでのみ設定されていることを確認してください。 |

<div id="owned-media" />

### オウンドメディア

SRN以外のアドネットワークと同様に、オウンドメディアからインストールを計測するには、MMP計測リンクを使用する必要があります。ただし、メーリングリスト、SMS、QRコードなどの一部の種類のオウンドメディアでは、MMPは1回のエンゲージメントで一度だけデータを送信できます。AppsFlyerの <Anchor target="_blank" href="/marketers/ja/docs/convert-your-mobile-web-visitors-to-app-users">モバイルウェブ間アトリビューション</Anchor> ソリューションでは **ウェブサイトやランディングページからのインストール**を測定できます。MMPアトリビューションの比較にオウンドメディアを使用する利点は、インストールやイベントの重複排除が必要ないことです。

<div id="avoiding-attribution-discrepancies" />

## アトリビューション不一致の回避

* 両方の MMP がアプリに同じタイムゾーンを使用していることを確認します。<Anchor target="_blank" href="/marketers/ja/docs/changing-app-time-zone-settings">AppsFlyerでアプリのタイムゾーンを設定する</Anchor>方法は次のとおりです。
* たとえば、両方のMMPで同じルックバック期間を設定します。
* MMP ダッシュボードまたはレポートのデータを比較する場合は、同じ日付範囲のトラフィックや地域など、同じ条件を必ず比較してください。

<div data-zendesk-anchors="ability-to-measure-with-multiple-mmps=%E6%A6%82%E8%A6%81 01H7TP9P86DE0J04VHXJYKE3PA=%E6%A6%82%E8%A6%81 details-and-limitations-of-media-source-measurement=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E6%B8%AC%E5%AE%9A%E3%81%AE%E8%A9%B3%E7%B4%B0%E3%81%A8%E5%88%B6%E9%99%90 01H81ANMGMEKCZCS2FNBY67321=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E6%B8%AC%E5%AE%9A%E3%81%AE%E8%A9%B3%E7%B4%B0%E3%81%A8%E5%88%B6%E9%99%90 selfreporting-networks=%E3%82%BB%E3%83%AB%E3%83%95%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF 01H81APGNBGCMREZVFXJW9KN6H=%E3%82%BB%E3%83%AB%E3%83%95%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF 01H7TP9P86YQ75N0XFY7EW2JHQ=skan nonsrn-ad-networks=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF 01H7TP9P86TEWC47MZZVQ1965K=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF owned-media=%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 01H7W2YTXYMAEN403WCHYH8G7W=%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 avoiding-attribution-discrepancies=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E4%B8%8D%E4%B8%80%E8%87%B4%E3%81%AE%E5%9B%9E%E9%81%BF 01H7YVHVW3YY8XY8GHQX1B0WZN=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E4%B8%8D%E4%B8%80%E8%87%B4%E3%81%AE%E5%9B%9E%E9%81%BF" />
