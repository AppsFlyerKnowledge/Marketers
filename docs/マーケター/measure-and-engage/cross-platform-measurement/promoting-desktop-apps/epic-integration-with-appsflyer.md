---
title: Epic連携ガイド
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
  created_at: '2023-04-03T07:18:07Z'
  edited_at: '2026-10-14T09:29:48Z'
  id: 14241298075921
  locale: ja
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ja/articles/14241298075921
---
> **概要： 概要： EpicゲームをAppsFlyerと連携し、Epicキャンペーンのアトリビューションやイベントデータを受け取ります。Epic APIの実装は、Epicアプリのアトリビューションとイベント計測（つまり、ユーザーのEpicデバイスでのアトリビューションと記録）をサポートしています。**

<div id="about-epic-game-attribution" />

## Epicゲームのアトリビューションについて

マーケターは、これらのインサイトを活用してマーケティング活動を測定および最適化できます。

<div id="example-attribution-flow" />

### アトリビューションフローの例

**注意**：

<Image align="center" alt="Epic_journey.jpg" src="https://files.readme.io/c5807442cff142ceb4aa3c4d55628e75b37627a011ca531fa390e46ccc3e23b8-small-14241275857553.jpg" />

1. マーケティングタッチポイント
2. ゲームのランディングページゲームのランディングページは、ユーザーをEpicゲームページに誘導します。この手順は、UTM およびその他の URLパラメータを収集して、クリック / インストールしたユーザーを元のメディアソースまたはオウンドメディアソースに結び付けるために重要です。  
   たとえば、ランディングページにXbox、マイクロソフトストア、およびSteamページへのリンクを含めることができます。
3. Epicアプリページこれは、ユーザーがダウンロードできるEpicアプリをホストするEpicストアフロントページです。
4. ゲームのインストールゲームのインストール： ユーザーがゲームをインストールし、アトリビューションをトリガーし、アプリ内イベントとセッションを記録します。

<div id="integration-procedures" />

## 連携手順

次の表では、EpicゲームにAppsFlyerを実装するために必要なタスクを記載しています。

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
        * <Anchor target="_blank" href="/marketers/ja/docs/user-management">適切な権限を持つアカウントユーザーを追加します。</Anchor>
        * <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">AppsFlyer管理画面にEpicゲームを追加する</Anchor>
      </td>
      <td>
        マーケティング担当者
      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        連携には、次の2つの方法があります：S2S & クライアント側

        S2Sメソッドの場合：

        AppsFlyerへ以下のイベントをレポートするコマンドを使用して、AppsFlyer Epic APIをアプリに実装してください。

        * 初回起動
        * In-app events
        * セッション

        **注意**：

        * アプリの初回起動は、アプリ内イベントやセッションの前にレポートする必要があります。
        * APIを使用してイベントを送信する必要があります。 開発担当者にどのイベントを送信したいかを伝えてください。
        * オウンドメディア接触を計測するには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">インプレッションエンゲージメントAPI</Anchor>を実装してください。

        クライアント側のメソッドには、ネイティブ <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">C++</Anchor>、 <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unreal-epic-sample-app">Unreal</Anchor>、<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-epic-sample-app">Unity</Anchor> の 3つのバージョンがあります。

        **注：**
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
        **推奨：**  AppsFlyer Smart Scriptを実行するクロスプラットフォームのランディングページでは、ウェブからアプリへのアトリビューションを実行できます。EpicやSteamのような、他のプラットフォームでも利用可能なアプリをキャンペーンで宣伝する場合に最もおすすめです。

        <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">詳細：クロスプラットフォームのランディングページについて</Anchor>

        <Anchor target="_blank" href="/marketers/ja/docs/cross-platform-landing-pages-with-smart-script">詳細：クロスプラットフォームのランディングページの設定方法</Anchor>

        **注：**

        必須パラメーター：

        * **platform**  
          epic
        * **app\_id**  
          app\_idEpicストアのゲームページのアプリID  

          固有のゲームIDは、Epic開発者コンソールで確認できます。　（例：）

          ```http
          https://store.epicgames.com/en-us/p/YOUR-GAME-ID
          ```
        * **media\_source**

        次のパラメーターは必須ではありませんが、推奨です：

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**  

          例えば、`https://store.epicgames.com/en-us/p/12345678/`
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

        <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">詳細：ダイレクトアトリビューションリンクの作成方法</Anchor>
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

      </td>
    </tr>
  </tbody>
</Table>


<div id="traits-and-limitations" />

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

## 特性と制限

| 特性 | 備考 |
| --- | --- |
| リターゲティング | 現在サポートされていません |
| コストデータ | コスト（広告費）データは、メールによるアップロードファイルを使用して、<Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">広告費用の取り込み</Anchor>で送信する必要があります。 |

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC、コンソールプラットフォームの概要</Anchor>

<div data-zendesk-anchors="about-steam-attribution=epic%E3%82%B2%E3%83%BC%E3%83%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z1F3SE03BXJD0WAJV8RE7Q=epic%E3%82%B2%E3%83%BC%E3%83%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 flow=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B 01H7Z1F3SETVXQKRQ71YAJACY3=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B integration-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z1F3SF4J2WJ2Y6QG3VGGVK=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 removing-appsflyer-data-when-uninstalling-the-app=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01J3349MAA4J231B6FJ74V3PTB=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HF9WA5FJ6P4C357ZE231GMR0=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HE7T4JX3RX3SZW2VPW5ZZY7E=%E5%8F%82%E7%85%A7" />
