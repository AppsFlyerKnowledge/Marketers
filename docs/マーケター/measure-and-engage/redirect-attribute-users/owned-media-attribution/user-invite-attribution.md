---
title: ユーザー招待の計測
metadata:
  keywords:
    - OneLink
    - Advertisers
    - User invite
    - Developers
    - Marketers
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2017-08-30T12:13:45Z'
  edited_at: '2026-10-14T09:35:55Z'
  id: 115004480866
  locale: ja
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ja/articles/115004480866
---
> **概要：** 既存ユーザーが他のユーザーにアプリを紹介した際に、「ユーザー招待経由」として新規インストールを計測します。

[![Invite_Attribution_new.png](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)

## ユーザー招待の計測について

ユーザー招待とは、既存のアプリのユーザーがリンクを共有し、他のユーザー（例えば、その友人）にアプリをダウンロード / 開くように誘導することです。

ユーザー招待の計測とは、新しいアプリのインストールやエンゲージメントを、紹介を行ったユーザーに紐づけることを意味します。

ユーザー招待の計測でできること：

* ユーザー招待のコストとROIを分析します。ユーザー招待は、広告収益を生成するために使用できるアプリの広告スペースを利用できます。ユーザー招待が他の方法よりもROIが高いかどうかを確認できます。
* 他のユーザーを最も多く紹介したユーザーの情報を記録します。アプリに他のユーザーを招待するユーザーは、価値が高く、エンゲージメントの高いユーザーであり、リターゲティングやインセンティブの提供を希望するかもしれません。

リンク先のデータを利用することもできます：

* 招待経由でインストールした新しいユーザーのアプリ導線をカスタマイズ：例えば、アプリ起動時に特定のコンテンツ画面を表示したり、一般的なメッセージの代わりに、"XXさん、ようこそ！あなたの友人 マリアがゲームに挑戦したいと言っています。今すぐプレイしましょう！” のようなウェルカムメッセージをパーソナライズしたりします。
* 紹介したユーザーにインセンティブを付与する：[詳細はこちら](/docs/user-invite-attribution#reward-referrers-for-user-invite-installs)

ユーザーが他のユーザーに共有するユーザー招待リンクは、実際にはアプリに実装されたAppsFlyer SDKによって生成されたOneLinkのカスタムリンクです。OneLinkの設定により、招待を受けたユーザーが正しい場所にリダイレクトされるようにします。正しいアプリストアに、アプリに、またはアプリの特定の画面にディープリンク / ディファードリンクされるようにします。<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">[OneLinkの詳細はこちら]</Anchor>

### フロー

フローは次のとおりです：

1. ユーザーAが、アプリ内から「友人招待」をタップして、アプリを友人に共有（ユーザーAはアプリを持っていて、ログインしています）
2. タップすると、ユーザーAを識別するパラメータが付いたリンクが生成されます。
3. ユーザーAはユーザーBにメールやWhatsApp、SMSなどでリンクを送信します。
4. ユーザーBが -
   * 既にアプリを所持している場合、アプリを直接起動します。（この時にアプリ内の特定の画面にディープリンクさせたり、インセンティブを受け取ることができます。）
   * アプリをインストールしていない場合、正しいアプリストアに遷移させます。（ユーザーBのアプリ初回起動後に、アプリ内の特定の画面へディファードディープリンクさせることができ、また、ユーザーAは報酬を得ることができます。）
   * アプリ内イベントを実施すると、ユーザーAは報酬を得ることができます。

## データの確認

ユーザー招待のデータは、AppsFlyerのダッシュボードやレポートから入手できます。AppsFlyerのダッシュボードでは、ユーザー招待のアトリビューションを以下の方法でフィルターすることができます。

* **メディアソース：** App invite
* **チャネル：** マーケターが決定した値（例：アプリ名など）
* **キャンペーン：** マーケターが決定した値

レポートでは、メディアソース（ `pid` パラメーター）はSDKにより、デフォルト値の `af_app_invites` で送信されます。

## 手順

**ユーザー招待リンクの作成方法：**

1. <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>を作成します。
2. チャネルとキャンペーンのパラメータ値を決定します。詳細：[パラメータ](/docs/user-invite-attribution#parameters)
3. リンクに必要なユースケースを決めます。一般的な使用例：
   * 新規ユーザーをアプリ内の特定画面にディープリンクする
   * どのユーザーが紹介したかを計測する（CUIDベース）
   * 新規ユーザーへのインセンティブ付与
4. AndroidとiOSの開発者と連携し、リンクに求めるユースケースをどのパラメータで担当するか計画します。参照：利用可能な[パラメータ](/docs/user-invite-attribution#parameters)
5. 開発者に、コード内のパラメータの希望する動作を使用して、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">ディープリンクを実装</Anchor>するよう依頼します。
6. 次のプラットフォームでユーザー招待を実装するように開発者に指示します：

   <Tabs>
   <Tab title="Android">

   AppsFlyer公式デベロッパーハブの[Androidユーザー招待](https://dev.appsflyer.com/hc/docs/dl_android_user_invite)を参照してください。

   </Tab>

   <Tab title="iOS">

   AppsFlyer公式デベロッパーハブの[iOSユーザー招待](https://dev.appsflyer.com/hc/docs/dl_ios_user_invite)を参照してください。

   </Tab>

   <Tab title="Unity">

   AppsFlyer公式デベロッパーハブの[ユーザー招待](https://dev.appsflyer.com/hc/docs/userinvite)を参照してください。

   </Tab>
   </Tabs>

<div id="parameters" />

<Accordion title="パラメーター">

#### SDKに実装するため開発者に提供されるパラメータ / 値

<table><thead><tr><th>パラメータ / 値</th><th>備考</th><th>開発者が実装すべき値 / ユースケース</th></tr></thead><tbody><tr><td>OneLinkテンプレートID</td><td>すべてのユーザー招待リンクのベースとなる、基本設定と動作が構成されているOneLinkテンプレートのID例：H5hv</td><td> </td></tr><tr><td>チャネル</td><td>チャネル名AppsFlyer管理画面でチャネルごとに計測値をソート・フィルターして表示するのに役立ちます。</td><td> </td></tr><tr><td>キャンペーン</td><td>キャンペーン名AppsFlyer管理画面でキャンペーンごとに計測値をソート・フィルターして表示するのに役立ちます。</td><td> </td></tr><tr><td> <span>is_retargeting=true</span><br/> </td><td>既存ユーザーのCV計測を目的としたキャンペーンの場合に追加します。</td><td> </td></tr><tr><td>deep_link_value</td><td>紹介されたユーザーの端末で、特定の挙動を提供するために使用されるパラメータ。通常、これはユーザーがリダイレクトされる特定のページの名前付けに使用されます。たとえば、アプリがフルーツを販売している場合、ユーザーをリンゴページにディープリンクできます。</td><td> </td></tr><tr><td>deep_link_sub1</td><td rowspan="10">紹介されたユーザーの端末で、特定の挙動を提供するために使用されるパラメータ。deep_link_value は通常、ユーザーをアプリ内の特定の画面に誘導するために使用されるため、このパラメータは他の任意の機能に使用することができます。例：インセンティブやディスカウントを付与 / 紹介したユーザーを計測、など </td><td> </td></tr><tr><td>deep_link_sub2</td><td> </td></tr><tr><td>deep_link_sub3</td><td> </td></tr><tr><td>deep_link_sub4</td><td> </td></tr><tr><td>deep_link_sub5</td><td> </td></tr><tr><td>deep_link_sub6</td><td> </td></tr><tr><td>deep_link_sub7</td><td> </td></tr><tr><td>deep_link_sub8</td><td> </td></tr><tr><td>deep_link_sub9</td><td> </td></tr><tr><td>deep_link_sub10</td><td> </td></tr><tr><td>[オプション] pid</td><td><p>デフォルトでは、生成するリンクには、 値 <code>af_app_invites</code> を持つメディアソース（ <code>pid</code> パラメータ）が含まれます。 </p><p>値を変更するには、開発者は必要な値で呼び出される <code>pid</code> カスタムパラメーターを追加する必要があります。　<strong>注：</strong>Androidの場合、これはSDK V6.4.2以降でのみサポートされています。</p></td><td> </td></tr><tr><td>ブランド名</td><td>ブランドドメイン名。AppsFlyer UIでブランドドメインごとにアトリビューションを並べ替えたり、表示するのに役立ちます。</td><td> </td></tr></tbody></table>

</Accordion>

<div id="example" />

<Accordion title="例">

マーケターのマークは、果物を販売するアプリを持っています。彼は、ユーザーを特定のフルーツのページにディープリンクさせ、特定の量のフルーツを購入できるようなリンクを作りたいと考えています。

このリンクをユーザー招待で送ることができ、その紹介が新しいアプリのインストールや果物の購入につながるたびに、紹介者に報酬が与えられるようにしたいとのことです。

これを実現するために、Markは開発者に次のようなパラメータと値のリストを送り、ユーザー招待リンクの実装を依頼しました：

| パラメータ | 値 | 備考 |
| --- | --- | --- |
| deep\_link\_value | fruit\_name | AppsFlyerのUDL APIを使ったディープリンクに対応 |
| deep\_link\_sub1 | promo\_code | AppsFlyerのUDL APIを使ったディープリンクに対応 |
| deep\_link\_sub2 | referrer\_id | SDKでのリンク作成用 |
| param\_1 | referrer\_id | 購入のたびに計測されるアプリ内イベント |
| チャネル | mobile\_share | アトリビューション表示、およびAppsFlyerでデータを確認するため |
| キャンペーン | summer\_sale | アトリビューション表示、およびAppsFlyerでデータを確認するため |

</Accordion>

## 追加情報

<div id="record-user-invites-as-inapp-events" />

<Accordion title="ユーザー招待をアプリ内イベントとして計測">

ユーザーがユーザー招待を送信した際にアプリ内イベントを計測することで、他人を紹介したユーザーや、紹介者を獲得したメディアソースを特定することができます。

**ユーザー招待のアプリ内イベントを計測するには：**

* <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#invite-af_invite">af\_inviteイベント</Anchor>を送信します。開発者が、AppsFlyer公式デベロッパーハブの手順に従って実装する必要があります。

**注：** イベントに紐付けたいパラメータをさらに追加することができます。イベントに追加のコンテキストを提供し、データをより充実させるパラメーターを選びます。<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">詳細はこちら</Anchor>

</Accordion>

<div id="reward-referrers-for-user-invite-installs" />

<Accordion title="ユーザー招待のインストールで紹介者にインセンティブを付与する">

**インストールに至ったユーザー招待の紹介者に報酬を与えるには：**

1. リファラーIDが [deep\_link\_sub1-10 パラメーター](/docs/user-invite-attribution#parameters)のいずれかに含まれていることを確認してください。
2. 開発者に、コード内のパラメータの希望する動作を使用して、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">ディープリンクを実装</Anchor>するよう依頼します。
3. バックエンドの開発者に、アプリの開発者と協力して（AppsFlyerのレポートから）リファラーIDを取得し、リファラーに報酬を与えるよう伝えてください。

例：

1. ユーザーAが、ユーザーBにあなたのアプリをインストールするように誘いました。
2. ユーザーBがアプリを起動すると、アプリはユーザーAのリファラーIDを取得します。
3. バックエンドは、AppsFlyerのレポートからリファラーIDを取得します。
4. バックエンドで、報酬を受け取るユーザーのリストにユーザーAのリファラーIDを追加します。
5. ユーザーAがアプリを起動した際に、リファラーIDが報酬対象ユーザーリストにあるかどうかを確認し、該当する場合に報酬を与えます。

</Accordion>

<div id="reward-referrers-for-referred-user-actions" />

<Accordion title="紹介されたユーザーのアクションに対して紹介者にインセンティブを付与する">

**特定のアプリ内イベントが発生したユーザー招待に対して、紹介者に報酬を与えるには：**

1. 報酬を付与したい<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#アプリ内イベントの設定">アプリ内イベントを作成</Anchor>します。
2. イベントにパラメータ (例えば param\_1) を追加し、その値をリファラーIDにするように開発者に指示します。　**注：** リファラーIDは、もともとアプリインストール時に、お客様が選択した パラメータ (deep\_link\_sub1-10) を使って記録されます。
3. バックエンドの開発者に、アプリの開発者と協力して（AppsFlyerのレポートから）リファラーIDを取得し、リファラーに報酬を与えるよう伝えてください。

例：

1. ユーザーAは、ユーザーBにアプリ内のアクションを実行するように誘います。
2. ユーザーBがアクションを実行すると、ユーザーAのリファラーIDを含むアプリ内イベントが計測されます。
3. バックエンドは、AppsFlyerのレポートからリファラーIDを取得します。
4. バックエンドで、報酬を受け取るユーザーのリストにユーザーAのリファラーIDを追加します。
5. ユーザーAがアプリを起動した際に、リファラーIDが報酬対象ユーザーリストにあるかどうかを確認し、該当する場合に報酬を与えます。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 説明 |
| --- | --- |
| SDKバージョン | AppsFlyer SDKのバージョン4.8.0以降、およびUnity SDKのバージョン4.17.0以降。 |
| <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">ソーシャルメディアアプリのランディングページ</Anchor> | ユーザー招待で生成されたリンクは、ソーシャルメディアアプリのランディングページには設定できません。 |
| リンクの有効期限（TTL） | SDKユーザー招待によって作成されたOneLinkショートURLのデフォルトの有効期間（TTL）は 60日です。TTLは、リンクがクリックされるたびに60日間延長されます。 |
| 料金 | すべてのアカウントプランで無料で利用できます。 |
| iOS 14以降 | ユーザー招待の計測はIDFAを使用しないため、iOS 14の影響は一切ありません。 |
| URL ID | URL ID（またはショートリンク ID）を編集して、キャンペーンのオファー内容を強調して表示できます。例：[https://myapp.onelink.me/abc123/apples](https://myapp.onelink.me/abc123/apples)　ー　URL IDは文字と数字の組み合わせで最大50文字まで設定できます。デフォルト：8文字のランダムな英数字<br /><br />**注：** URL IDを編集できるのは、現在のIDがまだ使用されていない場合のみです。 |

</Accordion>

<div data-zendesk-anchors="about-user-invite-attribution=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%8B%9B%E5%BE%85%E3%81%AE%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01H98E1CZ2AG8AW2H77SPPHFGR=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%8B%9B%E5%BE%85%E3%81%AE%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 flow=%E3%83%95%E3%83%AD%E3%83%BC h_01H98E1CZ234MRBWDEYGZFCDRE=%E3%83%95%E3%83%AD%E3%83%BC viewing-data=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01H98E1CZ23FEAS8JJC7FFTFXD=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D procedures=%E6%89%8B%E9%A0%86 h_01H98E1CZ2VBCG0RREERW8FNJE=%E6%89%8B%E9%A0%86 h_01H98E1CZ2WE6DJW717C6AJWXD=parameters parametersvalues-provided-to-the-developer-to-implement-in-the-sdk=sdk%E3%81%AB%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E3%81%9F%E3%82%81%E9%96%8B%E7%99%BA%E8%80%85%E3%81%AB%E6%8F%90%E4%BE%9B%E3%81%95%E3%82%8C%E3%82%8B%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF--%E5%80%A4 h_01H98E1CZ2CANBK1T55DD103JB=sdk%E3%81%AB%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E3%81%9F%E3%82%81%E9%96%8B%E7%99%BA%E8%80%85%E3%81%AB%E6%8F%90%E4%BE%9B%E3%81%95%E3%82%8C%E3%82%8B%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF--%E5%80%A4 h_01H98E1CZ2NXCCYEV12JC6EMFG=example additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01H98E1CZ28T2SJ3YNY8TNCAZY=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01H98E1CZ2172W6845K099F814=record-user-invites-as-inapp-events h_01H98E1CZ316WWYK55XTN4C8JE=reward-referrers-for-user-invite-installs h_01H98E1CZ330FXG06A4MVQ56PW=reward-referrers-for-referred-user-actions h_01H98E1CZ3SPASZDF5CCY3T3B3=traits-and-limitations" />
