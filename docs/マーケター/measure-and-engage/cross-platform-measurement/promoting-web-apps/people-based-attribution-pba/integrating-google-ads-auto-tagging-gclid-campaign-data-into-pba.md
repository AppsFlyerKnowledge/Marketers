---
title: Google Adsの自動タグ (GCLID) キャンペーンデータをPBAに連携する
metadata:
  keywords:
    - PBA
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-08-02T05:47:05Z'
  edited_at: '2026-10-14T09:38:41Z'
  id: 360011487937
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360011487937
---
> **概要：** 概要：Google Adsと接続し、GCLIDキャンペーン情報を自動タグ付けすることで、PBAデータを充実させましょう。

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png" />

<div id="integrating-google-ads-campaign-data-in-pba" />

## PBAにGoogle Adsキャンペーンデータを連携する

Google Adsアカウント（1つ以上）をブランドバンドルに接続してください。  Google Adsキャンぺーンデータは、管理画面の分析機能を向上させ、ローデータレポートをさらに強化できます。

* 注意
* この連携により、次のデータ項目が強化されます：（項目の利用可否は、PBAダッシュボードとローデータレポートによって異なります。）
  * キャンペーン名とキャンペーン ID
  * 広告セット名と広告セットID
  * 広告グループ名と広告グループ ID
* この連携で提供されるデータが優先され、UTM項目から抽出されたキャンペーン名データが上書きされます。キャンペーンとキャンペーンIDは、ローデータレポートで使用できます。
* 複数のGoogle Adsアカウントをお持ちの場合は、Webサイトにトラフィックをもたらすキャンペーンを実行しているアカウントを必ず接続してください。

**キャンペーン階層が入力されたWebsiteアトリビューションダッシュボード**

<Image align="center" alt="PBAWebSite.png" src="https://files.readme.io/46004298b827d3f4eaa4adae9fb2a8676867e6b5dde44a7ff087fe1bda07f054-4403138621713.png" />

キャンペーンと広告階層のデータは、次のようにダッシュボードとローデータで使用できます：

* ダッシュボード：
  * Websiteアトリビューション
  * Webアシストインストール
* **ローデータ：**
  * **Webからアプリ:** web\_googleads\_campaign\_id, web\_googleads\_campaign\_name

**Google Adsへの接続方法：**

2. **Google Ads 連携**タブへ移動してください。
3. **アカウント接続**をクリックしてください。  
   Google Adsのサインインページが開きます。
4. Google Adsアカウントでサインインしてください。AppsFlyerにアクセスを付与するプロセスを完了してください。

**Google Adsの接続を管理する**

Google Ads連携ページでは、次のアクションが可能です：

* 連携先の削除
* 接続を有効／無効にする

<div id="pbagoogle-ads-status-messages" />

### PBA—Google Adsステータスメッセージ

| ステータス | 意味 | 備考／必要なアクション |
| --- | --- | --- |
| アクティブ | 接続は完了しており、データを取得しています | N/A |
| Inactive (非アクティブ) | 接続は手動で無効にされました | 再度データを抽出するには接続を有効にしてください |
| Never synced (一度も同期されていない) | セットアップが完了しました | セットアップが完了しました。AppsFlyerが初めてGoogle Adsからデータを取得するまでに最大24時間かかる場合があります。このメッセージが24時間以上続く場合は、AppsFlyerサポートまでお問合せください。 |
| No data (データなし) | 接続は正常に完了しました | Google Adsは、クエリにデータを返しませんでした。全ての関連するGoogle AdsアカウントがPBAに接続されていることを確認してください。 |
| No response (応答なし) | Google Adsサーバーに連絡できません | 現在Google Adsサーバーに接続できません。このステータスが24時間以上続く場合は、AppsFlyerサポートへお問合せください。 |
| Invalid Credentials（認証情報が無効です） | 認証情報が無効のためAppsFlyerはデータを取得できません | 正しい認証情報がGoogle Ads連携ページに設定されていることを確認してください。最新の認証情報を使用して再度接続をお試しください。問題が解決しない場合は、AppsFlyerサポートに連絡してください。 |
| General error (一般的なエラー) |  | このステータスが24時間以上続く場合は、AppsFlyerサポートまでお問合せください。 |

<div data-zendesk-anchors="integrating-google-ads-campaign-data-in-pba=pba%E3%81%ABgoogle-ads%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B h_01HKW2V24JE5V959999TJDR2RX=pba%E3%81%ABgoogle-ads%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B pba%E2%80%94google-ads-status-messages=pbagoogle-ads%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8 h_01HKW2V24KM85CCC2F0CZHY359=pbagoogle-ads%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8" />
