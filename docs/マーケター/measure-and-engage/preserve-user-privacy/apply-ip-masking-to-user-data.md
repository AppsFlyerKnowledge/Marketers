---
title: IPマスキング
metadata:
  keywords:
    - IP masking
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-05-23T12:59:55Z'
  edited_at: '2026-10-14T09:35:52Z'
  id: 208879066
  locale: ja
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ja/articles/208879066
---
> **概要：**

## IPマスキング

IPマスキングをオンにした場合：

* ユーザーのIPアドレスは、ローデータレポートには記載されず、パートナーへのポストバックを通じて提供されることもありません
* IPアドレスフィールドには、1.1.1.1という値が入力されます

> 📘 **注意**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/meta-ads-aggregate-event-measurement-aem-for-ios#aemのデータ共有">IPマスキングがオンになっている場合</Anchor>、AEMデータ共有はサーバー間イベントとSDKイベントの両方でサポートされません。つまり、データはMeta広告と共有されません。

> 📄 **例**
>
> * アプリのインストール表に示されるように、3人のユーザーが異なる日付にアプリをインストールします
>
> アプリインストール：
>
>
>
> | Install date | ユーザーID | IPアドレス |
> | --- | --- | --- |
> | 1月2日 | User\_A | 192.0.2.1 |
> | 1月7日 | User\_B | 192.0.2.33 |
> | 1月14日 | User\_C | 203.0.113.1 |
>
>
>
> IPマスキングとローデータ：
>
>
>
> | 日付 | IPマスキング設定状況： | ローデータレポート |
> | --- | --- | --- |
> | 1月1日 | オフ | User A 192.0.2.1 |
> | 1月2日 | オン | User\_A 192.0.2.1 |
> | 1月8日 | オン | User\_A 192.0.2.1  <br />User\_B 1.1.1.1 |
> | 1月9日 | オフ | User\_A 192.0.2.1  <br />User\_B 1.1.1.1 |
> | 1月15日 | オフ | User\_A 192.0.2.1  <br />User\_B 1.1.1.1  <br />User\_C 203.0.113.1 |


<span id="enabling-ip-masking"></span>IPマスキングはアプリごとに設定され、すべてのソースからのインストールに影響します。

**IPマスキングを有効にするには：**

1. **AppsFlyer管理画面左メニュー** **設定** > アプリ設定へ移動します。

## ローデータレポートでIP Maskingを有効にする

* 新規インストールとアプリ内イベントには、1.1.1.1.のIPアドレスが表示されます。
* 国や都市などの<Anchor target="_blank" href="/marketers/ja/docs/determine-user-location">地域関連のパラメーター</Anchor>は、引き続きローデータレポートに表示されます。

**ローデータレポートの例**

![ip_masking.png](https://files.readme.io/e52f8bd698191f0b1ac08e595e539f15bda59567ed51ddda32a0d80db3bdf23c-360001962938.png)

<div data-zendesk-anchors="ip-masking=ip%E3%83%9E%E3%82%B9%E3%82%AD%E3%83%B3%E3%82%B0 h_01HA91HHADCTT7QS2K79TJEY2C=ip%E3%83%9E%E3%82%B9%E3%82%AD%E3%83%B3%E3%82%B0 h_01HA92HF3ZYR2NBTXQ1S2AHCAA=%E6%B3%A8%E6%84%8F h_01HA91HHAD7BCXRZW6AD9NRDBN=%E4%BE%8B h_01HA91HHAEM220CE8805GFQYKR=enabling-ip-masking ip-masking-in-raw-data-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7ip-masking%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B h_01HA91HHAE14D6ES1ERNK93VY9=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7ip-masking%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B" />
