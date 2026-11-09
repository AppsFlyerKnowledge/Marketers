---
title: お知らせ： Unity Adsコスト連携におけるアップデート
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2024-06-20T14:43:15Z'
  edited_at: '2026-10-14T09:29:37Z'
  id: 26078530790289
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/26078530790289
---
| **新着情報** | Unity Ads側のAPIアップデートにより、コストデータ連携の設定が変更となります。新しいAPIは既に利用可能で、2024年10月1日までに移行作業を完了する必要があります。Unity Adsのコストデータを継続取得するには、期日までにコスト連携設定をアップデートする必要があります。 |
| --- | --- |
| **発効日** | 2020年8月6日 |
| **知っておくべきこと** | <ul><li>Unityは、新しいコストAPI連携を導入します。</li><li>古いコストAPI連携は、2024年10月1日の終了日まで有効です。</li></ul> |
| **必須事項：** | 2024年10月1日以降も引き続きコストデータを取得するには、新しいUnityコストAPI連携の資格情報を更新する必要があります。<br /><br />必要な資格情報は次のとおりです：<ul><li>Organization Core ID</li><li>Service Account Secret Key</li><li>Service Account Key ID</li></ul>AppsFlyerでUnityコスト連携へ移行するには、次のセクションの手順に従ってください。作業は以下2つのステップに分かれます：<ol><li>Unity管理画面から[新しいUnity認証情報を取得](/docs/bulletin-unity-ads-cost-api-integration-update#get-unity-credentials)します。</li><li>[AppsFlyer管理画面の連携済みパートナーページで新しい資格情報を入力して、Unity コスト連携を設定します。](/docs/bulletin-unity-ads-cost-api-integration-update#set-up-unity-cost-api-integration-in-appsflyer)</li></ol> |

<div id="unity-cost-api-integration-procedures" />

## Unityのコスト連携設定手順

Unityの新しいコスト連携を設定するには、次の2つの手順が必要です：

1. Unity管理画面から新しいUnity認証情報を取得します。
2. AppsFlyer管理画面の連携済みパートナーページで新しい資格情報を入力して、Unity コスト連携を設定します。

手順については次のセクションで説明します。

<div id="get-unity-credentials" />

<Accordion title="Unityの認証情報を取得">

UnityコストAPI連携に必要な資格情報は次のとおりです：

* Organization Core ID
* Service Account Secret Key
* Service Account Key ID

**注：** Secret KeyとKey IDを取得するには、新しいUnityサービスアカウントを作成することをお勧めします。方法については以下で説明します。

**Unityサービスアカウントを設定し、UnityコストAPI連携に必要な資格情報を取得：**

1. Unity Cloudアカウントにログインします。
2. 左側のメニューから、**Grow (Unity Ads User Acquisition)**>**設定**に移動します。  
    <Image align="center" alt="" src="https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png" />
3. **Organization Core ID**を見つけてコピーし、保存します。  
   Organization Core IDの例（形式）：5773102414648
4. 左側のメニューから、**Grow (Unity Ads User Acquisition)**> **`{ }` API Management** に移動し、**Stats API v2.0**セクションで **Service Account**をクリックします。  
    <Image align="center" alt="" src="https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png" />
5. 新しいサービスアカウントを作成するには、**+ New** をクリックします。  
    <Image align="center" alt="" src="https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png" />
6. **Keys**セクションで、**+ Add Key** をクリックして、サービスアカウントのキーを作成します。  
    <Image align="center" alt="" src="https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png" />
7. **Key ID**と**Secret Key**を保存します。　**注：** シークレットキーにアクセスできるのはこのときだけなので、必ず保存してください。
   * サービスアカウントのシークレットキーの例： b0de73b1-b3ad-4175-bf9b-4913a0ff83ec
   * サービス アカウントのシークレットキーのキー ID の例： a0X\_cqHiXH4ABPS1Qr9TCy6EJdvG8ql5  
      <Image align="center" alt="" src="https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png" />
8. **組織の役割** セクションで、**+ 組織の役割の管理**をクリックします。  
    <Image align="center" alt="" src="https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png" />
9. **組織内の役割の編集**で、 **グロースをAdvertise Stats APIMMPViewer**に設定します。  
    <Image align="center" alt="" src="https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png" />

</Accordion>

<div id="set-up-unity-cost-api-integration-in-appsflyer" />

<Accordion title="AppsFlyerでUnityコスト連携設定を更新">

**AppsFlyerでUnityコスト連携設定更新するには**：

1. AppsFlyer管理画面左メニュー **連携** >**連携済みパートナー**をクリックし、**Unity**を選択します。
2. **連携設定**をクリックします。
3. 連携広告媒体の**コスト**タブを開きます。
4. **コストデータを取得**トグルをオンにします。（必須）
5. Unityの資格情報を入力します。
6. 画面右下の**コストを保存**をクリックしてください。
7. **接続テスト**をクリックします。  
   * APIが有効になりました。AppsFlyerはパートナーから1日6回（平均約4時間ごとに）データを収集します。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data">コスト連携設定の詳細はこちら</Anchor>

</Accordion>

<div data-zendesk-anchors="unity-cost-api-integration-procedures=unity%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A%E6%89%8B%E9%A0%86 h_01J11ZP5XG6VDSQKRWASAYK4QJ=unity%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A%E6%89%8B%E9%A0%86 h_01J14M3C6WNXPJJQHVWVNFB4GS=get-unity-credentials h_01J11ZHPJDZDZ7S24ZQK58B2FN=set-up-unity-cost-api-integration-in-appsflyer" />
