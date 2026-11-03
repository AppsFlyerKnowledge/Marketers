---
title: Smart Banners｜モバイルWebからアプリへの誘導（マーケター向け）
metadata:
  keywords:
    - Landing Page
    - Advertisers
    - Web Attribution
    - Developers
    - Smart Banner
    - sb
    - Marketers
    - Banner
    - Banners
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-01-14T12:33:07Z'
  edited_at: '2026-10-28T09:20:16Z'
  id: 360000764837
  locale: ja
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ja/articles/360000764837
---
> **概要：** Smart Bannersを使って、Webサイトの訪問者をモバイルアプリのユーザーへ誘導します。

[![](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)

> 📘 **注意**
>
> AppsFlyerのSmart Banners Web SDK v1は、2023年11月8日をもって非推奨となりました。 WebサイトにSmart Bannersを表示するには、v2へのアップグレードが必要です。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">詳細はこちら。</Anchor>

## Smart Banners

Smart Bannersでは、次のことができます。

* **自社ブランドのモバイルWebサイトにバナーを表示**し、関心の高いユーザーのコンバージョン率を高めます。
* モバイルWebサイトの訪問者によるアプリのインストールの質を計測します。
* SRNを含むすべてのメディアソースについて、Webキャンペーンからモバイルアプリへの成果を正確に紐づけます。
* Smart Bannersは、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#ユーザーの広告接触に基づくアトリビューションの種類">ビュースルーアトリビューションとクリックスルーアトリビューション</Anchor>に対応し、インプレッションもカウントできます。
  * **クリック：** ユーザーがSmart Bannerをクリックし、インストールへ進みます。
  * **インプレッション：** バナーが読み込まれ、ユーザーに表示されると、インプレッションをカウントするイベントがAppsFlyerに送信されます。

ユーザーの経路は次のとおりです。

1. ユーザーが広告をクリックし、広告主のモバイルWebサイトへ移動します。
2. 広告主のモバイルWebサイトにSmart Bannerが[表示](/docs/smart-banners-mobile-web-to-app-for-marketers#banner-group-display-logic)されます。
3. ユーザーがSmart Bannerをクリックすると、次のように動作します。
   * **アプリがインストールされていない場合**は、アプリストアへ移動してインストールします。
   * **アプリがインストール済みの場合**は、Universal Links、App Links、URIリンクのいずれかが設定されていれば、アプリが直接起動します。
4. ユーザーは、プロモーションに関連するアプリ内コンテンツに到達します。
5. ユーザーの成果は、最初の広告を表示したメディアソースに紐づきます。

**担当者**

* Webサイトの開発者が行うのは、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#installation">WebサイトのHTMLにコードスニペットを挿入する作業</Anchor>だけです。
* その他の作業は、マーケターだけで対応できます。

---

**前提条件**

* 少なくとも1つのアプリが登録されたAppsFlyerアカウント
* Smart Bannersで宣伝するアプリを含む<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">OneLinkテンプレート</Anchor>。訪問者のデバイスに応じて適切なアプリストアのページへ誘導するために必要です。

---

**所要時間**

約20分。

---

**設定後にできること**

* Webサイトの訪問者がCTAボタンをクリックすると、デバイスに応じたアプリストアまたはWebページへ移動します。
* すでにモバイルアプリを利用しているユーザーは、CTAボタンのクリック後、ディープリンクでアプリ内へ誘導できます。
* クリックやインストールが、元のメディアソースまたは自社のオウンドメディアに紐づきます。
* バナーのパフォーマンスは、パフォーマンスページとカードで確認できます。

---

---

> 📄 **例**
>
> マークは、好調なフードデリバリーサービス「Feed Me」のマーケターです。
>
> Feed MeのモバイルWebサイトの訪問者を、アプリユーザーへ誘導したいと考えています。
>
> そこで、独自の画像やテキストを使ったSmart Bannersを活用します。
>
> Smart Bannersは、OneLinkを基盤としています。モバイルWebサイトの訪問者がCTAボタンをクリックすると、**適切なアプリストアまたはランディングページへ自動的に移動**し、簡単にアプリをインストールできます。既存のモバイルユーザーがCTAボタンをクリックすると、アプリが起動します。
>
> AppsFlyerは、**クリックやインストールを、マークが指定したメディアソースとキャンペーンに紐づけます**。

> 🚧 **重要**
>
> AppsFlyerのSmart Bannersと、iOSのSafariのスマートアプリバナーは、どちらか一方だけを使用してください。併用すると、モバイルWebサイトでの表示の問題や、アトリビューションの不一致が発生する可能性があります。

## 設定

以下の手順で、次の機能を持つSmart Bannerを設定します。

* モバイルサイトからSmart Bannerを経由し、デバイスに応じたアプリストアまたはアプリ内のページへユーザーを誘導します。
* OneLinkを使用して、クリックやインストールを自社のオウンドメディアに紐づけます。

<div id="1-website-workplace-setup" />

<Accordion title="1. Webサイトのワークスペースの設定">

#### 初めてSmart Bannersを表示するためのモバイルサイトの準備

1. AppsFlyerのサイドメニューから、**［Engage］** > **［Web-to-app］** > **［Smart Banners］** > <strong>［Smart Bannersへ移動］</strong>を選択します。
2. <strong>［はじめる］</strong>をクリックします。設定ウィザードの案内に従って、以下の手順を進めます。 Webサイトのワークスペースを追加する場合は、後述の手順を参照してください。
3. Webサイトのワークスペース名を入力します。
4. <strong>［作成］</strong>をクリックします。 Webサイトのワークスペースが開きます。
5. バナーの**コードスニペット**をコピーします。
6. Webサイトにコードスニペットを実装します。この作業は、Webサイトごとに一度だけ行います。
   * Googleタグマネージャー、Adobe Tag Manager、Shopify、Wix、Squarespace、WordPressでWebサイトにコードを追加する方法は、<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-website-code-implementation-for-marketers">Smart Banners｜Webサイトへのコード実装（マーケター向け）</Anchor>を参照してください。
   * 他のプラットフォームでの実装や、要件に合わせたコードの変更（パラメータの追加、ディープリンク、バナーの非表示、PBAとSmart Bannersの連携など）については、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Smart Banners｜Webサイトへのコード実装（開発者向け）</Anchor>を参照してください。
7. ［任意］**Webキー**をコピーします。（このキーは、コードスニペットにも含まれています。）
8. <strong>［続行］</strong>をクリックします。

#### 2つ目以降のWebサイトのワークスペースを作成するには

1. AppsFlyerのサイドメニューから、**［Engage］** > **［Web-to-app］** > **［Smart Banners］** > <strong>［Studio］</strong>を選択します。
2. オプションメニューをクリックします。
3. <strong>［新しいWebサイトのワークスペース］</strong>を選択します。
4. Webサイトのワークスペース名を入力します。
5. <strong>［作成］</strong>をクリックします。 Webサイトのワークスペースが開きます。
6. バナーの**コードスニペット**をコピーします。
7. Webサイトにコードスニペットを実装します。この作業は、Webサイトごとに一度だけ行います。
   * Googleタグマネージャー、Adobe Tag Manager、Shopify、Wix、Squarespace、WordPressでWebサイトにコードを追加する方法は、<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-website-code-implementation-for-marketers">Smart Banners｜Webサイトへのコード実装（マーケター向け）</Anchor>を参照してください。
   * 他のプラットフォームでの実装や、要件に合わせたコードの変更（パラメータの追加、ディープリンク、バナーの非表示、PBAとSmart Bannersの連携など）については、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Smart Banners｜Webサイトへのコード実装（開発者向け）</Anchor>を参照してください。
8. ［任意］**Webキー**をコピーします。（このキーは、コードスニペットにも含まれています。）
9. <strong>［続行］</strong>をクリックします。

</Accordion>

<div id="2-banner-group-setup" />

<Accordion title="2. バナーグループの設定">

バナーグループには、1つ以上のバナーを含められます。ここでは、次の設定を行えます。

* Webサイトの訪問者の誘導先となるモバイルアプリを含む、バナーグループ用のOneLinkテンプレートを選択します。
* 特定のディープリンク用スキームを設定します。
* バナーグループ内のすべてのバナーに適用する、ターゲティングルール、配信スケジュール、表示動作、アトリビューションの詳細を設定します。
* どのページを訪問したときに、バナーグループ内のバナーを表示するかを設定します。

**バナーグループを設定または複製するには：**

1. AppsFlyerのサイドメニューから、**［Engage］** > **［Web-to-app］** > <strong>［Smart Banners］</strong>を選択します。
2. **初めてバナーグループを設定する場合**
   1. 左側の<strong>［バナーグループを追加］</strong>をクリックします。
   2. 手順5以降に進みます。
3. **バナーグループを追加する場合**
   1. <strong>［Studio］</strong>タブに移動します。
   2. <strong>［＋新規］</strong>をクリックします。
   3. 手順5以降に進みます。
4. **バナーグループを複製する場合**
   1. 削除アイコンの隣にある**複製**アイコンをクリックします。
5. 重複しない**バナーグループ名**を入力します。宣伝するアプリなど、グループ内に作成するバナーに共通するテーマが分かる名前にしてください。
6. バナーグループに使用するOneLinkテンプレートを選択します。
7. ［任意］Universal LinksやAndroid App Linksが機能しない場合の代替手段として、バナーグループに**URIスキーム**を設定します。デフォルトではOneLinkテンプレートの値が使用されるため、通常は設定不要です。テンプレートと異なる値が必要な場合にのみ、バナーグループ側で設定してください。
8. <span id="attributed-sources"></span>このバナーグループ経由の新規インストールについて、優先的に使用する**成果の紐づけ先**と、それを使用できない場合の代替の紐づけ先を設定します。   

   **クリックIDの引き継ぎに関する注意：** 受信URLにFBCLID、GCLID、WBRAID、GBRAID、ttclid、twclid、ScCidが含まれている場合、送信URLに自動で引き継がれます。 GoogleのクリックIDがあり、keywordパラメータも見つかった場合は、その値が送信URLのaf\_keywordsに設定されます。

   以下の表を参考に、カスタムリンクに最適な設定を選択してください。

<div id="param-table" />

| 選択肢 | 選択するケース | 補足 |
| --- | --- | --- |
| **UTMパラメータを使用** | 非オーガニック訪問者の大半が、UTMパラメータを付与した流入元からモバイルWebサイトへ訪問する場合に選択します。 | ◦ メディアソース名（pid）＝UTM\_Source  <br />◦ キャンペーン（c）＝UTM\_campaign  <br />◦ UTM\_sourceまたはUTM\_campaignがない場合は、代わりに固定の名前が使用されます。 |
| **受信アトリビューションリンクのパラメータを使用** | 非オーガニック訪問者の大半が、AppsFlyerのアトリビューションリンクを使用してクリックを計測するアドネットワークから、モバイルWebサイトへ訪問する場合に選択します。 | ◦ 受信したAppsFlyerのアトリビューションリンク内にある、利用可能なすべてのパラメータがSmart Bannerのリンクに追加されます。<br /><br />◦ 同じパラメータが受信したAppsFlyerのアトリビューションリンクとSmart Bannerの両方にある場合、最終的なカスタムリンクでは受信パラメータが優先されます。 |
| **アトリビューションパラメータを追加** | 必要に応じて、Webサイトに関連するアトリビューションデータを追加できます。これにより、インストールごとに詳しく分析できます。 | たとえばECサイトでは、商品カテゴリごとにaf\_adsetの値だけが異なるカスタムリンクを作成します（例：「af\_adset=fruit」）。 |
| **デフォルトのアトリビューションパラメータを使用** | ◦ 選択するケース： ▪ モバイルWebサイトの訪問者の大半がオーガニックである場合。   ▪ 非オーガニック訪問者の流入元が、クリックの計測に対応するアドネットワークでも、UTMパラメータを付与した流入元でもない場合。 ◦ パラメータの値はカスタマイズできます。 | **重要：** UTMパラメータまたは受信アトリビューションリンクのパラメータを選択することをおすすめします。メディアソース名、キャンペーン名、チャネル名を取得できない場合は、どちらを選んでも、Smart Bannerのデフォルトのアトリビューションパラメータが代替値としてカスタムリンクに使用されます。 |

9. ［推奨］Smart Banner経由のすべてのインストールを特定のチャネルに紐づけるには、デフォルトのアトリビューションパラメータで<strong>［チャネル名］</strong>を設定します。これにより、**コホートレポート**、**Overview dashboard**、**リテンションレポート**などで、複数のメディアソースの情報を同じチャネルとして集計できます。
10. <span id="2-banner-group-setup-step10"></span>［任意］バナーをクリックしたユーザーのリエンゲージメントをバナーグループで記録する場合は、<strong>［リターゲティング］</strong>を有効にします。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティングアトリビューションガイド</Anchor>を参照してください。

    > 🚧 **重要**
    >
    > リターゲティングを機能させるには、次の設定も必要です。
    >
    > * <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#アプリのリターゲティングの有効化">アプリのリターゲティングを有効にします</Anchor>。


    既存ユーザーがOneLinkを使用したリターゲティング以外のバナーリンク（UA）をクリックした場合も、同様にアプリが起動し、ユーザー体験は変わりません。ただし、この場合のリエンゲージメントは通常のセッションとして記録されるため、オウンドメディアキャンペーンの成果を計測できません。
11. ［任意］<strong>［アクティブユーザーをリターゲティング対象から除外］</strong>を有効にし、非アクティブ期間を選択します。バナーグループのリンクにaf\_inactivity\_window=[number of days]が追加され、指定した期間にアクティブだったユーザーはすべてリターゲティングの対象から除外されます。
12. リエンゲージメント後、アプリ内イベントをリターゲティングのメディアソースに紐づける期間を、リエンゲージメント期間として設定します。
    * 日単位（1～90日）、時間単位（最大23時間）、または無期限で設定できます。
    * リエンゲージメント期間は、リンクのaf\_reengagement\_windowパラメータに追加されます。
13. <span id="dismissal-behaviour"></span>［任意］<strong>［バナーを閉じた後の再表示設定］</strong>を設定します。これは、ユーザーがグループ内のバナーを閉じてから、同じバナーを再表示できるようになるまでの最短時間です。次のいずれかを選択します。
    * 時間を指定：1時間、1日、1週間。
    * 次のセッション：ユーザーがバナーを閉じた後、別のタブやウィンドウで開始するセッションを指します。
    * 再表示しない：そのバナーを再び表示しません。 **注意**：
      * ユーザーがブラウザーのキャッシュを削除した場合や、プライベートブラウジングモードでサイトを閲覧した場合、再表示設定の情報は失われます。
      * 再表示設定はユーザーが閉じたバナーに適用されます。同じグループ内の他のバナーは、引き続き表示できます。
14. ［任意］**［フリークエンシーキャップ］**（表示回数の上限）を設定します。  フリークエンシーキャップは、バナーグループ内の各バナーを、1人のユーザーに何回まで表示するかを定める設定です。常にバナーを表示する<strong>［上限なし］</strong>、または<strong>［バナーの表示回数を制限］</strong>を選択できます。

    たとえば、バナーグループに3つのバナーがあり、上限を1回に設定した場合、各バナーがユーザーごとに1回ずつ表示されます。この場合、ユーザーは3回の訪問でグループ内の3つのバナーをすべて見ることになります。 4回目以降の訪問では、そのグループのバナーは表示されません。上限を2回に設定した場合は、各バナーがユーザーごとに2回ずつ表示されるため、グループ全体の上限に達するまでに計6回の訪問が必要です。
15. ［任意］バナーを表示する**OS**を設定します。
    * すべてのモバイルOS。
    * Androidのみ、またはiOSのみ。
16. ［任意］バナーグループの配信**スケジュール**を設定します。すぐに開始する（デフォルト）か、配信期間を指定できます。
17. ［任意］バナーグループを表示する**地域**を設定します。
    1. すべてのユーザーに表示するには、<strong>［全世界］</strong>を選択します。必要に応じて、特定の地域、国、州からの訪問者を除外します。
    2. 1つ以上の特定の地域のユーザーに表示するには、<strong>［特定の地域を選択］</strong>を選択します。
18. ［任意］<strong>［表示対象のページ］</strong>で、バナーグループを表示するページを設定します。
    * ［デフォルト］Webサイトの<strong>［すべてのページに表示］</strong>。 **注意**：他の条件に当てはまらない場合にも表示できるよう、すべてのページを対象とするバナーグループを少なくとも1つ作成することをおすすめします。
    * **［特定のページに表示］**：バナーを表示する条件として、ページやURLに含まれる文字列、または含まれない文字列を指定します。
      * 次のいずれかを選択できます。
        * **［特定のページ］**：バナーを表示するページのホストやパスを指定します。クエリを入力しても無視されます。例：http://www.example.com/path?query
        * **［URLのパスとクエリ］**：バナーの表示条件となるパスやクエリを入力します。例：path?query。 **注意**：[http://www.example.com/path?query](http://www.example.com/path?query)のように、URL全体を入力しないでください。パスやクエリのみを入力します。

* AND／ORを使って、最大15個の条件を追加できます。
* 条件が矛盾する場合、バナーは表示されません。

1. <strong>［バナーグループを作成］</strong>をクリックします。
2. ［任意］バナーグループを再編集するには、<strong>［ターゲティングと表示動作］</strong>にカーソルを合わせ、<strong>［編集］</strong>をクリックします。

> 📄 **例**
>
> マークは、フードデリバリーサービス「Feed Me」のマーケターです。アプリで実施するプラムのセールに向けて、キャンペーンを作成することにしました。キャンペーンには、SMSの一斉配信に加え、アドネットワークとGoogleを利用します。
>
> マークはキャンペーンの準備として、次の設定を行います。
>
> * 受信リンクのアトリビューションパラメータとUTMパラメータの両方を使用する設定にします。どちらにも該当しないクリックには、代わりにデフォルトのパラメータを使用します。
> * Feed Meのモバイルサイトのプラムのセールページへユーザーを誘導するため、キャンペーン用の固有のアトリビューションリンクをアドネットワークに渡します。リンクには、セールページのURLを指定したリダイレクト先URL（af\_r）パラメータを含めます：`http://feedme.com/plums_link`。
> * 「plums\_utm」を含むモバイルWebページに訪問するユーザー向けに、Google広告キャンペーンを準備します。
> * SMS用には、Feed Meのモバイルサイトのプラムのセールページへ誘導するキャンペーンリンクに、固有のアトリビューションパラメータを追加します。リンクにはpidパラメータを含め、プラムのセールページへ誘導します：`http://feedme.com/plums_link?pid=sms&c=plums`。
>
> キャンペーンの配信を開始します。
>
> ユーザーは、次の経路をたどります。
>
> * プラムのセールの広告を見てクリックし、Feed Meのモバイルサイトに移動します。
> * Google広告を含むすべてのクリックは受信リンクのランディングページに到達し、ページに応じたSmart Bannerが表示されます。
> * モバイルサイトに表示されたSmart Bannerをクリックします。
> * Feed Meアプリのダウンロード先へ移動し、ダウンロードしてインストールします。
> * アプリを起動すると、プラムのセールへ誘導されます。
> * Feed Meのモバイルサイトへの訪問につながった、正しいメディアソースに成果が紐づきます。

#### ターゲティングと表示動作

［ターゲティングと表示動作］パネルでは、そのバナーグループに設定した内容を確認できます。編集するには、編集アイコンをクリックします。

</Accordion>

<div id="3-banner-setup" />

<Accordion title="3. バナーの設定">

**バナーグループ内にバナーを作成するには：**

1. <strong>［新しいバナー］</strong>をクリックし、<strong>［バナーを編集］</strong>ページを開きます。
2. バナーの**名前**を設定します。
3. <strong>［クリエイティブをデザイン］</strong>でクリエイティブを作成します。
   1. <strong>［クリエイティブをデザイン］</strong>をクリックして、バナーのクリエイティブを設定します。

      バナーテンプレートを選択するウィンドウが開きます。

      [![](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)
   2. **クリエイティブテンプレート**にカーソルを合わせて<strong>［作成］</strong>をクリックし、<strong>［クリエイティブを作成］</strong>の設定ページを開きます。
   3. Smart Bannerのクリエイティブの各要素をカスタマイズします。要素名から選択するか、プレビュー画像内の要素をクリックします。 **注意：** テンプレートによって、使用できる要素は異なります。
      * タイトル
      * 説明
      * 評価の星
      * 閉じるボタン
      * CTA
      * アプリのロゴ
      * 背景
      * バナーの表示位置
      * バナーの余白（サイズ調整用）
      * Device transparency
      * 画像はjpeg、jpg、pngのいずれかの形式を使用してください。 **注意**：webp形式には対応していません。  画像の推奨仕様は以下のとおりです。

| テンプレートの種類 | 画像ファイルの最大サイズ | 画像の縦横比 | 画像の高さ | 画像の幅 |
| --- | --- | --- | --- | --- |
| Minimal | 300 KB | 3:1（幅×高さ） | 70 px | デバイスに合わせて調整 |
| Standard | 300 KB | 3:1（幅×高さ） | 70 px | デバイスに合わせて調整 |
| Enhanced | 300 KB | 9:4（幅×高さ） | 110 px | デバイスに合わせて調整 |
| Multi-choice | 300 KB | 9:4（幅×高さ） | 110 px | デバイスに合わせて調整 |
| Promotional | 300 KB | 4:5（幅×高さ） | 300 px | デバイスに合わせて調整 |
| Multi-choice overlay | 300 KB | 9:4（幅×高さ） | 110 px | デバイスに合わせて調整 |
| Interstitial | 700 KB | 9:16（幅×高さ） | デバイスに合わせて調整 | デバイスに合わせて調整 |

   4. <strong>［レビュー］</strong>をクリックしてクリエイティブを確認し、各種デバイスでの表示をテストします。**注意**：実際の配信時には、プレビュー画像と表示が多少異なる場合があります。
   5. 変更が必要な場合は、<strong>［エディターに戻る］</strong>をクリックします。
   6. <strong>［完了］</strong>をクリックして、バナーの設定ページに戻ります。
4. ［任意］カスタムのアトリビューションパラメータを追加します。たとえば、`af_adset`や`af_ad`を追加できます。**注意**：`pid`、`c`、`channel`はバナーグループ単位のパラメータのため、個別のバナーには追加できません。
5. 新しいクリエイティブの作成が完了し、保存すると、バナーのステータスが有効になります。<strong>［ステータス］</strong>のトグルで、<strong>［有効］</strong>と<strong>［一時停止］</strong>を切り替えます。
6. <strong>［すべて保存］</strong>をクリックして変更を保存します。保存してバナーの設定ページを閉じる場合は、<strong>［すべて保存して閉じる］</strong>をクリックします。

> 📄 **例**
>
> 活用のヒントは、<Anchor target="_blank" href="https://drive.google.com/file/d/1mr6g3uNwlLw6UQ_WgtQZprJMhauw7Xi3/view?usp=sharing">Smart Bannersのクイックリファレンス</Anchor>を参照してください。

</Accordion>

<div id="4-testing" />

<Accordion title="4. テスト">

クリエイティブが完成したら、ユーザー向けに公開・配信する**前に**テストします。

**Smart Bannerのクリエイティブをテストするには：**

**前提条件：** WebサイトにSmart Bannersのコードスニペットが実装されていることを確認します。

1. <strong>［クリエイティブをテスト］</strong>ページに、Smart Banners SDKを実装したWebページのリンクを入力します（[Smart Bannersの開発者向けドキュメント](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2)を参照）。
2. <strong>［生成］</strong>をクリックします。
3. 生成されたリンクをコピーしてテストデバイスに送信するか、テストデバイスでQRコードを読み取ります。 **リンクを開くかQRコードを読み取ると、Webページへ移動し、作成したクリエイティブのバナーが表示されます。**
4. <strong>［クリエイティブを編集］</strong>をクリックすると設定に戻り、<strong>［完了］</strong>をクリックするとクリエイティブが保存されます。

</Accordion>

## バナーのパフォーマンスの確認

パフォーマンスページでは、すべてのバナーの成果を確認・比較できます。

特定のバナーの成果は、そのバナーのパフォーマンスカードですばやく確認できます。

バナーのパフォーマンスデータには、以下の指標が含まれます。

* インプレッション数
* バナーが閉じられた回数
* クリック数
* インストール数
* リエンゲージメント数
* リアトリビューション数
* クリック率（CTR）。計算式：クリック数／インプレッション数×100
* コンバージョン率（CVR）。計算式：アトリビューション数／クリック数×100

**注意**：

* データのタイムゾーンはUTCです。
* データは<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">継続</Anchor>して更新されます。
* データは、バナーとOneLinkテンプレートの単位で表示されます。そのため、バナーとOneLinkテンプレートに複数のアプリ（AndroidとiOSの両方など）が設定されている場合、表示されるパフォーマンスデータには複数のアプリが含まれます。
* ビュースルーとクリックスルーの両方のアトリビューションをカウントするため、CVRが想定より高くなり、100%を超える場合もあります。

<div id="performance-page" />

<Accordion title="パフォーマンスページ">

パフォーマンスページでは、すべてのSmart Bannersについて、最大過去90日分のパフォーマンスデータを確認・比較できます。

**パフォーマンスページを表示するには：**

1. AppsFlyerのサイドメニューから、**［Engage］** > **［Web-to-app］** > **［Smart Banners］** > <strong>［パフォーマンス］</strong>を選択します。
2. 成果を確認する期間を選択します。デフォルトの期間は過去7日間です。
3. ［任意］<strong>［現在有効なバナーのみ表示］</strong>を有効にします。有効にすると、選択した期間中に配信されていても、現在一時停止中または無効のバナーのデータは表示されません。選択した期間のパフォーマンスデータが表示されます。

</Accordion>

<div id="performance-cards" />

<Accordion title="パフォーマンスカード">

各バナーの過去7日間のパフォーマンスデータを確認できます。

**バナーのパフォーマンスを確認するには：**

1. AppsFlyerのサイドメニューから、**［Engage］** > **［Web-to-app］** > **［Smart Banners］** > <strong>［Studio］</strong>を選択します。
2. 成果を確認するWebサイトのワークスペースとバナーグループを選択します。
3. バナーグループ内のいずれかのバナーにカーソルを合わせます。過去1週間のパフォーマンスデータが表示されます。

</Accordion>

## 補足情報

<div id="banner-group-display-logic" />

<Accordion title="バナーグループの表示ロジック">

AppsFlyerは、Smart Bannerを表示するかどうか、また、どのバナーを表示するかを判断する際に、次の点を確認します。

* バナーグループにルール（再表示設定、フリークエンシーキャップ、地域、表示対象のページなど）が設定されているか。
* ユーザーがルールの条件を満たし、バナーの表示対象になっているか。

両方に該当する場合、つまりルールが設定されており、ユーザーが表示対象になっている場合は、以下の表のとおりに表示するバナーを選択します。

| バナーグループの設定 | 表示するバナー | 例 |
| --- | --- | --- |
| バナーグループが1つの場合 | すべてのバナーグループ内の有効なバナーが、対象ユーザーに均等な割合で表示されます。 | • 例1：有効なバナーが1つある場合。すべてのユーザーに表示されます。<br /><br />• 例2：バナーが2つある場合。ユーザーの50%にバナー1、残りの50%にバナー2が表示されます。<br /><br />• 例3：バナーが3つある場合、対象ユーザーの3分の1ずつに各バナーが表示されます。<br /><br />• 例4：有効なバナーがない場合。何も表示されません。 |
| 同じルールのバナーグループが複数ある場合 | すべてのバナーグループ内の有効なバナーが、対象ユーザーに均等な割合で表示されます。 | バナーグループAとBがあり、それぞれに3つずつ、合計6つのバナーがあります。対象ユーザーの6分の1ずつに各バナーが表示されます。 |
| 異なるルールのバナーグループが複数ある場合 | *ユーザーに一致する条件が最も具体的なバナーグループ*から、有効なバナーが均等な割合で表示されます。条件の種類が異なっていても、対象の絞り込みの度合いが同じであれば、それらすべてのグループのバナーが表示対象になります。 | • 例1：バナーグループAとBがあり、Aは全世界、Bは日本で表示する設定になっています。 Bのほうが条件が具体的なため、日本のユーザーにはBのバナーだけが表示されます。そのグループに有効なバナーがない場合は、何も表示されません。<br /><br />• 例2：バナーグループAとBがあり、Aは全世界、Bはウクライナ以外のすべての地域で表示する設定になっています。 Bのほうが条件が具体的なため、ウクライナ以外のユーザーにはBのバナーだけが表示されます。 Bに有効なバナーがない場合は、何も表示されません。ウクライナでは、バナーグループAが表示されます。<br /><br />• 例3：バナーグループAとBがあり、Aは日本で、Bは4月に表示する設定になっています。条件の種類は異なりますが、対象の絞り込みの度合いは同じです。そのため、4月の日本では、どちらのグループも優先されず、両方のグループのバナーが表示対象になります。 |

</Accordion>

<div id="ab-testing-banner-performance" />

<Accordion title="バナーのパフォーマンスのA/Bテスト">

パフォーマンスダッシュボードで成果を比較し、バナーのA/Bテストを行えます。アトリビューションに関するデータをさらに取得するには、クリエイティブまたはバナーグループごとに固有の値を設定した`af_adset`、`af_ad`などのパラメータを追加することをおすすめします。ただし、`pid`、`c`、`channel`は除きます。これらのパラメータを使い、AppsFlyerのダッシュボードやレポートでバナーグループごとの成果を比較できます。

</Accordion>

## よくある質問

<div id="why-does-my-banner-not-display" />

<Accordion title="バナーが表示されないのはなぜですか？">

バナーグループに設定したフリークエンシーキャップが原因です。フリークエンシーキャップは、1人のユーザーにバナーを何回まで表示するかを定める設定です。 たとえば上限を3回に設定し、ユーザーがサイトを4回訪問した場合、最初の3回はバナーが表示されますが、4回目以降は表示されません。フリークエンシーキャップは無効にできます。表示回数の上限を選択するか、フリークエンシーキャップを無効にしてください。

</Accordion>

<div id="can-i-use-my-own-font-for-my-banner" />

<Accordion title="バナーに独自のフォントを使用できますか？">

はい。[開発者ハブの手順](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#control-smart-banner-font)に従い、Webサイトで使用している独自のフォントをバナーにも設定できます。

* Webサイトの開発者による実装が必要です。
* そのフォントは、Webサイト上のすべてのバナーと、バナー内のすべてのテキスト要素に適用されます。
* クリエイティブエディターでは、そのフォントを確認できません。
* 実装後は、[バナーのクリエイティブをテストしてください](/docs/smart-banners-mobile-web-to-app-for-marketers#4-testing)。
* フォントが正しく表示されない場合は、[クリエイティブエディター](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup)でバナーを再保存してください。

</Accordion>

<div id="can-i-add-parameters-to-the-url-of-my-smart-banners" />

<Accordion title="Smart BannersのURLにパラメータを追加できますか？">

はい。Smart Script内で次の2つの関数を呼び出すことで追加できます。

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">showBanner</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor>

</Accordion>

<div id="do-smart-banners-support-deep-linking" />

<Accordion title="Smart Bannersはディープリンクに対応していますか？">

はい。以下のいずれかの方法で<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep\_link\_valueパラメータ</Anchor>を追加します。

* AppsFlyerの管理画面で、[バナーの設定](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup)時に固定値のカスタムアトリビューションパラメータを追加します。
* [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=)関数のadditionalParamsを使い、バナーの表示前にURLにパラメータを追加します。
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor>関数を使い、バナーの表示後にURLにパラメータを追加します。

deep\_link\_valueに応じて意図した動作になるよう、開発者が実装していることを確認してください。

</Accordion>

<div id="can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed" />

<Accordion title="ユーザーがアプリをインストール済みかどうかに応じて、Smart Bannersの表示内容を変えられますか？">

いいえ。インストール済みかどうかを把握できない場合は、どちらのユーザーにも適したCTAにすることをおすすめします。例：「アプリへ移動」「アプリを開く」。

</Accordion>

<div id="do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page" />

<Accordion title="ユーザーがバナーのランディングページから離れ、再び戻った場合も、元の受信URLのパラメータをSmart BannerのURLに使用できますか？">

はい。元の受信URLにutm\_sourceまたはpidパラメータが含まれていれば、ブラウジングセッション中は元のURLが保持され、バナーの送信URLにそのパラメータが適用されます。

</Accordion>

<div id="can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app" />

<Accordion title="モバイルサイトではバナーを表示し、ラッパーアプリやハイブリッドアプリでは非表示にできますか？">

はい。ラッパーアプリやハイブリッドアプリにSmart Bannersを実装し、Webブラウザーではなくアプリからバナーのページを読み込む場合は、アプリ内にバナーを表示する[showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=)関数を使用しないでください。または、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#hidebanner">hideBanner</Anchor>関数を使用してください。

</Accordion>

<div id="do-smart-banners-support-web-accessibility" />

<Accordion title="Smart BannersはWebアクセシビリティに対応していますか？">

AppsFlyerは、障害のある方を含むすべてのユーザーが、Smart Bannersに十分にアクセスし、利用できるよう取り組んでいます。

そのため、Smart Bannerの要素に必要なHTML属性を設定するなど、WCAG 2.1のベストプラクティスに従い、Webアクセシビリティへの対応を進めています。

ただし、Smart Bannersの使用目的に応じて適用されるアクセシビリティ要件を判断する責任は、お客様にあります。使用するSmart Bannersが、該当するWebアクセシビリティ要件に従って、引き続きすべてのユーザーに利用可能な状態にあることを保証する責任は、お客様にあります。

バナー内の要素の色やサイズの編集など、Smart Bannerへの各種変更によって、該当するアクセシビリティ要件への適合性が変わる可能性がある点にご注意ください。

</Accordion>

<div id="if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed" />

<Accordion title="バナーグループからSmart Bannerを削除すると、そのグループに関連するデータも削除されますか？">

いいえ。 Smart Bannerを削除しても、アトリビューションデータは削除されません。

</Accordion>

## トラブルシューティング・特性・制限事項

| 項目 | 説明 |
| --- | --- |
| バナーの表示割合 | 有効なバナーは、ユーザーに均等な割合で表示されます。特定のバナーの表示を増やしたり減らしたりすることはできません。たとえば、グループ内にバナーが2つある場合、ユーザーの50%ずつに各バナーが表示されます。 70%と30%の割合に変更することはできません。 |
| カスタムパラメータ | • カスタムパラメータでは、次の特殊文字を使用できません：;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, / • これらの特殊文字を使用して定義したパラメータは保存されません。 |
| 名前の変更 | バナーグループ名とバナー名は変更できます。パフォーマンスデータには影響せず、そのまま引き継がれます。 |
| 閉じるボタンが押された回数 | 2026年2月17日以降のデータを利用できます。データの保持期間は90日です。 |
| 特定のページ | 特定のページでバナーを表示するようバナーグループを設定した場合、入力したホストやパスに対してのみ、そのルールが適用されます。完全に一致しない場合（サイトのページに、ルールの設定に含まれない文字列が付いている場合など）は、ルールが適用されません。 |
| タブレット | • Smart Bannersはモバイルデバイス向けに設計されており、大画面のタブレットでは解像度が最適化されていない場合があります。 • タブレットのブラウザーが、モバイルデバイスとして認識されない場合があります。 |
| バナーの横に空白の領域が表示される | この現象が発生した場合は、以下の点を確認して原因を調べてください。<ul><li>WebページにSDKのコードスニペットを重複して実装していないか確認します。</li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">`showBanner`</Anchor>関数を複数回呼び出していないか確認します。</li></ul> |

<div data-zendesk-anchors="h_01HB5W700P3GP7JS4PFDF65EWT=%E6%B3%A8%E6%84%8F h_01HB5W700PWY5G45BYNWPKAC52=smart-banners h_01HB5W700QQMYSEFBBXVJ97M0M=%E4%BE%8B h_01HB5W700QGWTWDXBNB2GAPQ3B=%E9%87%8D%E8%A6%81 setup=%E8%A8%AD%E5%AE%9A h_01HB5W700QVNYJT48VAP9Y7HQS=%E8%A8%AD%E5%AE%9A h_01HB5W700Q7G5E98V0DBN9P5VZ=1-website-workplace-setup prepare-your-mobile-site-to-display-smart-banners-for-the-first-time=%E5%88%9D%E3%82%81%E3%81%A6smart-banners%E3%82%92%E8%A1%A8%E7%A4%BA%E3%81%99%E3%82%8B%E3%81%9F%E3%82%81%E3%81%AE%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E6%BA%96%E5%82%99 h_01HB5W700QE7MDBSN5GH4E7ABR=%E5%88%9D%E3%82%81%E3%81%A6smart-banners%E3%82%92%E8%A1%A8%E7%A4%BA%E3%81%99%E3%82%8B%E3%81%9F%E3%82%81%E3%81%AE%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E6%BA%96%E5%82%99 to-create-website-workplaces-after-the-first-time=2%E3%81%A4%E7%9B%AE%E4%BB%A5%E9%99%8D%E3%81%AEweb%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E3%83%AF%E3%83%BC%E3%82%AF%E3%82%B9%E3%83%9A%E3%83%BC%E3%82%B9%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01HB5W700Q57WXKFSWXNF22QZ1=2%E3%81%A4%E7%9B%AE%E4%BB%A5%E9%99%8D%E3%81%AEweb%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E3%83%AF%E3%83%BC%E3%82%AF%E3%82%B9%E3%83%9A%E3%83%BC%E3%82%B9%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01HB5W700QY1FH2SYX6DM4HDEQ=2-banner-group-setup h_01HDH1BQSXCQV9QCJGZ4VNXGPQ=%E9%87%8D%E8%A6%81-1 h_01HB5W700QYJ9NR5F4VT59NG2Q=%E4%BE%8B-1 targeting-behavior=%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A8%E8%A1%A8%E7%A4%BA%E5%8B%95%E4%BD%9C h_01HB5W700QYC48YTJY9B8JT0XM=%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A8%E8%A1%A8%E7%A4%BA%E5%8B%95%E4%BD%9C h_01HB5W700QG54YYQFHGA2J41RY=3-banner-setup h_01HB5W700QD0WKNAP5X6T9E6DQ=%E4%BE%8B-2 h_01HB5W700QX5J59BBK1AV7VFV6=4-testing view-banner-performance=%E3%83%90%E3%83%8A%E3%83%BC%E3%81%AE%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%81%AE%E7%A2%BA%E8%AA%8D h_01HB5W700Q6WHMVFNSVM2E9JXN=%E3%83%90%E3%83%8A%E3%83%BC%E3%81%AE%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%81%AE%E7%A2%BA%E8%AA%8D h_01HB5W700QEP46WV78KEYD1RT1=performance-page h_01HB5W700QZ705H5EE0PFHB1KY=performance-cards additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HB5W700Q9XD8MGEK0B3ZZJS3=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HB5W700QHW078W3RRCB81AWM=banner-group-display-logic h_01HB5W700QNYT482FR0FRHP2DC=ab-testing-banner-performance faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HB5W700Q90F1KMASF94EZWEM=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HB5W700Q1ZP3RAR94T41SXK2=why-does-my-banner-not-display h_01HB5W700QKBVFQHH9D8WD36R2=can-i-use-my-own-font-for-my-banner h_01HB5W700R2AJC2C1PRT5PTH8G=can-i-add-parameters-to-the-url-of-my-smart-banners h_01HB5W700RAVG10QZDBPXWT14G=do-smart-banners-support-deep-linking h_01HB5W700R12DSA6HF4HVWGW9P=can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed h_01HB5W700RT122T2M6NXFPSXDV=do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page h_01HB5W700RH40FGHWVJ9J31R9F=can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app h_01HB5W700R11SHAKV5W21MXCX8=do-smart-banners-support-web-accessibility h_01JSVH17EH97S8B7EBCD4QHS1Q=if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed traits-and-limitations=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E7%89%B9%E6%80%A7%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HB5W700RXHC22QGXDX4GG1AR=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E7%89%B9%E6%80%A7%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
