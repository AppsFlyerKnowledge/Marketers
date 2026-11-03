---
title: PBA ブランドバンドルの設定
metadata:
  keywords:
    - Advertisers
    - Bundles
    - Web Attribution
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2026-10-14T09:34:10Z'
  id: 360000646498
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360000646498
---
> **概要：** ブランドバンドルによって、そのブランドに関連するアプリやWebサイトのアトリビューション、イベント、訪問数、収益の情報を統合することが可能です。ブランドバンドルの設定ページを使えば、コンバージョンイベントをマークしたり、Google Adsとの連携もできます。

![BrandBundles.png](https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png)

## ブランドバンドルについて

今日、多くの企業がWebとモバイルの両方を含むエコシステムでブランドを運営しています。広告主として、Webとモバイルの両方のプラットフォームでブランドのパフォーマンスを把握したいと思うのは当然でしょう。PBAでは、ブランドバンドルを利用することでモバイルとWebのデータを1つにまとめ、分析とローデータの取得を可能にします。

> 📘 **Webアプリとは？**
>
> Webアプリとは、パフォーマンスを計測したいWebサイトを特定する<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">AppsFlyerで作成／追加したアプリ</Anchor>を指します。
>
> * Webアプリは2022年2月9日にAppsFlyerに追加されました。それ以前は、ブランドバンドルの作成時に、ブランドバンドルのドメインの別の設定として入力していました。今後は、まずドメインを定義するWebアプリを作成し、その後バンドルの作成時にそのWebアプリを含める必要があります。
> * 2022年2月9日の時点で既存のブランドバンドルが存在する場合は、**My Apps**ページにそれらのブランドバンドルに対応するWebアプリが表示されます。<strong>ご安心ください！</strong>Webトラフィックは、以前と同様にアトリビューションされており、PBAダッシュボードやローデータレポートに他の変更はございません。

**ブランドバンドルの基本：**

* ブランドバンドルには、1つのWebアプリ*（必須）*と1つまたは複数のモバイルアプリ*（任意）*が含まれています。
* アプリ（Webまたはモバイル）は1つのバンドルにのみ属することができます。
* [元のバンドルを削除](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle)しない限り、アプリをバンドルから削除したり、別のバンドルに移動したりすることはできません。
  * バンドルを削除すると、AppsFlyerはそのバンドルのPBAデータのアトリビューションを停止し、過去のデータへもアクセスできなくなりますのでご注意ください。

## ブランドバンドルへのアクセス

**ブランドバンドル**ページへアクセスして、ブランドバンドルとその設定を管理してください：

* - または -

## ブランドバンドルの管理

ブランドバンドルの追加、削除、管理を行うには、**ブランドバンドル**ページから以下の3つのうち1つのオプションを選択してください：

| 任意 | 詳細 |
| --- | --- |
| ブランドバンドルを追加 |  |
| PBA管理画面 | ブランドの管理画面を開きます |
| ブランドバンドルID | ブランドバンドルIDをクリップボードにコピーします |
| Web Dev Key | Web Devキーをクリップボードにコピーします |
| 既存のバンドルを選択して設定とオプションの更新 | 利用可能なオプション：<ul><li>イベントをコンバージョンイベントとしてマーク：<ul><li>[Webイベントの設定](/docs/pba-brand-bundles-and-settings#web-event-settings)</li></ul></li><li>[ドメイン除外](/docs/pba-brand-bundles-and-settings#domain-exclusion)</li><li><Anchor target="_blank" href="/marketers/ja/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Adsの連携</Anchor></li></ul> |
| 削除アイコン | [選択したブランドバンドルを削除します](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle)（削除することを確認したあとに実行されます） |

<div id="add-brand-bundle" />

<Accordion title="ブランドバンドルの追加">

先に進む前に、バンドルに追加したい全てのアプリがアカウントに追加されていることを確認してください。一度ブランドバンドルを作成すると、[バンドルを削除](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle)し再度作成しない限り、バンドルに含まれるアプリを変更することはできません。

ブランドバンドルを追加する方法：

1. [ブランドバンドル](/docs/pba-brand-bundles-and-settings#ブランドバンドルへのアクセス)ページから、**ブランドバンドルを追加**をクリックしてください。
2. **ブランドバンドル名**（バンドルを識別するための任意の名前）を入力してください。
3. バンドルに含めるアプリを選択してください。

   **注記：** 注記：他のバンドルに含まれているアプリは選択できません。

   * * バンドルの作成にモバイルアプリは必須ではありません。
     * バンドルに含めるモバイルアプリの個数に上限はありません。
4. バンドルを作成をクリックしてください。

> 🚧 **重要！**
>
> 以下の場合は、ブランドバンドルを作成できません。
>
> * バンドルに含めるために選択されたWebアプリが有効なURLにポイントしていない場合。
> * バンドルに含めるために選択されたWebアプリとAndroidモバイルアプリが同じアプリIDを持っている場合。

</Accordion>

<div id="web-event-settings" />

<Accordion title="Webイベントの設定">

Webイベントには、**スタンダード**と**コンバージョン**の2つのタイプがあります。最適化作業にフォーカスして優先順位をつけるために、いくつかのイベントをコンバージョンイベントとして設定してください。

* PBAでは、スタンダードイベントとコンバージョンイベントを同じ方法で計測します。
* <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータ</Anchor>レポートには、両方のイベントが含まれます。
* PBAの管理画面には、コンバージョンイベントのみが表示されます。
* イベントタイプはいつでも変更できますが、変更内容は過去分に遡って反映されません。

**コンバージョンイベントの設定：**

1. [ブランドバンドル](/docs/pba-brand-bundles-and-settings#ブランドバンドルへのアクセス)ページから、ブランドバンドルを選択してください。  
   **ブランドバンドルを更新**ページが開きます。
2. **Webイベント設定**のタブへ移動してください。
3. 必要であれば、**コンバージョンイベント** としてマークしてください。
4. **バンドルを更新**をクリックしてください。

</Accordion>

［デフォルト仕様］収益を含むアプリ内イベントが、コンバージョンイベントとしてマークされます。**ご注意ください**デフォルトのイベントから変更する場合には、収益を含むイベントもご自身でマークする必要があります。

**アプリ内イベントをコンバージョンイベントとしてマークするには：**

1. [ブランドバンドル](/docs/pba-brand-bundles-and-settings#ブランドバンドルへのアクセス)ページから、ブランドバンドルを選択してください。  
   **ブランドバンドルを更新**ページが開きます。
2. **アプリ内イベントの設定タブ**へ異動してください。
3. 必要であれば、**コンバージョンイベント** としてマークしてください。
4. **バンドルを更新**をクリックしてください。


<div id="domain-exclusion" />

<Accordion title="ドメイン除外">

<Anchor target="_blank" href="/marketers/ja/docs/pba-media-source-attribution-rules">PBAのメディアソースルールの一部である</Anchor>ドメイン除外のメカニズムは、以下のことを防止するために実装されています：

* 自己アトリビューションセルフアトリビューション：つまり、AppsFlyerは、イベントをWebアプリ自体で定義されたWebサイトや、そのWebサイトに紐づく指定したドメインにアトリビューションしません。
* ブランドの一部ではないものの、ユーザーのフローに含まれているドメインに関連付けられたイベントは紐付け / 記録します。例：支払い用のゲートウェイ

| ドメインタイプ | 説明 | 除外による影響 |
| --- | --- | --- |
| プライマリ | ブランドバンドルに含まれているWebアプリのドメイン。これにはサブドメインも含まれます。<br /><br />例：あなたのドメインがmydomain.co.za だった場合、a.mydomain.co.zaやb.mydomain.co.zaなどのサブドメインは自動的に除外されます。<br /><br />Webアプリを削除し再度作成しない限り、Webアプリのドメインは変更できません（これはWebアプリが含まれているバンドルを削除することを意味します）。 | セルフアトリビューションなし |
| 内部ドメイン | ブランドを形成するその他のドメインをリストアップしてください。（例：mydomain.com、mydomain.in、mydomain.co.ng、abc.com） | セルフアトリビューションなし |
| 外部ドメイン(ユーザーによるリストアップ) | Webサイトが直接使用しているドメインですが、ブランドの一部ではないものです。これには、支払いゲートウェイ、支払い処理サイト等が含まれます。 | <Anchor target="_blank" href="/marketers/ja/docs/pba-media-source-attribution-rules#visit-recognition-rules">訪問は無視されます</Anchor> |
| 外部ドメイン(AppsFlyerによるリストアップ) | AppsFlyerによってリストアップされ、常に除外されるドメインです。<ul><li>PayPal</li><li>Stripe</li><li>Adyen</li></ul>自動ドメインのリストは編集できません。 | <Anchor target="_blank" href="/marketers/ja/docs/pba-media-source-attribution-rules#visit-recognition-rules">訪問は無視されます</Anchor> |

**社内外のドメインを除外するには：**

1. [ブランドバンドル](/docs/pba-brand-bundles-and-settings#ブランドバンドルへのアクセス)ページから、ブランドバンドルを選択してください。  
   **ブランドバンドルを更新**ページが開きます。
2. **ドメイン除外のタブ**を開いてください。
3. **ドメインを追加**をクリックしてください。
4. ドメイン名を入力してください。
6. **ドメインを追加**をクリックしてください。  
   除外ルールが有効になるまで、約1時間掛かります。

</Accordion>

## よくある質問

<div id="can-i-include-the-same-app-in-more-than-one-bundle" />

<Accordion title="一つのアプリを複数のバンドルに含めることはできますか？">

<strong>いいえ。</strong>いいえ、アプリが1つのバンドルに追加された場合、他のバンドルにはそのアプリを追加できません。

</Accordion>

<div id="can-i-add-or-remove-apps-after-creating-a-bundle" />

<Accordion title="バンドル作成後に、アプリの追加または削除は可能ですか？">

<strong>いいえ。</strong>いいえ。一旦バンドルが作成されると、バンドルに含まれるアプリを変更することはできません。

どうしてでしょう？各アプリは独自のデータを持っており、AppsFlyerはこのデータを使用してプラットフォーム（Webとアプリ）全体のユーザージャーニーを分析します。アプリを変更してしまうと、異なるデータセットがプロセスに導入され、以前のデータとの互換性がなくなってしまいます。

</Accordion>

<div id="how-do-i-add-or-remove-delete-apps-from-a-bundle" />

<Accordion title="バンドルにアプリを追加したり削除するにはどうすればいいですか？">

アプリが含まれるバンドルを変更するには、元のバンドルを削除し、アプリを含む新しいバンドルを作成する必要があります。

</Accordion>

<div id="what-happens-if-i-delete-a-bundle" />

<Accordion title="バンドルを削除するとどうなりますか？">

#### よくある質問 バンドルを削除するとどうなりますか

バンドルを削除すると、以下のことが発生します：

* AppsFlyerはそのバンドルへのアトリビューションを停止します。
* バンドルのデータは保持されます（つまり、永久に削除されるわけではありません）が、データを確認するためにバンドル自体を復元することができません。

  <strong>どうしてでしょう？</strong>新しいバンドルでは異なるWeb dev keyを使用するため、同じアプリが含まれていても元のバンドルは復元されません。

</Accordion>

<div id="why-are-certain-apps-not-available-for-me-to-add-to-a-bundle" />

<Accordion title="バンドルに追加できないアプリがあるのはなぜですか？">

* **管理者**アドミン：バンドル作成時にアプリが選択できない場合、アプリがAppsFlyerアカウントに追加されていて、さらに別のバンドルに追加されていないことを確認してください。
* 他のアカウントユーザー：追加しようとしているアプリへアクセスするための役割と権限が付与されていることをアカウントアドミンに確認してください。

</Accordion>

<div data-zendesk-anchors="about-brand-bundles=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HE0Y2A3A5W86YY44RWCTKM1Y=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HE0Y2A3AYAFFSPRSH2BQ00Z3=web%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A8%E3%81%AF accessing-brand-bundles=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01HE0Y2A3A7265NYM7GVBZVXEN=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 managing-brand-bundles=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%81%AE%E7%AE%A1%E7%90%86 h_01HE0Y2A3A272QJ4ZQH7VXJWCC=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%81%AE%E7%AE%A1%E7%90%86 h_01HE0Y2A3ATX4ZDYZSRQGSJ4G7=add-brand-bundle h_01HE0Y2A3AQC5MMNQA0AV34MZ3=%E9%87%8D%E8%A6%81 h_01HE0Y2A3ATN6DEQ2KHCGT6VPQ=web-event-settings h_01HE0Y2A3A7F2YEW2SK0PSXXE4=domain-exclusion faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HE0Y2A3AB24NCNPAYFC0J4YH=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HE0Y2A3A5E816CYG2TMZ37DA=can-i-include-the-same-app-in-more-than-one-bundle h_01HE0Y2A3BENKY1AM51VM76TVS=can-i-add-or-remove-apps-after-creating-a-bundle h_01HE0Y2A3BK4JKMTND0JFCB179=how-do-i-add-or-remove-delete-apps-from-a-bundle h_01HE0Y2A3BKJTQZJXV49X32N1E=what-happens-if-i-delete-a-bundle faqs-what-happens-if-i-delete-a-bundle=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F-%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%82%92%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B%E3%81%A8%E3%81%A9%E3%81%86%E3%81%AA%E3%82%8A%E3%81%BE%E3%81%99%E3%81%8B h_01HE0Y2A3B276FV92EYBCZRA6C=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F-%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%82%92%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B%E3%81%A8%E3%81%A9%E3%81%86%E3%81%AA%E3%82%8A%E3%81%BE%E3%81%99%E3%81%8B h_01HE0Y2A3BEB2JG8CPSX3DA1V9=why-are-certain-apps-not-available-for-me-to-add-to-a-bundle h_01HE0Y2KTXS06WHN57MQ91AD09=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F-%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%82%92%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B%E3%81%A8%E3%81%A9%E3%81%86%E3%81%AA%E3%82%8A%E3%81%BE%E3%81%99%E3%81%8B" />
