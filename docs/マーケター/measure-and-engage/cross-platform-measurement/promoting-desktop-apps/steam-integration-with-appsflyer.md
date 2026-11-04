---
title: AppsFlyerでのSteam連携・計測
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-12-08T10:02:09Z'
  edited_at: '2026-10-14T09:26:57Z'
  id: 11241130508433
  locale: ja
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ja/articles/11241130508433
---
> **概要： 概要： SteamゲームやアプリをAppsFlyerと連携し、Steamキャンペーンのアトリビューションやイベントデータを受け取ります。**

<div id="about-steam-attribution" />

## Steamのアトリビューション計測について

Steamは、WindowsおよびMacデバイス、Steamデッキ、およびその他のSteam OSデバイスで動作します。

PC上で稼働するアプリは、S2S APIまたはSDKを介してAppsFlyerと連携し、どのソースやキャンペーンがアプリ起動イベントやアプリ内イベントを促進したかに関するアトリビューションデータやパフォーマンス測定値を受け取ることができます。マーケターは、これらのインサイトを活用してマーケティング活動を測定および最適化できます。

<div id="example-attribution-flow" />

### アトリビューションフローの例

**注：**

![Steam_user_journey.jpg](https://files.readme.io/4979821043af1ed3e662b55c84df10a17a863e79084d050c478fa31767ed8eaa-51473918246929.jpg)

1. マーケティングタッチポイント
2. ゲームのランディングページゲームのランディングページは、ユーザーをSteamゲームページに誘導します。この手順は、UTM およびその他の URLパラメータを収集して、クリック / インストールしたユーザーを元のメディアソースまたはオウンドメディアソースに結び付けるために重要です。  
   たとえば、ランディングページにXbox、マイクロソフトストア、およびSteamページへのリンクを含めることができます。  
   ![awesome_game.png](https://files.readme.io/37cabff10a2e0a721b4d2901e7df47f53a7dedff25bdac80b97003b60eaef430-51473918248465.png)
3. <span id="marketing-touchpoint"></span>Steamアプリページこれは、ユーザーがダウンロードできるSteamアプリをホストするSteamストアフロントページです。
4. ゲームのインストールゲームのインストール： ユーザーがゲームをインストールし、アトリビューションをトリガーし、アプリ内イベントとセッションを記録します。

<div id="integration-procedures" />

## 連携手順

以下の表では、SteamアプリにAppsFlyerを実装するために必要なタスクを記載しています。

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
        * <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">SteamアプリのAppsFlyer管理画面への追加</Anchor>
      </td>
      <td>
        マーケティング担当者
      </td>
    </tr>
    <tr>
      <td>
        SDKとアプリの実装（S2SまたはSDK経由）
      </td>
      <td>
        連携には、次の2つの方法があります：S2SおよびSDK

        S2Sの場合：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">AppsFlyer API</Anchor>をアプリに実装し、以下のイベントをAppsFlyerにレポートするコマンドを使用します。

        * 初回起動
        * In-app events
        * セッション

        **注意**：

        * アプリの初回起動は、アプリ内イベントやセッションの前にレポートする必要があります。

        * APIを使用してイベントを送信する必要があります。開発担当者にどのイベントを送信したいかを伝えてください。APIを設定する際、AppsFlyerに送信するCTVイベントを設定しマッピングしていることを確認してください。
        * オウンドメディア接触を計測するには、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">インプレッションエンゲージメントAPI</Anchor>を実装してください。

        SDKメソッドには、ネイティブ <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/steam-vanilla">C++</Anchor>、 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-steam">Unreal</Anchor>、 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-steam">Unity</Anchor>の 3 つのバージョンがあります。

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

        **注意**：

        * **steam\_app\_id**:  

          一意のアプリIDを見つけるには、URLバーからアプリIDをコピーするか、https://steamdb.info/ に移動してゲームを検索します。　（例：）

          ```http
          https://store.steampowered.com/app/12345678/
          ```

          アプリID：12345678
        * **media\_source**

        次のパラメーターは必須ではありませんが、推奨です：

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**:例えば、`https://store.steampowered.com/app/12345678/`
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
        マーケター / データエンジニア
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
> * CTV、PC、コンソールプラットフォームのアトリビューションの概念

<div data-zendesk-anchors="about-steam-attribution=steam%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H7Z1DJRW1KPJQ4CZ6T85ASRK=steam%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 flow=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B 01H7Z1DJRWHB8TQC15WW4FVSHG=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B integration-procedures=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 01H7Z1DJRWX54DN2SNS21GPGXB=%E9%80%A3%E6%90%BA%E6%89%8B%E9%A0%86 removing-appsflyer-data-when-uninstalling-the-app=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01J3349MAA4J231B6FJ74V3PTB=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HDEHMH0HF201TH4XDW691STH=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HDP1K6FDDEED5P2WNESST7GE=%E5%8F%82%E7%85%A7" />
