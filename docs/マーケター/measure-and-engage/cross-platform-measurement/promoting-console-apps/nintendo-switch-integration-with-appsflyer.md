---
title: Nintendo SwitchとAppsFlyerの連携
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-05-02T10:50:43Z'
  edited_at: '2026-10-14T09:36:47Z'
  id: 14988397864593
  locale: ja
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/ja/articles/14988397864593
---
> **概要：** Nintendo SwitchゲームやアプリをAppsFlyerと連携して、Nintendo Switchキャンペーンのアトリビューションやイベントデータを受け取ります。

## Nintendo Switchのアトリビューションについて

PC上で稼働するアプリは、S2S APIまたはSDKを介してAppsFlyerと連携し、どのソースやキャンペーンがアプリ起動イベントやアプリ内イベントを促進したかに関するアトリビューションデータやパフォーマンス測定値を受け取ることができます。マーケターは、これらのインサイトを活用してマーケティング活動を測定および最適化できます。

### アトリビューションフローの例

以下は、広告のエンゲージメントからアトリビューションまでのユーザージャーニーにおける最も重要なステップを強調したフロー例です。AppsFlyerが推奨するクロスプラットフォームのランディングページも含まれています。 　**注意**：クロスプラットフォームのランディングページを使用することをお勧めしますが、ダイレクト計測リンクを使用することもできます。

![User_windows.jpg](https://files.readme.io/ce8489a16998ffbc4720fe2aae4496393db921cc582a331f59edb775a59b1331-small-22325350590097.jpg)

1. <span id="marketing-touchpoint"></span>マーケティングタッチポイント：ユーザーが、オンラインまたはオフラインのマーケティングのタッチポイントを通じてブランドと接触します。これらには、メールやニュースレター、ソーシャルメディア、モバイルウェブなどが含まれます。
2. ゲームのランディングページ：ゲームのランディングページは、ユーザーをアプリのダウンロードページに誘導します。この手順は、UTM およびその他の URLパラメータを収集して、クリック / インストールしたユーザーを元のメディアソースまたはオウンドメディアソースに結び付けるために重要です。  
   ランディングページは、ゲームがサポートするさまざまなプラットフォームへのリンクを提供するのに有益です。たとえば、ランディングページにXbox、マイクロソフトストア、およびSteamページへのリンクを含めることができます。
3. アプリのページ：これは、ユーザーがダウンロードするアプリをホストするNintendo Switch AppページのURLです。
4. ゲームのインストール：ユーザーがゲームをインストールし、アトリビューションをトリガー、アプリ内イベントとセッションを記録します。

## 連携手順

次の表に、Nintendo SwitchをAppsFlyerと連携するために必要なタスクを示します。

<Table>
  <thead>
    <tr>
      <th>
        タスク
      </th>
      <th>
        アクション
      </th>
      <th>
        作業担当者
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        アプリ設定
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">AppsFlyerアカウントを作成</Anchor>
        * <Anchor target="_blank" href="/marketers/ja/docs/user-management">適切な権限を持つアカウントユーザーの追加</Anchor>
        * <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">AppsFlyer管理画面にNintendo Switchアプリを追加</Anchor>
      </td>
      <td>
        マーケティング担当者
      </td>
    </tr>
    <tr>
      <td>
        アプリとAPIの連携（S2SまたはSDK経由）
      </td>
      <td>
        AppsFlyerへ以下のイベントをレポートするコマンドを使用して、AppsFlyer APIをアプリに実装してください。

        * 初回起動
        * アプリ内イベント
        * セッション

        **注意**：

        * アプリの初回起動は、アプリ内イベントやセッションの前にレポートする必要があります。
        * `device_ids` パラメーターは、`custom` タイプを選択してください。
          * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">初回起動</Anchor>時に生成される `custom` IDは、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">アプリ内イベント</Anchor>と<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">セッション</Anchor>計測時のIDと一致させる必要があります。
          * APIを使用してイベントを送信する必要があります。デベロッパーにどのイベントを送信したいかを伝えてください。 APIを設定する際、AppsFlyerに送信するイベントを設定しマッピングしていることを確認してください。

        オウンドメディアのエンゲージメントをレポートするには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">インプレッションエンゲージメントAPI</Anchor>を連携してください。
      </td>
      <td>
        アプリ開発者
      </td>
    </tr>
    <tr>
      <td>
        クロスプラットフォームのランディングページ設定
      </td>
      <td>
        **推奨：** AppsFlyerのスマートスクリプトを実行するクロスプラットフォームのランディングページでは、ウェブからアプリへのアトリビューションを実行できます。EpicやSteamのような、他のプラットフォームでも利用可能なアプリをキャンペーンで宣伝する場合に最もおすすめです。

        詳細：<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">クロスプラットフォームのランディングページについて</Anchor>

        <Anchor target="_blank" href="/marketers/ja/docs/cross-platform-landing-pages-with-smart-script">詳細：クロスプラットフォームのランディングページの設定方法</Anchor>

        **注意**：

        Nintendo Switchの場合、次のパラメータが必要です：

        * **platform**  
          switch
        * **nintendo\_app\_id**  
          アプリページのID。  

          一意のアプリIDを取得するには、URLバーからコピーするか、 <Anchor target="_blank" href="https://www.nintendo.com/store/products/octopath-traveler-ii-switch/">https://www.nintendo.com/store/products/</Anchor>で自身のゲームを検索して確認します。　例：

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```

          上記URLの**app-id**は一意のアプリIDです。
        * **media\_source**

        次のパラメーターは必須ではありませんが、推奨です：

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**  
          **nintendo\_app\_id** を含むアプリのNintendo Switchストアフロントの完全なURL。  
          例：

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```
      </td>
      <td>
        マーケター（開発者の支援が必要な場合があります）
      </td>
    </tr>
    <tr>
      <td>
        リンクの設定
      </td>
      <td>
        クロスプラットフォームのランディングページを使用しない場合は、ダイレクト計測リンクを作成し、広告からの遷移先URLとして入稿できます。

        詳細：<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">ダイレクト計測リンクの作成方法</Anchor>
      </td>
      <td>
        マーケティング担当者
      </td>
    </tr>
    <tr>
      <td>
        レポートの設定 / データの表示
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#データの可用性">詳細：管理画面とレポートでのデータの可用性</Anchor>
      </td>
      <td>
        マーケター / データエンジニア
      </td>
    </tr>
  </tbody>
</Table>

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| リターゲティング | 現在サポートされていません |
| コストデータ | コスト（広告費）データは、メールによるファイルアップロードを使用して、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">広告費用の取り込み</Anchor>で送信する必要があります。 |

</Accordion>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC、コンソールプラットフォームの概要</Anchor>

<div data-zendesk-anchors="about-nintendo-switch-attribution=nintendo-switch%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z1HPD0AB0VP6REMBF2HCR8=nintendo-switch%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 example-attribution-flow=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B h_01HP1QDGDAXV0Y7MVJYHW3H4SQ=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z1HPD0VAMPEHBPN8MAT3ST=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z1HPD0CS7CTX2KS2RVD3VA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%E5%8F%82%E7%85%A7" />
